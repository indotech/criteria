# Основные
## Компоненты
### Один файл — один реакт-компонент
Каждый реакт-компонент должен находиться в своем файле

**Почему**: для облегчения поиска по файлам

### Расширение для файлов компонентов
Используем расширение .jsx

**Почему**: чтобы легче было отделять файлы компонентов от обычных js-файлов

## Пропсы
### Пропсы логического типа
Если значение пропса true, то не указываем его

**Правильно**
```js
<MyComponent isValid>
```

**Неправильно**
```js
<MyComponent isValid={ true }>
```
### Обязательный атрибут key при рендере списка элементов
При рендере списка элементов обязательно указываем уникальный для каждого элемента атрибут key

**Почему**: атрибут key помогает Реакту однозначно идентифицировать каждый элемент списка и помогает уменьшить количество ненужных удалений и добавлений элементов

**Правильно**
```js
return (
  <ul>
    {
      elements.map(
        (el) => (<li key={ el.id }>{ el.value }</li>)
      )
    }
  </ul>
)
```

**Неправильно**
```js
return (
  <ul>
    {
      elements.map(
        (el) => (<li>{ el.value }</li>)
      )
    }
  </ul>
)
```

### Уникальный id элемента в качестве key
В качестве атрибута key необходимо использовать уникальное значение, которое не изменится с течением времени (например id из БД). Нельзя использовать индекс массива в качестве key, так как при удалении элемента индексы могут сдвигаться, что приводит к неожиданным сайд-эффектам.

**Правильно**
```js
return (
  <ul>
    {
      elements.map(
        (el) => (<li key={ el.id }>{ el.value }</li>)
      )
    }
  </ul>
)
```

**Неправильно**
```js
return (
  <ul>
    {
      elements.map(
        (el, index) => (<li key={ index }>{ el.value }</li>)
      )
    }
  </ul>
)
```

## Именование
### Именование компонентов
Используем PascalCase для именования компонентов

**Почему**: чтобы визуально сразу можно было определить компоненты.

Правильно
```js
const MyAwesomeComponent = ({ one }) => return (<div>{ one }</div>)
```

Неправильно
```js
const myAwesomeComponent = ({ one }) => return (<div>{ one }</div>)
```

### Именование экземпляров компонентов
Используем camelCase для именования экземпляров компонентов

**Правильно**
```js
const myAwesomeComponent = <MyAwesomeComponent />
```

**Неправильно**
```js
const MyAwesomeComponent = <MyAwesomeComponent />
```

### Именование пропсов
Используем camelCase для именования пропсов

**Правильно**
```js
<MyAwesomeComponent 
  firstProp={ id }
  secondProp={ name }
  thirdProp={ value }
/>
```

**Неправильно**
```js
<MyAwesomeComponent 
  firstprop={ id }
  second-prop={ name }
  third_prop={ value }
/>
```

## Оформление
### Выравнивание пропсов
Если атрибутов больше одного, переносим каждый на следующую строку, отделяем двумя пробелами.

**Почему**: чтобы было легче читать и искать нужные пропсы. Такая запись напоминает привычный объект. Редактор в большинстве случаев при переносе строки автоматически ставит нужный отступ, поэтому не нужно заморачиваться с выравниванием

**Правильно**
```js
<MyAwesomeComponent 
  firstProp={ id }
  secondProp={ name }
  thirdProp={ value }
/>
```

**Неправильно**
```js
//такой код тяжело читать
<MyAwesomeComponent firstProp={ id } secondProp={ name } thirdProp={ value }/>

//тяжело читать
<MyAwesomeComponent 
firstProp={ id }
secondProp={ name }
thirdProp={ value }
/>

//много времени тратится на выравнивание
<MyAwesomeComponent firstProp={ id }
                    secondProp={ name }
                    thirdProp={ value }
/>
```

### Выравнивание вложенного компонента
**Правильно**
```js
<MyAwesomeComponent 
  firstProp={ id }
  secondProp={ name }
  thirdProp={ value }
>
  <ChildComponent 
    name={ name }
    value={ value }
  />
</MyAwesomeComponent>

{ showComponent && <MyAwesomeComponent /> }

/* не могу решить как лучше: в первом случае получается большая вложенность, а во втором — пробел, который совершенно не к месту. Так что обсуждаемо. */

{ 
  showComponent && (
    <MyAwesomeComponent 
      firstProp={ id }
      secondProp={ name }
      thirdProp={ value }
    />
  ) 
}

{ showComponent && (
    <MyAwesomeComponent 
      firstProp={ id }
      secondProp={ name }
      thirdProp={ value }
    />
) }
```

### Кавычки
Используем одинарные кавычки

**Правильно**
```js
<MyAwesomeComponent 
  className='Awesome__Class'
  name={ locale('Awesome__Name') }
  value={ value }
/>
```

**Неправильно**
```js
<MyAwesomeComponent 
  className="Awesome__Class"
  name={ locale("Awesome__Name") }
  value={ value }
/>
```

### Пробелы
- Отделяем закрывающую часть одиночного тега пробелом (если она не перенесена на другую строку)
- В пропсах отделяем фигурные скобки от значения пробелом
- В содержимом компонента тоже отделяем фигурные скобки от значения пробелом

