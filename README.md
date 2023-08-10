## Стандартные компоненты

#### Space

| Props    | Default value | Description                                                              |
|----------|---------------|--------------------------------------------------------------------------|
| {number} | undefined     | Любое число в пикселях. Оно будет конвертировано в блок с такой высотой. |

`<Space 16 />`

#### Container

| Props           | Default value | Description                      |
|-----------------|---------------|----------------------------------|
| backgroundColor | #EBFAF2       | Цвет контейнера                  |
| borderRadius    | 5             | Закругление границ контейнера    |
| padding         | 16            | Внутренний отступ контейнера     |
| children        | undefined     | Внутреннее содержимое контейнера |

`<Container>Текст внутри конейнера</Container>`

`<Container backgroundColor="#ccc">Текст внутри серого конейнера</Container>`

#### Image

| Props  | Default value | Description                                 |
|--------|---------------|---------------------------------------------|
| src    | undefined     | Ссылка на картинку или гиф                  |
| alt    | undefined     | Текст в случае, если картинка не загрузится |
| height | 180           | Высота картинки                             |
| width  | 100%          | Ширина картинки                             |

```
<Image
src="https://images.pexels.com/photos/268533/pexels-photo-268533.jpeg?cs=srgb&dl=pexels-pixabay-268533.jpg&fm=jpg"
width="372"
height="196"
alt="test"
/>

<Image src="https://images.pexels.com/photos/268533/pexels-photo-268533.jpeg?cs=srgb&dl=pexels-pixabay-268533.jpg&fm=jpg" />
```

#### YoutubeIframeVideo

| Props    | Default value | Description                        |
|----------|---------------|------------------------------------|
| src      | undefined     | Ссылка на ютуб видео               |
| height   | 180           | Высота картинки                    |
| width    | 100%          | Ширина картинки                    |
| children | undefined     | Использовать компонент `<Image />` |

```
<YoutubeIframeVideo src="https://www.youtube.com/embed/nVQ-Q4maz1s">
<Image src="https://images.unsplash.com/photo-1481349518771-20055b2a7b24"/>
</YoutubeIframeVideo>
```

#### Title

| Props    | Default value | Description             |
|----------|---------------|-------------------------|
| children | undefined     | Стилизованный заголовок |

`<Title>Мой текст</Title>`

#### SubTitle

| Props    | Default value | Description                |
|----------|---------------|----------------------------|
| children | undefined     | Стилизованный подзаголовок |

`<SubTitle>Мой текст</SubTitle>`

#### Text

| Props    | Default value | Description         |
|----------|---------------|---------------------|
| children | undefined     | Стилизованный текст |

`<Text>Мой текст</Text>`

#### Link

| Props      | Default value | Description                                                        |
|------------|---------------|--------------------------------------------------------------------|
| to         | undefined     | Ссылка на файл                                                     |
| isFullPath | false         | Если true, то в ссылку to нужно вставлять полноценный путь на файл |
| children   | undefined     | Стилизованный текст                                                |

`<Link to="/calltracking/step1.txt">Текст ссылки</Link>`

```
<Link 
to="https://raw.githubusercontent.com/comagic/comagic-app-onboarding/main/ru/comagic/analytics/summary_analytics.txt"
isFullPath
>
Текст ссылки
</Link>
```

## Config

Все объекты должны лежать в массиве routes. Возможные поля в объекте:

#### id

| Тип      | Описание                  |
|----------|---------------------------|
| `string` | Уникальный идентификатор. |

#### pattern

| Тип      | Описание                  |
|----------|---------------------------|
| `string` | Паттерн для сравнения url |

