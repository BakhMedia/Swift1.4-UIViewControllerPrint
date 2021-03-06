# ViewControllers
### Урок 4.


В этом уроке рассмотрим обязательный пункт для всех **iOS-Swift** программистов, а именно назначение визуальному компоненту его реализацию в коде. Рассматривать мы это будем на примере наших новых трёх экранов с [предыдущего урока](https://github.com/BakhMedia/Swift1.3-TabBar). То есть у нас есть 4 экрана, у одного из них уже есть исполняемый код в файле **ViewController.swift**, мы там описывали работу «**Ночного режима**» и работу **if** и **else** во [втором уроке](https://github.com/BakhMedia/Swift1.2-IfElseSwitchStatusBar). Но на оставшихся трёх экранах нам же тоже понадобится писать код и описывать его работу. Давайте подготовим **Swift** файлы для каждого экрана и свяжем их с нашими визуальными экранами. Так же чтобы нам сразу что-нибудь работающее написать в каждом **Swift**-файле и удостоверится, что всё работает, мы расскажем вам про удобный инструмент разработчиков — Логи, каких их читать и зачем🧐.
Погнали!

1. Запускаем **Xcode** и откроем наш проект с предыдущего урока ([скачать можно здесь](https://github.com/BakhMedia/Swift1.3-TabBar)).

![Image1](https://raw.githubusercontent.com/BakhMedia/Swift1.4-UIViewControllerPrint/master/images/1.gif "Image1")

2. Создадим **Swift**-файл для нашей будущей ленты новостей. Жмём правой кнопкой на жёлтой папке в нашем проекте (она называется так же как и сам проект и в ней лежат все файлы нашего проекта). В появившемся меню выбираем «**New file…**». В появившемся диалоге выбираем «**Swift file**». Нас спрашивают как назвать файл и куда сохранить. Имя файла вводим **FeedViewController**. Расположение файла не меняем. **ВАЖНО**: удостоверимся что в нижней части диалога в поле **Targets** галочкой отмечен наш проект. Откроется только что созданный файл, напишем в нём следующий код:

```swift
import UIKit

class FeedViewController: UIViewController {

    override func viewDidLoad() {
        super.viewDidLoad()
    }

}
```

3. Точно так же создаем еще 2 файла с именами: **InfoViewController** и **ChatViewController**. Содержание файла пока отличаться будет только одной строкой. Вот их содержимое:

Для **InfoViewController**:
```swift
import UIKit

class InfoViewController: UIViewController {

    override func viewDidLoad() {
        super.viewDidLoad()
    }

}
```

Для **ChatViewController**:
```swift
import UIKit

class ChatViewController: UIViewController {

    override func viewDidLoad() {
        super.viewDidLoad()
    }

}
```

Давайте немного познакомимся с тем что мы здесь написали (**ВАЖНО!**: скорее всего написанное тяжело будет понять этот раз, не пугайтесь, ничего страшного в этом нет, так как в будущем мы будем много раз сталкиваться с этим и более подробно в примерах разбирать). 
- Первая строка **import UIKit** импортирует набор инструментов для UI — **User Interface**. Из этой библиотеки нам понадобится класс **UIViewController**, который мы используем в следующей строке.
- Вторая строка class InfoViewController: UIViewController { говорит о том что сейчас мы начнем описывать работу нашего InfoViewController после фигурной скобки. А после двоеточия мы сообщаем, что наш InfoViewController будет принадлежать к классу UIViewController, наследуя все его свойства и методы. Это как раз один из стандартных классов экранов в iOS.
- Третья строка уже внутри фигурных скобок класса InfoViewController — это override func viewDidLoad() {. Тут объявляется функция viewDidLoad с помощью ключевого слова func. Так же важно обратить внимание на слово override, оно обозначает что сама функция  viewDidLoad() есть в родительском классе, то есть в UIViewController и мы её как говорят программисты перегружаем. То есть переопределяем заменяя функцию viewDidLoad() на свою.
- Четвертая строка super.viewDidLoad(). super — означает обращение к родительскому классу, в нашем случае UIViewController. И вызываем из него функцию viewDidLoad(). Да-да! Ту самую функцию которую мы перегрузили, но так как мы не хотим переписывать, то что делает сам UIViewController, то просто вызовем её и всё 😎. У этого класса есть много необходимых функций, к примеру наша viewDidLoad() существует для описания действий, которые следует выполнить ПОСЛЕ того как экран будет загружен, о чем интуитивно нам говорит название функции: View Did Load 🧐. Вот еще несколько примеров функций, которые мы можем описывать для описываемого экрана (Вы заметите что их названия интуитивны понятны и многие из них мы с вами рассмотрим):
viewDidAppear — что сделать когда наш экран появился;
viewWillAppear — что сделать перед тем как как экран появится;
viewWillDisappear — что сделать перед тем как экран исчезнет;
viewDidDisappear — что сделать после того как экран исчез;
didReceiveMemoryWarning — что сделать если экрану не хватает памяти.
- Следующие две строки мы закрываем фигурные скобки. Первая скобка закрывает нашу описанную функцию viewDidLoad(). Вторая закрывает описание самого класса InfoViewController.

![Image2](https://raw.githubusercontent.com/BakhMedia/Swift1.4-UIViewControllerPrint/master/images/2.gif "Image2")

4. У нас созданы экраны, их визуальная часть. Созданы и файлы Swift (классы) для каждого из экранов. Осталось сообщить Xcode`y какой из экранов какой из файлов исполняет, грубо говоря связать экраны с кодом. Выбираем экран с нашей будущей «Лентой», нажимая на его заголовок. Затем справа выбираем «Show the Identity Inspector» и ищем поле Class. Вписываем туда FeedViewController. Если обратим внимание, то во время того как мы будем вводить символы в это поле Xcode будет нам подсказывать доступные значения для этого поля. Просто когда увидим нужное значение в нашем поле, то просто нажмём Enter. Готово, теперь экран «Лента» связан с нашим FeedViewController.


5. Проделаем тоже самое для всех остальных экранов:
- Экран «Информация» — назначаем InfoViewController;
- Экран «Чат» — назначаем ChatViewController;
Экран «Настройки», если посмотрим, то уже назначен на «ViewController», созданный Xcode по умолчанию в самом [ПЕРВОМ УРОКЕ(ссылка)]. В этом моменте мы чуть-чуть понимаем создаваемый Xcode`ом код и файлы, а именно что создан начальный экран и автоматом к нему привязан файл-Swift, хотя мы не принимали в этом участия — зачем нам писать лишний код, если Apple это уже сделали за нас🤨.


6. Давайте теперь напишем что-нибудь в коде, чтобы проверить, что написанное нами работает. Самый простой способ — это **Логи**. В языке **Swift** для этого используется команда **print**. В каждой функции **viewDidLoad()** напишем следующую строку:

```swift
print("this view is loaded")
```

По логике: когда наш экран будет **DidLoad** (то есть будет загружен) в **Логи** будет добавлена строка «**this view is loaded**». По сути Логи это то, что записывается во время исполнения любой программы, будь то на телефоне или на сервере или даже Вашем домашнем компьютере. Где же её увидеть?


![Image3](https://raw.githubusercontent.com/BakhMedia/Swift1.4-UIViewControllerPrint/master/images/3.gif "Image3")


7. В верхнем правом углу Xcode найдём кнопку «Hide or show Debug area», нажмём её. Снизу всплывёт пара пустых областей. Именно здесь будут выводиться наши логи, во время исполнения нашей программы, то есть приложения. Запустим наше приложение чтобы прочитать что сделает наша команда print (мы рекомендуем запускать пока всё на симуляторе для простоты проверки того что мы делаем, в будущем мы придем к запуску на реальном устройстве, но еще и как сделать так чтоб Ваше приложение оказалось в AppStore доступно всем для скачивания). Запуская приложение и нажимая по вкладкам мы будем видеть как появляется надпись «this view is loaded» в логах. Это как минимум означает что наш код print() выполняется.




8. Для наглядности работы логов давайте добавим еще пару строк скажем в **InfoViewController**:

```swift
override func viewDidAppear(_ animated: Bool) {
    print("Info экран был показан")
}
```

viewDidAppear() эта функция, которая выполняется каждый раз когда view появляется на экране. Теперь выглядит так:

![Image5](https://raw.githubusercontent.com/BakhMedia/Swift1.4-UIViewControllerPrint/master/images/5.png "Image5")

Вот что теперь мы можем наблюдать:

![Image6](https://raw.githubusercontent.com/BakhMedia/Swift1.4-UIViewControllerPrint/master/images/6.gif "Image6")

То есть при каждом появлении «**Информации**» у нас появляется наш сигнал. Таким образом мы проверили, что код исполняется, однако внешних признаков в самом приложении для пользователя этой проверки нет. Программистам часто нужно проверить выполнение кода или же вывести какие-то промежуточные результаты и при этом не меняя ничего внешнего. Именно эту задачу логи и выполняют.

9. Внешне в нашем приложении ничего не изменилось — это да. Но внутри мы сделали важный шаг: для каждого из наших экранов мы завели свой файл с кодом, в котором в будущем будем описывать его функционал. Пока сложно, ничего страшного мы еще вернёмся к этому много раз. Пока просто сделайте то, что мы описали.

**Сейчас попробуйте по памяти все повторить, желательно 2-3 раза.**

**Домашнее задание**: Попробуйте самостоятельно написать логи на появление каждого экрана и прочтите их.





