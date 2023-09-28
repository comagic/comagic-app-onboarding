### Открытые линии Битрикс24: передача чатов <br />

**Ценность**  <br /> 
Интеграция позволяет передавать чаты из онлайн-виджета и мессенджеров в наш кабинет для построения аналитики. <br />  

**Функционал интеграции**  
- Передача онлайн-чатов из виджета с сессией.  
- Передача чатов мессенджеров из виджета без сессии.  
- Передача чатов мессенджеров оставленных не через виджет без сессии. 
<br />

**Какие данные передаются**   
- контактные данные (имя,телефон,email);  
- дату и время создания;  
- данные сессии (рекламную кампанию, источник, UTM-метки и тд);  
- в случае отсутствия сессии (по мессенджерам), дефолтную РК или источник;  
- текст чата.  
<br />

**Необходимые для подключения компоненты:**  
- Загрузка чатов из внешней системы в нашем ЛК.
<br />

**Настройка интеграции**  
1. Нажмите "Активен" на этой странице.
2. Заполните настройки интеграции <br />

- **Настройте Webhook в Битрикс24**
  
<details>
  <summary style="font-weight:bold;"> Подробнее </summary> <br /> 
 
   - Настройте исходящий веб-хук на событие "Создание лида (ONCRMLEADADD)" или "Создание сделки  (ONCRMINVOICEADD) в зависимости от того, какая сущность создается по факту чата
   - В поле "URL вашего обработчика" необходимо указать адрес из поля "Webhook url" из настройки интеграции.

</details> 
<br />

- **Авторизация**
  
<details>
  <summary style="font-weight:bold;"> Подробнее </summary> <br /> 
 
   - Для авторизации, необходимо завести локальное приложение в Битрикс24 . Разработчикам → Другое → Локальное приложение
   - В приложении указать след URL  https://uc-http-requester-prod-api.comagic.ru/oauth2/callback 
   - В нем будут выданы ключ и id юзера, которые необходимо ввести в Авторизации в настройках интеграции. 
</details> 
<br />

- В разделе **Сотрудник** выберете сотрудника на которого будут назначаться полученные чаты.
- Через переключатель Рекламная кампания/Источник выберете сущность в которую будут передаваться наши чаты без сессии.
- В зависимости от положения переключателя "Рекламная кампания/источник" выводится либо список рекламных кампаний из личного кабинета клиента, либо список источников и сайтов.
Необходимо указать какую **Рекламную кампанию/источник и сайт** используем в случае отсутствия сессии.
- В разделе **Соответствие мессенджеров и источников** укажите в какую Рекламную кампанию/Источник будут попадать чаты из мессенджеров с неопределившейся сессией.
 <br /> 
3. Нажмите сохранить. <br />
4. После сохранения будет выведен скрипт, который необходимо установить на сайт в соответствие с описанием в настройках.<br />
 
После подключения интеграции заявки будут попадать в  Сырые данные -> Обращения и цели.  <br /> 
Для проверки корректности работы интеграции оставьте тестовое обращение в виджете открытых линий Битрикс24. <br />