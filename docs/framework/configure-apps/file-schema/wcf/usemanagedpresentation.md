---
title: <useManagedPresentation>
ms.date: 03/30/2017
ms.assetid: 17a0dd77-af54-41db-a9d0-4b17ff42878f
ms.openlocfilehash: bb2989ed52a88d805510d65e1dc1740df7bb55eb
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/06/2020
ms.locfileid: "73735944"
---
# \<useManagedPresentation>
<span data-ttu-id="165c7-101">Элемент привязки, используемый для связи со службой маркеров безопасности CardSpace, которая поддерживает CardSpace-профиль WS-Trust.</span><span class="sxs-lookup"><span data-stu-id="165c7-101">A binding element used to communicate with a CardSpace Security Token Service that supports the CardSpace profile of WS-Trust.</span></span> <span data-ttu-id="165c7-102">Этот элемент не имеет атрибутов и представлен как пустой переключатель.</span><span class="sxs-lookup"><span data-stu-id="165c7-102">This element has no attribute and is present as an empty switch.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<bindings>**](bindings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<customBinding>**](custombinding.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<binding>**\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<useManagedPresentation>**  
  
## <a name="syntax"></a><span data-ttu-id="165c7-103">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="165c7-103">Syntax</span></span>  
  
```xml  
<useManagedPresentation />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="165c7-104">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="165c7-104">Attributes and Elements</span></span>  
 <span data-ttu-id="165c7-105">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="165c7-105">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="165c7-106">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="165c7-106">Attributes</span></span>  
 <span data-ttu-id="165c7-107">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="165c7-107">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="165c7-108">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="165c7-108">Child Elements</span></span>  
 <span data-ttu-id="165c7-109">Нет</span><span class="sxs-lookup"><span data-stu-id="165c7-109">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="165c7-110">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="165c7-110">Parent Elements</span></span>  
  
|<span data-ttu-id="165c7-111">Элемент</span><span class="sxs-lookup"><span data-stu-id="165c7-111">Element</span></span>|<span data-ttu-id="165c7-112">Описание</span><span class="sxs-lookup"><span data-stu-id="165c7-112">Description</span></span>|  
|-------------|-----------------|  
|[\<binding>](bindings.md)|<span data-ttu-id="165c7-113">Определяет все возможности пользовательской привязки.</span><span class="sxs-lookup"><span data-stu-id="165c7-113">Defines all binding capabilities of the custom binding.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="165c7-114">Примечания</span><span class="sxs-lookup"><span data-stu-id="165c7-114">Remarks</span></span>  
 <span data-ttu-id="165c7-115">Этот элемент используется поставщиком удостоверения для отражения в своей политике поддержки CardSpace-профиля WS-Trust.</span><span class="sxs-lookup"><span data-stu-id="165c7-115">This element is used by an identity provider to express in its policy the fact that it supports the CardSpace profile of WS-Trust.</span></span> <span data-ttu-id="165c7-116">Поставщики удостоверений, которые предоставляют такое утверждение политики, должны быть способны выдавать маркеры на основе этого профиля CardSpace.</span><span class="sxs-lookup"><span data-stu-id="165c7-116">Identity providers that publish such a policy assertion should be able to issue tokens based on that CardSpace profile.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="165c7-117">См. также</span><span class="sxs-lookup"><span data-stu-id="165c7-117">See also</span></span>

- <xref:System.ServiceModel.Configuration.UseManagedPresentationElement>
- <xref:System.ServiceModel.Channels.UseManagedPresentationBindingElement>
- <xref:System.ServiceModel.Channels.CustomBinding>
- [<span data-ttu-id="165c7-118">Привязки</span><span class="sxs-lookup"><span data-stu-id="165c7-118">Bindings</span></span>](../../../wcf/bindings.md)
- [<span data-ttu-id="165c7-119">Расширение привязок</span><span class="sxs-lookup"><span data-stu-id="165c7-119">Extending Bindings</span></span>](../../../wcf/extending/extending-bindings.md)
- [<span data-ttu-id="165c7-120">Пользовательские привязки</span><span class="sxs-lookup"><span data-stu-id="165c7-120">Custom Bindings</span></span>](../../../wcf/extending/custom-bindings.md)
- [\<customBinding>](custombinding.md)
