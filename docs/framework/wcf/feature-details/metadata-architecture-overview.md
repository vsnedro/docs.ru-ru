---
description: 'Подробнее: Общие сведения об архитектуре метаданных'
title: Общие сведения об архитектуре метаданных
ms.date: 03/30/2017
helpviewer_keywords:
- metadata [WCF], overview
ms.assetid: 1d37645e-086d-4d68-a358-f3c5b6e8205e
ms.openlocfilehash: 63e513c340ea37914da5942ac2479af4be6b8519
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2021
ms.locfileid: "99733935"
---
# <a name="metadata-architecture-overview"></a>Общие сведения об архитектуре метаданных

Windows Communication Foundation (WCF) предоставляет обширную инфраструктуру для экспорта, публикации, извлечения и импорта метаданных службы. Службы WCF используют метаданные, чтобы описать, как взаимодействовать с конечными точками службы, чтобы средства, такие как Svcutil.exe, могли автоматически создавать код клиента для доступа к службе.  
  
 Большинство типов, составляющих инфраструктуру метаданных WCF, находятся в <xref:System.ServiceModel.Description> пространстве имен.  
  
 WCF использует <xref:System.ServiceModel.Description.ServiceEndpoint> класс для описания конечных точек в службе. Вы можете использовать WCF для создания метаданных для конечных точек службы или импорта метаданных службы для создания <xref:System.ServiceModel.Description.ServiceEndpoint> экземпляров.  
  
 WCF представляет метаданные для службы как экземпляр <xref:System.ServiceModel.Description.MetadataSet> типа, структура которой строго привязана к формату сериализации метаданных, определенному в WS-MetadataExchange. Тип <xref:System.ServiceModel.Description.MetadataSet> объединяет фактические метаданные службы, например документы на языке WSDL, документы схемы XML или выражения WS-Policy, в коллекцию экземпляров <xref:System.ServiceModel.Description.MetadataSection>. Каждый экземпляр <xref:System.ServiceModel.Description.MetadataSection?displayProperty=nameWithType> содержит собственный идентификатор и диалект метаданных. Свойство <xref:System.ServiceModel.Description.MetadataSection?displayProperty=nameWithType> объекта <xref:System.ServiceModel.Description.MetadataSection.Metadata%2A?displayProperty=nameWithType> может содержать следующие элементы.  
  
- Необработанные метаданные.  
  
- Экземпляр <xref:System.ServiceModel.Description.MetadataReference>.  
  
- Экземпляр <xref:System.ServiceModel.Description.MetadataLocation>.  
  
 Экземпляры <xref:System.ServiceModel.Description.MetadataReference?displayProperty=nameWithType> указывают на другую конечную точку обмена метаданными (MEX), а экземпляры <xref:System.ServiceModel.Description.MetadataLocation?displayProperty=nameWithType> указывают на документ метаданных, используя URL-адрес HTTP. WCF поддерживает использование документов WSDL для описания конечных точек служб, контрактов служб, привязок, шаблонов обмена сообщениями, сообщений и сообщений об ошибках, реализованных службой. Используемые службой типы данных описываются в документах WSDL с помощью схемы XML. Дополнительные сведения см. в разделе [Импорт и экспорт схемы](schema-import-and-export.md). WCF можно использовать для экспорта и импорта расширений WSDL для поведения службы, поведения контрактов и элементов привязки, расширяющих функциональные возможности службы. Дополнительные сведения см. в разделе [Экспорт пользовательских метаданных для расширения WCF](../extending/exporting-custom-metadata-for-a-wcf-extension.md).  
  
