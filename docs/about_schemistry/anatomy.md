---
sidebar_label: 'Анатомия schemistry.toml'
---

### Общая информация

Вы можете настраивать поведение schemistry через файл schemistry.toml. Этот файл хранит информацию о целевом реестре, а также описывает список контрактов сервиса со списком клиентских контрактов.

Schemistry автоматически находит schemistry.toml файлы в локальной директории.

### Анатомия конфигурационного файла schemistry.toml

```toml
Remote = 'http://some.url' #schema registry url
Owner = 'organization_name'
Repository = 'repository_name'

[Modules]
Path = './contracts'
List = []

[Deps]
Path = './dep_vendor'

# список контрактов, который импортировали
[[Deps.List]]
Remote = 'http://some.url' #schema registry url
Owner = 'organization_name'
Repository = 'repository_name'
Name = 'some_name' # название контракта
Language = 'proto3' # язык контракта
VersionNumber = '1.0.0' # версия контракта
```
