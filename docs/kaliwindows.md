# Встановлення Kali Linux паралельно та всередині Windows 10 без віртуальної машини

Підтримка та розвиток інформаційних ресурсів [ХНЕУ ім. С. Кузнеця](https://www.hneu.edu.ua/). Кафедра [кібербезпеки та інформаційних технологій](http://www.kafcbit.hneu.edu.ua/).

---

У даній статті буде розглянуто два способи установки самого популярного дистрибутива Linux для інформаційної безпеки - Kali Linux


## Підготовка до встановлення Kali Linux поруч з Windows 10

Kali Linux можна використовувати в якості додаткової системи, залишивши на ПК і Windows 10. Для цього потрібно встановити дистрибутив Kali разом з Windows.
Linux і Windows не можуть використовувати один і той же розділ. Тому для спільної установки буде потрібно виділити вільне місце для Kali Linux. Зробити це можна прямо з встановленої Windows 10.
Спочатку потрібно відкрити інструмент для управління Windows10 - наприклад, через правий клік по іконці комп'ютера на робочому столі.

![](img/img-6001.png)

*Рисунок 1 – Пошук інструмента управління дисками*

Перейдемо до меню управління дисковим простором у Windows 10

![](img/img-6002.png)

*Рисунок 2 – Меню управління дисками Win10*

Тепер потрібно вибрати «Стиснути том» для диска С: (на ньому стоїть Windows 10) з контекстного меню.

![](img/img-6003.png)

*Рисунок 3 – Том для стиснення*

Після пророблених нами дій відкриється вікно, в якому необхідно вказати розмір стискання. Для встановлення Linux дистрибутиву будє достатньо 20 або більше гігабайтів вільного місця, для комфортної роботи з системою ми обираємо 30 гігабайтів.

![](img/img-6004.png)

*Рисунок 4 – Стискаємо том*

Тепер ми маємо вільне місце для встановлення ОС, вільне місце в панелі управління відмічається чорним кольором та має характерний заголовок "Не розподілена".

![](img/img-6005.png)

*Рисунок 5 – Результат розподілення вільного місця під Kali Linux*

Тепер можна перезавантажуватися і запускати інсталятор Kali з флешки або з DVD.

## Встановлення на нерозподілене місце

Необхідно завантажитися з носія Kali Linux і вибрати пункт Graphical Install.

![](img/img-6006.png)

*Рисунок 6 – Меню встановлення*

Перейдемо до мовних налаштуваннь:

![](img/img-6007.png)

*Рисунок 7 – Мовні налаштування*

Та обираємо зручну для нас розкладку зміни мови клавіатури

![](img/img-6008.png)

*Рисунок 8 – Зміна розкладки*

Далі Linux налаштує мережу в автоматичному режимі :

![](img/img-6009.png)

*Рисунок 9 – Налаштування мережі*

Далі необхідно буде ввести пароль для суперкористувача Kali.

![](img/img-6010.png)

*Рисунок 10 – Встановлення паролю суперкористувача*

Наступний крок установки найважливіший: на етапі розмітки дисків потрібно вказати інсталятору, як встановити Linux.
Раніше нами було підготовлено незайнятого простору, потрібно вибрати пункт «Авто - використовувати найбільше вільне місце».

![](img/img-6011.png)

*Рисунок 11 – Розмітка дискового простору*

За замовчуванням пропонується всі дані Linux помістити в єдиному новому розділі. Можна погодитися або винести частину системи на окремі розділи.

![](img/img-6012.png)

*Рисунок 12 – Вибір шляху встановлення*

Інсталятор покаже покаже структуру (розділи Windows 10 відображаються з типом ntfs).

![](img/img-6013.png)

*Рисунок 13 – Існуючі розділи*

Необхідно підтвердити внесення змін.

![](img/img-6014.png)

*Рисунок 14 – Прийняття змін у дисковому просторі*

Після чого починається встановлення системи:

![](img/img-6015.png)

*Рисунок 15 – Процес встановлення*

Kali Linux запитає, чи використовувати дзеркало архіву. Якщо образ скачували давно, могли з'явитися поновлення для програм і варто підключити репозиторій Linux.

![](img/img-6016.png)

*Рисунок 16 – Процес встановлення*

Нарешті, необхідно встановити на диск завантажувач GRUB - саме він дозволяє коректно поставити Linux поруч з Windows 10 і вибирати, яку ОС запустити.

![](img/img-6017.png)

*Рисунок 17 – Встановлення системи завантаження GRUB*

Після цього з'явиться повідомлення про завершення установки Linux. Потрібно прибрати носій, з якого встановлені раніше Kali.

![](img/img-6018.png)

*Рисунок 18 – Успішне завершення встановлення*

---

# Встановлення Kali Linux всередені Windows 10.

## Підготовка стендової машини

Для прикладу встановлення буде використовуватися Virtualbox та образ Windows 10.
Налаштовуємо віртуальну машину під потреби операційної системи.

![](img/img-6019.png)

*Рисунок 19 – Налаштування віртуальної машини*

Перейдемо до встановлення Windows 10 на ВМ

![](img/img-6020.png)

*Рисунок 20 – Обираємо образ ОС*

Далі Windows 10 пропонує вибрати мову

![](img/img-6021.png)

*Рисунок 21 – Обираємо мову ОС*

Для встановлення операційної системи необхідно створити розділ, шляхом форматування вільного простору на диску.

![](img/img-6022.png)

*Рисунок 22 – Підготовка розділу до встановлення ОС*

Після зроблених нами дій розпочинається встановлення операційної системи на створений нами розділ.

![](img/img-6023.png)

*Рисунок 23 – Процес встановлення ОС*

Для продовження встановлення ОС будемо використовувати автономний обліковий запис, але пізніше потрібно мати обліковий запис Microsot.

![](img/img-6024.png)

*Рисунок 24 – Обліковий запис користувача Win10*

Установка відбувається за допомогою скачування системи Kali Linux з офіційного магазину Microsoft.

![](img/img-6025.png)

*Рисунок 25 – Сторінка Kali Linux в Microsoft Store*

Починаємо завантаження:

![](img/img-6026.png)

*Рисунок 26 – Процес завантаження підсистеми*

Після завантаження основного додатки, нам необхідно активувати підсистему Linux в Windows 10.
Активуємо чекбокс через установку додаткових компонентів панелі управління (Панель управління -> Програми та засоби -> Включення або відключення компонентів Windows 10 відзначивши галочкою пункт Підсистема Windows для Linux).

![](img/img-6027.png)

*Рисунок 27 – Підключення підтримки під системи Linux*

Система приймає наші зміни:

![](img/img-6028.png)

*Рисунок 28 – Windows прийняла налаштування, тепер необхідно перезавантажити ВМ*

Після завантаження системи, заходимо в ПУСК і пишемо Kali:

![](img/img-6029.png)

*Рисунок 29 – Додаток Kali Linux *

Запустивши, система попросить створити користувача і пароль до нього, створіть їх.
Один по одному виконайте наступні команди (потрібне підключення до Інтернету).
```
sudo apt update 
sudo apt dist-upgrade 
sudo apt install -y kali-win-kex 
```
![](img/img-6030.png)

*Рисунок 30 – Підключення до підсистеми Kali Linux *

В ході виконання останньої команди вам буде запропоновано вибрати клавіатуру. 
 По завершенні установки введіть команду kex для запуску Kali Linux з графічним інтерфейсом. При першому запуску вам буде запропоновано створити окремий пароль, можна від цього відмовитися.
В результаті запуститься Kali Linux з графічним інтерфейсом в повноекранному режимі. Для виходу з повноекранного режиму можете викликати меню клавішею F8 і відключити опцію «Full Screen».

![](img/img-6031.png)

*Рисунок 31 – Результат запуску підсистеми *

# Підсумки

За підсумком ми маємо інструкції, які дозволяють використовувати нам Kali Linux без видалення Windows 10, що буде дуже зручно, для тих, хто не любить використовувати віртуальні машини або не готовий повністю перейти на Linux систему.

Публікацію підготував: *Макаренко Антон*.

---

## Корисні посилання

1.	https://kali-linuks.ru/2018/06/15/ustanovka-kali-linuks-vmeste-s-windows-10/
2.	https://www.kali.org/
3.	https://docs.microsoft.com/en-us/windows/wsl/install-win10
