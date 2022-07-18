
Язык/Language:
turtleScript
[english, scripting programming language]
(эта раскладка включает четыре клавиатуры:
   *turtleScript основан на раскладке qwerty;
   *программирование ключевых слов для управления потоком;
   *математические команды черепахового скрипта;
   *цифровая клавиатура с арифметическими/логическими операторами)
(this layout includes four keyboards:
  *turtleScript based on qwerty layout;
  *programming keywords for flow control;
  *mathematical commands of turtleScript;
  *numeric keyboard with arithmetical/logic operators)

Особенности (peculiarities):
эта раскладка сделана для ускорения разработки программ на образовательном скриптовом языке черепаха.
 она предназначена для планшетов (я использую один с 10,1-дюймовым экраном для редактирования
 текста/источника).
раскладка не содержит значков что делает её более удобной для старых устройств — вместо этого на
 специальных клавишах есть символы юникода (UTF-8).
 было бы лучше использовать её с не отвлекающей высококонтрастной кожей, хорошо различающей текстовые
 метки на клавишах (с ней я использую свою собственную flat-dark-violet.skin, она использует контрастные цвета,
 помогающие сосредоточить моё внимание).

 посетите https://apps.kde.org/kturtle/ чтобы получить эту среду программирования
  (вам понадобится образовательная IDE kTurtle из KDE, чтобы можно было использовать этот материал.
 IDE пока не доступна для Android но вы можете подключиться к настольной системе через VNC (linux) или
 RDP (ОС Windows) и легко отразить окно kTurtle)
 вы можете посетить https://docs.kde.org/stable5/en/kturtle/kturtle/index.html для документации по языку.

эта клавиатура основана на qwerty, но некоторые символические кнопки изменены: некоторые скобки
 используются чаще, поэтому они сделаны более доступными или этот знак '$' используется для обозначения
 переменных в скрипте или запятая ',' и арифметические операторы, такие как плюс '+', пишутся с пробелом
 в конце, например ', ' и '+ ', чтобы скрипт выглядел аккуратно визуально (последняя группа может быть введена
 без пробела при использовании кнопки «+clean» [при длительном нажатии]).
 две крайние правые кнопки в первом ряду вызывают специальные клавиатуры:
      [и они так же выглядят на этих вспомогательных клавиатурах]
 «0≠1» [длительное нажатие] для чисел/операторов и «снежинка» (2745, «Плотная трехлистная снежинка»)
 с [длительным нажатием] «Снежинкой Коха» (2721, «Звезда Давида») для ключевых слов в TurtleScript.
 на некоторых кнопках повторяются ключевые слова — такие пишутся с пробелом в конце или в качестве
 альтернативы при длительном нажатии они могут использоваться для замены других ключевых слов
 во время кодирования (вы знаете, хакеры делают это очень часто :D)
 [выберите слово для замены, затем нажмите и удерживайте требуемую клавишу, и ваша черепашка будет
 двигаться не «вперед», а «назад»].
 также я сделала несколько предварительно отформатированных специальных конструкций «если-иначе».

 вы также можете прочитать мои собственные исходные коды, написанные на этом языке программирования:
   https://github.com/irulanCorrino


****hotfix
была явная проблема с первой реализацией этой  раскладки, но из-за этой дыры в моем коде я поняла
что визуальная привлекательность моего макета очень зависит от конкретных библиотек, установленных на
каждом Android-устройстве.
я делала это, используя свой планшет Jelly Bean с 10,1-дюймовым экраном и общесистемным шрифтом
«choco cookie» ... но затем я установила его на свой смартфон Kit Kat [что делать не рекомендуется,
при условии, что экраны меньшего размера не подходит для тяжелого редактирования текста] — и некоторые
клавиши выглядели не так, как на моем планшете!
и шрифт (я думаю, какой-то «serif») не соответствовал размерам кнопок даже с меньшими значениями;
так что я изменила шрифт на «choco cookie» и все текстовые метки [кроме тех, что с неправильным кодом]
выглядят красиво!!!
но некоторые символы Юникода различаются между библиотеками разных устройств и даже между шрифтами
одного устройства!
Я не использую значки, но я и не стремилась добиться единообразия между устройствами, поэтому я
придерживаюсь Unicode.

теперь исправляю этот мой код.  исправлено!!!
проблема заключалась в том, что разные системы Android по-разному обрабатывают флаги «specKey» или
«smallLabel», поэтому следующий код
   <Key android:keyLabel="bS⇦" android:codes="-5" android:keyWidth="9.0%p" android:isRepeatable="true" />
   <Key android:keyLabel="⇨dl" android:codes="-5112" android:specKey="true" android:isRepeatable="true" />
сделал синюю кнопку «backspace» и красную кнопку «delete» на моем смартфоне с Kit Kat, но они обе были
красными пока я писала эту раскладку на своем планшете Jelly Bean (и они оба на Android 4) [я знала об этом
несоответствие в моем коде, но сначала я оставила его для целей тестирования, и когда я исправляла эти
несоответствия в других местах (эти флаги используются часто) я забыла проверить эти кнопки на двух
клавиатурах].
я сделала обе клавиши синими для Android Kit Kat и сделала то же самое для «отменить» и «повторить»
(они были красными) но ИДЕНТИЧНАЯ ЧАСТЬ кода делает красные клавиши отмены/повтора
на вспомогательной клавиатуре!

