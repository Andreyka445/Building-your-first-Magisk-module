# Создаём свой первый Magisk модуль / [Creating your first Magisk module - eng ver of instruction](https://github.com/Andreyka445/Building-your-first-Magisk-module/tree/eng_ver)  
# Что такое Magisk и ROOT менеджеры
Magisk — это инструмент, который дает root-права, а Root-менеджер — это приложение, которое контролирует, кто этими правами может пользоваться. В Magisk эти две функции объединены в одном пакете.

# Для начала нужно определится для чего нам нужен модуль?
самые популярные модули - это модули , которые редактируют системные файлы, заменяют .prop переменные и выполнение всякого рода скриптов.
После того, как определилиь для чего нам нужен модуль приступаем к следующему шагу - сборке модуля.

# Содержание
1) [Что такое Magisk и ROOT менеджеры?](https://github.com/Andreyka445/Building-your-first-Magisk-module?tab=readme-ov-file#%D1%87%D1%82%D0%BE-%D1%82%D0%B0%D0%BA%D0%BE%D0%B5-magisk-%D0%B8-root-%D0%BC%D0%B5%D0%BD%D0%B5%D0%B4%D0%B6%D0%B5%D1%80%D1%8B-%D0%B2-%D1%86%D0%B5%D0%BB%D0%BE%D0%BC)
2) [Определяемся для чего нам нужен модуль](https://github.com/Andreyka445/Building-your-first-Magisk-module?tab=readme-ov-file#%D0%B4%D0%BB%D1%8F-%D0%BD%D0%B0%D1%87%D0%B0%D0%BB%D0%B0-%D0%BD%D1%83%D0%B6%D0%BD%D0%BE-%D0%BE%D0%BF%D1%80%D0%B5%D0%B4%D0%B5%D0%BB%D0%B8%D1%82%D1%81%D1%8F-%D0%B4%D0%BB%D1%8F-%D1%87%D0%B5%D0%B3%D0%BE-%D0%BD%D0%B0%D0%BC-%D0%BD%D1%83%D0%B6%D0%B5%D0%BD-%D0%BC%D0%BE%D0%B4%D1%83%D0%BB%D1%8C)
3) [Сборка модуля](https://github.com/Andreyka445/Building-your-first-Magisk-module#2-%D0%B2%D1%82%D0%BE%D1%80%D0%BE%D0%B9-%D1%81%D1%86%D0%B5%D0%BD%D0%B0%D1%80%D0%B8%D0%B9---%D0%B7%D0%B0%D0%BC%D0%B5%D0%BD%D0%B0-%D0%B8-%D0%B4%D0%BE%D0%B1%D0%B0%D0%B2%D0%BB%D0%B5%D0%BD%D0%B8%D0%B5--prop-%D0%BF%D0%B5%D1%80%D0%B5%D0%BC%D0%B5%D0%BD%D0%BD%D1%8B%D1%85)
4) [Замена системных файлов](https://github.com/Andreyka445/Building-your-first-Magisk-module#1-%D1%81%D1%86%D0%B5%D0%BD%D0%B0%D1%80%D0%B8%D0%B9-%D0%B8%D1%81%D0%BF%D0%BE%D0%BB%D1%8C%D0%B7%D0%BE%D0%B2%D0%B0%D0%BD%D0%B8%D1%8F---%D0%B7%D0%B0%D0%BC%D0%B5%D0%BD%D0%B0-%D1%81%D0%B8%D1%81%D1%82%D0%B5%D0%BC%D0%BD%D1%8B%D1%85-%D1%84%D0%B0%D0%B9%D0%BB%D0%BE%D0%B2)
5) [Замена/Добавление .prop переменных](https://github.com/Andreyka445/Building-your-first-Magisk-module#2-%D0%B2%D1%82%D0%BE%D1%80%D0%BE%D0%B9-%D1%81%D1%86%D0%B5%D0%BD%D0%B0%D1%80%D0%B8%D0%B9---%D0%B7%D0%B0%D0%BC%D0%B5%D0%BD%D0%B0-%D0%B8-%D0%B4%D0%BE%D0%B1%D0%B0%D0%B2%D0%BB%D0%B5%D0%BD%D0%B8%D0%B5--prop-%D0%BF%D0%B5%D1%80%D0%B5%D0%BC%D0%B5%D0%BD%D0%BD%D1%8B%D1%85)

# Сборка модуля
ТРЕБОВАНИЯ: Magisk 20.04+
Все config файлы должны быть в кодировке UTF-8. Для удобного редактирования файлов рекомендую использовать [NotePad++](https://notepad-plus-plus.org/).
Модуль обязателно должен быть в .zip архиве без защиты паролем.

Чтобы приступить к сборке модуля скачайте "пустышку".
1) Распакуйте пустышку в любую папку
2) Добавьте необходимые изменения и соберите готовый модуль в .zip

# Кратко пройдёмся по каждому из сценариев

# 1) Сценарий использования - Замена системных файлов

  Замена системных файлов.
Внутри пустышки есть папка system в неё поместите файлы, которые нужно заменить, но при этом соблюдайте пусть к оригинальному файлу.


 Необходимо заменить framework-res.apk, который лежит по пути /system/framewrok
 Решение: В папке с распакованной "пустышкой" есть папки _system_, создайте в ней папку _framework_ и поместите туда свой изменённый оверлей.

 Что делать, если файл, который нужно заменить находится в другом разделе?

 Если требуется замена в другом разделе _/system_ext_ , _/product_ или _/vendor_, то __ВАЖНО (bold)__ внури папки _system_, которая уже есть в пустыше создайте папку с нужным вам разделом, напиример _vendor_ и укажите путь к файлу выглядить это должно вот так:     
 _/system/vendor/etc/hw/init.aee.rc_
 # 2) Второй сценарий - Замена и добавление  .prop переменных
   Необходимо: Заменить/Добаить .prop
   
   Решение: В скачаной пустышке есть файл _sytem.prop_ , добавьте в него вашу переменную так, как она должна выглядеть в системе.

   Пример: Нужно отключить blur, который включен по дэфолту в системе, для этого в файл _system.prop_ копирую переменные "ro.sf.blurs_are_expensive=1" и ro.surface_flinger.support_background_blur=1", где "1" - это _true (включено)_ , а "0" - это _false (выключено)_
   
   Конечный результат в файле _system.prop_ выглядит так: _"ro.sf.blurs_are_expensive=0" и ro.surface_flinger.support_background_blur=0"_

   
 
