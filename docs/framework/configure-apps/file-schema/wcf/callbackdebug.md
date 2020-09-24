---
title: <callbackDebug>
ms.date: 03/30/2017
ms.assetid: 4073feda-1857-4be4-9947-227afb847ced
ms.openlocfilehash: 02632cc3f668bb9e4cc6f8c9726d7bcb3cab2c5d
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/24/2020
ms.locfileid: "91183823"
---
# \<callbackDebug>

<span data-ttu-id="60c86-101">Указывает отладку службы для объекта обратного вызова Windows Communication Foundation (WCF).</span><span class="sxs-lookup"><span data-stu-id="60c86-101">Specifies service debugging for a Windows Communication Foundation (WCF) callback object.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<behaviors>**](behaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<endpointBehaviors>**](endpointbehaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<behavior>**](behavior-of-endpointbehaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<callbackDebug>**  
  
## <a name="syntax"></a><span data-ttu-id="60c86-102">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="60c86-102">Syntax</span></span>  
  
```xml  
<callbackDebug includeExceptionDetailInFaults="Boolean" />
```  
  
## <a name="type"></a><span data-ttu-id="60c86-103">Type</span><span class="sxs-lookup"><span data-stu-id="60c86-103">Type</span></span>  

 `Type`  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="60c86-104">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="60c86-104">Attributes and Elements</span></span>  

 <span data-ttu-id="60c86-105">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="60c86-105">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="60c86-106">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="60c86-106">Attributes</span></span>  
  
|<span data-ttu-id="60c86-107">Атрибут</span><span class="sxs-lookup"><span data-stu-id="60c86-107">Attribute</span></span>|<span data-ttu-id="60c86-108">Описание</span><span class="sxs-lookup"><span data-stu-id="60c86-108">Description</span></span>|  
|---------------|-----------------|  
|`includeExceptionDetailInFaults`|<span data-ttu-id="60c86-109">Значение, которое указывает, возвращают ли объекты обратного вызова клиента сведения об управляемом исключении в ошибках SOAP назад в службу.</span><span class="sxs-lookup"><span data-stu-id="60c86-109">A value that specifies whether client callback objects return managed exception information in SOAP faults back to the service.</span></span><br /><br /> <span data-ttu-id="60c86-110">Если программным способом задать этому атрибуту значение `true`, в объекте обратного вызова клиента можно включить поток сведений об управляемом исключении назад в службу для отладки.</span><span class="sxs-lookup"><span data-stu-id="60c86-110">If you set this attribute to `true` programmatically, you can enable the flow of managed exception information in a client callback object back to the service for debugging purposes.</span></span> <span data-ttu-id="60c86-111">**Внимание!**  Возврат сведений об управляемом исключении клиентам может представлять угрозу безопасности.</span><span class="sxs-lookup"><span data-stu-id="60c86-111">**Caution:**  Returning managed exception information to clients can be a security risk.</span></span> <span data-ttu-id="60c86-112">Это связано с тем, что подробные данные об исключении содержат сведения о внутренней реализации службы, которые могут использоваться неавторизованными клиентами.</span><span class="sxs-lookup"><span data-stu-id="60c86-112">This is because exception details expose information about the internal service implementation that could be used by unauthorized clients.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="60c86-113">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="60c86-113">Child Elements</span></span>  

 <span data-ttu-id="60c86-114">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="60c86-114">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="60c86-115">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="60c86-115">Parent Elements</span></span>  
  
|<span data-ttu-id="60c86-116">Элемент</span><span class="sxs-lookup"><span data-stu-id="60c86-116">Element</span></span>|<span data-ttu-id="60c86-117">Описание</span><span class="sxs-lookup"><span data-stu-id="60c86-117">Description</span></span>|  
|-------------|-----------------|  
|[\<behavior>](behavior-of-endpointbehaviors.md)|<span data-ttu-id="60c86-118">Задает поведение конечной точки.</span><span class="sxs-lookup"><span data-stu-id="60c86-118">Specifies an endpoint behavior.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="60c86-119">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="60c86-119">See also</span></span>

- <xref:System.ServiceModel.Configuration.CallbackDebugElement>
- <xref:System.ServiceModel.Description.CallbackDebugBehavior>
