## Интеграция с Mindbox 
<br />

Интеграция подразумевает передачу информации о клиентах после совершения звонка, заявки из UIS в Mindbox в режиме реального времени. 
В дальнейшем эти контакты могут использоваться в Mindbox для рассылок, сегментации клиентов и тд. <br />


## Подключение интеграции <br />

1. На стороне Mindbox необходимо создать требуемую операцию. [Инструкция по созданию операции](https://help.mindbox.ru/docs/%D0%BE%D0%BF%D0%B5%D1%80%D0%B0%D1%86%D0%B8%D0%B8-v-%D0%BE%D1%81%D0%BD%D0%BE%D0%B2%D0%BD%D1%8B%D0%B5-%D1%81%D0%B2%D0%B5%D0%B4%D0%B5%D0%BD%D0%B8%D1%8F) <br />
Далее произведите настройки интеграции в UIS. <br />
2. Активируйте интеграцию. <br />
3. Нажмите "Сохранить". Требуется для подтягивания доп. настройек в тело уведомления.
4. Под каждую операцию добавьте требуемые уведомления и заполните настройки:
   - **Название операции** - укажите название операции. 
   - **URL** - укажите URL, сформированный в настройках операции в Mindbox.
     - Вместо {Идентификатор точки интеграции} укажите endpointId интеграции из Mindbox.
     - При использовании deviceUUID, дополните параметр &deviceUUID={UUID устройства})
   - **Тип коммуникации** - выберите тип коммуникации. Есть возможность настроить уведомления по звонкам, офлайн-заявкам и заявкам такси.
   - **Условия фильтрации** - при необходимости заполните условия фильтрации.
   - **Тело** - заполните тело уведомления в формате JSON. Тело также берется из настроек операции в Mindbox. 
Его необходимо отредактировать и вместо значений после ":" добавить нашу мнемонику, по аналогии со стандартными http уведомлениями.

<details>
  <summary style="font-weight:bold;"> Пример тела </summary> <br />
  
```python
  {
    "customer": {
      "fullName": {{visitor_name}},
      "mobilePhone": {{contact_phone_number}},
      "email": {{visitor_email}},
      "subscriptions": [
        {
          "brand": "NFdBH",
          "pointOfContact": "Email",
          "topic": "93534775"
        },
        {
          "brand": "NFdBH",
          "pointOfContact": "Email",
          "topic": "93534775"
        }
      ]
    }
  }
  ```


</details> 

5. Нажмите "Сохранить"
