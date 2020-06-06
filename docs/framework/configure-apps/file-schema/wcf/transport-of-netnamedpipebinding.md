---
title: <transport> из <netNamedPipeBinding>
ms.date: 03/30/2017
ms.assetid: d9eff52d-4bde-4586-b56a-b0ec24611f8d
ms.openlocfilehash: d40178e59b89c2912123e1927e9e960f6d880871
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/06/2020
ms.locfileid: "73735957"
---
# <a name="transport-of-netnamedpipebinding"></a><span data-ttu-id="a5842-102">\<transport> из \<netNamedPipeBinding></span><span class="sxs-lookup"><span data-stu-id="a5842-102">\<transport> of \<netNamedPipeBinding></span></span>
<span data-ttu-id="a5842-103">Определяет параметры безопасности транспорта для именованного канала.</span><span class="sxs-lookup"><span data-stu-id="a5842-103">Defines the transport security settings for a named pipe.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<bindings>**](bindings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<netNamedPipeBinding>**](netnamedpipebinding.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<binding>**\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<security>**](security-of-netnamedpipebinding.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<transport>**  
  
## <a name="syntax"></a><span data-ttu-id="a5842-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="a5842-104">Syntax</span></span>  
  
```xml  
<netNamedPipeBinding>
  <binding>
    <security mode="None/Transport">
      <transport protectionLevel="None/Sign/EncryptAndSign" />
    </security>
  </binding>
</netNamedPipeBinding>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="a5842-105">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="a5842-105">Attributes and Elements</span></span>  
 <span data-ttu-id="a5842-106">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="a5842-106">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="a5842-107">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="a5842-107">Attributes</span></span>  
  
|<span data-ttu-id="a5842-108">Атрибут</span><span class="sxs-lookup"><span data-stu-id="a5842-108">Attribute</span></span>|<span data-ttu-id="a5842-109">Описание:</span><span class="sxs-lookup"><span data-stu-id="a5842-109">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="a5842-110">protectionLevel</span><span class="sxs-lookup"><span data-stu-id="a5842-110">protectionLevel</span></span>|<span data-ttu-id="a5842-111">Определяет уровень защиты именованного канала.</span><span class="sxs-lookup"><span data-stu-id="a5842-111">Defines protection level of the named pipe.</span></span> <span data-ttu-id="a5842-112">Подпись сообщений уменьшает риск подделки сообщения сторонними лицами при его передаче.</span><span class="sxs-lookup"><span data-stu-id="a5842-112">Signing messages mitigates the risk of a third party tampering with the message while it is being transferred.</span></span> <span data-ttu-id="a5842-113">Шифрование обеспечивает конфиденциальность на уровне данных во время транспортировки.</span><span class="sxs-lookup"><span data-stu-id="a5842-113">Encryption provides data-level privacy during transport.</span></span> <span data-ttu-id="a5842-114">Допустимые значения.</span><span class="sxs-lookup"><span data-stu-id="a5842-114">Valid values include the following:</span></span><br /><br /> <span data-ttu-id="a5842-115">-None: защита отсутствует.</span><span class="sxs-lookup"><span data-stu-id="a5842-115">-   None: No protection.</span></span><br /><span data-ttu-id="a5842-116">-Sign: сообщения подписываются.</span><span class="sxs-lookup"><span data-stu-id="a5842-116">-   Sign: Messages are signed.</span></span><br /><span data-ttu-id="a5842-117">-EncryptAndSign: сообщения шифруются и подписываются.</span><span class="sxs-lookup"><span data-stu-id="a5842-117">-   EncryptAndSign: Messages are encrypted and signed.</span></span><br /><br /> <span data-ttu-id="a5842-118">Значение по умолчанию - EncryptAndSign.</span><span class="sxs-lookup"><span data-stu-id="a5842-118">The default value is EncryptAndSign.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="a5842-119">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="a5842-119">Child Elements</span></span>  
 <span data-ttu-id="a5842-120">Нет</span><span class="sxs-lookup"><span data-stu-id="a5842-120">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="a5842-121">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="a5842-121">Parent Elements</span></span>  
  
|<span data-ttu-id="a5842-122">Элемент</span><span class="sxs-lookup"><span data-stu-id="a5842-122">Element</span></span>|<span data-ttu-id="a5842-123">Описание</span><span class="sxs-lookup"><span data-stu-id="a5842-123">Description</span></span>|  
|-------------|-----------------|  
|[\<security>](security-of-netnamedpipebinding.md)|<span data-ttu-id="a5842-124">Определяет параметры безопасности для привязки.</span><span class="sxs-lookup"><span data-stu-id="a5842-124">Defines the security settings for a binding.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="a5842-125">См. также</span><span class="sxs-lookup"><span data-stu-id="a5842-125">See also</span></span>

- <xref:System.ServiceModel.NamedPipeTransportSecurity>
- <xref:System.ServiceModel.Configuration.NetNamedPipeSecurityElement.Transport%2A>
- <xref:System.ServiceModel.NetNamedPipeSecurity.Transport%2A>
- <xref:System.ServiceModel.Configuration.NamedPipeTransportSecurityElement>
- [<span data-ttu-id="a5842-126">Защита служб и клиентов</span><span class="sxs-lookup"><span data-stu-id="a5842-126">Securing Services and Clients</span></span>](../../../wcf/feature-details/securing-services-and-clients.md)
- [<span data-ttu-id="a5842-127">Привязки</span><span class="sxs-lookup"><span data-stu-id="a5842-127">Bindings</span></span>](../../../wcf/bindings.md)
- [<span data-ttu-id="a5842-128">Настройка привязок, предоставляемых системой</span><span class="sxs-lookup"><span data-stu-id="a5842-128">Configuring System-Provided Bindings</span></span>](../../../wcf/feature-details/configuring-system-provided-bindings.md)
- [<span data-ttu-id="a5842-129">Использование привязок для настройки служб и клиентов</span><span class="sxs-lookup"><span data-stu-id="a5842-129">Using Bindings to Configure Services and Clients</span></span>](../../../wcf/using-bindings-to-configure-services-and-clients.md)
- [\<binding>](bindings.md)
