## Интеграция с Megaplan <br />  

Решение позволяет передавать в наш кабинет данные по сделкам, для дальнейшего построения Сквозной аналитики, а также интегрировать функционал телефонии и передавать данные по звонкам и текстовым коммуникациям в Megaplan. <br />  

## Функционал интеграции <br />  

<details>
 <summary style="font-weight:bold;"> Подробнее </summary> <br />

Данные передаваемые по звонкам:  <br />

- всплывающая карточка контакта при звонке сотруднику;
- прослушивание записанных разговоров прямо в личном кабинете Megaplan;
- сохранение всей истории коммуникаций с клиентом в его карточке;
- автоматическое соединение клиента с его персональным менеджером;
- исходящий звонок по клику или звонок из виджета;
- автоматическое создание контакта при любом звонке;
- создание задачи на потерянные входящие и неуспешные исходящие звонки;
- возможность создавать коммуникации по выбранным направлениям звонков;
- синхронизация с режимом “не беспокоить” веб-телефона Megaplan;
- переадресация на ответственного из CRM, при настройки соответственного сценария в ЛК <br />

Данные передаваемые по текстовым коммуникациям:  <br />

- возможность гибкой настройки создания контактов, дел, процессов по обращениям;
- передача текста заявок или переписки в контакт и процесс;
- встройка нашего виджета РМО в кабинет Megaplan при подключении соответствующего расширения. <br />


 Данные получаемые по сделкам:    <br />
- сделки: сумма сделки, валюту, товары/услуги и тд;  
- воронка продаж и ее этапы;  
- контакты;  
- ответственный менеджер.  <br />  

</details> 
<br />
<br />


## Подключение учетной записи <br />

<details>
 <summary style="font-weight:bold;"> Шаги по подключению </summary> <br />

Для авторизации в Megaplan необходимо в ЛК UIS: <br />  

- нажать "Авторизация в Megaplan";
- если ранеее добавляли учетные данные Megaplan, то выбрать их из списка, если нет, то нажать "Добавить учетные данные";
- заполнить значения:
  - название;
  - логин(username) и пароль(password) от Megaplan;
  - домен Megaplan в формате https://mp361546.megaplan.ru , часть 'mp361546' будет у каждого клиента уникальной.
    
После добавления учетных данных на странице появятся Параметры интеграции. 



</details> 

<br />
<br />
<br />
<br />
<br />
<br />
<br />

## Подключение телефонии   <br />

<details>
 <summary style="font-weight:bold;"> Шаги по подключению </summary> <br />


1. **Синхронизация данных**  <br /> 


<details>
 <summary style="font-weight:bold;"> 2.1. Синхронизация настройки телефонии </summary> <br />
   
- В **Megaplan** заполните настройку телефонии: <br /> 

a. Подключите приложение UIS 
  -  Под пользователем, который входит в группу «Директора» или «Админы», зайдите в личный кабинет Megaplan. 
  -  В аккаунте выберите раздел «Маркет приложений» - > «Магазин интеграций». 
  - Найдите приложение «UIS телефония и мессенджеры» в категории «Телефония» и установите его.
  - После установки необходимо авторизоваться в личном кабинете UIS под администратором.
  - Далее вас переадресует на маркетплейс UIS.  <br />

![image](megaplan.jpg) 
<br />

b. Подключите расширение 

  -  В Megaplan необходимо указать для каждого пользователя Megaplan внутренний номер виртуальной АТС UIS. 
     - Для этого откройте интерфейс Megaplan, перейдите в раздел “Настройки”, откройте вкладку “Интеграция”, в меню слева выберите пункт “Телефония”. 
     - Установите “Подключение к телефонии по API” и затем нажмите “Настройки телефонии”. 
     - Перейдите на вкладку на “Пользователи”.
     - Добавьте всех пользователей, использующих телефонию. Для каждого из них укажите внутренние номера АТС из раздела "Сотрудники".  <br />

     ![image](megaplan_telephony.gif) 

     **Важно:** если сотрудник не будет указан в данном разделе, то функционал поднятия карточки звонка и передача информации по нему не будет доступен.  <br /> 
     - Нажимаем сохранить.  <br />
 
- Нажмите кнопку "Синхронизировать настройки телефонии из Megaplan". <br />

 </details> 
<br />

<details>
 <summary style="font-weight:bold;"> 2.2. Синхронизация сотрудников </summary> <br />

**Синхронизировать сотрудников** - настройка позволяет импортировать выбранных сотрудников из Megaplan в UIS. Связь сотрудника в UIS с сотрудником из Megaplan происходит по e-mail. <br />
При прожатии будут выведены дополнительные настройки: <br />
- список сотрудников из Megaplan. Необходимо выбрать тех сотрудников, которых требуется создать в UIS. <br />
- кнопка"Синхронизировать", для принудительной синхронизации сотрудников. По умолчанию синхронизация происходит каждые 2 часа. 
<br />
</details> 
<br />
   
