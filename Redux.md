# Основные
## Именование экшенов через camelCase

**Почему**: чтобы именование в коде было единообразным.

**Правильно**
```js
dispatch(currentUserAction.setUser(profile));

dispatch(currentUserAction.checkPassword(password));
```

**Неправильно**
```js
dispatch(currentUserAction.set_user(profile));

dispatch(currentUserAction.check_password(password));
```

## Данные, переданные в экшен, записываем в payload

**Почему**: единообразие кода. Все данные будут передаваться в одном объекте, а не будут разрозненно находиться в экшене. Отсутствие каких-то данных или передача их в другом порядке (теоретически) не приведет к ошибке.

**Правильно**
```js
// SomeComponent.jsx
const userInfo = {
  userId,
  userName,
  userEmail,
  userRole,
  statisticAccess
};
dispatch(usersActions.editUser(userInfo));

// user.js
editUser(data) {
  return {
    type: TYPES.EDIT_USER,
    payload: data
  }
};
```

**Неправильно**
```js
// SomeComponent.jsx
dispatch(
  usersActions.editUser(
    userId,
    userName,
    userEmail,
    userRole,
    statisticAccess
  ));

// user.js
editUser(userId, userName, userEmail, userRole, statisticAccess) {
  return {
    type: TYPES.EDIT_USER,
    userId,
    userName,
    userEmail,
    userRole,
    statisticAccess
  }
}
```

# Дополнительные
## Пишется dispatch вместо this.props.dispatch

**Почему**: если у нас есть другие пропсы, мы все равно их получаем с помощью деструктуризации. Можно деструктурировать и диспатч. Тогда в момент вызова код будет занимать меньше места.

**Правильно**
```js
const { dispatch, profile } = this.props;
dispatch(currentUserAction.setUser(profile));

const { dispatch, password } = this.props;
dispatch(currentUserAction.checkPassword(password));
```

**Неправильно**
```js
this.props.dispatch(currentUserAction.setUser(this.props.profile));

this.props.dispatch(currentUserAction.checkPassword(this.props.password));
```

## Не вызывать друг за другом несколько диспатчей

**Почему**: каждый диспатч дергает все экшены с переданным именем, что чревато лишними перерисовками. Если нужно произвести одновременно несколько действий в разных частях стора, лучше создать под это новый экшен в этих частях и вызывать только один диспатч с этим экшеном.

**Правильно**
```js
dispatch(doSmthAndSmthMore(data));
```

**Неправильно**
```js
dispatch(doSmth(data));
dispatch(doSmthMore());
```

## Если название экшена очень длинное, переносим на новую строку(?)

**Почему**: чтобы легче было читать код

**Правильно**
```js
dispatch(
  screenActions.changeAllScreensVisibility(
    screens, 
    id, 
    value
  )
);
```

**Неправильно**
```js
dispatch(screenActions.changeAllScreensVisibility(screens, id, value));
```
