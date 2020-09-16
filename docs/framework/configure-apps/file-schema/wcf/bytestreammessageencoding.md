---
title: <byteStreamMessageEncoding>
ms.date: 03/30/2017
ms.assetid: bbadd8dd-60a2-4007-b959-89373a8a7d60
ms.openlocfilehash: e2b92b88c3e2a8abb14f58af90aab6e2e58ce14a
ms.sourcegitcommit: 27a15a55019f6b5f2733961738babe94aec0def3
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/15/2020
ms.locfileid: "90557298"
---
# \<byteStreamMessageEncoding>
<span data-ttu-id="c8504-101">Указывает кодировку сообщения в виде потока байтов, также позволяет указать кодировку символов.</span><span class="sxs-lookup"><span data-stu-id="c8504-101">Specifies the message encoding as a stream of bytes, with the option to specify the character encoding.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<bindings>**](bindings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<customBinding>**](custombinding.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<binding>**\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<byteStreamMessageEncoding>**  
  
## <a name="syntax"></a><span data-ttu-id="c8504-102">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="c8504-102">Syntax</span></span>  
  
```xml  
<byteStreamMessageEncoding />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="c8504-103">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="c8504-103">Attributes and Elements</span></span>  
 <span data-ttu-id="c8504-104">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="c8504-104">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="c8504-105">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="c8504-105">Attributes</span></span>  
  
|<span data-ttu-id="c8504-106">Атрибут</span><span class="sxs-lookup"><span data-stu-id="c8504-106">Attribute</span></span>|<span data-ttu-id="c8504-107">Описание</span><span class="sxs-lookup"><span data-stu-id="c8504-107">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="c8504-108">messageVersion</span><span class="sxs-lookup"><span data-stu-id="c8504-108">messageVersion</span></span>|<span data-ttu-id="c8504-109">Задает версию SOAP сообщений, отправленных с помощью привязки.</span><span class="sxs-lookup"><span data-stu-id="c8504-109">Specifies the SOAP version of the messages sent using the binding.</span></span> <span data-ttu-id="c8504-110">Этому свойству может быть задано только значение версии сообщения <xref:System.ServiceModel.Channels.MessageVersion.None%2A>.</span><span class="sxs-lookup"><span data-stu-id="c8504-110">This property can only be set to the message version value of <xref:System.ServiceModel.Channels.MessageVersion.None%2A>.</span></span> <span data-ttu-id="c8504-111">Составной кодировщик сообщений потока байтов не поддерживает другие версии сообщений.</span><span class="sxs-lookup"><span data-stu-id="c8504-111">The byte stream message encoder does not support any other message versions.</span></span><br /><br /> <span data-ttu-id="c8504-112">Это атрибут типа <xref:System.ServiceModel.Channels.MessageVersion>.</span><span class="sxs-lookup"><span data-stu-id="c8504-112">This attribute is of type <xref:System.ServiceModel.Channels.MessageVersion>.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="c8504-113">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="c8504-113">Child Elements</span></span>  
  
|<span data-ttu-id="c8504-114">Элемент</span><span class="sxs-lookup"><span data-stu-id="c8504-114">Element</span></span>|<span data-ttu-id="c8504-115">Описание</span><span class="sxs-lookup"><span data-stu-id="c8504-115">Description</span></span>|  
|-------------|-----------------|  
|[\<readerQuotas>](/previous-versions/dotnet/netframework-4.0/ms731325(v=vs.100))|<span data-ttu-id="c8504-116">Определяет ограничения по сложности сообщений SOAP, которые могут обрабатываться конечными точками, настроенными с использованием этой привязки.</span><span class="sxs-lookup"><span data-stu-id="c8504-116">Defines the constraints on the complexity of SOAP messages that can be processed by endpoints configured with this binding.</span></span> <span data-ttu-id="c8504-117">Это элемент типа <xref:System.ServiceModel.Configuration.XmlDictionaryReaderQuotasElement>.</span><span class="sxs-lookup"><span data-stu-id="c8504-117">This element is of type <xref:System.ServiceModel.Configuration.XmlDictionaryReaderQuotasElement>.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="c8504-118">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="c8504-118">Parent Elements</span></span>  
  
|<span data-ttu-id="c8504-119">Элемент</span><span class="sxs-lookup"><span data-stu-id="c8504-119">Element</span></span>|<span data-ttu-id="c8504-120">Описание</span><span class="sxs-lookup"><span data-stu-id="c8504-120">Description</span></span>|  
|-------------|-----------------|  
|[\<binding>](bindings.md)|<span data-ttu-id="c8504-121">Определяет все возможности пользовательской привязки.</span><span class="sxs-lookup"><span data-stu-id="c8504-121">Defines all binding capabilities of the custom binding.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="c8504-122">См. также</span><span class="sxs-lookup"><span data-stu-id="c8504-122">See also</span></span>

- <xref:System.ServiceModel.Configuration.ByteStreamMessageEncodingElement>
- <xref:System.ServiceModel.Channels.CustomBinding>
- <xref:System.ServiceModel.Channels.MessageEncodingBindingElement>
- <xref:System.ServiceModel.Channels.ByteStreamMessageEncodingBindingElement>
- [<span data-ttu-id="c8504-123">Message Encoding</span><span class="sxs-lookup"><span data-stu-id="c8504-123">Message Encoding</span></span>](message-encoding.md)
- [<span data-ttu-id="c8504-124">Выбор кодировщика сообщений</span><span class="sxs-lookup"><span data-stu-id="c8504-124">Choosing a Message Encoder</span></span>](../../../wcf/feature-details/choosing-a-message-encoder.md)
- [<span data-ttu-id="c8504-125">Привязки</span><span class="sxs-lookup"><span data-stu-id="c8504-125">Bindings</span></span>](../../../wcf/bindings.md)
- [<span data-ttu-id="c8504-126">Расширение привязок</span><span class="sxs-lookup"><span data-stu-id="c8504-126">Extending Bindings</span></span>](../../../wcf/extending/extending-bindings.md)
- [<span data-ttu-id="c8504-127">Пользовательские привязки</span><span class="sxs-lookup"><span data-stu-id="c8504-127">Custom Bindings</span></span>](../../../wcf/extending/custom-bindings.md)
- [\<customBinding>](custombinding.md)
