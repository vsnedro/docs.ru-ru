---
title: Создание библиотеки клиентов службы данных (службы данных WCF)
ms.date: 03/30/2017
helpviewer_keywords:
- client applications, WCF Data Services
- WCF Data Services, client library
- Add Service Reference dialog box
ms.assetid: 314077c1-ac10-47e1-bed4-940b5462359d
ms.openlocfilehash: a6a388f837d00d63a39212843c3fa88b28482b26
ms.sourcegitcommit: 27a15a55019f6b5f2733961738babe94aec0def3
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/15/2020
ms.locfileid: "90545811"
---
# <a name="generating-the-data-service-client-library-wcf-data-services"></a><span data-ttu-id="d4a76-102">Создание библиотеки клиентов службы данных (службы данных WCF)</span><span class="sxs-lookup"><span data-stu-id="d4a76-102">Generating the Data Service Client Library (WCF Data Services)</span></span>
<span data-ttu-id="d4a76-103">Служба данных, которая реализует Open Data Protocol (OData), может возвращать документ метаданных службы, описывающий модель данных, предоставляемую веб-каналом OData.</span><span class="sxs-lookup"><span data-stu-id="d4a76-103">A data service that implements the Open Data Protocol (OData) can return a service metadata document that describes the data model exposed by the OData feed.</span></span> <span data-ttu-id="d4a76-104">Дополнительные сведения см. в разделе "документ метаданных службы" статьи [OData: Overview](https://www.odata.org/documentation/odata-version-2-0/overview/) .</span><span class="sxs-lookup"><span data-stu-id="d4a76-104">For more information, see the Service Metadata Document section in the [OData: Overview](https://www.odata.org/documentation/odata-version-2-0/overview/) article.</span></span> <span data-ttu-id="d4a76-105">Можно использовать диалоговое окно **Добавление ссылки на службу** в Visual Studio, чтобы добавить ссылку на службу на основе OData.</span><span class="sxs-lookup"><span data-stu-id="d4a76-105">You can use the **Add Service Reference** dialog in Visual Studio to add a reference to an OData-based service.</span></span> <span data-ttu-id="d4a76-106">При использовании этого средства для добавления ссылки на метаданные, возвращенные веб-каналом OData в клиентском проекте, выполняются следующие действия.</span><span class="sxs-lookup"><span data-stu-id="d4a76-106">When you use this tool to add a reference to the metadata returned by an OData feed in a client project, it performs the following actions:</span></span>  
  
- <span data-ttu-id="d4a76-107">Запрашивает документ с метаданными службы из службы данных и интерпретирует возвращенные метаданные.</span><span class="sxs-lookup"><span data-stu-id="d4a76-107">Requests the service metadata document from the data service and interprets the returned metadata.</span></span>  
  
    > [!NOTE]
    > <span data-ttu-id="d4a76-108">Возвращенные метаданные сохраняются в клиентском проекте в виде файла EDMX.</span><span class="sxs-lookup"><span data-stu-id="d4a76-108">The returned metadata is stored in the client project as an .edmx file.</span></span> <span data-ttu-id="d4a76-109">Файл EDMX нельзя открыть с помощью конструктора моделей EDM, поскольку его формат отличается от формата файла EDMX, используемого платформой Entity Framework.</span><span class="sxs-lookup"><span data-stu-id="d4a76-109">This .edmx file cannot be opened by using the Entity Data Model designer because it does not have the same format an .edmx file used by the Entity Framework.</span></span> <span data-ttu-id="d4a76-110">Открыть этот файл метаданных можно с помощью редактора XML или любого текстового редактора.</span><span class="sxs-lookup"><span data-stu-id="d4a76-110">You can view this metadata file by using the XML editor or any text editor.</span></span> <span data-ttu-id="d4a76-111">Дополнительные сведения см. в разделе [ \[ MC-EDMX \] : EDM для формата упаковки служб данных](/openspecs/windows_protocols/mc-edmx/5dff5e25-56a1-408b-9d44-bff6634c7d16).</span><span class="sxs-lookup"><span data-stu-id="d4a76-111">For more information, see [\[MC-EDMX\]: Entity Data Model for Data Services Packaging Format](/openspecs/windows_protocols/mc-edmx/5dff5e25-56a1-408b-9d44-bff6634c7d16).</span></span>
  
- <span data-ttu-id="d4a76-112">Формирует представление службы в виде класса контейнера сущностей, порожденного от класса <xref:System.Data.Services.Client.DataServiceContext>.</span><span class="sxs-lookup"><span data-stu-id="d4a76-112">Generates a representation of the service as an entity container class that inherits from <xref:System.Data.Services.Client.DataServiceContext>.</span></span> <span data-ttu-id="d4a76-113">Этот сформированный класс контейнера сущностей аналогичен контейнеру сущностей, формируемому программами для работы с моделью EDM.</span><span class="sxs-lookup"><span data-stu-id="d4a76-113">This generated entity container class resembles the entity container that the Entity Data Model tools generate.</span></span> <span data-ttu-id="d4a76-114">Дополнительные сведения см. в разделе [Обзор служб объектов (Entity Framework)](/previous-versions/bb386871(v=vs.100)).</span><span class="sxs-lookup"><span data-stu-id="d4a76-114">For more information, see [Object Services Overview (Entity Framework)](/previous-versions/bb386871(v=vs.100)).</span></span>  
  
- <span data-ttu-id="d4a76-115">Формирует классы данных типов модели данных, обнаруженных в метаданных службы.</span><span class="sxs-lookup"><span data-stu-id="d4a76-115">Generates data classes for the data model types that it discovers in the service metadata.</span></span>  
  
- <span data-ttu-id="d4a76-116">Добавляет в проект ссылку на сборку `System.Data.Services.Client`.</span><span class="sxs-lookup"><span data-stu-id="d4a76-116">Adds a reference to the `System.Data.Services.Client` assembly to the project.</span></span>  
  
 <span data-ttu-id="d4a76-117">Дополнительные сведения см. [в разделе инструкции. Добавление ссылки на службу данных](how-to-add-a-data-service-reference-wcf-data-services.md).</span><span class="sxs-lookup"><span data-stu-id="d4a76-117">For more information, see [How to: Add a Data Service Reference](how-to-add-a-data-service-reference-wcf-data-services.md).</span></span>  
  
 <span data-ttu-id="d4a76-118">Классы службы данных клиента также можно создать с помощью средства [DataSvcUtil.exe](wcf-data-service-client-utility-datasvcutil-exe.md) из командной строки.</span><span class="sxs-lookup"><span data-stu-id="d4a76-118">The client data service classes can also be generated by using the [DataSvcUtil.exe](wcf-data-service-client-utility-datasvcutil-exe.md) tool at the command prompt.</span></span> <span data-ttu-id="d4a76-119">Дополнительные сведения см. [в разделе как вручную создавать классы службы данных клиента](how-to-manually-generate-client-data-service-classes-wcf-data-services.md).</span><span class="sxs-lookup"><span data-stu-id="d4a76-119">For more information, see [How to: Manually Generate Client Data Service Classes](how-to-manually-generate-client-data-service-classes-wcf-data-services.md).</span></span>  
  
## <a name="client-data-type-mapping"></a><span data-ttu-id="d4a76-120">Сопоставление клиентских типов данных</span><span class="sxs-lookup"><span data-stu-id="d4a76-120">Client Data Type Mapping</span></span>  
 <span data-ttu-id="d4a76-121">При использовании диалогового окна **Добавление ссылки на службу** в Visual Studio или `DataSvcUtil.exe` средства для создания клиентских классов данных, основанных на канале OData, типы данных .NET Framework сопоставляются с типами-примитивами из модели данных следующим образом:</span><span class="sxs-lookup"><span data-stu-id="d4a76-121">When you use the **Add Service Reference** dialog in Visual Studio or the `DataSvcUtil.exe` tool to generate client data classes that are based on an OData feed, the .NET Framework data types are mapped to the primitive types from the data model as follows:</span></span>  
  
|<span data-ttu-id="d4a76-122">Тип модели данных</span><span class="sxs-lookup"><span data-stu-id="d4a76-122">Data model type</span></span>|<span data-ttu-id="d4a76-123">Тип данных платформы .NET</span><span class="sxs-lookup"><span data-stu-id="d4a76-123">.NET Framework data type</span></span>|  
|---------------------|------------------------------|  
|`Edm.Binary`|<span data-ttu-id="d4a76-124"><xref:System.Byte> `[]`</span><span class="sxs-lookup"><span data-stu-id="d4a76-124"><xref:System.Byte> `[]`</span></span>|  
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
  
 <span data-ttu-id="d4a76-125">Дополнительные сведения см. в разделе примитивные типы данных статьи [OData: Overview](https://www.odata.org/documentation/odata-version-2-0/overview/) .</span><span class="sxs-lookup"><span data-stu-id="d4a76-125">For more information, see the Primitive Data Types section in the [OData: Overview](https://www.odata.org/documentation/odata-version-2-0/overview/) article.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="d4a76-126">См. также</span><span class="sxs-lookup"><span data-stu-id="d4a76-126">See also</span></span>

- [<span data-ttu-id="d4a76-127">Библиотека клиентов служб данных WCF</span><span class="sxs-lookup"><span data-stu-id="d4a76-127">WCF Data Services Client Library</span></span>](wcf-data-services-client-library.md)
- [<span data-ttu-id="d4a76-128">Краткое руководство</span><span class="sxs-lookup"><span data-stu-id="d4a76-128">Quickstart</span></span>](quickstart-wcf-data-services.md)
