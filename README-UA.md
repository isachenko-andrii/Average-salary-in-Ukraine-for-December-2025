
![Project-logo](https://github.com/isachenko-andrii/Average-salary-in-Ukraine-for-December-2025/blob/main/Project-logo.png)  
#### [EN](https://github.com/isachenko-andrii/Average-salary-in-Ukraine-for-December-2025/blob/main/README.md) | [UA](https://github.com/isachenko-andrii/Average-salary-in-Ukraine-for-December-2025/blob/main/README-UA.md) Цей матеріал також доступний англійською мовою.  
---  
<div align="center">  
    
## Середня зарплата в Україні за грудень 2025 року<br>(Візуалізація даних за допомогою Power BI)   
  
</div>

## Опис проекту  
  
Цей проект присвячений візуалізації та аналізу рівня середньої заробітної плати за регіонами України станом на грудень 2025 року. Головною метою є виявлення економічних диспропорцій між регіонами та представлення даних у зручному для користувача форматі за допомогою Power BI.  
  
## Інструменти  
  
* **Візуалізація:** Power BI Desktop  
* **Картографія:** Налаштована карта TopoJSON (для точного відображення регіональних меж)  
* **Джерела даних:** [Міністерство фінансів (index.minfin.com.ua)](https://index.minfin.com.ua/ua/labour/salary/average/)  
* **Формати даних:** JSON (геодані), Excel (статистика)  
  
## Основні можливості панелі інструментів  
  
1. **Інтерактивна карта України:** Кольорове відображення рівнів доходів для кожного регіону.  
  
2. **Порівняльний аналіз:** Можливість швидко визначити провідні регіони та регіони з найнижчими показниками.  
  
3. **Підказки:** При наведенні курсора на регіон відображається точна сума та відхилення від середнього показника.
   
## Як переглянути проєкт  
  
1. Завантажте файл `project.pbix` з цього репозиторію.  
  
2. Відкрийте його за допомогою [Power BI Desktop](https://powerbi.microsoft.com/desktop/).  
  
- додатково завантажте карту України (Ukraine-regions.json) та файл із даними про зарплати (szp.xlsx, для коректного завантаження даних розмістіть файл на робочому столі)  
  
3. Проєкт доступний за [посиланням](https://github.com/isachenko-andrii/Average-salary-in-Ukraine-for-December-2025/blob/main/project.pbix).  
  
## Ключові висновки  
  
* **Київ** залишається лідером за рівнем доходів, що зумовлено високою концентрацією компаній сфери послуг та ІТ.  
* Спостерігається позитивна тенденція у західних регіонах завдяки розвитку логістичних центрів.  
* Аномально висока середня зарплата в Луганській області у 2025 році (яка може бути навіть вищою за київську) є класичним статистичним винятком, спричиненим певними факторами.
  
## Структура репозиторію  
  
**Середня-зарплата-в-Україні-за-грудень-2025**/ — Дані проекту  
├── дані/ — Дані проекту  
├── зображення/ — Скріншоти проекту  
├── Ukraine-regions.json — Файл карти, що використовується для візуалізації  
├── Project.pbix — Основний файл звіту Power BI  
├── ЛІЦЕНЗІЯ — Ліцензія MIT  
├── project-logo.png — Обкладинка проекту  
└── README.md — Документація проекту   
    
## Візуалізація  
  
![Середня зарплата в Україні](https://github.com/isachenko-andrii/Average-salary-in-Ukraine-for-December-2025/blob/main/images/Average-Salary.png)  
 
## Приклад формули  
  
**Назва таблиці:** region_tbl  
**Назва стовпця з регіонами:** Регіон  
**Назва стовпця зі значеннями для кожного регіону:** Значення  
  
Щоб створити картку, що відображає середню зарплату, ми скористаємося такою формулою:  
  
**Формула DAX для кожного регіону виглядатиме так:**  
  
<code>Kyiv  lbl =   
VAR CurrentRegion = "Kyiv"   
VAR CurrentValue = FORMAT(CALCULATE(SUM(region_tbl[Value]), region_tbl[Region] = CurrentRegion), "#,##0")  
VAR RegionExists = COUNTROWS(FILTER(region_tbl, region_tbl[Region] = CurrentRegion)) > 0  
RETURN  
    IF(RegionExists, IF(ISBLANK(CurrentValue) || CurrentValue = "0", CurrentRegion & ": 0", CurrentValue & " ₴ " ), CurrentRegion & ": No Data")</code>  
    
## Контакти  
  
**Автор:** [Андрій Ісаченко](https://isachenko-andrii.github.io)  
**LinkedIn:** [Андрій Ісаченко](https://www.linkedin.com/in/isachenko-andrii/)  
**Електронна пошта:** andrii.isachenko@gmail.com  
 
## Подяки  
  
- Особлива подяка [Микіті Тимошенко](https://github.com/NickTimosh) за високоякісні [уроки](https://github.com/Youtube-NikitaTymoshenko/PowerBI-UkraineMap/blob/main/README.md) з аналітики даних українською мовою.  
- Дякую за курс [Аналітик даних/GoIT](https://goit.global/ua/courses/data-analytics/).  
  
---  
  
**Статус проєкту:** Завершено.  
  
**Ліцензія:** Ліцензія MIT.  
  
