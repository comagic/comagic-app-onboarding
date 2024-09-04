## Стандартные компоненты

#### Markdown
Все возможности с примерами тут https://www.markdownguide.org/basic-syntax/

#### br

Отступ в 8px

`<br>`

#### Alert

| Props           | Default value | Description                      |
|-----------------|---------------|----------------------------------|
| backgroundColor | #EBFAF2       | Цвет контейнера                  |
| borderRadius    | 5             | Закругление границ контейнера    |
| padding         | 16            | Внутренний отступ контейнера     |
| children        | undefined     | Внутреннее содержимое контейнера |

`<Alert>Текст внутри конейнера</Alert>`

`<Alert backgroundColor="#ccc">Текст внутри серого конейнера</Alert>`

#### IframeVideo

| Props           | Default value                                                                                         | Description                                                                                            |
|-----------------|-------------------------------------------------------------------------------------------------------|--------------------------------------------------------------------------------------------------------|
| src             | undefined                                                                                             | Ссылка на ютуб видео                                                                                   |
| height          | 180                                                                                                   | Высота картинки                                                                                        |
| width           | 100%                                                                                                  | Ширина картинки                                                                                        |
| allow           | 'accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture; web-share' | Specifies a [Permissions Policy](https://developer.mozilla.org/en-US/docs/Web/HTTP/Permissions_Policy) |
| autoplay        | 1                                                                                                     | Включить или выключить авто воспроизведение                                                            |
| allowFullScreen | true                                                                                                  | Разрешить раскрывать на полный экран                                                                   |
| children        | undefined                                                                                             | Использовать компонент `<img />`                                                                       |

```
<IframeVideo src="https://www.youtube.com/embed/nVQ-Q4maz1s">
<img src="https://images.unsplash.com/photo-1481349518771-20055b2a7b24" alt="" width="100%" height="180px"/>
</IframeVideo>
```

#### OnboardingLink

| Props        | Default value | Description                                                        |
|--------------|---------------|--------------------------------------------------------------------|
| to           | undefined     | Ссылка на файл                                                     |
| is_full_path | false         | Если true, то в ссылку to нужно вставлять полноценный путь на файл |
| children     | undefined     | Стилизованный текст                                                |

`<OnboardingLink to="/calltracking/step1.md">Текст ссылки</OnboardingLink>`

```
<OnboardingLink
to="https://raw.githubusercontent.com/comagic/comagic-app-onboarding/main/ru/comagic/analytics/summary_analytics.md"
isFullPath
>
Текст ссылки
</OnboardingLink>
```

#### button

| Props        | Default value | Description                                                        |
|--------------|---------------|--------------------------------------------------------------------|
| b_type       | fill          | fill \| outline \| ghost                                           |
| b_theme      | primary       | primary \| secondary \| error                                      |
| b_to         | undefined     | Ссылка на файл                                                     |
| b_href       | undefined     | Ссылка на внешнюю страницу                                         |
| is_full_path | undefined     | Если true, то в ссылку to нужно вставлять полноценный путь на файл |
| children     | undefined     | Текст                                                              |

`<OnboardingLink to="/calltracking/step1.md">Текст ссылки</OnboardingLink>`

```
<button b_to="/analytics/summary_analytics.md" b_type="outline" b_theme="secondary">
Текст ссылки
</button>
```

#### img

| Props     | Default value | Description                                |
|-----------|---------------|--------------------------------------------|
| no_margin | undefined     | Если true, то у картинки не будет отступов |
| src       | undefined     | Путь до картинки                           |
| width     | undefined     | Ширина                                     |
| height    | undefined     | Высота                                     |

`<img src="img.png" no_margin="true" />`


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
#### Обязателен для заполнения. Если хотите показывать онбординг по ID, то указываем пустой патерн
```
{
      "id": "Test_amo",
      "pattern": "",
      "filePath": "/marketplace/amocrm/readme.md"
}
```

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
    {
      "id": "Test_1",
      "pattern": "/call_tracking/rules/:id#step2_static_external_area",
      "filePath": "/call-tracking/rules/step2_static_external_area.md",
      "conditions": {
        "parameter": "user_id",
        "operator": "=",
        "value": 2870
      }
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

#### isDefaultOpen

| Тип       | Описание                        |
|-----------|---------------------------------|
| `boolean` | Всегда открывать при совпадении |

#### type

| Тип                  | Дефолтное значение | Описание                   |
|----------------------|--------------------|----------------------------|
| `modal`  \| `drawer` | `drawer`           | Вид отображения онбординга |

#### width

| Тип                  | Описание |
|----------------------|----------|
| `string` \| `number` | Ширина   |

## Управление с помощью консоли
*Внимание: Все работа в консоле производиться в режиме godmode*

- Открыть онбординг по id `rootStore.onboardingStore.showOnboardingById('123')`
    - 1ый параметр id онбодинга
- Открыть онбординг по пути `rootStore.onboardingStore.showOnboardingByPath('/path', false)`
    - 1ый параметр путь до онбординга
    - 2ой параметр опционален. Если true, то нужно указывать абсолютный путь
- Открыть Editor `rootStore.onboardingStore.setShowEditor(true)`
    - 1ый параметр true или false для открытия или закрытия
- Установить ветку, в которую будут идти запросы `rootStore.onboardingStore.setBranchName('branchName')`
    - 1ый параметр название ветки

## Обновление
- Изменения применяются после 5 минут