значения (для «choco cookie», установите «по умолчанию» в настройках приложения для получения
системного шрифта на клавиатуре!):
[я предполагаю, что «choco cookie» не имеет жирного шрифта или курсива]
планшет 10,1"
                      —основной шрифт 32;
                      —символьный шрифт 24;
                      —шрифт для меток 18;
смартфон 4,5"
                      —основной шрифт 30;
                      —символьный шрифт 15;
                      —шрифт для меток 12.
                      установка разумных значений здесь ОЧЕНЬ ВАЖНА для того, чтобы метки не конфликтовали друг
                      с другом или были незаслуженно уменьшенным.  Система Android рассчитывает окончательный
                      размер каждой метки, используя* эти три основных переменные:
                      0. размер кнопки;  1. размер шрифта по запросу пользователя;  2. длина метки в пикселях;
                      но если пользователь запрашивает основной или меточный шрифт большего размера, чем система
                      может обработать, то даже если на кнопке нет другой метки, то система сделает отображаемую
                      метку значительно меньше чем могло бы быть при вменяемом значении размера шрифта.
                       *[и есть такие константы, как «dpi» или «размер экрана»]

---***---
this layout is made for speeding up development of programs in educational scripting language turtleScript.
it is intended for tablets (i use one with 10.1" screen for editing text/source). it does not include icons for
making it more friendly to older devices -- instead there are unicode (UTF-8) symbols on special keys.
it would be the best to use it with non-distracting high contrast skin well differentiating between text labels
on keys (i use my own flat-dark-violet.skin with it, it uses contrasting colors that help focusing my attention).

 visit https://apps.kde.org/kturtle/ for getting this programming environment
 (you would need kTurtle educational IDE from KDE for this stuff being usable. IDE is not available for Android yet
 but you may connect to desktop system via VNC (linux) or RDP (windows OS) and to mirror kTurtle's window easily)
 you may want to visit https://docs.kde.org/stable5/en/kturtle/kturtle/index.html for documentation of the language.

this keyboard is based on qwerty but some symbolic buttons are changed: some brackets are used more oftenly so
 they are made more accessible or this sign '$' is used for marking variables in a script or comma ',' and arithmetical
 operators like plus '+' are spelled with a trailing space like ', ' and '+ ' so the script is looking neatly visually (last
 group may be entered without the space if using '+clean' button [on long press]).
 two rightmost buttons at the first row are calling special keyboards:
     [and so they are looking like at those helper keyboards too]
 '0≠1' [long press] is for numbers/operators and 'snowflake' (2745, 'Tight Trifoliate Snowflake')
 with [long press] 'Koch snowflake' (2721, 'Star Of David') are for turtleScript keywords.
 there are duplicated keywords on some buttons -- such ones are spelled with trailing space or if using long press
 alternatively they may be used for replacing other keywords during coding (you know hackers do it :D very oftenly)
 [select a word to replace then long press required key and your turtle moves not 'forward' but 'backward'].
 also i have made some pre-formatted 'if-else' specials.

you may want to read my own source codes written in this programming language too:
  https://github.com/irulanCorrino


****hotfix
there was glaring issue with first implementation of this layout but because of that hole in my code i have realized
that visual appeal of my layout is very dependent on specific libraries installed on each Android device.
i made it using my Jelly Bean tablet with 10.1" screen having 'choco cooky' font systemwide ...but then i have
installed it on my Kit Kat smartphone [that is not recommended to do, provided that smaller screens are not
suitable for heavy text editing] —and some keys were looking differently from their appearance on my tablet!
and the font (some 'serif' i guess) was not fitting button sizes even with smaller values; so i have changed
the font to 'choco cooky' and all text labels [except ones with that wrong code] are looking nice!!!
but some Unicode symbols differ between libraries of different devices and even between fonts of one device!
i do not use icons but i was not targeting to get uniform look between devices either —so i stick with Unicode.

now fixing that my code. fixed!!!
the issue was in that different Android systems treat 'specKey' or 'smallLabel' flags differently so following code
  <Key android:keyLabel="bS⇦" android:codes="-5" android:keyWidth="9.0%p" android:isRepeatable="true" />
  <Key android:keyLabel="⇨dl" android:codes="-5112" android:specKey="true" android:isRepeatable="true" />
has made blue 'backspace' and red 'delete' buttons on my smartphone with Kit Kat but they both were red
while i was writing this layout on my Jelly Bean tablet (and they both are Android 4) [i was aware of this
inconsistency in my code but firstly i have left it be for testing purposes and when i was fixing these inconsistencies
in other places (these flags are used oftenly) i have forgotten to check these buttons on two keyboards].
i have made both keys blue for Android Kit Kat and have done the same for 'undo' and 'redo' (they were red)
but an IDENTICAL PIECE of code makes red undo/redo keys at a helper keyboard!

values (for 'choco cooky', set 'default' in app’s settings for getting system font on keyboard!):
[i guess 'choco cooky' does not have bold or italic styles]
tablet 10.1" 
                     —primary font 32;
                     —symbol font 24;
                     —font for labels 18;
smartphone 4.5"
                     —primary font 30;
                     —symbol font 15;
                     —font for labels 12.
                     setting reasonable values here is VERY IMPORTANT for having labels not clashing one with another
                     or being diminished injustly. Android system calculates final size of each label using* these three main
                     variables: 0. size of the button; 1. font size as requested by a user; 2. length of the label in pixels;
                     but if the user requests primary or label font of bigger size than system can handle then even if
                     there is no another label on the button the system would make rendered label significantly smaller
                     than it could be with a sane value of font size.
                      *[and there are constants like 'dpi' or 'screen size']


