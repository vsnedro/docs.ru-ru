---
title: <policyImporter>
ms.date: 03/30/2017
ms.assetid: b0d03456-546f-44bb-ab12-1b2ce7f98fca
ms.openlocfilehash: 4ef5890d52c3f2af42322f023b9a2a23cb583035
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/06/2020
ms.locfileid: "70855061"
---
# \<policyImporter>
<span data-ttu-id="c2baa-101">Задает средство импорта политики, контролирующее импорт положений пользовательской политики о привязках.</span><span class="sxs-lookup"><span data-stu-id="c2baa-101">Specifies a policy importer that controls the import of custom policy assertions about bindings.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<client>**](client.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<metadata>**](metadata.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<policyImporters>**](policyimporters.md)  
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<policyImporter>**  
  
## <a name="syntax"></a><span data-ttu-id="c2baa-102">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="c2baa-102">Syntax</span></span>  
  
```xml  
<metadata>
  <policyImporters>
    <policyImporter type="String" />
  </policyImporters>
</metadata>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="c2baa-103">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="c2baa-103">Attributes and Elements</span></span>  
 <span data-ttu-id="c2baa-104">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="c2baa-104">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="c2baa-105">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="c2baa-105">Attributes</span></span>  
  
|<span data-ttu-id="c2baa-106">Атрибут</span><span class="sxs-lookup"><span data-stu-id="c2baa-106">Attribute</span></span>|<span data-ttu-id="c2baa-107">Описание:</span><span class="sxs-lookup"><span data-stu-id="c2baa-107">Description</span></span>|  
|---------------|-----------------|  
|`type`|<span data-ttu-id="c2baa-108">Тип этого элемента.</span><span class="sxs-lookup"><span data-stu-id="c2baa-108">The type of this element.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="c2baa-109">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="c2baa-109">Child Elements</span></span>  
 <span data-ttu-id="c2baa-110">Нет</span><span class="sxs-lookup"><span data-stu-id="c2baa-110">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="c2baa-111">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="c2baa-111">Parent Elements</span></span>  
  
|<span data-ttu-id="c2baa-112">Элемент</span><span class="sxs-lookup"><span data-stu-id="c2baa-112">Element</span></span>|<span data-ttu-id="c2baa-113">Описание</span><span class="sxs-lookup"><span data-stu-id="c2baa-113">Description</span></span>|  
|-------------|-----------------|  
|[\<policyImporters>](policyimporters.md)|<span data-ttu-id="c2baa-114">Задает все средства импорта политики, контролирующие импорт утверждений пользовательской политики о привязках.</span><span class="sxs-lookup"><span data-stu-id="c2baa-114">Specifies all the policy importers that control the import of custom policy assertions about bindings.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="c2baa-115">Примечания</span><span class="sxs-lookup"><span data-stu-id="c2baa-115">Remarks</span></span>  
 <span data-ttu-id="c2baa-116">Средство импорта политики используется для поиска утверждений пользовательской политики о свойствах привязки, а также для подключения пользовательского элемента привязки, реализующего свойства, необходимые для утверждения.</span><span class="sxs-lookup"><span data-stu-id="c2baa-116">A policy importer is used to search custom policy assertions about binding features, as well as attach a custom binding element that implements the features the assertion requires.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c2baa-117">См. также</span><span class="sxs-lookup"><span data-stu-id="c2baa-117">See also</span></span>

- <xref:System.ServiceModel.Configuration.PolicyImporterElementCollection>
- <xref:System.ServiceModel.Configuration.PolicyImporterElement>
- <xref:System.ServiceModel.Configuration.MetadataElement>
- <xref:System.ServiceModel.Description.MetadataImporter>
- [<span data-ttu-id="c2baa-118">Конфигурация клиента WCF</span><span class="sxs-lookup"><span data-stu-id="c2baa-118">WCF Client Configuration</span></span>](../../../wcf/feature-details/client-configuration.md)
- [<span data-ttu-id="c2baa-119">Клиенты</span><span class="sxs-lookup"><span data-stu-id="c2baa-119">Clients</span></span>](../../../wcf/feature-details/clients.md)