**Правильно**
```js
<MyAwesomeComponent />

<MyAwesomeComponent 
  className='Awesome__Class'
  name={ locale('Awesome__Name') }
  value={ value }
>
  { showComponent && <ChildComponent /> }
</MyAwesomeComponent>
```

**Неправильно**
```js
<MyAwesomeComponent
/>

<MyAwesomeComponent      />

<MyAwesomeComponent/>

<MyAwesomeComponent 
  value={value}
/>
```
### Переносы
- Заключаем компонент в круглые скобки, если он занимает больше одной строки
- Если нет вложенных компонентов, всегда используем самозакрывающиеся тэги
- Если компонент занимает больше одной строки, закрывающую скобку переносим на новую строку
- Если атрибутов больше одного, переносим на следующую строку

**Правильно**
```js
return (
  <MyAwesomeComponent 
    awesomeProp={ hello }
    notAwesomeProp={ bye }
  />
)
```

**Неправильно**
```js
return <MyAwesomeComponent 
        awesomeProp={ hello }
        notAwesomeProp={ bye }
       ></MyAwesomeComponent>
```

## Методы и обработчики
### Методы и обработчики
В компонентах-классах вместо стрелочных функций в методах и обработчиках используем стандартные методы классов и привязываем их к контексту с помощью bind в конструкторе.

**Правильно**
```js
class MyAwesomeComponent extends React.Component {
  constructor(props) {
    super(props);
  
    this.state = {
      value: ''
    }

    this.onChangeFileInput = this.onChangeFileInput.bind(this);
    this.addFiles = this.addFiles.bind(this);
  }

  onChangeFileInput(e) {
    ...
  }

  addFiles(file) {
    ...
  }

  render() {
    return {
      ...
    }
  }
}
```

**Неправильно**
```js
class MyAwesomeComponent extends React.Component {
  constructor(props) {
    super(props);
  
    this.state = {
      value: ''
    }
  }

  onChangeFileInput = (e) => {
    ...
  }

  addFiles = (file) => {
    ...
  }

  render() {
    return {
      ...
    }
  }
}
```

## В методе render обязательно возвращаем значение

**Правильно**
```js
render() {
  return <MyAwesomeComponent { ...awesomeProps }>
}
```

**Неправильно**
```js
render() {
  (<MyAwesomeComponent { ...awesomeProps }>)
}
```

## Порядок свойств и аргументов
### Порядок свойств внутри компонента-класса
1. constructor
   1. state
   2. привязка обработчиков
2. getChildContext (получение значения контекста)
3. componentWillMount (лучше не использовать)
4. componentDidMount
5. componentWillReceiveProps (лучше не использовать)
6. shouldComponentUpdate
7. componentWillUpdate (лучше не использовать)
8. componentDidUpdate
9. componentWillUnmount
10. Обработчики событий
11. Прочие методы
12. render

### Порядок пропсов
1. Деструктурированные пропсы от родителя ({ ...this.props })
2. className - чтобы легче было идентифицировать компонент
3. нативные атрибуты тегов (name, value, checked, href, src)
4. пропсы
5. обработчики событий (onClick, onChange)

# Дополнительные
## Пропсы
### propTypes и defaultProps
Для всех компонентов прописываем propTypes, для необязательных свойств прописываем defaultProps. Пишем в новых компонентах, в старых — по возможности, переписывая в рамках текущих задач.

**Почему**: propTypes — своеобразная форма документации кода. Позволит избежать неожиданностей и передачи параметров не того типа, который нужен.

**Правильно**
```js
const MyAwesomeComponent = ({ one, two, three }) => {
  return (
    <div>
      { one }
      { two }
      { three }
    </div>
  );
};

MyAwesomeComponent.propTypes = {
  one: PropTypes.string.isRequired,
  two: PropTypes.string,
  three: PropTypes.number,
};
MyAwesomeComponent.defaultProps = {
  three: '',
  two: 0,
};
```

### Передаем только нужные пропсы
Перед передачей `{ ...this.props }` в компонент по возможности фильтруем неиспользуемые в компоненте пропсы.

**Почему**: чтобы не захламлять компонент ненужными значениями

**Правильно**
```js
const MyAwesomeComponent = (props) => {
  const { unused, unusedToo, ...rest } = props;
  return (<MyAwesomeChildComponent { ...rest }>);
}
```

**Неправильно**
```js
const MyAwesomeComponent = (props) => {
  return (<MyAwesomeChildComponent { ...props }>);
}
```

### Деструктуризация пропсов
По возможности используем деструктуризацию пропсов в функциональных компонентах.

**Почему**: сокращается количество кода. Мотивирует передавать меньшее количество пропсов.

**Правильно**
```js
const MyAwesomeComponent = ({ one, two }) => {
  return (
    <div>
      { one }
      <p>{ two }</p>
    </div>
  );
}

const MyAwesomeComponent = (props) => {
  const { one, two } = props;
  return (
    <div>
      { one }
      <p>{ two }</p>
    </div>
  );
}
```

**Хуже**
```js
const MyAwesomeComponent = (props) => {
  return (
    <div>
      { props.one }
      <p>{ props.two }</p>
    </div>
  );
}
```
