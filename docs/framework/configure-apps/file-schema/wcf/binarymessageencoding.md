---
title: <binaryMessageEncoding>
ms.date: 03/30/2017
ms.assetid: e4ae3cd4-6b67-4ce1-af4b-9400e0a38dba
ms.openlocfilehash: 4179d7ac1919610b0be131b079b28da0cd9cad75
ms.sourcegitcommit: 27a15a55019f6b5f2733961738babe94aec0def3
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/15/2020
ms.locfileid: "90540299"
---
# \<binaryMessageEncoding>
<span data-ttu-id="42118-101">Определяет кодировщик двоичных сообщений, кодирующий сообщения Windows Communication Foundation (WCF) в двоичном формате в сети.</span><span class="sxs-lookup"><span data-stu-id="42118-101">Defines a binary message encoder that encodes Windows Communication Foundation (WCF) messages in binary on the wire.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<bindings>**](bindings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<customBinding>**](custombinding.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<binding>**\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<binaryMessageEncoding>**  
  
## <a name="syntax"></a><span data-ttu-id="42118-102">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="42118-102">Syntax</span></span>  
  
```xml  
<binaryMessageEncoding maxReadPoolSize="Integer"
                       maxSessionSize="Integer"
                       maxWritePoolSize="Integer"
                       messageVersion="Soap11Addressing10/Soap12Addressing10" />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="42118-103">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="42118-103">Attributes and Elements</span></span>  
 <span data-ttu-id="42118-104">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="42118-104">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="42118-105">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="42118-105">Attributes</span></span>  
  
|<span data-ttu-id="42118-106">Атрибут</span><span class="sxs-lookup"><span data-stu-id="42118-106">Attribute</span></span>|<span data-ttu-id="42118-107">Описание</span><span class="sxs-lookup"><span data-stu-id="42118-107">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="42118-108">maxReadPoolSize</span><span class="sxs-lookup"><span data-stu-id="42118-108">maxReadPoolSize</span></span>|<span data-ttu-id="42118-109">Целое число, определяющее количество сообщений, которые можно читать одновременно, не выделяя памяти для новых средств чтения.</span><span class="sxs-lookup"><span data-stu-id="42118-109">An integer that defines how many messages can be read simultaneously without allocating new readers.</span></span> <span data-ttu-id="42118-110">Пул больших размеров повышает устойчивость системы при всплесках активности за счет большего рабочего набора.</span><span class="sxs-lookup"><span data-stu-id="42118-110">Larger pool sizes make the system more tolerant to activity spikes at the cost of a larger working set.</span></span> <span data-ttu-id="42118-111">Значение по умолчанию — 64.</span><span class="sxs-lookup"><span data-stu-id="42118-111">The default is 64.</span></span>|  
|<span data-ttu-id="42118-112">maxSessionSize</span><span class="sxs-lookup"><span data-stu-id="42118-112">maxSessionSize</span></span>|<span data-ttu-id="42118-113">Положительное целое число, задающее размер буфера, используемого для кодирования (в байтах).</span><span class="sxs-lookup"><span data-stu-id="42118-113">A positive integer that sets the size, in bytes, of the buffer used for encoding.</span></span> <span data-ttu-id="42118-114">Буфер большего размера повышает скорость кодирования за счет размера рабочего набора.</span><span class="sxs-lookup"><span data-stu-id="42118-114">A larger buffer increases encoding speed at the expense of the size of the working set.</span></span> <span data-ttu-id="42118-115">Значение по умолчанию — 2048.</span><span class="sxs-lookup"><span data-stu-id="42118-115">The default is 2048.</span></span>|  
|<span data-ttu-id="42118-116">maxWritePoolSize</span><span class="sxs-lookup"><span data-stu-id="42118-116">maxWritePoolSize</span></span>|<span data-ttu-id="42118-117">Целое число, обозначающее количество сообщений, которые можно отправлять одновременно, не выделяя памяти для новых средств записи.</span><span class="sxs-lookup"><span data-stu-id="42118-117">An integer that defines how many messages can be sent simultaneously without allocating new writers.</span></span> <span data-ttu-id="42118-118">Пул больших размеров повышает устойчивость системы при всплесках активности за счет большего рабочего набора.</span><span class="sxs-lookup"><span data-stu-id="42118-118">Larger pool sizes make the system more tolerant to activity spikes at the cost of a larger working set.</span></span> <span data-ttu-id="42118-119">Значение по умолчанию равно 16.</span><span class="sxs-lookup"><span data-stu-id="42118-119">The default is 16.</span></span>|  
|<span data-ttu-id="42118-120">messageVersion</span><span class="sxs-lookup"><span data-stu-id="42118-120">messageVersion</span></span>|<span data-ttu-id="42118-121">Определяет используемые или ожидаемые версии сообщения SOAP и WS-Addressing.</span><span class="sxs-lookup"><span data-stu-id="42118-121">Specifies the SOAP message and WS-Addressing versions that are used or expected.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="42118-122">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="42118-122">Child Elements</span></span>  
  
|<span data-ttu-id="42118-123">Элемент</span><span class="sxs-lookup"><span data-stu-id="42118-123">Element</span></span>|<span data-ttu-id="42118-124">Описание</span><span class="sxs-lookup"><span data-stu-id="42118-124">Description</span></span>|  
|-------------|-----------------|  
|[\<readerQuotas>](/previous-versions/dotnet/netframework-4.0/ms731325(v=vs.100))|<span data-ttu-id="42118-125">Определяет ограничения по сложности сообщений SOAP, которые могут обрабатываться конечными точками, настроенными с использованием этой привязки.</span><span class="sxs-lookup"><span data-stu-id="42118-125">Defines the constraints on the complexity of SOAP messages that can be processed by endpoints configured with this binding.</span></span> <span data-ttu-id="42118-126">Это элемент типа <xref:System.ServiceModel.Configuration.XmlDictionaryReaderQuotasElement>.</span><span class="sxs-lookup"><span data-stu-id="42118-126">This element is of type <xref:System.ServiceModel.Configuration.XmlDictionaryReaderQuotasElement>.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="42118-127">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="42118-127">Parent Elements</span></span>  
  
|<span data-ttu-id="42118-128">Элемент</span><span class="sxs-lookup"><span data-stu-id="42118-128">Element</span></span>|<span data-ttu-id="42118-129">Описание</span><span class="sxs-lookup"><span data-stu-id="42118-129">Description</span></span>|  
|-------------|-----------------|  
|[\<binding>](bindings.md)|<span data-ttu-id="42118-130">Определяет все возможности пользовательской привязки.</span><span class="sxs-lookup"><span data-stu-id="42118-130">Defines all binding capabilities of the custom binding.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="42118-131">Примечания</span><span class="sxs-lookup"><span data-stu-id="42118-131">Remarks</span></span>  
 <span data-ttu-id="42118-132">Кодирование — это процесс преобразования сообщения в последовательность байтов.</span><span class="sxs-lookup"><span data-stu-id="42118-132">Encoding is the process of transforming a message into a sequence of bytes.</span></span> <span data-ttu-id="42118-133">Декодирование представляет собой обратный процесс.</span><span class="sxs-lookup"><span data-stu-id="42118-133">Decoding is the reverse process.</span></span> <span data-ttu-id="42118-134">В Windows Communication Foundation (WCF) имеется три типа кодирования для сообщений SOAP: Text, Binary и MTOM.</span><span class="sxs-lookup"><span data-stu-id="42118-134">Windows Communication Foundation (WCF) includes three types of encoding for SOAP messages: Text, Binary and Message Transmission Optimization Mechanism (MTOM).</span></span>  
  
 <span data-ttu-id="42118-135">Элемент `binaryMessageEncoding` указывает двоичный формат .NET для XML и содержит параметры, задающие кодировку символов и версию SOAP и WS-Addressing для использования.</span><span class="sxs-lookup"><span data-stu-id="42118-135">The `binaryMessageEncoding` element specifies the .NET Binary Format for XML and has options to specify the character encoding and the SOAP and WS-Addressing version to be used.</span></span> <span data-ttu-id="42118-136">Кодировщик двоичных сообщений кодирует сообщения Windows Communication Foundation (WCF) в двоичном формате в сети.</span><span class="sxs-lookup"><span data-stu-id="42118-136">The binary message encoder encodes Windows Communication Foundation (WCF) messages in binary on the wire.</span></span> <span data-ttu-id="42118-137">Результатом этой кодировки является очень быстрая передача сообщений, однако вследствие этого теряются возможности взаимодействия, основанные на стандартах WS-\*.</span><span class="sxs-lookup"><span data-stu-id="42118-137">While this encoding results in very fast transmission of messages, interoperability based on the WS-\* standards is lost.</span></span>  
  
## <a name="example"></a><span data-ttu-id="42118-138">Пример</span><span class="sxs-lookup"><span data-stu-id="42118-138">Example</span></span>  
  
```xml  
<binaryMessageEncoding maxReadPoolSize="211"
                       maxWritePoolSize="2132"
                       maxSessionSize="3141" />
```  
  
## <a name="see-also"></a><span data-ttu-id="42118-139">См. также</span><span class="sxs-lookup"><span data-stu-id="42118-139">See also</span></span>

- <xref:System.ServiceModel.Configuration.BinaryMessageEncodingElement>
- <xref:System.ServiceModel.Channels.CustomBinding>
- <xref:System.ServiceModel.Channels.MessageEncodingBindingElement>
- <xref:System.ServiceModel.Channels.BinaryMessageEncodingBindingElement>
- [<span data-ttu-id="42118-140">Message Encoding</span><span class="sxs-lookup"><span data-stu-id="42118-140">Message Encoding</span></span>](message-encoding.md)
- [<span data-ttu-id="42118-141">Выбор кодировщика сообщений</span><span class="sxs-lookup"><span data-stu-id="42118-141">Choosing a Message Encoder</span></span>](../../../wcf/feature-details/choosing-a-message-encoder.md)
- [<span data-ttu-id="42118-142">Привязки</span><span class="sxs-lookup"><span data-stu-id="42118-142">Bindings</span></span>](../../../wcf/bindings.md)
- [<span data-ttu-id="42118-143">Расширение привязок</span><span class="sxs-lookup"><span data-stu-id="42118-143">Extending Bindings</span></span>](../../../wcf/extending/extending-bindings.md)
- [<span data-ttu-id="42118-144">Пользовательские привязки</span><span class="sxs-lookup"><span data-stu-id="42118-144">Custom Bindings</span></span>](../../../wcf/extending/custom-bindings.md)
- [\<customBinding>](custombinding.md)
