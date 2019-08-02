Отладка внешних обработок
=========================

Расширение позволяет отлаживать внешние отчеты и обработки в 1С.

Как пользоваться
----------------

Сохраняем файл отчета или обработки на диск в конфигураторе. Запускаем режим предприятия. Добавляем обработку в конфигурацию как внешнюю (добавляем в справочник ДополнительныеОтчетыИОбработки). 
В разделе администрирование - справочник "Отладка внешних отлаживаемые" добавляем запись отлаживаемой обработки. Указываем ссылку на обработку из справочника ДополнительныеОтчетыИОбработки, имя файла на диске (который открыт в конфигураторе) и при желании пользователя, под которым нужна отладка.

Если файла обработки нет в указанном месте, он выгрузится из конфигурации. Если есть, он не замещается. Не забываем по окончании отладки обновить его в базе данных.

Если пользователь указан, то отладка только под этим пользователем. Если не указан, то под любым.

В конфигураторе открываем указанный файл и ставим точки останова. Обновлять можно на лету, просто пересохраняя файл. "Обновить из файла" делать не нужно.

В случае серверной базы расположение файла нужну указывать относительно сервера.

Описание принципа работы
------------------------

Принцип действия простой. Заменяется функция БСП ДополнительныеОтчетыИОбработки.ПодключитьВнешнююОбработку, в которой нужная обработка создается не в памяти, а подключается как файл с диска.

Информация для отлаживаемой обработки хранится в созданном справочнике ОтладкаВнешних_Отлаживаемые (Раздел администрирование)
Там указывается ссылка на обработку из справочника ДополнительныеОтчетыИОбработки, признак отладки, имя файла и пользователь.
Пользователя можно не указывать. Если указан, отладка идет только под данным пользователем

Вариантов хранения информации много, выбрал этот. Можно просто сохранять файл в каталог базы, если она файловая. Можно писать имя файла в комментарии к обработке. Можно дополнить справочник ДополнительныеОтчетыИОбработки нужными полями.
