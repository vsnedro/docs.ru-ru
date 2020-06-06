---
title: <privacyNoticeAt>
ms.date: 03/30/2017
ms.assetid: 4cc96942-4eb9-4241-b2fd-45aa239915e8
ms.openlocfilehash: 2ff70d3a8636970434582e417e4549ab6b433fc1
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/06/2020
ms.locfileid: "73738763"
---
# \<privacyNoticeAt>
<span data-ttu-id="022bf-101">Представляет элемент конфигурации, который задает уведомление о конфиденциальности, используемое в привязке `wsFederationHttp`.</span><span class="sxs-lookup"><span data-stu-id="022bf-101">Represents a configuration element that specifies a privacy notice used in `wsFederationHttp` binding.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<bindings>**](bindings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<customBinding>**](custombinding.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<binding>**\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<privacyNotice>**  
  
## <a name="syntax"></a><span data-ttu-id="022bf-102">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="022bf-102">Syntax</span></span>  
  
```xml  
<privacyNotice url="String"
               version="Integer" />
```  
  
## <a name="type"></a><span data-ttu-id="022bf-103">Type</span><span class="sxs-lookup"><span data-stu-id="022bf-103">Type</span></span>  
 `Type`  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="022bf-104">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="022bf-104">Attributes and Elements</span></span>  
 <span data-ttu-id="022bf-105">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="022bf-105">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="022bf-106">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="022bf-106">Attributes</span></span>  
  
|<span data-ttu-id="022bf-107">Атрибут</span><span class="sxs-lookup"><span data-stu-id="022bf-107">Attribute</span></span>|<span data-ttu-id="022bf-108">Описание:</span><span class="sxs-lookup"><span data-stu-id="022bf-108">Description</span></span>|  
|---------------|-----------------|  
|`url`|<span data-ttu-id="022bf-109">Строка, задающая универсальный код ресурса (URI), определяющий расположение примечания о конфиденциальности.</span><span class="sxs-lookup"><span data-stu-id="022bf-109">A string that specifies the URI at which the privacy notice is located.</span></span>|  
|`version`|<span data-ttu-id="022bf-110">Целое число, определяющее версию этого уведомления о конфиденциальности.</span><span class="sxs-lookup"><span data-stu-id="022bf-110">An integer that specifies the version of this privacy notice.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="022bf-111">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="022bf-111">Child Elements</span></span>  
 <span data-ttu-id="022bf-112">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="022bf-112">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="022bf-113">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="022bf-113">Parent Elements</span></span>  
  
|<span data-ttu-id="022bf-114">Элемент</span><span class="sxs-lookup"><span data-stu-id="022bf-114">Element</span></span>|<span data-ttu-id="022bf-115">Описание</span><span class="sxs-lookup"><span data-stu-id="022bf-115">Description</span></span>|  
|-------------|-----------------|  
|[\<binding>](bindings.md)|<span data-ttu-id="022bf-116">Определяет все возможности пользовательской привязки.</span><span class="sxs-lookup"><span data-stu-id="022bf-116">Defines all binding capabilities of the custom binding.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="022bf-117">См. также</span><span class="sxs-lookup"><span data-stu-id="022bf-117">See also</span></span>

- <xref:System.ServiceModel.Configuration.PrivacyNoticeElement>
- <xref:System.ServiceModel.Channels.PrivacyNoticeBindingElement>
- <xref:System.ServiceModel.Channels.CustomBinding>
- [<span data-ttu-id="022bf-118">Привязки</span><span class="sxs-lookup"><span data-stu-id="022bf-118">Bindings</span></span>](../../../wcf/bindings.md)
- [<span data-ttu-id="022bf-119">Расширение привязок</span><span class="sxs-lookup"><span data-stu-id="022bf-119">Extending Bindings</span></span>](../../../wcf/extending/extending-bindings.md)
- [<span data-ttu-id="022bf-120">Пользовательские привязки</span><span class="sxs-lookup"><span data-stu-id="022bf-120">Custom Bindings</span></span>](../../../wcf/extending/custom-bindings.md)
- [\<customBinding>](custombinding.md)
