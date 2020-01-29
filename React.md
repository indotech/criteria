Основано на ~~реальных событиях~~ [стайл гайде от Airbnb](https://github.com/airbnb/javascript/tree/master/react)

- Оформление компонентов
  - [Один файл — один реакт-компонент](#%d0%9e%d0%b4%d0%b8%d0%bd-%d1%84%d0%b0%d0%b9%d0%bb--%d0%be%d0%b4%d0%b8%d0%bd-%d1%80%d0%b5%d0%b0%d0%ba%d1%82-%d0%ba%d0%be%d0%bc%d0%bf%d0%be%d0%bd%d0%b5%d0%bd%d1%82)
  - [Компоненты-классы и функциональные компоненты](#%d0%9a%d0%be%d0%bc%d0%bf%d0%be%d0%bd%d0%b5%d0%bd%d1%82%d1%8b-%d0%ba%d0%bb%d0%b0%d1%81%d1%81%d1%8b-%d0%b8-%d1%84%d1%83%d0%bd%d0%ba%d1%86%d0%b8%d0%be%d0%bd%d0%b0%d0%bb%d1%8c%d0%bd%d1%8b%d0%b5-%d0%ba%d0%be%d0%bc%d0%bf%d0%be%d0%bd%d0%b5%d0%bd%d1%82%d1%8b)
  - [Расширение для файлов компонентов](#%d0%a0%d0%b0%d1%81%d1%88%d0%b8%d1%80%d0%b5%d0%bd%d0%b8%d0%b5-%d0%b4%d0%bb%d1%8f-%d1%84%d0%b0%d0%b9%d0%bb%d0%be%d0%b2-%d0%ba%d0%be%d0%bc%d0%bf%d0%be%d0%bd%d0%b5%d0%bd%d1%82%d0%be%d0%b2)
- Пропсы
  - [Пропсы логического типа](#%d0%9f%d1%80%d0%be%d0%bf%d1%81%d1%8b-%d0%bb%d0%be%d0%b3%d0%b8%d1%87%d0%b5%d1%81%d0%ba%d0%be%d0%b3%d0%be-%d1%82%d0%b8%d0%bf%d0%b0)
  - [Обязательный атрибут key при рендере списка элементов](#%d0%9e%d0%b1%d1%8f%d0%b7%d0%b0%d1%82%d0%b5%d0%bb%d1%8c%d0%bd%d1%8b%d0%b9-%d0%b0%d1%82%d1%80%d0%b8%d0%b1%d1%83%d1%82-key-%d0%bf%d1%80%d0%b8-%d1%80%d0%b5%d0%bd%d0%b4%d0%b5%d1%80%d0%b5-%d1%81%d0%bf%d0%b8%d1%81%d0%ba%d0%b0-%d1%8d%d0%bb%d0%b5%d0%bc%d0%b5%d0%bd%d1%82%d0%be%d0%b2)
  - [Уникальный id элемента в качестве key](#%d0%a3%d0%bd%d0%b8%d0%ba%d0%b0%d0%bb%d1%8c%d0%bd%d1%8b%d0%b9-id-%d1%8d%d0%bb%d0%b5%d0%bc%d0%b5%d0%bd%d1%82%d0%b0-%d0%b2-%d0%ba%d0%b0%d1%87%d0%b5%d1%81%d1%82%d0%b2%d0%b5-key)
  - [propTypes и defaultProps](#proptypes-%d0%b8-defaultprops)
  - [Ненужные пропсы](#%d0%9d%d0%b5%d0%bd%d1%83%d0%b6%d0%bd%d1%8b%d0%b5-%d0%bf%d1%80%d0%be%d0%bf%d1%81%d1%8b)
  - [Деструктуризация пропсов](#%d0%94%d0%b5%d1%81%d1%82%d1%80%d1%83%d0%ba%d1%82%d1%83%d1%80%d0%b8%d0%b7%d0%b0%d1%86%d0%b8%d1%8f-%d0%bf%d1%80%d0%be%d0%bf%d1%81%d0%be%d0%b2)
- Именование
  - [Именование компонентов](#%d0%98%d0%bc%d0%b5%d0%bd%d0%be%d0%b2%d0%b0%d0%bd%d0%b8%d0%b5-%d0%ba%d0%be%d0%bc%d0%bf%d0%be%d0%bd%d0%b5%d0%bd%d1%82%d0%be%d0%b2)
  - [Именование экземпляров компонентов](#%d0%98%d0%bc%d0%b5%d0%bd%d0%be%d0%b2%d0%b0%d0%bd%d0%b8%d0%b5-%d1%8d%d0%ba%d0%b7%d0%b5%d0%bc%d0%bf%d0%bb%d1%8f%d1%80%d0%be%d0%b2-%d0%ba%d0%be%d0%bc%d0%bf%d0%be%d0%bd%d0%b5%d0%bd%d1%82%d0%be%d0%b2)
  - [Именование файла](#%d0%98%d0%bc%d0%b5%d0%bd%d0%be%d0%b2%d0%b0%d0%bd%d0%b8%d0%b5-%d1%84%d0%b0%d0%b9%d0%bb%d0%b0)
  - [Именование пропсов](#%d0%98%d0%bc%d0%b5%d0%bd%d0%be%d0%b2%d0%b0%d0%bd%d0%b8%d0%b5-%d0%bf%d1%80%d0%be%d0%bf%d1%81%d0%be%d0%b2)
- Оформление
  - [Выравнивание пропсов](#%d0%92%d1%8b%d1%80%d0%b0%d0%b2%d0%bd%d0%b8%d0%b2%d0%b0%d0%bd%d0%b8%d0%b5-%d0%bf%d1%80%d0%be%d0%bf%d1%81%d0%be%d0%b2)
  - [Выравнивание вложенного компонента](#%d0%92%d1%8b%d1%80%d0%b0%d0%b2%d0%bd%d0%b8%d0%b2%d0%b0%d0%bd%d0%b8%d0%b5-%d0%b2%d0%bb%d0%be%d0%b6%d0%b5%d0%bd%d0%bd%d0%be%d0%b3%d0%be-%d0%ba%d0%be%d0%bc%d0%bf%d0%be%d0%bd%d0%b5%d0%bd%d1%82%d0%b0)
  - [Кавычки](#%d0%9a%d0%b0%d0%b2%d1%8b%d1%87%d0%ba%d0%b8)
  - [Пробелы](#%d0%9f%d1%80%d0%be%d0%b1%d0%b5%d0%bb%d1%8b)
  - [Переносы](#%d0%9f%d0%b5%d1%80%d0%b5%d0%bd%d0%be%d1%81%d1%8b)
- Методы и обработчики
  - [Методы и обработчики](#%d0%9c%d0%b5%d1%82%d0%be%d0%b4%d1%8b-%d0%b8-%d0%be%d0%b1%d1%80%d0%b0%d0%b1%d0%be%d1%82%d1%87%d0%b8%d0%ba%d0%b8)
  - [В методе render обязательно возвращаем значение](#%d0%92-%d0%bc%d0%b5%d1%82%d0%be%d0%b4%d0%b5-render-%d0%be%d0%b1%d1%8f%d0%b7%d0%b0%d1%82%d0%b5%d0%bb%d1%8c%d0%bd%d0%be-%d0%b2%d0%be%d0%b7%d0%b2%d1%80%d0%b0%d1%89%d0%b0%d0%b5%d0%bc-%d0%b7%d0%bd%d0%b0%d1%87%d0%b5%d0%bd%d0%b8%d0%b5)
- Порядок свойств и аргументов
  - [Порядок свойств внутри компонента-класса](#%d0%9f%d0%be%d1%80%d1%8f%d0%b4%d0%be%d0%ba-%d1%81%d0%b2%d0%be%d0%b9%d1%81%d1%82%d0%b2-%d0%b2%d0%bd%d1%83%d1%82%d1%80%d0%b8-%d0%ba%d0%be%d0%bc%d0%bf%d0%be%d0%bd%d0%b5%d0%bd%d1%82%d0%b0-%d0%ba%d0%bb%d0%b0%d1%81%d1%81%d0%b0)
  - [Порядок пропсов](#%d0%9f%d0%be%d1%80%d1%8f%d0%b4%d0%be%d0%ba-%d0%bf%d1%80%d0%be%d0%bf%d1%81%d0%be%d0%b2)

# Компоненты
## Один файл — один реакт-компонент
Каждый реакт-компонент должен находиться в своем файле

**Зачем**: для облегчения поиска по файлам

## Компоненты-классы и функциональные компоненты
Если у компонента есть состояние — предпочитаем использовать компоненты-классы, если состояния нет — функциональные компоненты. Хуки пока не используем

**Зачем**: если у компонента нет состояния, не имеет смысла использовать компоненты-классы, функциональные компоненты более компактны. Если сохранять состояние только в родительских компонентах-контейнерах, а дочерние компоненты делать «глупыми» и передавать в них значения и обработчики через пропсы, будет легче контролировать ситуацию в приложении в целом.

## Расширение для файлов компонентов
Используем расширение .jsx

**Зачем**: чтобы легче было отделять файлы компонентов от обычных js-файлов

# Пропсы
## Пропсы логического типа
Если значение пропса true, то не указываем его

Хорошо
```
<MyComponent isValid>
```

Плохо
```
<MyComponent isValid={ true }>
```
## Обязательный атрибут key при рендере списка элементов
При рендере списка элементов обязательно указываем уникальный для каждого элемента атрибут key

**Зачем**: атрибут key помогает Реакту идентифицировать каждый элемент списка. При удалении/добавлении/редактировании какого-либо элемента реакт не перерисовывает весь список, а только новый изменяемый. Если не будет атрибута key, при изменении элемента отрендерится совершенно новый список и смысл в Реакте теряется.

Хорошо
```
return (
  <ul>
    {
      elements.map(
        el => (<li key={ el.id }>{ el.value }</li>)
      )
    }
  </ul>
)
```

Плохо
```
return (
  <ul>
    {
      elements.map(
        el => (<li>{ el.value }</li>)
      )
    }
  </ul>
)
```

## Уникальный id элемента в качестве key
В качестве атрибута key необходимо использовать уникальное значение, которое не изменится с течением времени (например id из БД). Нельзя использовать индекс массива в качестве key, так как при удалении элемента индексы могут сдвигаться и каждый раз список будет рендериться заново. Это негативно скажется на производительности.

Хорошо
```
return (
  <ul>
    {
      elements.map(
        el => (<li key={ el.id }>{ el.value }</li>)
      )
    }
  </ul>
)
```

Плохо
```
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

## propTypes и defaultProps
Для всех компонентов прописываем propTypes, для необязательных свойств прописываем defaultProps. Пишем в новых компонентах, в старых — по возможности, переписывая в рамках текущих задач.

**Зачем**: propTypes — своеобразная форма документации кода. Позволит избежать неожиданностей и передачи параметров не того типа, который нужен.

Хорошо
```
function MyAwesomeComponent({ one, two, three }) {
  return (
    <div>
      { one }
      { two }
      { three }
    </div>
  );
}
SFC.propTypes = {
  one: PropTypes.string.isRequired,
  two: PropTypes.string,
  three: PropTypes.number,
};
SFC.defaultProps = {
  three: '',
  two: 0,
};
```

## Ненужные пропсы
Перед передачей { ...this.props } в компонент по возможности фильтруем неиспользуемые в компоненте пропсы.

**Зачем**: чтобы не захламлять компонент ненужными значениями

Хорошо
```
const MyAwesomeComponent = (props) => {
  const { unused, unusedTo, ...rest } = props;
  return (<MyAwesomeChildComponent { ...rest }>);
}
```

## Деструктуризация пропсов
По возможности используем деструктуризацию пропсов в функциональных компонентах.

**Зачем**: сокращается количество кода. Мотивирует передавать меньшее количество пропсов.

Хорошо
```
const MyAwesomeComponent = ({ one, two }) => {
  return (
    <div>
      { one }
      <p>{ two }</p>
    </div>
  );
}
```

Не очень хорошо, но и не плохо
```
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

Хуже
```
const MyAwesomeComponent = (props) => {
  return (
    <div>
      { props.one }
      <p>{ props.two }</p>
    </div>
  );
}
```

# Именование
## Именование компонентов
Используем PascalCase для именования компонентов

**Зачем**: чтобы визуально сразу можно было определить компоненты

Хорошо
```
const MyAwesomeComponent = ({ one }) => return (<div>{ one }</div>)
```

Плохо
```
const myAwesomeComponent = ({ one }) => return (<div>{ one }</div>)
```

## Именование экземпляров компонентов
Используем camelCase для именования экземпляров компонентов

Хорошо
```
const myAwesomeComponent = <MyAwesomeComponent />
```

Плохо
```
const MyAwesomeComponent = <MyAwesomeComponent />
```

## Именование файла
Название файла компонента должно быть таким же, как и названию компонента (MyComponent.jsx). Корневой компонент папки должен называться index.jsx, а сама папка — так, как называется компонент.

Хорошо

```
import MyComponent from './MyComponent';
```

Плохо
```
import MyComponent from './MyComponent/MyComponent';
import MyComponent from './MyComponent/index';
```
## Именование пропсов
Используем camelCase для именования пропсов

Хорошо
```
<MyAwesomeComponent 
  firstProp={ id }
  secondProp={ name }
  thirdProp={ value }
/>
```
Плохо
```
<MyAwesomeComponent 
  firstprop={ id }
  second-prop={ name }
  third_prop={ value }
/>
```
1. Один пробел в одиночном тэге перед закрывающей частью(оформление)
2.  Пробел в фигурных скобках в пропсах(оформление)
# Оформление
## Выравнивание пропсов
Если атрибутов больше одного, переносим каждый на следующую строку, отделяем двумя пробелами.

**Зачем**: чтобы было легче читать и искать нужные пропсы. Такая запись напоминает привычный объект. Редактор в большинстве случаев при переносе строки автоматически ставит нужный отступ, поэтому не нужно заморачиваться с выравниванием

Хорошо
```
<MyAwesomeComponent 
  firstProp={ id }
  secondProp={ name }
  thirdProp={ value }
/>
```

Плохо
```
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

## Выравнивание вложенного компонента
Хорошо
```
<MyAwesomeComponent 
  firstProp={ id }
  secondProp={ name }
  thirdProp={ value }
/>
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

## Кавычки
Используем одинарные кавычки

Хорошо
```
<MyAwesomeComponent 
  className='Awesome__Class'
  name={ locale('Awesome__Name') }
  value={ value }
/>
```

Плохо
```
<MyAwesomeComponent 
  className="Awesome__Class"
  name={ locale("Awesome__Name") }
  value={ value }
/>
```

## Пробелы
- Отделяем закрывающую часть одиночного тега пробелом (если она не перенесена на другую строку)
- В пропсах отделяем фигурные скобки от значения пробелом
- В содержимом компонента тоже отделяем фигурные скобки от значения пробелом

Хорошо
```
<MyAwesomeComponent />

<MyAwesomeComponent 
  className='Awesome__Class'
  name={ locale('Awesome__Name') }
  value={ value }
>
  { showComponent && <ChildComponent /> }
</MyAwesomeComponent>
```

Плохо
```
<MyAwesomeComponent
/>

<MyAwesomeComponent      />

<MyAwesomeComponent/>

<MyAwesomeComponent 
  value={value}
/>
```
## Переносы
- Заключаем компонент в круглые скобки, если он занимает больше одной строки
- Если нет вложенных компонентов, всегда используем самозакрывающиеся тэги
- Если компонент занимает больше одной строки, закрывающую скобку переносим на новую строку
- Если атрибутов больше одного, переносим на следующую строку

Хорошо
```
return (
  <MyAwesomeComponent 
    awesomeProp={ hello }
    notAwesomeProp={ bye }
  />
)
```

Плохо
```
return <MyAwesomeComponent 
        awesomeProp={ hello }
        notAwesomeProp={ bye }
       ></MyAwesomeComponent>
```

# Методы и обработчики
## Методы и обработчики
Вместо стрелочных функций в методах и обработчиках используем стандартные методы классов и привязываем их к контексту с помощью bind в конструкторе

Хорошо
```
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

Плохо
```
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

Хорошо
```
render() {
  return <MyAwesomeComponent { ...awesomeProps }>
}
```

Плохо
```
render() {
  (<MyAwesomeComponent { ...awesomeProps }>)
}
```

# Порядок свойств и аргументов
## Порядок свойств внутри компонента-класса
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

## Порядок пропсов
1. Деструктурированные пропсы от родителя ({ ...this.props })
2. className - чтобы легче было идентифицировать компонент
3. нативные атрибуты тегов (name, value, checked, href, src)
4. пропсы
5. обработчики событий (onClick, onChange)