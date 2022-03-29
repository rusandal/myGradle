# Многомодульный проект на Gradle
## Описание
Программа реализует многомодульный проект с помощью Gradle:  
db - модуль работы с базой данных;  
api - модуль работы с web;  
service - слой сервисов.  

В корне создан settings.gradle с указанием модулей
```
rootProject.name = 'garedleStart'
include 'db'
include 'api'
include 'service'
```

В основном проекте создано 3 директории db, api, service, в каждой из которых создан свой build.gradle с необходимыми зависимотями.
```
...
plugins {
    id 'java'
}
group 'ru.netology'
version '1.0-SNAPSHOT'
repositories {
    mavenCentral()
}
dependencies {
    implementation project(":имя_модуля")//db|api|service
    implementation project(":имя_модуля")//db|api|service
}
``` 

Для демонтстрации работы модульности были созданы классы в bd и service. 
В папке api создаем точку входа main.
В результате получился модульный проект с разделением по функциональности.
