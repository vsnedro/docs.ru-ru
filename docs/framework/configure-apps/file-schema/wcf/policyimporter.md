---
title: <policyImporter>
ms.date: 03/30/2017
ms.assetid: b0d03456-546f-44bb-ab12-1b2ce7f98fca
ms.openlocfilehash: 72778ce0070d853f8b081a4889ead9524bafd0e8
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/24/2020
ms.locfileid: "91181353"
---
# \<policyImporter>

<span data-ttu-id="397f9-101">Задает средство импорта политики, контролирующее импорт положений пользовательской политики о привязках.</span><span class="sxs-lookup"><span data-stu-id="397f9-101">Specifies a policy importer that controls the import of custom policy assertions about bindings.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<client>**](client.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<metadata>**](metadata.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<policyImporters>**](policyimporters.md)  
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<policyImporter>**  
  
## <a name="syntax"></a><span data-ttu-id="397f9-102">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="397f9-102">Syntax</span></span>  
  
```xml  
<metadata>
  <policyImporters>
    <policyImporter type="String" />
  </policyImporters>
</metadata>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="397f9-103">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="397f9-103">Attributes and Elements</span></span>  

 <span data-ttu-id="397f9-104">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="397f9-104">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="397f9-105">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="397f9-105">Attributes</span></span>  
  
|<span data-ttu-id="397f9-106">Атрибут</span><span class="sxs-lookup"><span data-stu-id="397f9-106">Attribute</span></span>|<span data-ttu-id="397f9-107">Описание</span><span class="sxs-lookup"><span data-stu-id="397f9-107">Description</span></span>|  
|---------------|-----------------|  
|`type`|<span data-ttu-id="397f9-108">Тип этого элемента.</span><span class="sxs-lookup"><span data-stu-id="397f9-108">The type of this element.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="397f9-109">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="397f9-109">Child Elements</span></span>  

 <span data-ttu-id="397f9-110">Нет</span><span class="sxs-lookup"><span data-stu-id="397f9-110">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="397f9-111">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="397f9-111">Parent Elements</span></span>  
  
|<span data-ttu-id="397f9-112">Элемент</span><span class="sxs-lookup"><span data-stu-id="397f9-112">Element</span></span>|<span data-ttu-id="397f9-113">Описание</span><span class="sxs-lookup"><span data-stu-id="397f9-113">Description</span></span>|  
|-------------|-----------------|  
|[\<policyImporters>](policyimporters.md)|<span data-ttu-id="397f9-114">Задает все средства импорта политики, контролирующие импорт утверждений пользовательской политики о привязках.</span><span class="sxs-lookup"><span data-stu-id="397f9-114">Specifies all the policy importers that control the import of custom policy assertions about bindings.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="397f9-115">Remarks</span><span class="sxs-lookup"><span data-stu-id="397f9-115">Remarks</span></span>  

 <span data-ttu-id="397f9-116">Средство импорта политики используется для поиска утверждений пользовательской политики о свойствах привязки, а также для подключения пользовательского элемента привязки, реализующего свойства, необходимые для утверждения.</span><span class="sxs-lookup"><span data-stu-id="397f9-116">A policy importer is used to search custom policy assertions about binding features, as well as attach a custom binding element that implements the features the assertion requires.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="397f9-117">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="397f9-117">See also</span></span>

- <xref:System.ServiceModel.Configuration.PolicyImporterElementCollection>
- <xref:System.ServiceModel.Configuration.PolicyImporterElement>
- <xref:System.ServiceModel.Configuration.MetadataElement>
- <xref:System.ServiceModel.Description.MetadataImporter>
- [<span data-ttu-id="397f9-118">Конфигурация клиента WCF</span><span class="sxs-lookup"><span data-stu-id="397f9-118">WCF Client Configuration</span></span>](../../../wcf/feature-details/client-configuration.md)
- [<span data-ttu-id="397f9-119">Клиенты</span><span class="sxs-lookup"><span data-stu-id="397f9-119">Clients</span></span>](../../../wcf/feature-details/clients.md)
