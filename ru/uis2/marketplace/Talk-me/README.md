## Интеграция с Talk-me: передача чатов и заявок
<br />

Решение позволяет передавать в UIS чаты с онлайн виджета , а также заявки с офлайн формы, для дальнейшего построения Сквозной аналитики. <br />


 **Какие данные передаются**<br />
  
- контактные данные (имя,телефон,email);  
- дату и время создания;  
- текст чата;
- данные сессии (рекламную кампанию, источник, UTM-метки и тд);  
- в случае отсутствия сессии, дефолтную РК или источник.
<br />  


## Подключение интеграции <br />


1. Нажмите "Активен" на этой странице. <br />
2.  **Настройте Webhook в Talk-me**<br />

<details>
  <summary style="font-weight:bold;"> Подробнее </summary> <br />

  - **Webhook url для чатов** <br />
      - Зайдите в Talk-me в настройки сайта (по каждому сайту настройка производится отдельно). 
      - Найдите раздел События и выберете "Диалог завершен".
      - Добавьте обработчик, в нем добавьте действие "Webhook".
      - В URL хука укажите значение из поля "Webhook url для чатов ".
      - Сохраните обработчик и активируйте его. <br />

      ![image](talkme_chat.gif)

  - **Передавать offline заявки** — прожмите переключатель, если необходимо передавать offline заявки с формы offline вопроса. После прожатия появится отдельный URL для offline заявок <br />
  
  - **Webhook url для offline заявок** <br />
      - Зайдите в Talk-me в настройки сайта (по каждому сайту настройка производится отдельно) 
      - Найдите раздел События и выберете "Новый оффлайн вопрос"
      - Добавьте обработчик, в нем добавьте действие "Webhook"
      - В URL хука укажите значение из поля "Webhook url для offline заявок "
      - Сохраните обработчик и активируйте его    <br />  

      ![image](talkme_offline.gif)


</details> 
<br /> 

3. В разделе **Сотрудник**  выбираем сотрудника на которого будут назначаться полученные чаты.  
4. **Тип трафика** — необходимо выбрать какую сущность использовать для обращений без сессии. <br />  
В зависимости от выбранного **типа трафика** выводится либо список источников и сайтов  из личного кабинета клиента, либо список рекламных кампаний. Необходимо указать какой **источник и сайт/рекламную кампанию** используем в случае отсутствия сессии. <br /> 
5. В разделе **Соответствие мессенджеров и источников** настраиваем в какую РК/Источник будут попадать чаты из мессенджеров с неопределившейся сессией.  

<br />

6. Нажмите сохранить.<br />
7. После сохранения будет выведен скрипт, который необходимо установить на сайт в соответствие с описанием в настройках.<br />


После подключения интеграции заявки будут попадать в  Сырые данные -> Обращения и цели. <br />  
Для проверки корректности работы интеграции оставьте тестовое обращение в чате Talk-me.
