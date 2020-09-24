---
title: <windowsStreamSecurity>
ms.date: 03/30/2017
ms.assetid: 926bea29-90c7-4a26-9cf0-fb4aa44f6f70
ms.openlocfilehash: 3c82bd81bd0fabf10f2dd835188b346f62d038b5
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/24/2020
ms.locfileid: "91167084"
---
# \<windowsStreamSecurity>

<span data-ttu-id="18f06-101">Задает параметры безопасности потока Windows пользовательской привязки.</span><span class="sxs-lookup"><span data-stu-id="18f06-101">Specify Windows stream security settings of the custom binding.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<bindings>**](bindings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<customBinding>**](custombinding.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<binding>**\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<windowsStreamSecurity>**  
  
## <a name="syntax"></a><span data-ttu-id="18f06-102">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="18f06-102">Syntax</span></span>  
  
```xml  
<windowsStreamSecurity protectionLevel="None/Sign/EncryptAndSign" />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="18f06-103">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="18f06-103">Attributes and Elements</span></span>  

 <span data-ttu-id="18f06-104">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="18f06-104">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="18f06-105">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="18f06-105">Attributes</span></span>  
  
|<span data-ttu-id="18f06-106">Атрибут</span><span class="sxs-lookup"><span data-stu-id="18f06-106">Attribute</span></span>|<span data-ttu-id="18f06-107">Описание</span><span class="sxs-lookup"><span data-stu-id="18f06-107">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="18f06-108">protectionLevel</span><span class="sxs-lookup"><span data-stu-id="18f06-108">protectionLevel</span></span>|<span data-ttu-id="18f06-109">Определяет систему безопасности уровня сообщений.</span><span class="sxs-lookup"><span data-stu-id="18f06-109">Defines message-level security.</span></span> <span data-ttu-id="18f06-110">Подпись сообщений уменьшает риск подделки сообщения сторонними лицами при его передаче.</span><span class="sxs-lookup"><span data-stu-id="18f06-110">Signing messages mitigates the risk of a third party tampering with the message while it is being transferred.</span></span> <span data-ttu-id="18f06-111">Шифрование обеспечивает конфиденциальность на уровне данных во время транспортировки.</span><span class="sxs-lookup"><span data-stu-id="18f06-111">Encryption provides data-level privacy during transport.</span></span> <span data-ttu-id="18f06-112">Допустимые значения.</span><span class="sxs-lookup"><span data-stu-id="18f06-112">Valid values include the following:</span></span><br /><br /> <span data-ttu-id="18f06-113">-None: защита отсутствует.</span><span class="sxs-lookup"><span data-stu-id="18f06-113">-   None: No protection.</span></span><br /><span data-ttu-id="18f06-114">-Sign: сообщения подписываются.</span><span class="sxs-lookup"><span data-stu-id="18f06-114">-   Sign: Messages are signed.</span></span><br /><span data-ttu-id="18f06-115">-EncryptAndSign: сообщения подписываются и шифруются.</span><span class="sxs-lookup"><span data-stu-id="18f06-115">-   EncryptAndSign: Messages are signed and encrypted.</span></span><br /><br /> <span data-ttu-id="18f06-116">Значение по умолчанию - EncryptAndSign.</span><span class="sxs-lookup"><span data-stu-id="18f06-116">The default is EncryptAndSign.</span></span><br /><br /> <span data-ttu-id="18f06-117">Это атрибут типа <xref:System.Net.Security.ProtectionLevel>.</span><span class="sxs-lookup"><span data-stu-id="18f06-117">This attribute is of type <xref:System.Net.Security.ProtectionLevel>.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="18f06-118">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="18f06-118">Child Elements</span></span>  

 <span data-ttu-id="18f06-119">Нет</span><span class="sxs-lookup"><span data-stu-id="18f06-119">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="18f06-120">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="18f06-120">Parent Elements</span></span>  
  
|<span data-ttu-id="18f06-121">Элемент</span><span class="sxs-lookup"><span data-stu-id="18f06-121">Element</span></span>|<span data-ttu-id="18f06-122">Описание</span><span class="sxs-lookup"><span data-stu-id="18f06-122">Description</span></span>|  
|-------------|-----------------|  
|[\<binding>](bindings.md)|<span data-ttu-id="18f06-123">Определяет все возможности пользовательской привязки.</span><span class="sxs-lookup"><span data-stu-id="18f06-123">Defines all binding capabilities of the custom binding.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="18f06-124">Remarks</span><span class="sxs-lookup"><span data-stu-id="18f06-124">Remarks</span></span>  

 <span data-ttu-id="18f06-125">Транспорты, использующие такой поточно-ориентированный протокол, как TCP и именованные каналы, поддерживают потоковые обновления транспорта.</span><span class="sxs-lookup"><span data-stu-id="18f06-125">Transports that use a stream-oriented protocol such as TCP and named pipes support stream-based transport upgrades.</span></span> <span data-ttu-id="18f06-126">В частности, WCF обеспечивает обновления системы безопасности.</span><span class="sxs-lookup"><span data-stu-id="18f06-126">Specifically, WCF provides security upgrades.</span></span> <span data-ttu-id="18f06-127">Конфигурация этой защиты транспорта инкапсулирована этим элементом конфигурации, а также с [\<sslStreamSecurity>](sslstreamsecurity.md) , который можно настроить и добавить в пользовательскую привязку.</span><span class="sxs-lookup"><span data-stu-id="18f06-127">The configuration of this transport security is encapsulated by this configuration element  as well as by [\<sslStreamSecurity>](sslstreamsecurity.md), which can be configured and added to a custom binding</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="18f06-128">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="18f06-128">See also</span></span>

- <xref:System.ServiceModel.Channels.CustomBinding>
- <xref:System.ServiceModel.Configuration.WindowsStreamSecurityElement>
- <xref:System.ServiceModel.Channels.WindowsStreamSecurityBindingElement>
- [<span data-ttu-id="18f06-129">Привязки</span><span class="sxs-lookup"><span data-stu-id="18f06-129">Bindings</span></span>](../../../wcf/bindings.md)
- [<span data-ttu-id="18f06-130">Расширение привязок</span><span class="sxs-lookup"><span data-stu-id="18f06-130">Extending Bindings</span></span>](../../../wcf/extending/extending-bindings.md)
- [<span data-ttu-id="18f06-131">Пользовательские привязки</span><span class="sxs-lookup"><span data-stu-id="18f06-131">Custom Bindings</span></span>](../../../wcf/extending/custom-bindings.md)
- [\<customBinding>](custombinding.md)
