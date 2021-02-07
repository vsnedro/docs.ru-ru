---
description: 'Дополнительные сведения: создание клиентской библиотеки службы данных (службы данных WCF)'
title: Создание библиотеки клиентов службы данных (службы данных WCF)
ms.date: 03/30/2017
helpviewer_keywords:
- client applications, WCF Data Services
- WCF Data Services, client library
- Add Service Reference dialog box
ms.assetid: 314077c1-ac10-47e1-bed4-940b5462359d
ms.openlocfilehash: 3bac2459044ff910c8085ff56e60d9da6e0ba877
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2021
ms.locfileid: "99765936"
---
# <a name="generating-the-data-service-client-library-wcf-data-services"></a>Создание библиотеки клиентов службы данных (службы данных WCF)

[!INCLUDE [wcf-deprecated](~/includes/wcf-deprecated.md)]

Служба данных, которая реализует Open Data Protocol (OData), может возвращать документ метаданных службы, описывающий модель данных, предоставляемую веб-каналом OData. Дополнительные сведения см. в разделе "документ метаданных службы" статьи [OData: Overview](https://www.odata.org/documentation/odata-version-2-0/overview/) . Можно использовать диалоговое окно **Добавление ссылки на службу** в Visual Studio, чтобы добавить ссылку на службу на основе OData. При использовании этого средства для добавления ссылки на метаданные, возвращенные веб-каналом OData в клиентском проекте, выполняются следующие действия.  
  
- Запрашивает документ с метаданными службы из службы данных и интерпретирует возвращенные метаданные.  
  
    > [!NOTE]
    > Возвращенные метаданные сохраняются в клиентском проекте в виде файла EDMX. Файл EDMX нельзя открыть с помощью конструктора моделей EDM, поскольку его формат отличается от формата файла EDMX, используемого платформой Entity Framework. Открыть этот файл метаданных можно с помощью редактора XML или любого текстового редактора. Дополнительные сведения см. в разделе [ \[ MC-EDMX \] : EDM для формата упаковки служб данных](/openspecs/windows_protocols/mc-edmx/5dff5e25-56a1-408b-9d44-bff6634c7d16).
  
- Формирует представление службы в виде класса контейнера сущностей, порожденного от класса <xref:System.Data.Services.Client.DataServiceContext>. Этот сформированный класс контейнера сущностей аналогичен контейнеру сущностей, формируемому программами для работы с моделью EDM. Дополнительные сведения см. в разделе [Обзор служб объектов (Entity Framework)](/previous-versions/bb386871(v=vs.100)).  
  
- Формирует классы данных типов модели данных, обнаруженных в метаданных службы.  
  
- Добавляет в проект ссылку на сборку `System.Data.Services.Client`.  
  
 Дополнительные сведения см. [в разделе инструкции. Добавление ссылки на службу данных](how-to-add-a-data-service-reference-wcf-data-services.md).  
  
 Классы службы данных клиента также можно создать с помощью средства [DataSvcUtil.exe](wcf-data-service-client-utility-datasvcutil-exe.md) из командной строки. Дополнительные сведения см. [в разделе как вручную создавать классы службы данных клиента](how-to-manually-generate-client-data-service-classes-wcf-data-services.md).  
  
## <a name="client-data-type-mapping"></a>Сопоставление клиентских типов данных  

 При использовании диалогового окна **Добавление ссылки на службу** в Visual Studio или `DataSvcUtil.exe` средства для создания клиентских классов данных, основанных на канале OData, типы данных платформа .NET Framework сопоставляются с типами-примитивами из модели данных следующим образом:  
  
|Тип модели данных|Тип данных платформы .NET|  
|---------------------|------------------------------|  
|`Edm.Binary`|<xref:System.Byte> `[]`|  
|`Edm.Boolean`|<xref:System.Boolean>|  
|`Edm.Byte`|<xref:System.Byte>|  
|`Edm.DateTime`|<xref:System.DateTime>|  
|`Edm.Decimal`|<xref:System.Decimal>|  
|`Edm.Double`|<xref:System.Double>|  
|`Edm.Guid`|<xref:System.Guid>|  
|`Edm.Int16`|<xref:System.Int16>|  
|`Edm.Int32`|<xref:System.Int32>|  
|`Edm.Int64`|<xref:System.Int64>|  
|`Edm.SByte`|<xref:System.SByte>|  
|`Edm.Single`|<xref:System.Single>|  
|`Edm.String`|<xref:System.String>|  
  
 Дополнительные сведения см. в разделе примитивные типы данных статьи [OData: Overview](https://www.odata.org/documentation/odata-version-2-0/overview/) .
  
## <a name="see-also"></a>См. также

- [Библиотека клиентов служб данных WCF](wcf-data-services-client-library.md)
- [Краткое руководство](quickstart-wcf-data-services.md)
