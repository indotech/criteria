# 1. Именование экшенов через camelCase

**Зачем**: для единообразия кода.

Хорошо
```
dispatch(currentUserAction.setUser(profile));

dispatch(currentUserAction.checkPassword(password));
```

Плохо
```
dispatch(currentUserAction.set_user(profile));

dispatch(currentUserAction.check_password(password));
```

# 2. Пишем dispatch вместо this.props.dispatch

**Зачем**: если у нас есть другие пропсы, мы все равно их получаем с помощью деструктуризации. Можно деструктурировать и диспатч. Тогда в момент вызова код будет занимать меньше места.

Хорошо
```
const { dispatch, profile } = this.props;
dispatch(currentUserAction.setUser(profile));

const { dispatch, password } = this.props;
dispatch(currentUserAction.checkPassword(password));
```

Не очень хорошо
```
this.props.dispatch(currentUserAction.setUser(this.props.profile));

this.props.dispatch(currentUserAction.checkPassword(this.props.password));
```

# 3. Данные, переданные в экшен, записываем в payload

**Зачем**: единообразие кода. Все данные будут передаваться в одном объекте, а не будут разрозненно находиться в экшене

Хорошо
```
check_token(platform, token) {
  return { 
    type: TYPES.CHECK_TOKEN,
    payload: {
      platform,
      token
    }
  }
},
```

Не очень хорошо
```
edit_user(userId, userName, userEmail, userRole, statisticAccess, chatAccess, faqAccess, mailingAccess, statesAccess, paymentsAccess, constructAccess) {
  return { 
    type: TYPES.EDIT_USER, 
    userId, 
    userName, 
    userEmail, 
    userRole, 
    statisticAccess, 
    chatAccess, 
    faqAccess, 
    mailingAccess, 
    statesAccess, 
    paymentsAccess, 
    constructAccess 
  }
}
```

# 4. Не вызывать более одного диспатча единовременно (создаем новый?)

**Зачем**: каждый диспатч - это новая перерисовка. Нужно по возможности уменьшать их количество.

# 5. если название экшена очень длинное, переносим на новую строку (обсуждаемо)

**Зачем**: чтобы легче было читать код.

Хорошо
```
dispatch(
  screenActions.change_all_screens_visibility(
    Object.keys(screens), 
    bot._id, 
    value
  )
)
```

Не очень хорошо
```
dispatch(screenActions.change_all_screens_visibility(Object.keys(screens), bot._id, value))
```