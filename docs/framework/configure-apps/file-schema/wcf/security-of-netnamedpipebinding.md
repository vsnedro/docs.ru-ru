---
title: <security> из <netNamedPipeBinding>
ms.date: 03/30/2017
ms.assetid: bb3cb022-637e-49fd-92e8-6766038affa7
ms.openlocfilehash: 31ea31ce6880a770c966350cd931e487396c4d63
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/06/2020
ms.locfileid: "73736433"
---
# <a name="security-of-netnamedpipebinding"></a><span data-ttu-id="f009a-102">\<security> из \<netNamedPipeBinding></span><span class="sxs-lookup"><span data-stu-id="f009a-102">\<security> of \<netNamedPipeBinding></span></span>
<span data-ttu-id="f009a-103">Определяет параметры безопасности для привязки.</span><span class="sxs-lookup"><span data-stu-id="f009a-103">Defines the security settings for a binding.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<bindings>**](bindings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<netNamedPipeBinding>**](netnamedpipebinding.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<binding>**\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<security>**  
  
## <a name="syntax"></a><span data-ttu-id="f009a-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="f009a-104">Syntax</span></span>  
  
```xml  
<netNamedPipeBinding>
  <binding>
    <security mode="None/Transport">
      <transport protectionLevel="None/Sign/EncryptAndSign" />
    </security>
  </binding>
</netNamedPipeBinding>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="f009a-105">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="f009a-105">Attributes and Elements</span></span>  
 <span data-ttu-id="f009a-106">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="f009a-106">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="f009a-107">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="f009a-107">Attributes</span></span>  
  
|<span data-ttu-id="f009a-108">Атрибут</span><span class="sxs-lookup"><span data-stu-id="f009a-108">Attribute</span></span>|<span data-ttu-id="f009a-109">Описание:</span><span class="sxs-lookup"><span data-stu-id="f009a-109">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="f009a-110">mode</span><span class="sxs-lookup"><span data-stu-id="f009a-110">mode</span></span>|<span data-ttu-id="f009a-111">Задает тип системы безопасности, применяемой к этой привязке.</span><span class="sxs-lookup"><span data-stu-id="f009a-111">Specifies the type of security that is applied to this binding.</span></span> <span data-ttu-id="f009a-112">Допустимые значения.</span><span class="sxs-lookup"><span data-stu-id="f009a-112">Valid values include the following:</span></span><br /><br /> <span data-ttu-id="f009a-113">-None: отключает безопасность.</span><span class="sxs-lookup"><span data-stu-id="f009a-113">-   None: This disables security.</span></span><br /><span data-ttu-id="f009a-114">-Transport. безопасность обеспечивается с помощью базовой безопасности на основе транспорта.</span><span class="sxs-lookup"><span data-stu-id="f009a-114">-   Transport: Security is provided using underlying transport based security.</span></span> <span data-ttu-id="f009a-115">Этот режим позволяет контролировать уровень защиты.</span><span class="sxs-lookup"><span data-stu-id="f009a-115">It is possible to control the protection level with this mode.</span></span><br /><span data-ttu-id="f009a-116">— Значение по умолчанию — Transport.</span><span class="sxs-lookup"><span data-stu-id="f009a-116">-   The default value is Transport.</span></span> <span data-ttu-id="f009a-117">Это атрибут типа <xref:System.ServiceModel.NetNamedPipeSecurityMode>.</span><span class="sxs-lookup"><span data-stu-id="f009a-117">This attribute is of type <xref:System.ServiceModel.NetNamedPipeSecurityMode>.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="f009a-118">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="f009a-118">Child Elements</span></span>  
  
|<span data-ttu-id="f009a-119">Элемент</span><span class="sxs-lookup"><span data-stu-id="f009a-119">Element</span></span>|<span data-ttu-id="f009a-120">Описание</span><span class="sxs-lookup"><span data-stu-id="f009a-120">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="f009a-121">транспорт</span><span class="sxs-lookup"><span data-stu-id="f009a-121">transport</span></span>|<span data-ttu-id="f009a-122">Определяет параметры безопасности для данного транспорта.</span><span class="sxs-lookup"><span data-stu-id="f009a-122">Defines the security settings for the transport.</span></span> <span data-ttu-id="f009a-123">Это элемент типа <xref:System.ServiceModel.Configuration.NamedPipeTransportSecurityElement>.</span><span class="sxs-lookup"><span data-stu-id="f009a-123">This element is of type <xref:System.ServiceModel.Configuration.NamedPipeTransportSecurityElement>.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="f009a-124">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="f009a-124">Parent Elements</span></span>  
  
|<span data-ttu-id="f009a-125">Элемент</span><span class="sxs-lookup"><span data-stu-id="f009a-125">Element</span></span>|<span data-ttu-id="f009a-126">Описание</span><span class="sxs-lookup"><span data-stu-id="f009a-126">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="f009a-127">binding</span><span class="sxs-lookup"><span data-stu-id="f009a-127">binding</span></span>|<span data-ttu-id="f009a-128">Элемент Binding объекта [\<netNamedPipeBinding>](netnamedpipebinding.md) .</span><span class="sxs-lookup"><span data-stu-id="f009a-128">The binding element of the [\<netNamedPipeBinding>](netnamedpipebinding.md).</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="f009a-129">См. также</span><span class="sxs-lookup"><span data-stu-id="f009a-129">See also</span></span>

- <xref:System.ServiceModel.NetNamedPipeSecurity>
- <xref:System.ServiceModel.NetNamedPipeBinding.Security%2A>
- <xref:System.ServiceModel.Configuration.NetNamedPipeBindingElement.Security%2A>
- <xref:System.ServiceModel.Configuration.NetNamedPipeSecurityElement>
- [<span data-ttu-id="f009a-130">Защита служб и клиентов</span><span class="sxs-lookup"><span data-stu-id="f009a-130">Securing Services and Clients</span></span>](../../../wcf/feature-details/securing-services-and-clients.md)
- [<span data-ttu-id="f009a-131">Выбор типа учетных данных</span><span class="sxs-lookup"><span data-stu-id="f009a-131">Selecting a Credential Type</span></span>](../../../wcf/feature-details/selecting-a-credential-type.md)
- [<span data-ttu-id="f009a-132">Привязки</span><span class="sxs-lookup"><span data-stu-id="f009a-132">Bindings</span></span>](../../../wcf/bindings.md)
- [<span data-ttu-id="f009a-133">Настройка привязок, предоставляемых системой</span><span class="sxs-lookup"><span data-stu-id="f009a-133">Configuring System-Provided Bindings</span></span>](../../../wcf/feature-details/configuring-system-provided-bindings.md)
- [<span data-ttu-id="f009a-134">Использование привязок для настройки служб и клиентов</span><span class="sxs-lookup"><span data-stu-id="f009a-134">Using Bindings to Configure Services and Clients</span></span>](../../../wcf/using-bindings-to-configure-services-and-clients.md)
- [\<binding>](bindings.md)
