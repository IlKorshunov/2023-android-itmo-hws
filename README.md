### Вводные

На клиенте довольно часто вид получаемой информации и вид отображаемой отличны. В данном задании вид получаемой информации был умышленно сделан настолько неудобным :)

Вам дан класс Repository (который инкапсулирует в себе получение информации), у него есть один метод, возвращающий список некоторых Entity. В данном задании Entity являются классы User, Chat, Message. Предположим, Вам необходимо реализовать список чатов для конкретного пользователя. Необходимые для этого сущности вы получаете через репозиторий, но для отрисовки было бы удобнее использовать отдельную модель данных (аватарка собеседника, имя, последнее сообщение и было ли прочитано сообщение).

Также поздее появилось продуктовое требование добавить возможность фильтровать чаты по статусу прочитанности последнего сообщения, а также добавить групповые чаты.

### Задание

1) Добавить в сущность Message состояние State, которое может быть READ, UNREAD, DELETED, причем состояние DELETED хранит в себе id пользователя удалившего сообщение. - 2 балла

2) Реализовать класс MessageController который помогает получать необходимую валидную информацию из Repository. Валидным Entity считается объект у которого null может быть только в полях помеченных аннотацией @Nullable, невалидные Entity нужно фильтровать. - 5 баллов

   2.1) Реализовать модель для отображения (ChatItem), которая должна в себе хранить ссылку на аватарку пользователя, последнее сообщение от него, статус прочитано или нет сообщение. В случае если сообщение было удалено необходимо вывести "Сообщение было удалено {имя пользователя удалившего сообщение}"
   
   2.2) Реализовать метод получающий на вход id текущего пользователя и State сообщения опционально, на выход отдать список ChatItem для текущего пользователя, с заданным STATE если он был передан
   
   2.3) Реализовать метод, предоставляющий количество отправленных сообщений для переданного пользователя

3) Дописать новую сущность "Групповой чат" (В нем может быть своя аватарка и несколько пользователей) и учесть её обработку в контроллере (Фильтрация невалидных экземпляров, добавление необходимой для отображения информации в ChatItem)  - 3 балла

Все новые классы пишутся на Kotlin 