2. **Настройки фильтрации** <br />

2.1 **Фильтровать по виртуальным номерам** - выберите настройку, если требуется  фильтрация по виртуальным номерам (в случае подключения нескольких сетей/интеграций). <br />
При прожатии будет выведена дополнительная настройка с выбором виртуальных номеров. <br />

2.2 **Список виртуальных номеров** - укажите виртуальные номера, по которым необходимо отображать данные по звонкам в Megaplan в подключенной сети. <br />

3. **Ответственный по умолчанию** - данный сотрудник будет назначен ответственным на создаваемые  сущности, если выбрана соотвествующая настройка .<br />
  
4. **Обработка звонков**  <br />

4.1.  **Создавать контакт при звонке** - настройка позволяет создавать контакт в разделе "Клиенты" при начале разговора. <br />

При её выборе выводится дополнительная настройка выбора ответственного сотрудника. <br /> 
**Назначать ответственного на** - выберите кого назначать ответственным за успешный звонок от нового клиента (последний или первый разговаривавший). <br />

4.2. **Передавать дополнительные поля в клиента** - настройка позволяет передавать дополнительные поля в контакт. <br />
При её выборе выводятся дополнительные настройки соответствия полей в Megaplan и UIS. <br />
Добавьте все требуемые значения. Если требуется передавать значение в поля не только при первичных звонках(при создании контакта), но и при повторных, выберите настройку "Обновлять всегда". <br />
**Важно:** Обратите внимание, что передача информации возможна исключительно в дополнительных полях с типом "строка". Проверьте правильность используемых полей перед настройкой передачи данных.  <br />
 
4.3. **Создавать коммуникацию по звонку** - настройка позволяет создавать коммуникации в разделе "Клиенты" - "Коммуникации" с типом "Звонок" после завершения звонка. <br />
При её выборе выводятся дополнительные настройки передачи коммуникаций: <br />
  - **Создание коммуникации по направлению звонков** - добавьте необходимые направления звонков, по которым необходимо создавать коммуникацию в требуемом статусе. <br />
  - **Длительность коммуникации** - укажите время в минутах, которое необходимо добавлять к времени начала коммуникации, при формировании времени окончания. По умолчанию указано 120 минут (2 часа). <br />
   
4.4. **Создавать дело по звонку** - настройка позволяет создавать дело в разделе "Календарь" -> "Список дел" после завершения звонка. <br />
При её выборе выводятся дополнительные настройки cоздания дел по направлению звонка. <br />
Выберите необходимые направления звонков, их статусы, по которым необходимо создавать дела, а также ответственного за них.  <br />

4.5. **Создавать процесс по звонку** - - настройка позволяет создавать процесс в разделе “Процессы” после завершения звонка. <br />
При её выборе выводятся дополнительные настройки cоздания процесса по направлению звонка. <br />
Выберите необходимые направления звонков, их статусы, по которым необходимо создавать процессы, а также ответственного за них и схему из Megaplan.  <br />

4.6. Выберите настройку **Включить переадресацию на персонального менеджера**, если необходима переадресация на персонального менеджера из CRM.  <br /> 

**Важно:** переадресация на персонального менеджера из CRM будет работать при настроенном сценарии с соответствующей операцией в UIS , а также при соответствии внутренних номеров сотрудников в UIS и в разделе "Телефония" в Megaplan (подробнее в п.2.1).  <br /> 
   
5. **Звонки по клику из CRM** <br />

<br /> 

- **Номер для звонка по клику** - номер, который определяется у клиента при звонке от сотрудника, у которого нет зарегистрированной SIP-линии. <br /> 
- **Переопредeлять АОН для исходящих звонков** - выберите настройку, если требуется для всех исходящих звонков по клику отображать клиенту только выбранный номер в параметре "Номер для звонка по клику". <br />
  
6. Активируйте интеграцию. <br />

7. Нажмите сохранить <br />

<br />

Для проверки работы интеграции на тестовых звонках проверьте работы пунктов указаных в "Данные передаваемые по звонкам".
Если после всех настроек звонки в Megaplan не появляются, проверьте, совпадают ли внутренние номера сотрудников в разделе “Телефония” в Megaplan и нашем Личном кабинете.
   
 </details> 


<br />
<br />
<br />
<br />
<br />
<br />
<br />

## Подключение текстовых коммуникаций   <br />

<details>
 <summary style="font-weight:bold;"> Шаги по подключению </summary> <br />


1. **Передача заявок**  <br />

1.1. **Передавать заявки** -  выберите настройку, если требуется передавать данные по заявкам в Megaplan.<br />
При её выборе выводятся дополнительные настройки вариантов передачи заявок. <br />

1.2. **Условия фильтрации** - задайте условия, если требуется фильтровать заявки по сайтам и/или типам. <br />
1.3. **Ответственный по умолчанию** - данный сотрудник будет назначен ответственным на создаваемые  сущности, если выбрана соотвествующая настройка.<br />

