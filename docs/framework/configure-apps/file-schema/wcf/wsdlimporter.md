---
title: <wsdlImporter>
ms.date: 03/30/2017
ms.assetid: 986b2165-8430-4dba-b1b8-00396841bb96
ms.openlocfilehash: 317921a66fa3b8d1f0026d676ea674b67732b3df
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/06/2020
ms.locfileid: "70854754"
---
# \<wsdlImporter>
<span data-ttu-id="681e3-101">Задает все средства импорта WSDL, импортирующие метаданные на языке WSDL 1.1 с вложениями WS-Policy.</span><span class="sxs-lookup"><span data-stu-id="681e3-101">Specifies all the WSDL importers that imports Web Services Description Language (WSDL) 1.1 metadata with WS-Policy attachments.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<client>**](client.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<metadata>**](metadata.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<wsdlImporters>**](wsdlimporters.md)  
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<wsdlImporter>**  
  
## <a name="syntax"></a><span data-ttu-id="681e3-102">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="681e3-102">Syntax</span></span>  
  
```xml  
<metadata>
  <wsdlImporters>
    <wsdlImporter type="string" />
  </wsdlImporters>
</metadata>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="681e3-103">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="681e3-103">Attributes and Elements</span></span>  
 <span data-ttu-id="681e3-104">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="681e3-104">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="681e3-105">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="681e3-105">Attributes</span></span>  
  
|<span data-ttu-id="681e3-106">Атрибут</span><span class="sxs-lookup"><span data-stu-id="681e3-106">Attribute</span></span>|<span data-ttu-id="681e3-107">Описание:</span><span class="sxs-lookup"><span data-stu-id="681e3-107">Description</span></span>|  
|---------------|-----------------|  
|`type`|<span data-ttu-id="681e3-108">Тип этого элемента.</span><span class="sxs-lookup"><span data-stu-id="681e3-108">The type of this element.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="681e3-109">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="681e3-109">Child Elements</span></span>  
 <span data-ttu-id="681e3-110">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="681e3-110">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="681e3-111">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="681e3-111">Parent Elements</span></span>  
  
|<span data-ttu-id="681e3-112">Элемент</span><span class="sxs-lookup"><span data-stu-id="681e3-112">Element</span></span>|<span data-ttu-id="681e3-113">Описание</span><span class="sxs-lookup"><span data-stu-id="681e3-113">Description</span></span>|  
|-------------|-----------------|  
|[\<wsdlImporters>](wsdlimporters.md)|<span data-ttu-id="681e3-114">Задает все средства импорта WSDL, импортирующие метаданные на языке WSDL 1.1 с вложениями WS-Policy.</span><span class="sxs-lookup"><span data-stu-id="681e3-114">Specifies all the WSDL importers that imports Web Services Description Language (WSDL) 1.1 metadata with WS-Policy attachments.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="681e3-115">Примечания</span><span class="sxs-lookup"><span data-stu-id="681e3-115">Remarks</span></span>  
 <span data-ttu-id="681e3-116">Средство импорта WSDL используется для импорта метаданных, а также для их преобразования в различные классы, представляющие данные контракта и конечной точки.</span><span class="sxs-lookup"><span data-stu-id="681e3-116">A WSDL importer is used to import metadata as well as convert that information into various classes that represent contract and endpoint information.</span></span> <span data-ttu-id="681e3-117">Он может выборочно импортировать сведения контракта и конечной точки, а также свойства, предоставляющие сведения об ошибках и принимающие сведения о типах, относящиеся к процессу импорта и преобразования.</span><span class="sxs-lookup"><span data-stu-id="681e3-117">It can selectively import contract and endpoint information and properties that expose any import errors and accept type information relevant to the import and conversion process.</span></span> <span data-ttu-id="681e3-118">Оно также поддерживает импорт данных привязки и свойств, предоставляющих доступ к каким-либо документам политики, документам WSDL, расширениям WSDL и документам схемы XML.</span><span class="sxs-lookup"><span data-stu-id="681e3-118">It also supports importing binding information and properties that provide access to any policy documents, WSDL documents, WSDL extensions, and XML schema documents.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="681e3-119">См. также</span><span class="sxs-lookup"><span data-stu-id="681e3-119">See also</span></span>

- <xref:System.ServiceModel.Configuration.WsdlImporterElement>
- <xref:System.ServiceModel.Configuration.MetadataElement>
- <xref:System.ServiceModel.Configuration.WsdlImporterElementCollection>
- <xref:System.ServiceModel.Description.MetadataImporter>
- <xref:System.ServiceModel.Description.WsdlImporter>
- [<span data-ttu-id="681e3-120">Конфигурация клиента WCF</span><span class="sxs-lookup"><span data-stu-id="681e3-120">WCF Client Configuration</span></span>](../../../wcf/feature-details/client-configuration.md)
- [<span data-ttu-id="681e3-121">Клиенты</span><span class="sxs-lookup"><span data-stu-id="681e3-121">Clients</span></span>](../../../wcf/feature-details/clients.md)
