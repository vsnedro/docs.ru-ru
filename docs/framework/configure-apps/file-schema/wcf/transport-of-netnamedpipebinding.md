---
title: <transport> из <netNamedPipeBinding>
ms.date: 03/30/2017
ms.assetid: d9eff52d-4bde-4586-b56a-b0ec24611f8d
ms.openlocfilehash: 81c52405478d4c1ab5c65aab73f7feff61b879d0
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/24/2020
ms.locfileid: "91178025"
---
# <a name="transport-of-netnamedpipebinding"></a><span data-ttu-id="27205-102">\<transport> из \<netNamedPipeBinding></span><span class="sxs-lookup"><span data-stu-id="27205-102">\<transport> of \<netNamedPipeBinding></span></span>

<span data-ttu-id="27205-103">Определяет параметры безопасности транспорта для именованного канала.</span><span class="sxs-lookup"><span data-stu-id="27205-103">Defines the transport security settings for a named pipe.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<bindings>**](bindings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<netNamedPipeBinding>**](netnamedpipebinding.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<binding>**\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<security>**](security-of-netnamedpipebinding.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<transport>**  
  
## <a name="syntax"></a><span data-ttu-id="27205-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="27205-104">Syntax</span></span>  
  
```xml  
<netNamedPipeBinding>
  <binding>
    <security mode="None/Transport">
      <transport protectionLevel="None/Sign/EncryptAndSign" />
    </security>
  </binding>
</netNamedPipeBinding>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="27205-105">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="27205-105">Attributes and Elements</span></span>  

 <span data-ttu-id="27205-106">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="27205-106">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="27205-107">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="27205-107">Attributes</span></span>  
  
|<span data-ttu-id="27205-108">Атрибут</span><span class="sxs-lookup"><span data-stu-id="27205-108">Attribute</span></span>|<span data-ttu-id="27205-109">Описание</span><span class="sxs-lookup"><span data-stu-id="27205-109">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="27205-110">protectionLevel</span><span class="sxs-lookup"><span data-stu-id="27205-110">protectionLevel</span></span>|<span data-ttu-id="27205-111">Определяет уровень защиты именованного канала.</span><span class="sxs-lookup"><span data-stu-id="27205-111">Defines protection level of the named pipe.</span></span> <span data-ttu-id="27205-112">Подпись сообщений уменьшает риск подделки сообщения сторонними лицами при его передаче.</span><span class="sxs-lookup"><span data-stu-id="27205-112">Signing messages mitigates the risk of a third party tampering with the message while it is being transferred.</span></span> <span data-ttu-id="27205-113">Шифрование обеспечивает конфиденциальность на уровне данных во время транспортировки.</span><span class="sxs-lookup"><span data-stu-id="27205-113">Encryption provides data-level privacy during transport.</span></span> <span data-ttu-id="27205-114">Допустимые значения.</span><span class="sxs-lookup"><span data-stu-id="27205-114">Valid values include the following:</span></span><br /><br /> <span data-ttu-id="27205-115">-None: защита отсутствует.</span><span class="sxs-lookup"><span data-stu-id="27205-115">-   None: No protection.</span></span><br /><span data-ttu-id="27205-116">-Sign: сообщения подписываются.</span><span class="sxs-lookup"><span data-stu-id="27205-116">-   Sign: Messages are signed.</span></span><br /><span data-ttu-id="27205-117">-EncryptAndSign: сообщения шифруются и подписываются.</span><span class="sxs-lookup"><span data-stu-id="27205-117">-   EncryptAndSign: Messages are encrypted and signed.</span></span><br /><br /> <span data-ttu-id="27205-118">Значение по умолчанию - EncryptAndSign.</span><span class="sxs-lookup"><span data-stu-id="27205-118">The default value is EncryptAndSign.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="27205-119">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="27205-119">Child Elements</span></span>  

 <span data-ttu-id="27205-120">Нет</span><span class="sxs-lookup"><span data-stu-id="27205-120">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="27205-121">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="27205-121">Parent Elements</span></span>  
  
|<span data-ttu-id="27205-122">Элемент</span><span class="sxs-lookup"><span data-stu-id="27205-122">Element</span></span>|<span data-ttu-id="27205-123">Описание</span><span class="sxs-lookup"><span data-stu-id="27205-123">Description</span></span>|  
|-------------|-----------------|  
|[\<security>](security-of-netnamedpipebinding.md)|<span data-ttu-id="27205-124">Определяет параметры безопасности для привязки.</span><span class="sxs-lookup"><span data-stu-id="27205-124">Defines the security settings for a binding.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="27205-125">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="27205-125">See also</span></span>

- <xref:System.ServiceModel.NamedPipeTransportSecurity>
- <xref:System.ServiceModel.Configuration.NetNamedPipeSecurityElement.Transport%2A>
- <xref:System.ServiceModel.NetNamedPipeSecurity.Transport%2A>
- <xref:System.ServiceModel.Configuration.NamedPipeTransportSecurityElement>
- [<span data-ttu-id="27205-126">Защита служб и клиентов</span><span class="sxs-lookup"><span data-stu-id="27205-126">Securing Services and Clients</span></span>](../../../wcf/feature-details/securing-services-and-clients.md)
- [<span data-ttu-id="27205-127">Привязки</span><span class="sxs-lookup"><span data-stu-id="27205-127">Bindings</span></span>](../../../wcf/bindings.md)
- [<span data-ttu-id="27205-128">Настройка привязок, предоставляемых системой</span><span class="sxs-lookup"><span data-stu-id="27205-128">Configuring System-Provided Bindings</span></span>](../../../wcf/feature-details/configuring-system-provided-bindings.md)
- [<span data-ttu-id="27205-129">Использование привязок для настройки служб и клиентов</span><span class="sxs-lookup"><span data-stu-id="27205-129">Using Bindings to Configure Services and Clients</span></span>](../../../wcf/using-bindings-to-configure-services-and-clients.md)
- [\<binding>](bindings.md)
