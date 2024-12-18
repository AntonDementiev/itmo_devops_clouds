# Лабораторная работа 2. Сравнение сервисов Amazon Web Services и Microsoft Azure. Создание единой кросс-провайдерной сервисной модели.

## 3 вариант

## Цель работы: 
Получение навыков аналитики и понимания спектра публичных облачных сервисов без привязки к вендору. Формирование у студентов комплексного видения Облака. 

## Дано: 
Данные лабораторной работы 1.
Слепок данных биллинга от провайдера после небольшой обработки в виде SQL-параметров. Символ % в начале/конце означает, что перед/после него может стоять любой набор символов.
Образец итогового соответствия, что желательно получить в конце. В этом же документе  

## Необходимо: 
Импортировать файл .csv в Excel или любую другую программу работы с таблицами. Для Excel делается на вкладке Данные – Из текстового / csv файла – выбрать файл, разделитель – точка с запятой.
Распределить потребление сервисов по иерархии, чтобы можно было провести анализ от большего к меньшему (напр. От всех вычислительных ресурсов Compute дойти до конкретного типа использования - Выделенной стойка в датацентре Dedicated host usage). При этом сохранять логическую концепцию, выработанную в Лабораторной работе 1.
Сохранить файл и залить в соответствующую папку на Google Drive.

## Ход работы:
1. Дан следующий слепок биллинга:
![image](https://github.com/user-attachments/assets/7e715c56-8b44-4640-b07a-542a1c112f81)

2. Заполним 5 столбцов таблицы:
![image](https://github.com/user-attachments/assets/6b966e56-d620-4ee6-9825-4da9a37b3d8a)

## Опишем сервисы, которые мы использовали:

### Machine Learning: ML Model Managment, ML Studio
ML Model Management - управление моделями машинного обучения:
  - `Model Hosting` - управление развертыванием

ML Studio - тестирование и среда разработки для машинного обучения:
  - `Experiment Compute` - ресурсы для эксперимента
![image](https://github.com/user-attachments/assets/40aaa43b-1062-434c-8572-bb06694654f2)

### Cognitive Services: Text Analytics, Emotion API
Text Analytics - анализ текста:
`Free Tier` - использование для анализа текста

Emotion API - распознавание эмоций в видео/фото:
  `Emotion Api` - распознавание эмоций
![image](https://github.com/user-attachments/assets/4d7c36fb-47f8-4a51-b121-412ff0a6b3c5)

### Compute: Functions, Virtual Machines, Azure Batch
Functions - серверные вычисления:
   - `Execution` - выполнение функций
   - `Duration` - время выполнения функции

Virtual Machines - виртуальные машигы для вычислительных задач и хостинга приложений:
`A, D, E, F, G, H, B, N, M, S Series` - конфигурации ВМ.

Azure Batch - вычисления для обработки ольшого количества задач
![image](https://github.com/user-attachments/assets/a802b95b-763f-482b-abd9-f0cf10a895a2)

### Data Services: SQL Data Waterhouse
  - мы используем для аналитики больших данных
![image](https://github.com/user-attachments/assets/30cd4dbf-e4b8-4598-9345-f74ff7b85b2d)

### Insight and Analytics: Log Analytics
  - устранение ошибок и мониторинг производительности:
      - `Data Included per Node` - объём, включённый в мониторинг узлов.
      - `Data Overage per Node` - перерасход
      - `Node Monitoring` - услуга мониторинга узлов
![image](https://github.com/user-attachments/assets/a5325817-f1e3-4ada-91b2-2ace0b81f803)

### Security: Key Vault
  - управление ключами и защищённое хранение:
    `Secrets Managment` - управление секретами, чтобы безопасно хранились данные
![image](https://github.com/user-attachments/assets/974423e1-124b-4d01-9918-8f473e96f7ad)


### Integration: Logic Apps
  - автоматизация и интеграция процессов:
    `Workflow Automation` - автоматизация раб. процессов.
![image](https://github.com/user-attachments/assets/11aa82e2-7f55-4de3-a76e-2015da7beb77)

### Mobile Services: App Hosting
  - хостинг мобильных приложений (разработка и  тестирование):
    `Free Tier` - бесплатно для тестирования
![image](https://github.com/user-attachments/assets/e73b98a5-5c78-4146-b8c7-f3ec4aa1211b)

### Networking: VPN Gateaway, Traffic Manager, Azure Firewall
VPN Gateway - подключние к облачным сервисам:
 - `Gateway` - время работы шлюза.
 - `Gateway Data Transfer` - пердача данных через шлюз.

Traffic Manager - управление маршрутизацией трафика между серверами:
 - `Azure Endpoint` - управление конечными точками.
 - `DNS Queries` - запрсосы DNS.

Azure Firewall - защита сети от различных угроз:
 - `Deployment` - развертывание
 - `Data Processed` - обработка данных
![image](https://github.com/user-attachments/assets/19da72e7-ce42-45d9-8c0c-d7ed6e3e1f78)

### Storage: Data Transfer
  - передача данных между облаком и внешней системой:
     `Data Transfer Out` - передача данных из облака
![image](https://github.com/user-attachments/assets/11da8288-bacc-4a15-9a7f-60bb3217c66c)


### Media Services: Media Encoding
  - потоковая передача данных и кодирование:
    `Streaming Services` - часы кодирования для потоковой передачи информации
![image](https://github.com/user-attachments/assets/4c79697a-ee9a-4868-b68b-89219754b46b)

### IoT: IoT Hub
  - управление устройствами IoT и подключением:
   `Device Management` - управление устройством и подключением
![image](https://github.com/user-attachments/assets/08001a3f-49e9-4f8a-849f-1c4648851588)

### Recovery Services: Azure Site Recovery
  - восстановление виртуальных машин для обеспечения нормального состояния и отказоустойчивости:
  `VM Replicated to Azure` - репликация ВМ в облако
![image](https://github.com/user-attachments/assets/30442993-c115-4e76-9c5a-c8c224ec5ff8)
