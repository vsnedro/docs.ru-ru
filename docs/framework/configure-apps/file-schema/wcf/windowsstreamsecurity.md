---
title: <windowsStreamSecurity>
ms.date: 03/30/2017
ms.assetid: 926bea29-90c7-4a26-9cf0-fb4aa44f6f70
ms.openlocfilehash: dab8505a9ddb348a6f7fe16ae9acb3a0119a8b06
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/06/2020
ms.locfileid: "73735893"
---
# \<windowsStreamSecurity>
<span data-ttu-id="b66e8-101">Задает параметры безопасности потока Windows пользовательской привязки.</span><span class="sxs-lookup"><span data-stu-id="b66e8-101">Specify Windows stream security settings of the custom binding.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<bindings>**](bindings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<customBinding>**](custombinding.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<binding>**\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<windowsStreamSecurity>**  
  
## <a name="syntax"></a><span data-ttu-id="b66e8-102">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="b66e8-102">Syntax</span></span>  
  
```xml  
<windowsStreamSecurity protectionLevel="None/Sign/EncryptAndSign" />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="b66e8-103">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="b66e8-103">Attributes and Elements</span></span>  
 <span data-ttu-id="b66e8-104">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="b66e8-104">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="b66e8-105">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="b66e8-105">Attributes</span></span>  
  
|<span data-ttu-id="b66e8-106">Атрибут</span><span class="sxs-lookup"><span data-stu-id="b66e8-106">Attribute</span></span>|<span data-ttu-id="b66e8-107">Описание:</span><span class="sxs-lookup"><span data-stu-id="b66e8-107">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="b66e8-108">protectionLevel</span><span class="sxs-lookup"><span data-stu-id="b66e8-108">protectionLevel</span></span>|<span data-ttu-id="b66e8-109">Определяет систему безопасности уровня сообщений.</span><span class="sxs-lookup"><span data-stu-id="b66e8-109">Defines message-level security.</span></span> <span data-ttu-id="b66e8-110">Подпись сообщений уменьшает риск подделки сообщения сторонними лицами при его передаче.</span><span class="sxs-lookup"><span data-stu-id="b66e8-110">Signing messages mitigates the risk of a third party tampering with the message while it is being transferred.</span></span> <span data-ttu-id="b66e8-111">Шифрование обеспечивает конфиденциальность на уровне данных во время транспортировки.</span><span class="sxs-lookup"><span data-stu-id="b66e8-111">Encryption provides data-level privacy during transport.</span></span> <span data-ttu-id="b66e8-112">Допустимые значения.</span><span class="sxs-lookup"><span data-stu-id="b66e8-112">Valid values include the following:</span></span><br /><br /> <span data-ttu-id="b66e8-113">-None: защита отсутствует.</span><span class="sxs-lookup"><span data-stu-id="b66e8-113">-   None: No protection.</span></span><br /><span data-ttu-id="b66e8-114">-Sign: сообщения подписываются.</span><span class="sxs-lookup"><span data-stu-id="b66e8-114">-   Sign: Messages are signed.</span></span><br /><span data-ttu-id="b66e8-115">-EncryptAndSign: сообщения подписываются и шифруются.</span><span class="sxs-lookup"><span data-stu-id="b66e8-115">-   EncryptAndSign: Messages are signed and encrypted.</span></span><br /><br /> <span data-ttu-id="b66e8-116">Значение по умолчанию - EncryptAndSign.</span><span class="sxs-lookup"><span data-stu-id="b66e8-116">The default is EncryptAndSign.</span></span><br /><br /> <span data-ttu-id="b66e8-117">Это атрибут типа <xref:System.Net.Security.ProtectionLevel>.</span><span class="sxs-lookup"><span data-stu-id="b66e8-117">This attribute is of type <xref:System.Net.Security.ProtectionLevel>.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="b66e8-118">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="b66e8-118">Child Elements</span></span>  
 <span data-ttu-id="b66e8-119">Нет</span><span class="sxs-lookup"><span data-stu-id="b66e8-119">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="b66e8-120">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="b66e8-120">Parent Elements</span></span>  
  
|<span data-ttu-id="b66e8-121">Элемент</span><span class="sxs-lookup"><span data-stu-id="b66e8-121">Element</span></span>|<span data-ttu-id="b66e8-122">Описание</span><span class="sxs-lookup"><span data-stu-id="b66e8-122">Description</span></span>|  
|-------------|-----------------|  
|[\<binding>](bindings.md)|<span data-ttu-id="b66e8-123">Определяет все возможности пользовательской привязки.</span><span class="sxs-lookup"><span data-stu-id="b66e8-123">Defines all binding capabilities of the custom binding.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="b66e8-124">Примечания</span><span class="sxs-lookup"><span data-stu-id="b66e8-124">Remarks</span></span>  
 <span data-ttu-id="b66e8-125">Транспорты, использующие такой поточно-ориентированный протокол, как TCP и именованные каналы, поддерживают потоковые обновления транспорта.</span><span class="sxs-lookup"><span data-stu-id="b66e8-125">Transports that use a stream-oriented protocol such as TCP and named pipes support stream-based transport upgrades.</span></span> <span data-ttu-id="b66e8-126">В частности, WCF обеспечивает обновления системы безопасности.</span><span class="sxs-lookup"><span data-stu-id="b66e8-126">Specifically, WCF provides security upgrades.</span></span> <span data-ttu-id="b66e8-127">Конфигурация этой защиты транспорта инкапсулирована этим элементом конфигурации, а также с [\<sslStreamSecurity>](sslstreamsecurity.md) , который можно настроить и добавить в пользовательскую привязку.</span><span class="sxs-lookup"><span data-stu-id="b66e8-127">The configuration of this transport security is encapsulated by this configuration element  as well as by [\<sslStreamSecurity>](sslstreamsecurity.md), which can be configured and added to a custom binding</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b66e8-128">См. также</span><span class="sxs-lookup"><span data-stu-id="b66e8-128">See also</span></span>

- <xref:System.ServiceModel.Channels.CustomBinding>
- <xref:System.ServiceModel.Configuration.WindowsStreamSecurityElement>
- <xref:System.ServiceModel.Channels.WindowsStreamSecurityBindingElement>
- [<span data-ttu-id="b66e8-129">Привязки</span><span class="sxs-lookup"><span data-stu-id="b66e8-129">Bindings</span></span>](../../../wcf/bindings.md)
- [<span data-ttu-id="b66e8-130">Расширение привязок</span><span class="sxs-lookup"><span data-stu-id="b66e8-130">Extending Bindings</span></span>](../../../wcf/extending/extending-bindings.md)
- [<span data-ttu-id="b66e8-131">Пользовательские привязки</span><span class="sxs-lookup"><span data-stu-id="b66e8-131">Custom Bindings</span></span>](../../../wcf/extending/custom-bindings.md)
- [\<customBinding>](custombinding.md)