## <a name="exporting-service-metadata"></a>Экспорт метаданных службы  

 В WCF *Экспорт метаданных* — это процесс описания конечных точек службы и их проецирование в параллельное стандартизованное представление, которое клиенты могут использовать, чтобы понять, как использовать службу. Для экспорта метаданных из экземпляров <xref:System.ServiceModel.Description.ServiceEndpoint> используется реализация абстрактного класса <xref:System.ServiceModel.Description.MetadataExporter>. Реализация <xref:System.ServiceModel.Description.MetadataExporter?displayProperty=nameWithType> создает метаданные, которые инкапсулируются в экземпляр <xref:System.ServiceModel.Description.MetadataSet>.  
  
 Класс <xref:System.ServiceModel.Description.MetadataExporter?displayProperty=nameWithType> предоставляет платформу для создания выражений политики, которые описывают возможности и требования привязки конечной точки, а также связанные с ней операции, сообщения и ошибки. Эти выражения политики попадают в экземпляр <xref:System.ServiceModel.Description.PolicyConversionContext>. Реализация <xref:System.ServiceModel.Description.MetadataExporter?displayProperty=nameWithType> может затем прикрепить эти выражения политики к создаваемым ею метаданным.  
  
 <xref:System.ServiceModel.Description.MetadataExporter?displayProperty=nameWithType> делает вызовы в каждый элемент <xref:System.ServiceModel.Channels.BindingElement?displayProperty=nameWithType>, который реализует интерфейс <xref:System.ServiceModel.Description.IPolicyExportExtension> в привязке для <xref:System.ServiceModel.Description.ServiceEndpoint>, при создании объекта <xref:System.ServiceModel.Description.PolicyConversionContext> для используемой реализации <xref:System.ServiceModel.Description.MetadataExporter?displayProperty=nameWithType>. Можно экспортировать утверждения новой политики, реализовав интерфейс <xref:System.ServiceModel.Description.IPolicyExportExtension> в пользовательских реализациях типа <xref:System.ServiceModel.Channels.BindingElement>.  
  
 <xref:System.ServiceModel.Description.WsdlExporter>Тип является реализацией <xref:System.ServiceModel.Description.MetadataExporter?displayProperty=nameWithType> абстрактного класса, входящего в состав WCF. Тип <xref:System.ServiceModel.Description.WsdlExporter> создает метаданные WSDL с прикрепленными выражениями политики.  
  
 Чтобы экспортировать пользовательские метаданные языка WSDL или расширения языка WSDL для поведений конечной точки, поведений контракта или элементов привязки конечной точки службы, можно реализовать интерфейс <xref:System.ServiceModel.Description.IWsdlExportExtension>. При создании документа WSDL объект <xref:System.ServiceModel.Description.WsdlExporter> ищет в экземпляре <xref:System.ServiceModel.Description.ServiceEndpoint> элементы привязки, поведения операций, поведения контрактов и поведения конечных точек, которые реализуют интерфейс <xref:System.ServiceModel.Description.IWsdlExportExtension>.  
  
## <a name="publishing-service-metadata"></a>Публикация метаданных службы  

 Службы WCF публикуют метаданные, предоставляя одну или несколько конечных точек метаданных. Публикация метаданных службы делает метаданные службы доступными через стандартизованные протоколы, например MEX и запросы HTTP/GET. Конечные точки метаданных похожи на другие конечные точки служб в том смысле, что у них есть адрес, привязка и контракт. Конечные точки метаданных можно добавлять к узлу службы с помощью файла конфигурации или кода.  
  
 Чтобы опубликовать конечные точки метаданных для службы WCF, необходимо сначала добавить экземпляр <xref:System.ServiceModel.Description.ServiceMetadataBehavior> поведения службы в службу. Добавление в службу экземпляра <xref:System.ServiceModel.Description.ServiceMetadataBehavior?displayProperty=nameWithType> расширяет службу, позволяя ей публиковать метаданные через одну или несколько конечных точек метаданных. После добавления поведения службы <xref:System.ServiceModel.Description.ServiceMetadataBehavior?displayProperty=nameWithType> можно публиковать конечные точки метаданных, поддерживающие протокол MEX, или конечные точки метаданных, отвечающие на запросы HTTP/GET.  
  
 Чтобы добавить конечные точки метаданных, использующие протокол MEX, добавьте конечные точки службы для узла службы, которые используют контракт службы с именем IMetadataExchange. WCF <xref:System.ServiceModel.Description.IMetadataExchange> , определяет интерфейс с этим именем контракта службы. WS-MetadataExchange конечные точки или точки обмена метаданными могут использовать одну из четырех привязок по умолчанию, предоставляемых статическими методами фабрики в <xref:System.ServiceModel.Description.MetadataExchangeBindings> классе, чтобы соответствовать привязкам по умолчанию, используемым средствами WCF, например Svcutil.exe. Настраивать конечные точки метаданных MEX также можно с помощью пользовательской привязки.  
  
 <xref:System.ServiceModel.Description.ServiceMetadataBehavior> использует <xref:System.ServiceModel.Description.WsdlExporter?displayProperty=nameWithType> для экспорта метаданных для всех конечных точек службы. Дополнительные сведения об экспорте метаданных из службы см. в разделе [Экспорт и импорт метаданных](exporting-and-importing-metadata.md).  
  
 Класс <xref:System.ServiceModel.Description.ServiceMetadataBehavior> расширяет узел службы, добавляя экземпляр <xref:System.ServiceModel.Description.ServiceMetadataExtension> в качестве расширения узла службы. Расширение <xref:System.ServiceModel.Description.ServiceMetadataExtension?displayProperty=nameWithType> обеспечивает реализацию протоколов публикации метаданных. Расширение <xref:System.ServiceModel.Description.ServiceMetadataExtension?displayProperty=nameWithType> также можно использовать для получения метаданных службы во время выполнения, обратившись к свойству <xref:System.ServiceModel.Description.ServiceMetadataExtension.Metadata%2A>.  
  
