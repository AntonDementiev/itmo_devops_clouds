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
![image](https://github.com/user-attachments/assets/e5fbe402-dce5-45bd-be11-544e2c8d3519)


## Опишем сервисы, которые мы использовали:

# Storage: SQL Data Warehouse, Data Transfer:
- **Описание**:  
Можно сказать, что мы используем Storage для хранения данных в Azure, имея высокопроизводительные решения для работы сбольшим обЪёмом.
  
![image](https://github.com/user-attachments/assets/a99e3a27-97b5-4502-a681-bd5a64416984)

- **Пример использования**:  
  - **Service Sub-Type**: Azure Synapse Analytics.  
  - **Meter Name**: 100 DWUs - использование вычислительных ресурсов.  
  - **Consumed Service**: Microsoft.Sql  


# Search & Analytics (Insight & Analytics)
![image](https://github.com/user-attachments/assets/0172c551-5d7d-4141-9a65-0348f393769b)

- **Описание**:  
  Предоставляет инструменты для выполнения аналитических вычислений и обработки данных.
  ## Log Analytics: Data Overage per Node
- **Описание**:  
  Учет данных, превышающих установленный лимит.  
  
- **Детали использования**:  
  - **Service Sub-Type**: Per Node - превышение лимитов данных для узлов.
  -  **Service Usage-Type**: Node Data Overage - превышение лимитов данных для узлов.
  - **Meter Name**: Data Overage per Node - избыточные данные.  
  - **Consumed Service**: microsoft.operationalinsights
![image](https://github.com/user-attachments/assets/8d28ac50-8005-46e9-8ebd-bd4668f14c7e)

## Log Analytics: Data Included per Node
- **Описание**:  
  Учет данных, превышающих установленный лимит.  
  
- **Детали использования**:  
  - **Service Sub-Type**: Per Node - превышение лимитов данных для узлов.  
  - **Meter Name**: Data Included per Node.  
  - **Consumed Service**: microsoft.operationalinsights

    
# Compute: Azure Functions, Virtual Machines
**Описание**:  
  Предоставляет инструменты для выполнения для выполнения различных типов рабочих нагрузок.
  
![image](https://github.com/user-attachments/assets/1951dad9-dc40-4210-a9e4-a714947dfec3)
- **Детали использования**: 
Meter Category: Functions относится к серверлес-вычислениям, грубо говоря, которые выполняют код без необходимости управлять инфраструктурой. Azure Functions автоматически масштабируется и выставляет счета только за фактическое время выполнения функций.

Meter Category: VM охватывает виртуальные машины, которые предоставляют полный контроль над операционной системой и вычислительными ресурсами.

### Functions Execution
- **Описание**:  
  Исполняемые функции общего назначения для выполнения операций в облаке.  
  
- **Детали использования**:  
  - **Service Sub-Type**: General Purpose - использование функций общего назначения.  
  - **Meter Name**: Functions Execution - выполнение функций.  
  - **Consumed Service**: Microsoft.Web  

### Functions Duration
- **Описание**:  
  Измерение времени выполнения функций в облаке.  
  
- **Детали использования**:  
  - **Service Sub-Type**: General Purpose - измерение времени выполнения функций.  
  - **Meter Name**: Functions Duration - длительность выполнения.  
  - **Consumed Service**: Microsoft.Web
  - 

# Cloud Services: Logic Apps, Mobile Services, Key Vault, Azure Site Recovery и т.д.
![image](https://github.com/user-attachments/assets/3c54c203-906a-4465-9867-ab044207b4dc)

- **Описание**:
Cloud Services представляют собой набор сервисов, предоставляющих масштабируемую инфраструктуру и платформенные возможности для создания, развертывания и управления приложениями, мультимедиа и т.д.

## К примеру, Media Services (Microsoft.Media)
  **Для чего?**:
Служба Azure Media Services предоставляет инструменты для обработки, хранения, потоковой передачи и распространения мультимедийного контента, такого как видео и аудио.

# AI & ML: ML Service, ML API Services, Cognitive Services
![image](https://github.com/user-attachments/assets/0aeeb2d3-5c44-49c8-974c-59a8f4380728)
- **Описание**:
Представляют собой инструменты для реализации задач, связанных с ИИ. Они обеспечивают разработку, обучение, управление и развертывание моделей ИИ, а также дают доступ к готовым API для обработки текста, изображений, речи и других данных.

## Например, ML Studio
- **Описание**:  
  Управление развертыванием и обслуживанием моделей машинного обучения.  
- **Детали использования**:  
 • Пример из таблицы:
 ◦ **Meter Name**:  Standard Workspace Fee
- **Consumed Service**: Microsoft.MachineLearning  
 • Использование:
 ◦Визуальная разработка и настройка моделей, хранение данных для обучения и т.д. 

# Networking: VPN Gateaway, Data Transfer Out, Endpoint Management, Domain Management и 
![image](https://github.com/user-attachments/assets/cb812d97-e738-486a-9788-24769c839e4b)

## VPN Gateway
 • Описание:
Сервис для создания защищенных VPN-соединений между локальной сетью и Azure либо между разными регионами Azure.

- **Gateway**:  
  - **Описание**: Подключение через VPN.  
  - **Consumed Service**: Microsoft.Network  

## Traffic Manager
- **Azure Endpoint**:  
  - **Описание**: Управление конечными точками.  
  - **Consumed Service**: Microsoft.Network  

- **Azure Firewall**:  
  - **Описание**: Сервис для обеспечения безопасности сети, позволяющий контролировать входящий и исходящий трафик через правила безопасности..  
 • Используемые метрики:
 ◦ Deployment: Учет количества развертываний Azure Firewall.
 ◦ Data Processed: Учет объема данных, обработанных через Azure Firewall.
