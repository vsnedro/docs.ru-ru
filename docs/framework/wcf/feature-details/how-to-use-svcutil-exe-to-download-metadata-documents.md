---
title: Практическое руководство. Использование Svcutil.exe для загрузки документов метаданных
ms.date: 03/30/2017
ms.assetid: 15524274-3167-4627-b722-d6cedb9fa8c6
ms.openlocfilehash: c04b63fa4963a5df0f910da8702643a6484a4edd
ms.sourcegitcommit: cdb295dd1db589ce5169ac9ff096f01fd0c2da9d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/09/2020
ms.locfileid: "84596933"
---
# <a name="how-to-use-svcutilexe-to-download-metadata-documents"></a>Практическое руководство. Использование Svcutil.exe для загрузки документов метаданных
Средство Svcutil.exe позволяет загружать метаданные из выполняющихся служб и сохранять эти метаданные в локальных файлах. Для схем URL-адресов HTTP и HTTPS Svcutil. exe пытается получить метаданные с помощью WS-MetadataExchange и [обнаружения веб-службы XML](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/fxx6cfx2(v=vs.100)). Для всех остальных URL-схем средство Svcutil.exe использует только протокол WS-MetadataExchange.  
  
 По умолчанию средство Svcutil.exe использует привязки, определенные в классе <xref:System.ServiceModel.Description.MetadataExchangeBindings>. Чтобы настроить привязку, используемую для протокола WS-MetadataExchange, необходимо в файле конфигурации Svcutil.exe (svcutil.exe.config) настроить конечную точку клиента, которая бы использовала контракт `IMetadataExchange` и имя которой совпадало бы со схемой универсального кода ресурса (URI) адреса конечной точки метаданных.  
  
> [!CAUTION]
> При запуске программы Svcutil. exe для получения метаданных для службы, которая предоставляет два разных контракта службы, каждая из которых содержит операцию с одним и тем же именем, программа Svcutil. exe выводит сообщение об ошибке "не удается получить метаданные из...." Например, если у вас есть служба, которая предоставляет контракт службы с именем `ICarService` , в котором есть операция `Get(Car c)` и та же служба предоставляет контракт службы с именем `IBookService` , который имеет операцию `Get(Book b)` . Для обхода этой проблемы выполните одно из следующих действий.
>
> - Переименуйте одну из операций.
> - Задайте другое имя в свойстве <xref:System.ServiceModel.OperationContractAttribute.Name%2A>.
> - Установите другое пространство имен для одной из операций с помощью свойства <xref:System.ServiceModel.ServiceContractAttribute.Namespace%2A>.
  
## <a name="to-download-metadata-using-svcutilexe"></a>Загрузка метаданных с помощью средства Svcutil.exe  
  
1. Найдите средство Svcutil.exe в следующей папке:  
  
     C:\Program Files\Microsoft SDKs\Windows\v1.0.\bin  
  
2. Из командной строки запустите средство, используя следующий формат.  
  
    ```console
    svcutil.exe /t:metadata  <url>* | <epr>  
    ```  
  
     Параметр `/t:metadata` необходимо указать, чтобы загружались метаданные. В противном случае будут созданы код и конфигурация клиента.  
  
3. Аргумент <`url`>указывает URL-адрес конечной точки службы, предоставляющей метаданные, или документ метаданных, размещенный в сети. Аргумент <`epr`> указывает путь к XML-файлу, содержащему WS-Addressing `EndpointAddress` для конечной точки службы, которая поддерживает WS-MetadataExchange.  
  
 Дополнительные сведения об использовании этого средства для скачивания метаданных см. в разделе [средство служебной программы метаданных ServiceModel (Svcutil. exe)](../servicemodel-metadata-utility-tool-svcutil-exe.md).  
  
## <a name="example"></a>Пример  
 Следующая команда позволяет загрузить документы с метаданными из выполняющейся службы.  
  
```console
svcutil /t:metadata http://service/metadataEndpoint  
```  
  
## <a name="see-also"></a>Дополнительно

- [Служебное средство ServiceModel Metadata Utility Tool (Svcutil.exe)](../servicemodel-metadata-utility-tool-svcutil-exe.md)
