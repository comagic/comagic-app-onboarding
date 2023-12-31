## Интеграция с Marquiz 
<br />

Интеграция с Marquiz позволяет передавать в наш сервис заявки с квиза для дальнейшего анализа эффективности рекламы. <br />

**Возможности интеграции**
1. Передача заявок с квизов (виджет на сайте).
2. Передача заявок с лендингов-квизов (отдельная страница квиза на домене mrqz.me/клиентском домене).
<br />

 **Какие данные передаются**
  
- контактные данные (имя,телефон,email);  
- дату и время создания;  
- вопросы/ответы квиза;
- данные сессии (рекламную кампанию, источник, UTM-метки и тд);  
- в случае отсутствия сессии, дефолтную РК или источник.
<br />  

## Подключение интеграции <br />

1. Нажмите **"Активен"** на этой странице.
2. **Название** — укажите название квиза/сайта, с которым подключаете интеграцию. (можете заводить под все квизы одну настройку, либо под каждый квиз подключить интеграцию отдельно) <br />
3. Настройте **Webhook** в Marquiz <br />
Скопируйте "Webhook url" из настройки интеграции, разместите в Марквиз и опубликуйте изменения, подробнее **[по ссылке](https://help.marquiz.ru/article/518)** .<br />  

4. Выберете формат загрузки текста заявки: <br />
  - **Загружать сообщения** —  по умолчанию, при такой настройке будут загружены вопросы и ответы по квизам, если не выбрана настройка **Загружать только ответы**. <br />
Если настройка **Загружать сообщения** не выбрана, текст заявки будет пустым. <br />
  - **Загружать только ответы** — при выборе настройки будут загружаться только ответы без вопросов. <br />  
5. **Тип трафика** — необходимо выбрать какую сущность использовать для обращений без сессии.<br />  
В зависимости от выбранного типа трафика выводится либо список источников и сайтов  из личного кабинета клиента, либо список рекламных кампаний. Необходимо указать какой источник и сайт/рекламную кампанию используем в случае отсутствия сессии. <br /> 

<details>
  <summary style="font-weight:bold;"> Расширенные настройки </summary> <br />

  При необходимости, выберите опции: <br />  
- **Игнорировать сессию** — при выборе все обращения будут загружаться принудительно в выбранную клиентом дефолтную РК или источник (в зависимости от выбранных выше значений).
- **Устанавливать теги** — при выборе появится список тегов из ЛК. Необходимо выбрать из данного списка какой тег будет проставляться на обращения с настроенного квиза.
- **Загружать UTM метки** — при выборе будут передаваться UTM метки которые определил сервис Marquiz в текст заявки.

</details> 

<br />

6. Нажмите сохранить.  <br />
7. Если у клиента лендинг с доменом mrqz.me (либо с доменом, незаведенным в нашем ЛК), то дополнительно необходимо:
 - Завести mrqz.me (или клиентский домен), как отдельный сайт в нашем ЛК. 
В качестве сайта заводится именно основной домен mrqz.me (или клиентский домен), если у клиента несколько лендингов с данным доменом, обращения с них будут падать в один сайт.
 - Настроить на него все необходимые рекламные кампании/источники в нашем ЛК.
 - В настройках Marquiz в разделе  "Интеграции"-"Свой код" вставить наш основной код вставки.

<br />

![image](marquiz_code.png)

<br />


После подключения интеграции квизы будут попадать в наши отчеты с типом **"Заявки" (Сырые данные -> Обращения и цели)**. <br />  
Для проверки корректности работы интеграции оставьте тестовое обращение в квизе Marquiz.