> [!CAUTION]
> Если добавить конечную точку MEX в файл конфигурации приложения, а затем добавить <xref:System.ServiceModel.Description.ServiceMetadataBehavior> в узел службы в коде, будет вызвано следующее исключение.  
>
> System.InvalidOperationException: не удалось найти имя контракта IMetadataExchange в списке контрактов, реализованных в службе Service1. Добавьте ServiceMetadataBehavior в файл конфигурации или непосредственно в ServiceHost, чтобы обеспечить поддержку этого контракта.  
>
> В качестве решения этой проблемы можно добавить <xref:System.ServiceModel.Description.ServiceMetadataBehavior> в файл конфигурации или добавить в код конечную точку и <xref:System.ServiceModel.Description.ServiceMetadataBehavior>.  
>
> Пример добавления <xref:System.ServiceModel.Description.ServiceMetadataBehavior> в файл конфигурации приложения см. в [Начало работы](../samples/getting-started-sample.md). Пример добавления <xref:System.ServiceModel.Description.ServiceMetadataBehavior> в код см. в разделе пример с [самостоятельным размещением](../samples/self-host.md) .  

> [!CAUTION]
> Если опубликовать метаданные для службы, которая представляет доступ к двум различным контрактам службы, которые содержат операции с одинаковыми именами, вызывается исключение. Например, если служба предоставляет доступ к контракту службы с именем ICarService, который содержит операцию Get(Car c), и эта же служба предоставляет доступ к контракту службы с именем IBookService, который содержит операцию Get(Book b), то при создании метаданных службы вызывается исключение или выводится сообщение об ошибке. Чтобы устранить эту проблему, выполните одно из следующих действий.  
>
> - Переименуйте одну из операций.
> - Задайте другое имя в свойстве <xref:System.ServiceModel.OperationContractAttribute.Name%2A>.  
> - Установите другое пространство имен для одной из операций с помощью свойства <xref:System.ServiceModel.ServiceContractAttribute.Namespace%2A>.  
  
## <a name="retrieving-service-metadata"></a>Извлечение метаданных службы  

 WCF может получать метаданные службы с помощью стандартизированных протоколов, таких как WS-MetadataExchange и HTTP. Оба эти протокола поддерживаются типом <xref:System.ServiceModel.Description.MetadataExchangeClient>. Чтобы извлечь метаданные службы с помощью типа <xref:System.ServiceModel.Description.MetadataExchangeClient?displayProperty=nameWithType>, необходимо указать адрес и необязательную привязку. В роли привязки, используемой экземпляром <xref:System.ServiceModel.Description.MetadataExchangeClient?displayProperty=nameWithType>, может выступать одна из привязок по умолчанию статического класса <xref:System.ServiceModel.Description.MetadataExchangeBindings>, предоставляемая пользователем привязка или привязка, загруженная из конфигурации конечной точки для контракта `IMetadataExchange`. Кроме того, тип <xref:System.ServiceModel.Description.MetadataExchangeClient?displayProperty=nameWithType> может выполнять разрешение URL-адресов ссылок HTTP на метаданные с помощью типа <xref:System.Net.HttpWebRequest>.  
  
 По умолчанию экземпляр <xref:System.ServiceModel.Description.MetadataExchangeClient?displayProperty=nameWithType> связан с одним экземпляром <xref:System.ServiceModel.Channels.ChannelFactoryBase>. Можно изменить или заменить экземпляр <xref:System.ServiceModel.Channels.ChannelFactoryBase>, используемый экземпляром <xref:System.ServiceModel.Description.MetadataExchangeClient?displayProperty=nameWithType>, переопределив виртуальный метод <xref:System.ServiceModel.Description.MetadataExchangeClient.GetChannelFactory%2A>. Аналогично можно изменить или заменить экземпляр <xref:System.Net.HttpWebRequest?displayProperty=nameWithType>, используемый экземпляром <xref:System.ServiceModel.Description.MetadataExchangeClient?displayProperty=nameWithType> для создания запросов HTTP/GET, переопределив виртуальный метод <xref:System.ServiceModel.Description.MetadataExchangeClient.GetWebRequest%2A?displayProperty=nameWithType>.  
  
 Метаданные службы можно получить с помощью WS-MetadataExchange или HTTP/GET, используя средство Svcutil.exe и передав параметр **/target: Metadata** и адрес. Средство Svcutil.exe загружает метаданные, расположенные по указанному адресу, и сохраняет файлы на диске. Средство Svcutil.exe использует внутри себя экземпляр <xref:System.ServiceModel.Description.MetadataExchangeClient?displayProperty=nameWithType> и загружает из файла конфигурации приложения конфигурацию конечной точки MEX, имя которой соответствует схеме адреса, переданного средству Svcutil.exe, если такая конечная точка существует. В противном случае средство Svcutil.exe по умолчанию использует одну из привязок, определенных в статическом типе производства <xref:System.ServiceModel.Description.MetadataExchangeBindings>.  
  
