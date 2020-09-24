---
title: <wsdlImporter>
ms.date: 03/30/2017
ms.assetid: 986b2165-8430-4dba-b1b8-00396841bb96
ms.openlocfilehash: 82704aa40b508f1b1e2237c9768a7b7599c5c87e
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/24/2020
ms.locfileid: "91158595"
---
# \<wsdlImporter>

<span data-ttu-id="258e1-101">Задает все средства импорта WSDL, импортирующие метаданные на языке WSDL 1.1 с вложениями WS-Policy.</span><span class="sxs-lookup"><span data-stu-id="258e1-101">Specifies all the WSDL importers that imports Web Services Description Language (WSDL) 1.1 metadata with WS-Policy attachments.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<client>**](client.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<metadata>**](metadata.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<wsdlImporters>**](wsdlimporters.md)  
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<wsdlImporter>**  
  
## <a name="syntax"></a><span data-ttu-id="258e1-102">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="258e1-102">Syntax</span></span>  
  
```xml  
<metadata>
  <wsdlImporters>
    <wsdlImporter type="string" />
  </wsdlImporters>
</metadata>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="258e1-103">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="258e1-103">Attributes and Elements</span></span>  

 <span data-ttu-id="258e1-104">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="258e1-104">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="258e1-105">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="258e1-105">Attributes</span></span>  
  
|<span data-ttu-id="258e1-106">Атрибут</span><span class="sxs-lookup"><span data-stu-id="258e1-106">Attribute</span></span>|<span data-ttu-id="258e1-107">Описание</span><span class="sxs-lookup"><span data-stu-id="258e1-107">Description</span></span>|  
|---------------|-----------------|  
|`type`|<span data-ttu-id="258e1-108">Тип этого элемента.</span><span class="sxs-lookup"><span data-stu-id="258e1-108">The type of this element.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="258e1-109">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="258e1-109">Child Elements</span></span>  

 <span data-ttu-id="258e1-110">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="258e1-110">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="258e1-111">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="258e1-111">Parent Elements</span></span>  
  
|<span data-ttu-id="258e1-112">Элемент</span><span class="sxs-lookup"><span data-stu-id="258e1-112">Element</span></span>|<span data-ttu-id="258e1-113">Описание</span><span class="sxs-lookup"><span data-stu-id="258e1-113">Description</span></span>|  
|-------------|-----------------|  
|[\<wsdlImporters>](wsdlimporters.md)|<span data-ttu-id="258e1-114">Задает все средства импорта WSDL, импортирующие метаданные на языке WSDL 1.1 с вложениями WS-Policy.</span><span class="sxs-lookup"><span data-stu-id="258e1-114">Specifies all the WSDL importers that imports Web Services Description Language (WSDL) 1.1 metadata with WS-Policy attachments.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="258e1-115">Remarks</span><span class="sxs-lookup"><span data-stu-id="258e1-115">Remarks</span></span>  

 <span data-ttu-id="258e1-116">Средство импорта WSDL используется для импорта метаданных, а также для их преобразования в различные классы, представляющие данные контракта и конечной точки.</span><span class="sxs-lookup"><span data-stu-id="258e1-116">A WSDL importer is used to import metadata as well as convert that information into various classes that represent contract and endpoint information.</span></span> <span data-ttu-id="258e1-117">Он может выборочно импортировать сведения контракта и конечной точки, а также свойства, предоставляющие сведения об ошибках и принимающие сведения о типах, относящиеся к процессу импорта и преобразования.</span><span class="sxs-lookup"><span data-stu-id="258e1-117">It can selectively import contract and endpoint information and properties that expose any import errors and accept type information relevant to the import and conversion process.</span></span> <span data-ttu-id="258e1-118">Оно также поддерживает импорт данных привязки и свойств, предоставляющих доступ к каким-либо документам политики, документам WSDL, расширениям WSDL и документам схемы XML.</span><span class="sxs-lookup"><span data-stu-id="258e1-118">It also supports importing binding information and properties that provide access to any policy documents, WSDL documents, WSDL extensions, and XML schema documents.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="258e1-119">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="258e1-119">See also</span></span>

- <xref:System.ServiceModel.Configuration.WsdlImporterElement>
- <xref:System.ServiceModel.Configuration.MetadataElement>
- <xref:System.ServiceModel.Configuration.WsdlImporterElementCollection>
- <xref:System.ServiceModel.Description.MetadataImporter>
- <xref:System.ServiceModel.Description.WsdlImporter>
- [<span data-ttu-id="258e1-120">Конфигурация клиента WCF</span><span class="sxs-lookup"><span data-stu-id="258e1-120">WCF Client Configuration</span></span>](../../../wcf/feature-details/client-configuration.md)
- [<span data-ttu-id="258e1-121">Клиенты</span><span class="sxs-lookup"><span data-stu-id="258e1-121">Clients</span></span>](../../../wcf/feature-details/clients.md)
