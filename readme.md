#### Glu Mobile. Тестовое задание (Unity) ####

Реализуйте игру камень-ножницы-бумага используя Unity (любой релизной версии не ниже 5.6)

Результатом тестового задания должен быть полный Unity проект в котором есть сцена Start, запуск которой в редакторе стартует игру.

Игра происходит по раундам, количество раундов не ограничено, конца игры не предусмотрено. 
Текущий счет по раундам (например 3 : 4) должен постоянно отображаться на экране.
Каждый раунд состоит из двух фаз
1) на экране три кнопки позволяющие игроку выбрать одну из трех фигур камень-ножницы-бумага. Нажатие на любую из трех кнопок фиксирует выбор фигуры игроком и переходит к фазе 2.
2) на экране последовательно отображаются
a. выбор фигуры оппонентом (AI)
b. результат раунда (победа-поражение)
c. изменение счета по раундам (например 3 : 4  -> 4 : 4)
d. по действию пользователя (например клик на специальную кнопку либо в любом месте экрана) начинается новый раунд

Игра должна уметь поддерживать два режима
"честный", когда выбор фигуры оппонентом никак не связан с выбором игрока
"нечестный", в этом случае оппонент должен побеждать в соответствии с заданной вероятностью P (число [0..1]) - т.е. при P=1 оппонент всегда побеждает, при P=0.5 - примерно в половине раундов и т.д.

Конфигурацию - выбор режима и вероятность выигрыша AI для "нечестного" режима - можно реализовать любым удобным способом. Возможностью динамически поменять конфигурацию в процессе игры можно пренебречь.

#### Краткое описание ####

Проект реализован как MVC структура. Контроллер представляет из себя FSM конфигурируемую кодом, ветвления не предусмотрены.

Фазы по заданию сложны и требуют уточнения. Пункты второй фазы в реализации представлены отдельными состояниями. Задание можно скорректировать, разбив раунд на пять фаз, выделив подпункты второй фазы в самомтоятельные. Последний подпункт можно опустить т.к. для рассчёта от пользователя достаточен один акт ввода за раунд. Кнопка сброса раунда так же подключена.
Переключение между режимами происходит кодом - заменой реализации генератора в контроллере.
В связи с простотой приложения корневой узел композиции не выделен (контроллер MVC можно считать таковым).