# Консольная игра "Виселица"

Реализация игры "Виселица" с консольным интерфейсом на Java.

---

## Правила игры

Загадывается слово, являющееся  именем существительным, нарицательным в именительном падеже единственного числа, либо множественного числа при отсутствии у слова формы единственного числа.<br>
Игрок должен отгадать это слово, поочередно называя буквы. Если буква есть в слове, то она вписывается на своё место в слово (если таких букв несколько — то вписываются все), а если нет — то рисуется одна часть тела человечка на виселице (голова, туловище, 2 руки, 2 ноги — всего 6 элементов-попыток).<br>
Если игрок не успел угадать слово раньше, чем виселица нарисована полностью, то он считается «повешенным», т.е. проигравшим. Если слово отгадано — то игрок выиграл.<br>
Более подробные правила на [Википедии](https://ru.wikipedia.org/wiki/%D0%92%D0%B8%D1%81%D0%B5%D0%BB%D0%B8%D1%86%D0%B0_%28%D0%B8%D0%B3%D1%80%D0%B0%29).

---

## Установка и запуск

*На компьютере должен быть установлен Java Development Kit (JDK).*

1. Откройте терминал. Перейдите в директорию, куда будет устанавливаться программа.
2. Клонируйте репозиторий

```
git clone https://github.com/IsaIsmailzade/Hangman.git
```

3. Перейдте в директорию проекта Hangman

```
cd Hangman
```

4. Скомпилируйте программу

```
javac src/*.java -d classes
```

5. Создайте jar файл

```
jar -cvfm Hangman.jar resources/META-INF/MANIFEST.MF -C classes . -C resources Dictionary.txt
```

6. Запустите игру

```
java -jar Hangman.jar
```

---

## Взаимодействие с приложением

1. При запуске приложение предлагает начать новую  игру.
2. При начале игры случайным образом загадывается слово. В консоли отображается исходное состояние виселицы и слово с зашифрованными буквами.
3. Игроку предлагается ввести букву. После того, как он это сделал, в консоли отображается информация о наличии этой буквы в слове, состояние виселицы, слово с отгаданными буквами, счетчик ошибок со списком неугаданных букв.
4. Повторно введенная буква не считается ошибкой. При введении чего-либо, отличного от одной буквы русского алафавита в любом регистре, предлагается ввести букву заново.
5. Игра продолжается до тех пор, пока слово не будет отгадано или все части человека на виселице не будут нарисованы (счетчик попыток не будет равен 0).
6. В конце игры в консоли отображается результат игры (проигрыш/победа игрока) и загаданное слово (в случае выигрыша). Приложение переходит к состоянию 1 (предложение начать новую игру).
