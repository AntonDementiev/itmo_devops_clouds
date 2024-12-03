# Отчет по лабораторной AWS

### Введение 
Мы брали информацию об `AWS` на [официальном сайте](https://aws.amazon.com)
Вот сервисы, которые были использованы в рамках лабораторной работы:

### AmazonElastiCache - Compute
- сервис повышает производительность веб-приложений, извлекая информацию из управляемых кешей в памяти.
Использование сервиса в лабораторной: `Tax` - налоги за использование; `Node Usage` - оплата за кеш-нод; 'Snapshot Creation' - создание резервных копий; `Backup Usage` - использование бэкапов.
![image](https://github.com/user-attachments/assets/59e307bd-06a4-489c-9c93-242746e5ab4d)


### AmazonES - Search & Analytics
- используется для поиска данных, хранения логов и их анализа: `Data Transfer` - передача данных; `Storage` - хранение данных; `Instance Usage` - использование виртуальныых машин; `Provisioned IOPS` - операция ввода-вывода.
  ![image](https://github.com/user-attachments/assets/f23761b1-f46e-407e-8f46-97b2549c5048)


### AmazonCloudfront - Content Delivery
- это сеть доставки контента, которая была создана для его кэширования ближе к потребителю.
  В `Data Transfer` у нас идёт оплата за передачу данных через этот сервис.

  ![image](https://github.com/user-attachments/assets/435b7ffd-11d0-43b8-afa8-30389ae4b415)


### AmazonQLDB - Database
- используется для ведения неизменяемых данных.
  Мы используем этот сервис для хранения данных и операции ввода-вывода (`Storage`, `IO Operations`).

  ![image](https://github.com/user-attachments/assets/61e43515-64ca-4fcf-b487-12a87857bfa4)

  
### AWS KMS, AWS CloudHSM - Security:
AWS KMS - обеспечивает безопасность ключей для защиты данных в сервисах.
Нам потребуется использовать это в таблице для `KMS API Requests` (API запросы) и `KMS Keys Usage` (для ключей шифрования).

AWS CloudHSM - используется для более сложных требований защиты (различные криптографические задачи и т.д.). Поэтому используем в `HSM Operations`. 
![image](https://github.com/user-attachments/assets/837f29d3-1a94-43f3-8a6d-7ebeaaf70a7e)


### AmazonRekognition, AmazonTextract, AmazonLex - AI & ML
AmazonRekognition - распознавание объектов и их анализ: `Image/Video Analysis` - анализ видео/изображения.
AmazonTextract - извлечение данных: Для `Pages Processed` мы используем этот сервис.
AmazonLex - создание чат-ботов: `API Requests` - запросы к API.
![image](https://github.com/user-attachments/assets/7de982ee-1dba-43bf-9ad1-2934ec2d7706)


### AWSCodePipeline - DevOps
- используется для ускорения разработки: `Trial Pipelines` и `Active Pipelines` (пробные и активные пайплайны)
  ![image](https://github.com/user-attachments/assets/cd8a09ca-8cea-4603-a374-c746c40dd110)


### AmazonSES, AmazonSNS - Messaging
AmazonSES - используется для отправки сообщений: 
`Recipients` - получатели; `Attachments Size Usage` - объём данных вложений.
AmazonSNS - передаёт сообщения в реальном времени:
`SMS` - отправка смс. `Delivery Attemps` - попытки доставить сообщения каналами.
![image](https://github.com/user-attachments/assets/a19bd525-04cb-483d-969c-43e68f8d3231)