1.4.  **Создавать контакт** -  настройка позволяет создавать контакт в разделе "Клиенты" по заявкам. <br />
При её выборе выводится дополнительная настройка дополнительных полей. <br /> 
- **Передавать дополнительные поля в клиента** - настройка позволяет передавать дополнительные поля в контакт. <br />
При её выборе выводятся дополнительные настройки соответствия полей в Megaplan и UIS. <br />
Добавьте все требуемые значения. Если требуется передавать значение в поля не только при первичных звонках(при создании контакта), но и при повторных, выберите настройку "Обновлять всегда". <br />
**Важно:** Обратите внимание, что передача информации возможна исключительно в дополнительных полях с типом "строка". Проверьте правильность используемых полей перед настройкой передачи данных.  <br />

1.5. **Создавать дело** - настройка позволяет создавать дело в разделе "Календарь" -> "Список дел" по заявке. <br />
При её выборе выводятся дополнительные настройки cоздания дел по типам заявок. <br />
Выберите необходимые типы заявок, по которым необходимо создавать дела, а также ответственного за них.  <br />

1.6. **Создавать процесс** - настройка позволяет создавать процесс в разделе “Процессы” по заявке. <br />
При её выборе выводятся дополнительные настройки cоздания процесса по типам заявок. <br />
Выберите необходимые типы заявок,  по которым необходимо создавать процессы, а также ответственного за них и схему из Megaplan.  <br />

2. **Передача чатов** <br />

2.1. **Передавать чаты** -  выберите настройку, если требуется передавать данные по чатам в Megaplan.<br />
При её выборе выводятся дополнительные настройки вариантов передачи чатов. <br />

2.2. **Условия фильтрации** - задайте условия, если требуется фильтровать заявки по сайтам, каналам и/или тегам <br />

2.3. **Ответственный по умолчанию** - данный сотрудник будет назначен ответственным на создаваемые  сущности, если выбрана соотвествующая настройка .<br />

2.4.  **Создавать контакт** -  настройка позволяет создавать контакт в разделе "Клиенты" по чатам. <br />
При её выборе выводятся дополнительные настройки: <br /> 

 - **Создавать клиента для чатов без контактных данных** -  настройка позволяет создавать контакт по чатам, в которых отсутствует номер телефона. При каждом новом чате с посетителем без контактных данных будет создаваться новый контакт, что может привести к дублям в Мегаплан.  <br />   

 - Выберите на **какое событие** создавать клиента: начало чата, завершение чата, простановка тега. <br />
 
 **Важно!** Текст переписки чата будет передан в журнал клиента только при завершении чата. <br />
  
 - **Передавать дополнительные поля в клиента** - настройка позволяет передавать дополнительные поля в контакт. <br />
 При её выборе выводятся дополнительные настройки соответствия полей в Megaplan и UIS. <br />
 Добавьте все требуемые значения. Если требуется передавать значение в поля не только при первичных звонках(при создании контакта), но и при повторных, выберите настройку "Обновлять всегда". <br />
 **Важно:** Обратите внимание, что передача информации возможна исключительно в дополнительных полях с типом "строка". Проверьте правильность используемых полей перед настройкой передачи данных.  <br />

2.5. **Создавать дело** - настройка позволяет создавать дело в разделе "Календарь" -> "Список дел" по заявке. <br />
При её выборе выводятся дополнительные настройки cоздания дел: <br />

- Выберите на **какое событие** создавать дело: начало чата, завершение чата, простановка тега. <br />
- Выберите кого указывать ответственным за дело. <br />

2.6. **Создавать процесс** - настройка позволяет создавать процесс в разделе “Процессы” по заявке. <br />
При её выборе выводятся дополнительные настройки cоздания процесса: <br />

- Выберите на **какое событие** создавать процесс: начало чата, завершение чата, простановка тега. <br />
- Выберите кого указывать ответственным за процесс. <br />
- Выберите схему из Megaplan , в которой требуется создавать процессы. <br />

3. Активируйте интеграцию. <br />

Для проверки работы интеграции на тестовых обращениях проверьте работы пунктов указаных в "Данные передаваемые по текстовым коммуникациям". <br />

 </details> 

<br />
<br />
<br />
<br />
<br />
<br />
<br />

 ## Подключение передачи сделок   <br />


<details>
 <summary style="font-weight:bold;"> Шаги по подключению </summary> <br />


1. Активируйте интеграцию. <br />  
2. Создайте приложение в Megaplan на Webhook url сервиса UIS из настроек.  <br />  

![image](megaplan_app.gif) 
<br />  

3.  Нажмите сохранить <br />  

После подключения интеграции сделки будут попадать в  Сырые данные -> Сделки.  <br />  
Для проверки корректности работы интеграции создайте тестовую сделку в Megaplan.

</details> 