Для реализации используется библиотека [path-to-regexp](https://github.com/pillarjs/path-to-regexp "path-to-regexp")

###### Примеры паттернов:

| Паттерн                                             | Пример значения                 | Описание                                                                               |
|-----------------------------------------------------|---------------------------------|----------------------------------------------------------------------------------------|
| `'/user/:id'`                                       | `'/user/123'`                   | Сопоставляет URL, где `:id` представляет любое значение                                |
| `'/route/:param?'`                                  | `'/route'`                      | Сопоставляет URL без значения `:param` или с его значением                             |
| `'/route/:param?'`                                  | `'/route/456'`                  | Сопоставляет URL с определенным значением `:param`                                     |
| `'/product/:name/details'`                          | `'/product/TV/details'`         | Сопоставляет URL, в котором `:name` представляет имя продукта                          |
| `'/file/:name.:ext'`                                | `'/file/test.jpg'`              | Сопоставляет URL, в котором `:name` - это имя файла, а `:ext` - это его расширение     |
| `'/animals/:type(birds\|fish)'`                     | `'/animals/birds'`              | Сопоставляет URL, где тип животного ограничивается значениями 'birds' или 'fish'       |
| `'/route/:param+'`                                  | `'/route/1/2/3'`                | Сопоставляет URL, где `:param` может представлять несколько значений                   |
| `'/assets/(.*)'`                                    | `'/assets/js/script.js'`        | Сопоставляет URL, где за 'assets/' следуют любые символы                               |
| `'/locations/:country/:city'`                       | `'/locations/australia/sydney'` | Сопоставляет URL, где `:country` и `:city` представляют страну и город                 |
| `'/book/:title(P\\w+)'`                             | `'/book/P123'`                  | Сопоставляет URL, где `:title` представляет заголовок книги, начинающейся с 'P'        |
| `'/user/:id/edit'`                                  | `'/user/159/edit'`              | Сопоставляет URL, который ведет к редактированию пользователя с определенным `:id`     |
| `'/post/:year(\\d{4})/:month(\\d{2})/:day(\\d{2})'` | `'/post/2022/12/31'`            | Сопоставляет URL, в котором `:year`, `:month` и `:day` представляют дату публикации    |
| `'/service/:action(view\|edit)'`                    | `'/service/edit'`               | Сопоставляет URL, где действие службы ограничивается значениями 'view' или 'edit'      |
| `'/route/:param*'`                                  | `'/route/one/two/three'`        | Сопоставляет URL, где `:param` может представлять несколько значений или отсутствовать |

#### conditions

`type ComparisonOperator = '=' | '>' | '<' | '!=' | 'include' | 'exclude' | 'isNull' | 'isNotNull';`

`type ComparisonValue = string | number | (string | number)[] | null;`

```
type Condition = { 
    parameter: string;
    operator: ComparisonOperator;
    value: ComparisonValue; 
};
```

```
type DataStructure = {
    and?: (Condition | DataStructure)[];
    or?: (Condition | DataStructure)[];
}
```

| Тип             | Описание                      |
|-----------------|-------------------------------|
| `DataStructure` | Условия для показа онбординга |

Для значения `parameter` доступны все поля, которые возвращаются в `getobj.account`

###### Пример использования

```
"conditions": {
    "parameter": "lang",
    "operator": "=",
    "value": "ru"
}
```

```
"conditions": {
    "and": [
      {
        "parameter": "app_id",
        "operator": "=",
        "value": 4735
      },
      {
        "parameter": "lang",
        "operator": "=",
        "value": "ru"
      },
      {
        "or": [
          {
            "parameter": "components",
            "operator": "include",
            "value": "operation"
          },
          {
            "parameter": "components",
            "operator": "include",
            "value": "asdqwe"
          }
        ]
      }
    ]
}
```

#### regExp

| Тип      | Описание                                   |
|----------|--------------------------------------------|
| `string` | Регулярное выражение для показа онбординга |

#### filePath

| Тип      | Описание                    |
|----------|-----------------------------|
| `string` | Относительный путь до файла |

## Управление с помощью консоли

- Открыть онбординг по id `rootStore.onboardingStore.showOnboardingById('123')`
    - 1ый параметр id онбодинга
- Открыть онбординг по пути `rootStore.onboardingStore.showOnboardingByPath('/path', false)`
    - 1ый параметр путь до онбординга
    - 2ой параметр опционален. Если true, то нужно указывать абсолютный путь
- Открыть Editor `rootStore.onboardingStore.setShowEditor(true)`
    - 1ый параметр true или false для открытия или закрытия
- Установить ветку, в которую будут идти запросы `rootStore.onboardingStore.setBranchName('branchName')`
    - 1ый параметр название ветки 


