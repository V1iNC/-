#### Аутентификация
При подключении клиента сервер должен выполнить несколько задач.Во-первых, идентифицировать пользователя, то есть определить его имя. Для этого пользователь представляется, но указанное имя может отличаться от имени пользователя БД (например, если пользователь представляется своим именем в ОС).
В целях выполнения данной лр я создал суперпользователя kat:
![avatar](https://sun9-24.userapi.com/impg/Mg1ABDx3zMZcfAwwRmeLgX1F-2b8A_Q9i8sueg/M9j6mWiC1YI.jpg?size=619x135&quality=96&sign=9201715919e35b2ad8917220d9b14232&type=album)
Затем я сохранил файл pg_hba.conf, чтобы иметь возможность восстановить:
![image](https://user-images.githubusercontent.com/113884588/202406157-52ef0eb5-b58f-4ec8-b881-6373ac5ffe3c.png)
Проверил содержимое pg_hba.conf(используя представление pg_hba_file_rules):
![avatar](https://sun9-10.userapi.com/impg/vupbUl0RSJudUqEKEnHUAbVnVX5Nud7OdA_ZVQ/RGb0KFI4Zrw.jpg?size=594x189&quality=96&sign=562641d0ade742f8cc0ca4a408636e7f&type=album)
Затем перезаписал pg_hba.conf с нуля:
![image](https://user-images.githubusercontent.com/113884588/202406213-97edbc2b-847e-45a9-8b0b-f0a247f02590.png)
Перезагрузил файл для сохранения настроек с помощью команды sudo pg_ctlcluster 12 main reload и просмотрел содержимое файла:
![image](https://user-images.githubusercontent.com/113884588/202406263-e8ca29d6-baa3-44d5-985a-faeb36e4c553.png)
Проверил подключение. Подключился как пользователь kat к тестовой БД bd1:
![avatar](https://sun9-87.userapi.com/impg/qawpIlDhDBnnmI54_-NW6SS7gIBiPwn0AcDSvg/hxeZkMYj5Kg.jpg?size=805x69&quality=96&sign=d37360eefe412a35b9ae69c3a497e24a&type=album)
На снимке видно, что подключение прошло успешно.
