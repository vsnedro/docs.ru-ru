---
title: <compositeDuplex>
ms.date: 03/30/2017
ms.assetid: 725004d1-ce88-4405-a220-78e89844f81f
ms.openlocfilehash: c3bae4dfee36e9de62c27bbccecd9a31a5b7d459
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/06/2020
ms.locfileid: "73736778"
---
# \<compositeDuplex>
<span data-ttu-id="b0786-101">Определяет элемент привязки, который используется, когда клиенту необходимо предоставить службе конечную точку для отправки сообщений обратно клиенту.</span><span class="sxs-lookup"><span data-stu-id="b0786-101">Defines the binding element that is used when the client must expose an endpoint for the service to send messages back to the client.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<bindings>**](bindings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<customBinding>**](custombinding.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<binding>**\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<compositeDuplex>**  
  
## <a name="syntax"></a><span data-ttu-id="b0786-102">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="b0786-102">Syntax</span></span>  
  
```xml  
<compositeDuplex clientBaseAddress="URI" />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="b0786-103">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="b0786-103">Attributes and Elements</span></span>  
 <span data-ttu-id="b0786-104">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="b0786-104">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="b0786-105">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="b0786-105">Attributes</span></span>  
  
|<span data-ttu-id="b0786-106">Атрибут</span><span class="sxs-lookup"><span data-stu-id="b0786-106">Attribute</span></span>|<span data-ttu-id="b0786-107">Описание:</span><span class="sxs-lookup"><span data-stu-id="b0786-107">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="b0786-108">clientBaseAddress</span><span class="sxs-lookup"><span data-stu-id="b0786-108">clientBaseAddress</span></span>|<span data-ttu-id="b0786-109">Универсальный код ресурса (URI), который задает адрес обратного канала при работе в дуплексном режиме.</span><span class="sxs-lookup"><span data-stu-id="b0786-109">A URI that sets the address of the back channel in duplex mode.</span></span> <span data-ttu-id="b0786-110">Служба использует данный адрес для осуществления контакта и создания подключения к клиенту.</span><span class="sxs-lookup"><span data-stu-id="b0786-110">The service uses this address to make contact and establish a connection with the client.</span></span><br /><br /> <span data-ttu-id="b0786-111">Если этот атрибут не задан, создается адрес по умолчанию `full qualified name+default port\TemporaryIndigoAddress\guid` .</span><span class="sxs-lookup"><span data-stu-id="b0786-111">If this attribute is not set, a default address "`full qualified name+default port\TemporaryIndigoAddress\guid`" is generated.</span></span> <span data-ttu-id="b0786-112">Значение по умолчанию — `null`.</span><span class="sxs-lookup"><span data-stu-id="b0786-112">The default is `null`.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="b0786-113">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="b0786-113">Child Elements</span></span>  
 <span data-ttu-id="b0786-114">Нет</span><span class="sxs-lookup"><span data-stu-id="b0786-114">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="b0786-115">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="b0786-115">Parent Elements</span></span>  
  
|<span data-ttu-id="b0786-116">Элемент</span><span class="sxs-lookup"><span data-stu-id="b0786-116">Element</span></span>|<span data-ttu-id="b0786-117">Описание</span><span class="sxs-lookup"><span data-stu-id="b0786-117">Description</span></span>|  
|-------------|-----------------|  
|[\<binding>](bindings.md)|<span data-ttu-id="b0786-118">Определяет все возможности пользовательской привязки.</span><span class="sxs-lookup"><span data-stu-id="b0786-118">Defines all binding capabilities of the custom binding.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="b0786-119">Примечания</span><span class="sxs-lookup"><span data-stu-id="b0786-119">Remarks</span></span>  
 <span data-ttu-id="b0786-120">Данный элемент конфигурации используется с теми типами транспорта, которые не имеют встроенной поддержки дуплексной связи, например HTTP.</span><span class="sxs-lookup"><span data-stu-id="b0786-120">This configuration element is used with transports that do not allow duplex communications natively, for example, HTTP.</span></span> <span data-ttu-id="b0786-121">Напротив, протокол TCP имеет встроенную поддержку дуплексной связи, и для него не требуется использовать этот элемент привязки для службы при отправке сообщений обратно клиенту.</span><span class="sxs-lookup"><span data-stu-id="b0786-121">TCP, by contrast, allows duplex communications natively, and does not require the use of this binding element for the service to send messages back to a client.</span></span>  
  
 <span data-ttu-id="b0786-122">Для осуществления контакта и установления подключения клиент должен предоставить службе адрес.</span><span class="sxs-lookup"><span data-stu-id="b0786-122">The client must expose an address for the service to make contact and establish a connection.</span></span> <span data-ttu-id="b0786-123">Этот адрес клиента предоставляется атрибутом `clientBaseAddress`.</span><span class="sxs-lookup"><span data-stu-id="b0786-123">This client address is provided by the `clientBaseAddress` attribute.</span></span> <span data-ttu-id="b0786-124">Обратите внимание, что Windows Communication Foundation (WCF) автоматически создает атрибут ClientBaseAddress в том случае, если он не был явно задан пользователем.</span><span class="sxs-lookup"><span data-stu-id="b0786-124">Note that Windows Communication Foundation (WCF) auto-generates a ClientBaseAddress if one is not explicitly set by the user.</span></span>  
  
## <a name="example"></a><span data-ttu-id="b0786-125">Пример</span><span class="sxs-lookup"><span data-stu-id="b0786-125">Example</span></span>  
  
```xml  
<compositeDuplex clientBaseAddress="http://www.contoso.com" />
```  
  
## <a name="see-also"></a><span data-ttu-id="b0786-126">См. также</span><span class="sxs-lookup"><span data-stu-id="b0786-126">See also</span></span>

- <xref:System.ServiceModel.Configuration.CompositeDuplexElement>
- <xref:System.ServiceModel.Channels.CompositeDuplexBindingElement>
- <xref:System.ServiceModel.Channels.CustomBinding>
- [<span data-ttu-id="b0786-127">Привязки</span><span class="sxs-lookup"><span data-stu-id="b0786-127">Bindings</span></span>](../../../wcf/bindings.md)
- [<span data-ttu-id="b0786-128">Расширение привязок</span><span class="sxs-lookup"><span data-stu-id="b0786-128">Extending Bindings</span></span>](../../../wcf/extending/extending-bindings.md)
- [<span data-ttu-id="b0786-129">Пользовательские привязки</span><span class="sxs-lookup"><span data-stu-id="b0786-129">Custom Bindings</span></span>](../../../wcf/extending/custom-bindings.md)
- [\<customBinding>](custombinding.md)