## <a name="importing-service-metadata"></a>Импорт метаданных службы  

 В WCF импорт метаданных — это процесс создания абстрактного представления службы или ее компонентов из метаданных. Например, WCF может импортировать <xref:System.ServiceModel.Description.ServiceEndpoint> экземпляры, <xref:System.ServiceModel.Channels.Binding> экземпляры или <xref:System.ServiceModel.Description.ContractDescription> экземпляры из документа WSDL для службы. Чтобы импортировать метаданные службы в WCF, используйте реализацию <xref:System.ServiceModel.Description.MetadataImporter> абстрактного класса. Типы, производные от <xref:System.ServiceModel.Description.MetadataImporter?displayProperty=nameWithType> класса, реализуют поддержку импорта форматов метаданных, которые используют преимущества логики импорта WS-Policy в WCF.  
  
 Реализация <xref:System.ServiceModel.Description.MetadataImporter?displayProperty=nameWithType> собирает выражения политики, прикрепленные к метаданным службы в объекте <xref:System.ServiceModel.Description.PolicyConversionContext>. Затем <xref:System.ServiceModel.Description.MetadataImporter?displayProperty=nameWithType> обрабатывает политики как часть импорта метаданных путем вызова реализаций интерфейса <xref:System.ServiceModel.Description.IPolicyImportExtension> в свойстве <xref:System.ServiceModel.Description.MetadataImporter.PolicyImportExtensions%2A>.  
  
 Можно добавить поддержку для импорта новых утверждений политики в <xref:System.ServiceModel.Description.MetadataImporter?displayProperty=nameWithType> путем добавления собственной реализации интерфейса <xref:System.ServiceModel.Description.IPolicyImportExtension> в коллекцию <xref:System.ServiceModel.Description.MetadataImporter.PolicyImportExtensions%2A> в экземпляре <xref:System.ServiceModel.Description.MetadataImporter?displayProperty=nameWithType>. В качестве альтернативы можно зарегистрировать расширение импорта политики в файле конфигурации клиентского приложения.  
  
 <xref:System.ServiceModel.Description.WsdlImporter?displayProperty=nameWithType>Тип является реализацией <xref:System.ServiceModel.Description.MetadataImporter?displayProperty=nameWithType> абстрактного класса, входящего в состав WCF. Тип <xref:System.ServiceModel.Description.WsdlImporter?displayProperty=nameWithType> импортирует метаданные языка WSDL с прикрепленными политиками, объединенными в объекте <xref:System.ServiceModel.Description.MetadataSet>.  
  
 Можно добавить поддержку для импорта расширений языка WSDL путем реализации интерфейса <xref:System.ServiceModel.Description.IWsdlImportExtension> и добавления реализации в свойство <xref:System.ServiceModel.Description.WsdlImporter.WsdlImportExtensions%2A> в экземпляре <xref:System.ServiceModel.Description.WsdlImporter?displayProperty=nameWithType>. Кроме того, <xref:System.ServiceModel.Description.WsdlImporter?displayProperty=nameWithType> может загружать реализации интерфейса <xref:System.ServiceModel.Description.IWsdlImportExtension?displayProperty=nameWithType>, зарегистрированного в файле конфигурации клиентского приложения.  
  
## <a name="dynamic-bindings"></a>Динамические привязки  

 Можно динамически обновлять привязку, используемую для создания канала к конечной точке службы, если привязка к конечной точке изменяется, или если необходимо создать канал к конечной точке, которая использует тот же контракт, но имеет другую привязку. С помощью статического класса <xref:System.ServiceModel.Description.MetadataResolver> можно во время выполнения извлекать и импортировать метаданные для конечных точек службы, реализующих заданный контракт. После этого импортированные объекты <xref:System.ServiceModel.Description.ServiceEndpoint?displayProperty=nameWithType> можно использовать для создания клиента или производства каналов для выбранной конечной точки.  
  
## <a name="see-also"></a>См. также

- <xref:System.ServiceModel.Description>
- [Форматы метаданных](metadata-formats.md)
- [Экспорт и импорт метаданных](exporting-and-importing-metadata.md)
- [Публикация метаданных](publishing-metadata.md)
- [Извлечение метаданных](retrieving-metadata.md)
- [Использование метаданных](using-metadata.md)
- [Вопросы безопасности при использовании метаданных](security-considerations-with-metadata.md)
- [Расширение системы метаданных](../extending/extending-the-metadata-system.md)
