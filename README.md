# Паттерны проектирования

В рамках этого домашнего задания вы начнете делать проект. Проект состоит из 4 частей, одна часть - одно домашнее задание, поэтому сегодняшнее задание и 3 следующих будут связаны. Мы предлагаем вам сделать мессенджер, но вы можете делать свой проект, главное, чтобы он соответствовал требованиям, которые будут представлены ниже.

1. [Описание проекта "Мессенджер"](#мессенджер)
2. [Требования, если делаете свой проект](#свой-проект)
3. [Критерии оценивания домашнего задания](#критерии-оценивания-домашнего-задания-часть-1-авторизация)

## Мессенджер
У вас есть:
- Макеты в [Figma](https://www.figma.com/file/fL1XK5Cb1R1Z8Hz5ZgHH8p/Студентам?type=design&node-id=0-1&mode=design&t=Mm02Hmz9qW5VFfDw-0)
- Сервер, с которым будет общаться ваше приложение, и [его описание](https://faerytea.name:8008/static/howto.md)

Дополнительно придумывать ничего не надо, вам остается лишь реализовать то, что от вас будет требоваться.

## Свой проект

Если вы делаете свой проект, то нужное АПИ вам надо искать самим и макеты использовать свои (ну или без них). Ваш проект должен соответствовать критериям.

**Общие критерии ко всем этапам:**
- Реализация экранов приложения должна быть сделана с использованием паттерна MVVM, о котором было расказанно на соответствующей лекции.
- Использование Firebase не допускается, так как решение проблем с ним может занять много времени, но не принесет вам баллов.
- Не использовать сторонние графические движки (Unity, Unreal и т.п.).
- Нужно использовать стандартный UI Kit.
- Поддержка вертикальной и горизонтальной ориентации экрана (но не надо делать отдульный layout для горизонтального вида), при повороте не должны теряться введенные данные. Блокировать поворот экрана не допускается.
- Необходимо наличие изображений в проекте. Отображать просто текстовые данные везде - недостаточно.
- Все экраны должны быть реализованы на фрагментах
- Проект собирается
- Приложение не крашится
- Отсутствуют утечки памяти

**Этап 1: Авторизация.**
Необходимо наличие экрана авторизации по логину и паролю (данные могут быть фейковыми и храниться в памяти приложения).
- Заголовок экрана
- Поле для ввода логина
    - Название поля (в виде текста до поля или внутри самого поля)
- Поле для ввода пароля
    - Название поля (в виде текста до поля или внутри самого поля)
    - Вводимые символы должны быть скрыты
- Кнопка входа
    - Если одно из полей пустое, то кнопка вход должна быть недоступна
    - При успешном логине должен открываться следующий экран (пока просто пустой)
- Обработка ошибок
    - Валидация логина или пароля
    - Какие-то непредвиденные ошибки (отсутствие интернета, не работает сервер и т.д.)
- Открывшийся после логина экран должен обрабатывать системное действие "назад" и делать разлогин (logout), возвращая на экран авторизации для возможности авторизоваться другим пользователем.

**Этап 2: Списки.**
Необходимо наличие экрана со списком данных.
- Заголовок экрана
- Поход в сеть за данными не в главном потоке (рекомендуется использовать Retrofit)
- Отображение состояния, когда данных нет (пустого экрана недостаточно, нужно отобразить хотя бы соответствующий текст)
- Отображение состояния, когда данные начали грузится (крутилка)
- Отображение состояния, когда произошла ошибка загрузки данных (пустого экрана недостаточно, нужно отобразить хотя бы соответствующий текст)
- Отображение состояния, когда данные пришли - список карточек с данными
    - Использовать RecyclerView
    - Постраничная подгрузка данных, грузить сразу весь список не допускается (если ваше АПИ такое позволяет делать)

**Этап 3: Снова списки.**
Второй экран со списком. Он будет отличаться от второго этапа содержанием, подробнее вам опишут критерии при выдаче ДЗ на лекции через 2 неделе. Для разных экранов со списками будут использованы разные макеты.

**Этап 4: Кеширование.**
Кэширование данных на экране со списком на случай отсутствия интернета.
- Обращаться к хранилищу через Room, но можно что-то другое. Голый JDBC/SQLiteOpenHelper - не допускается.
- Запись/чтение должны происходить не в главном потоке.

В момент выдачи ДЗ преподаватель может добавить еще какие-то критерии, но все главные - описаны здесь.

## Критерии оценивания домашнего задания. Часть 1: Авторизация.

В этой части вам необходимо реализовать экран авторизации в вашем проекте.
**Ограничения:**
- Не использовать сторонние графические движки (Unity, Unreal и т.п.).
- Нужно использовать стандартный UI Kit.
- Использование Firebase не допускается, так как решение проблем с ним может занять много времени, но не принесет вам баллов.

Если ограничения не будут соблюдены, то вы не получите баллов. Более детально требования и баллы к ним описаны ниже по пунктам. Также в некоторых случаях без этих ограничений мы просто не сможем проверить ваше задание и попросим выполнить его снова.

**Требования:**
1. Общие **(max 4.5 балла)**
    - Проект собирается (баллов не дает, так как без этого их не получится набрать)
    - Приложение не крашится **(0.5 балла)**
    - Отсутствуют утечки памяти **(1 баллов)**
    - Реализация экрана авторизации должна быть сделана с использованием паттерна MVVM, о котором было расказанно на лекции **(2 балл)**
    - Поддержка вертикальной и горизонтальной ориентации экрана (но не надо делать отдульный layout для горизонтального вида), при повороте не должны теряться введенные данные. Блокировать поворот экрана не допускается **(1 балл)**
2. Экран авторизации **(max 5.5 баллов)**
    - Заголовок экрана **(0.5 балла)**
    - Поле для ввода логина **(1 балл)**
        - Название поля (в виде текста до поля или внутри самого поля)
    - Поле для ввода пароля **(1 балл)**
        - Название поля (в виде текста до поля или внутри самого поля)
        - Вводимые символы должны быть скрыты
    - Кнопка входа **(1 балл)**
        - Если одно из полей пустое, то кнопка вход должна быть недоступна
        - При успешном логине должен открываться следующий экран (пока просто пустой)
    - Обработка ошибок **(1 балл)**
        - Несоответствие логина или пароля
        - Какие-то непредвиденные ошибки (отсутствие интернета, не работает сервер и т.д.)
    - Открывшийся после логина экран должен обрабатывать системное действие "назад" и делать разлогин (logout), возвращая на экран авторизации для возможности авторизоваться другим пользователем. **(1 балл)**

Все элементы соответствуются макетам (цвет, размер текста, отступы и т.д.), если что-то не соответствует макету, то за этот элемент не получится получить баллов (относится к тем, кто делает мессенджер).