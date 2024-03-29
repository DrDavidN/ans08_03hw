# «Использование Ansible» - Дрибноход Давид

## Подготовка к выполнению

1. Подготовьте в Yandex Cloud три хоста: для `clickhouse`, для `vector` и для `lighthouse`.
2. Репозиторий LightHouse находится [по ссылке](https://github.com/VKCOM/lighthouse).

## Основная часть

1. Допишите playbook: нужно сделать ещё один play, который устанавливает и настраивает LightHouse.
2. При создании tasks рекомендую использовать модули: `get_url`, `template`, `yum`, `apt`.
3. Tasks должны: скачать статику LightHouse, установить Nginx или любой другой веб-сервер, настроить его конфиг для открытия LightHouse, запустить веб-сервер.
4. Подготовьте свой inventory-файл `prod.yml`.
5. Запустите `ansible-lint site.yml` и исправьте ошибки, если они есть.
6. Попробуйте запустить playbook на этом окружении с флагом `--check`.
7. Запустите playbook на `prod.yml` окружении с флагом `--diff`. Убедитесь, что изменения на системе произведены.
8. Повторно запустите playbook с флагом `--diff` и убедитесь, что playbook идемпотентен.
9. Подготовьте README.md-файл по своему playbook. В нём должно быть описано: что делает playbook, какие у него есть параметры и теги.
10. Готовый playbook выложите в свой репозиторий, поставьте тег `08-ansible-03-yandex` на фиксирующий коммит, в ответ предоставьте ссылку на него.

## Решение

1. - 3. Дописал playbook
4. Сформировал свой inventory 

![image](https://github.com/DrDavidN/ans08_03hw/assets/128225763/f41e1560-d52c-4848-b17b-7a52e6e69f8f)

5. Проверил на ошибки `ansible-lint site.yml`, исправил наименование старых модулей
6. check вызывает ошибку так как во время проверки не скачиваются пакеты
7.

![image](https://github.com/DrDavidN/ans08_03hw/assets/128225763/4276a7aa-ec78-4cf6-b918-65ff1fbf9117)

8. Изменения связаны с перезапуском Vector

![image](https://github.com/DrDavidN/ans08_03hw/assets/128225763/d92f2b92-6781-4306-9019-aae481997b4d)

9. https://github.com/DrDavidN/ans08_03hw/blob/main/step%209/README.md
