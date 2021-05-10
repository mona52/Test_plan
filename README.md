# План автоматизации тестирования

**Объект тестирования:** Форма записи на обучение профессии «Тестировщик» в ЦОО Нетология-Групп (далее - `Форма записи`) на сайте netology.ru (далее - `Сайт`)

## Перечень автоматизируемых сценариев

**По итогам исследования поведения пользователей на Cайте, их путь к странице курсов "Тестировщик ПО" может быть следующим:**

1.	Переход с главной страницы Сайта в "Каталог курсов" / "Программирование" / "Тестировщик ПО", есть возможность установки фильтра (далее `Сценарий 1`)
2.	Переход с главной страницы Сайта в "Каталог курсов" / "Полный каталог" / "Тестировщик ПО", есть возможность поиска и установки фильтра (далее `Сценарий 2`)
3.	Переход с главной страницы Сайта из блока "Изучайте актуальные темы" / "Программирование" / "Тестировщик ПО", есть возможность установки фильтра (далее `Сценарий 3`)
4.	Переход с главной страницы Сайта из блока "Выберите вектор развития" / "Выбрать курс" / "Программирование" / "Тестировщик ПО", есть возможность поиска и установки фильтра (далее `Сценарий 4`)
5.	Переход через баннер с акциями / "Подробнее" / "Выбрать курс" / "Программирование" / "Тестировщик ПО", есть возможность поиска и установки фильтра (далее `Сценарий 5`)
6. Переход с главно страницы Сайта из блока  "Нео" / "Тестировщик ПО", есть возможность установки фильтра (далее `Сценарий 6`)

**Далее, после прохождения любого из Сценариев 1-6, возможны следующие переходы к Форме записи:**
1. нажатие кнопки "Записаться" в начале страницы в блоке с преимуществами
2. нажатие кнопки "Записаться" в блоке "Гарантия возврата денег"
3. заполнение формы записи внизу страницы в блоке "Запишитесь или получите консультацию"

**Форма записи может быть заполнена:**
- валидными данными
- невалидным именем
- невалидным номером телефона
- невалидным email

Далее происходит **Отправка формы**.

Для каждого из Сценариев 1-6 требуется 12 типовых тест-кейсов
Каждый из Сценариев должен быть пройден без регистрации и с регистрацией на сайте.
Итого, потребуется 144 тест-кейса. 
	
***Примечание:** тестирование фильтрации и поиска описано в Документе N*
		
## Перечень используемых инструментов с обоснованием выбора

| Инструмент  | Обоснование               |
|:------------|:--------------------------|
| JUnit5      | для создания и запуска тест-кейсов
| Lombok      | для автогенерации кода при написании тестов
| Selenide    | для воспроизводства действий пользователя при навигации и заполнении формы
| Faker       | для генерации тестовых данных пользователей
| REST API    | для проверки обмена данными с сервером
| DbUtils     | для упрощения кода при работе с СУБД
| Allure      | для автоматического получения отчетов о тестировании
 

## Перечень необходимых разрешений/данных/доступов

- доступ к SUT
- доступ к СУБД
- логин и пароль тестового пользователя
- признаки валидности / невалидности значений полей Формы записи

## Перечень и описание возможных рисков при автоматизации

1.	неверная оценка трудозатрат на тестирование может привести к увеличению сроков и удорожанию проекта;
2.  увольнение единственного QA инженера приведет к увеличению сроков и удорожанию проекта, так как потребуется ввод нового сотрудника, его обучение и вывод на «проектную мощность»;
3. недостаточная квалификация QA инженера может привести к затягиванию сроков и недостоверным результатам тестирования;
4.	недоступность тестируемого сервиса по техническим причинам может привести увеличение сроков  / невозможности тестирования;
5.	несогласованные изменения тестируемого сервиса может привести к увеличению сроков тестирования.


## Перечень необходимых специалистов для автоматизации
Один основной QA инженер + один резервный QA инженер

## Интервальная оценка с учётом рисков (в часах)
- трудозатраты на автоматизацию сценария 1 (12 тест-кейсов): 6-8 человеко-часов
- трудозатраты на автоматизация всех остальных сценариев 2-6 (132 тест-кейса): 3-5 человеко-часов
- **итого интеравльная оценка с учетом рисков: 9-13 часов**



