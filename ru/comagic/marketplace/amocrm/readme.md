 ### amoCRM: передача заявок
**Ценность интеграции.**
Интеграция позволяет передавать заявки из мультивиджета amoCRM в наш кабинет для построения аналитики.

**Функционал интеграции.**
- Передача заявок из онлайн-чата  мультивиджета.
- Передача заявок из мессенджеров мультивиджета.


**Какие данные передаются:**
- контактные данные (имя,телефон,email)
- дата и время создания
- данные сессии (рекламную компанию, источник, UTM-метки и тд)
- в случае отсутствия сессии, дефолтную РК или источник


**Необходимые для подключения компоненты:**
- Загрузка заявок из внешней системы.

**Настройка интеграции**
1. Активировать интеграцию переключателем активности.
2. Из поля "Webhook url" забираем адрес для настройки Webhook в amoCRM на событие "Беседа изменена"
Настройка хука в amoCRM:

<img src="https://github.com/comagic/comagic-app-onboarding/blob/marketplace/ru/comagic/marketplace/amocrm/images/amo_hook.gif?raw=true" alt="" width="100%" height="180px"/>
![image](images/amo_hook.gif)

3. Для авторизации в amoCRM требуется:
- создать приложение в amoCRM
  - в ссылку для перенаправления указываем URL https://uc-http-requester-prod-api.comagic.ru/oauth2/callback
  - предоставляем полный доступ, указываем название и описание, затем сохраняем
  - находим приложение в установленных , открываем его и из вкладки "Ключи и доступы" берем требуемые нам значения

- заполнить поля данными из приложения в настройках интеграции
  - в Название указываем любое название
  - в Client ID и Client secret указываем соотвествующие параметры из приложения amoCRM
  - в "AmoCRM URL" и "Token URL" вместо YOURDOMAIN, указываем домен от вашего ЛК amoCRM

<img src="https://github.com/comagic/comagic-app-onboarding/blob/marketplace/ru/comagic/marketplace/amocrm/images/auth_amo.gif?raw=true" alt="" width="100%" height="180px"/>

4. Кастомное поле для сессии - в амоСРМ создайте кастомное поле, в которое будет передаваться сессия CoMagic и выберете его из списка в настройках интеграции.
5. Рекламная компания/источник - необходимо выбрать какую сущность использовать для обращений без сессии. По умолчанию выбрана Рекламная компания (маркер не прожат), при прожатии маркера выбирается Источник.
В зависимости от положения маркера выводится либо список РК из личного кабинета клиента, либо список источников и сайтов. Необходимо указать какую РК/источник и сайт используем в случае отсутствия сессии.
6. В разделе "Соответствие мессенджеров и источников" настраиваем в какую РК\Источник будут попадать чаты из мессенджеров.

<img src="https://github.com/comagic/comagic-app-onboarding/blob/marketplace/ru/comagic/marketplace/amocrm/images/pc_source.gif?raw=true" alt="" width="100%" height="180px"/>

7. Сохраняем настройки.
8. После сохранения настроек будет выведено новое поле  "Скрипт для вашего сайта".
Из него забираем скрипт и устанавливаем на каждой странице ниже основного кода вставки нашего сервиса


