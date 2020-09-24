---
title: <textMessageEncoding>
ms.date: 03/30/2017
ms.assetid: e6d834d0-356e-45eb-b530-bbefbb9ec3f0
ms.openlocfilehash: 159c581955336575af87a66a796cb78dd35d09c7
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/24/2020
ms.locfileid: "91158660"
---
# \<textMessageEncoding>

<span data-ttu-id="4aa32-101">Указывает кодировку символов и управление версиями сообщений для текстовых сообщений XML.</span><span class="sxs-lookup"><span data-stu-id="4aa32-101">Specifies the character encoding and message versioning used for text-based XML messages.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<bindings>**](bindings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<customBinding>**](custombinding.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<binding>**\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<textMessageEncoding>**  
  
## <a name="syntax"></a><span data-ttu-id="4aa32-102">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="4aa32-102">Syntax</span></span>  
  
```xml  
<textMessageEncoding maxReadPoolSize="Integer"
                     maxWritePoolSize="Integer"
                     messageVersion="Soap11Addressing10/Soap12Addressing10"
                     writeEncoding="UnicodeFffeTextEncoding/Utf16TextEncoding/Utf8TextEncoding" />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="4aa32-103">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="4aa32-103">Attributes and Elements</span></span>  

 <span data-ttu-id="4aa32-104">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="4aa32-104">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="4aa32-105">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="4aa32-105">Attributes</span></span>  
  
|<span data-ttu-id="4aa32-106">Атрибут</span><span class="sxs-lookup"><span data-stu-id="4aa32-106">Attribute</span></span>|<span data-ttu-id="4aa32-107">Описание</span><span class="sxs-lookup"><span data-stu-id="4aa32-107">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="4aa32-108">maxReadPoolSize</span><span class="sxs-lookup"><span data-stu-id="4aa32-108">maxReadPoolSize</span></span>|<span data-ttu-id="4aa32-109">Целое число, задающее количество сообщений, которые можно читать одновременно, не выделяя памяти для новых модулей чтения.</span><span class="sxs-lookup"><span data-stu-id="4aa32-109">An integer that specifies how many messages can be read simultaneously without allocating new readers.</span></span> <span data-ttu-id="4aa32-110">Пул больших размеров повышает устойчивость системы при всплесках активности за счет большего рабочего набора.</span><span class="sxs-lookup"><span data-stu-id="4aa32-110">Larger pool sizes make the system more tolerant to activity spikes at the cost of a larger working set.</span></span> <span data-ttu-id="4aa32-111">Значение по умолчанию — 64.</span><span class="sxs-lookup"><span data-stu-id="4aa32-111">The default is 64.</span></span>|  
|<span data-ttu-id="4aa32-112">maxWritePoolSize</span><span class="sxs-lookup"><span data-stu-id="4aa32-112">maxWritePoolSize</span></span>|<span data-ttu-id="4aa32-113">Целое число, задающее количество сообщений, которые можно отправлять одновременно, не выделяя памяти для новых модулей записи.</span><span class="sxs-lookup"><span data-stu-id="4aa32-113">An integer that specifies how many messages can be sent simultaneously without allocating new writers.</span></span> <span data-ttu-id="4aa32-114">Пул больших размеров повышает устойчивость системы при всплесках активности за счет большего рабочего набора.</span><span class="sxs-lookup"><span data-stu-id="4aa32-114">Larger pool sizes make the system more tolerant to activity spikes at the cost of a larger working set.</span></span> <span data-ttu-id="4aa32-115">Значение по умолчанию равно 16.</span><span class="sxs-lookup"><span data-stu-id="4aa32-115">The default is 16.</span></span>|  
|<span data-ttu-id="4aa32-116">messageVersion</span><span class="sxs-lookup"><span data-stu-id="4aa32-116">messageVersion</span></span>|<span data-ttu-id="4aa32-117">Задает версию SOAP сообщений, отправленных с помощью привязки.</span><span class="sxs-lookup"><span data-stu-id="4aa32-117">Specifies the SOAP version of the messages sent using the binding.</span></span> <span data-ttu-id="4aa32-118">Допустимы следующие значения:</span><span class="sxs-lookup"><span data-stu-id="4aa32-118">Valid values are</span></span><br /><br /> <span data-ttu-id="4aa32-119">- Soap11Addressing10</span><span class="sxs-lookup"><span data-stu-id="4aa32-119">-   Soap11Addressing10</span></span><br /><span data-ttu-id="4aa32-120">- Soap12Addressing10</span><span class="sxs-lookup"><span data-stu-id="4aa32-120">-   Soap12Addressing10</span></span><br /><span data-ttu-id="4aa32-121">-Soap11</span><span class="sxs-lookup"><span data-stu-id="4aa32-121">-   Soap11</span></span><br /><span data-ttu-id="4aa32-122">-Soap12</span><span class="sxs-lookup"><span data-stu-id="4aa32-122">-  Soap12</span></span><br /><br /><span data-ttu-id="4aa32-123">Значение по умолчанию - Soap12Addressing10.</span><span class="sxs-lookup"><span data-stu-id="4aa32-123">The default is Soap12Addressing10.</span></span> <span data-ttu-id="4aa32-124">Это атрибут типа <xref:System.ServiceModel.Channels.MessageVersion>.</span><span class="sxs-lookup"><span data-stu-id="4aa32-124">This attribute is of type <xref:System.ServiceModel.Channels.MessageVersion>.</span></span>|  
|<span data-ttu-id="4aa32-125">writeEncoding</span><span class="sxs-lookup"><span data-stu-id="4aa32-125">writeEncoding</span></span>|<span data-ttu-id="4aa32-126">Задает кодировку, используемую при отправке сообщений через привязку.</span><span class="sxs-lookup"><span data-stu-id="4aa32-126">Specifies the character set encoding to be used for emitting messages on the binding.</span></span> <span data-ttu-id="4aa32-127">Допустимы следующие значения:</span><span class="sxs-lookup"><span data-stu-id="4aa32-127">Valid values are</span></span><br /><br /> <span data-ttu-id="4aa32-128">-Уникодефффетекстенкодинг: Юникод байтов кодировка</span><span class="sxs-lookup"><span data-stu-id="4aa32-128">-   UnicodeFffeTextEncoding: Unicode BigEndian encoding</span></span><br /><span data-ttu-id="4aa32-129">-Utf16TextEncoding: Кодировка Юникода</span><span class="sxs-lookup"><span data-stu-id="4aa32-129">-   Utf16TextEncoding: Unicode encoding</span></span><br /><span data-ttu-id="4aa32-130">-Utf8TextEncoding: 8-разрядная кодировка</span><span class="sxs-lookup"><span data-stu-id="4aa32-130">-   Utf8TextEncoding: 8-bit encoding</span></span><br /><br /> <span data-ttu-id="4aa32-131">Значение по умолчанию - Utf8TextEncoding.</span><span class="sxs-lookup"><span data-stu-id="4aa32-131">The default is Utf8TextEncoding.</span></span> <span data-ttu-id="4aa32-132">Это атрибут типа <xref:System.Text.Encoding>.</span><span class="sxs-lookup"><span data-stu-id="4aa32-132">This attribute is of type <xref:System.Text.Encoding>.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="4aa32-133">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="4aa32-133">Child Elements</span></span>  
  
|<span data-ttu-id="4aa32-134">Элемент</span><span class="sxs-lookup"><span data-stu-id="4aa32-134">Element</span></span>|<span data-ttu-id="4aa32-135">Описание</span><span class="sxs-lookup"><span data-stu-id="4aa32-135">Description</span></span>|  
|-------------|-----------------|  
|[\<readerQuotas>](/previous-versions/dotnet/netframework-4.0/ms731325(v=vs.100))|<span data-ttu-id="4aa32-136">Определяет ограничения по сложности сообщений SOAP, которые могут обрабатываться конечными точками, настроенными с использованием этой привязки.</span><span class="sxs-lookup"><span data-stu-id="4aa32-136">Defines the constraints on the complexity of SOAP messages that can be processed by endpoints configured with this binding.</span></span> <span data-ttu-id="4aa32-137">Это элемент типа <xref:System.ServiceModel.Configuration.XmlDictionaryReaderQuotasElement>.</span><span class="sxs-lookup"><span data-stu-id="4aa32-137">This element is of type <xref:System.ServiceModel.Configuration.XmlDictionaryReaderQuotasElement>.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="4aa32-138">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="4aa32-138">Parent Elements</span></span>  
  
|<span data-ttu-id="4aa32-139">Элемент</span><span class="sxs-lookup"><span data-stu-id="4aa32-139">Element</span></span>|<span data-ttu-id="4aa32-140">Описание</span><span class="sxs-lookup"><span data-stu-id="4aa32-140">Description</span></span>|  
|-------------|-----------------|  
|[\<binding>](bindings.md)|<span data-ttu-id="4aa32-141">Определяет все возможности пользовательской привязки.</span><span class="sxs-lookup"><span data-stu-id="4aa32-141">Defines all binding capabilities of the custom binding.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="4aa32-142">Remarks</span><span class="sxs-lookup"><span data-stu-id="4aa32-142">Remarks</span></span>  

 <span data-ttu-id="4aa32-143">Кодирование — это процесс преобразования сообщения в последовательность байтов.</span><span class="sxs-lookup"><span data-stu-id="4aa32-143">Encoding is the process of transforming a message into a sequence of bytes.</span></span> <span data-ttu-id="4aa32-144">Декодирование представляет собой обратный процесс.</span><span class="sxs-lookup"><span data-stu-id="4aa32-144">Decoding is the reverse process.</span></span> <span data-ttu-id="4aa32-145">В Windows Communication Foundation (WCF) имеется три типа кодирования для сообщений SOAP: Text, Binary и MTOM.</span><span class="sxs-lookup"><span data-stu-id="4aa32-145">Windows Communication Foundation (WCF) includes three types of encoding for SOAP messages: Text, Binary and Message Transmission Optimization Mechanism (MTOM).</span></span>  
  
 <span data-ttu-id="4aa32-146">Кодировка текста, представленная элементом `textMessageEncoding`, дает наибольшие возможности взаимодействия, но является наименее эффективной для сообщений XML.</span><span class="sxs-lookup"><span data-stu-id="4aa32-146">The text encoding represented by the `textMessageEncoding` element is the most interoperable, but the least efficient encoder for XML messages.</span></span>  <span data-ttu-id="4aa32-147">Кодировщик текста создает текстовые сообщения в сети.</span><span class="sxs-lookup"><span data-stu-id="4aa32-147">The text encoder creates text-based messages on the wire.</span></span> <span data-ttu-id="4aa32-148">Сообщения, созданные этим кодировщиком, подходят для взаимодействия на базе +WS-\*.</span><span class="sxs-lookup"><span data-stu-id="4aa32-148">Messages produced by this encoder are suitable for WS-\* based interop.</span></span> <span data-ttu-id="4aa32-149">Веб-служба или клиент веб-службы в общем могут понимать XML в текстовом виде.</span><span class="sxs-lookup"><span data-stu-id="4aa32-149">Web service or Web service client can generally understand textual XML.</span></span> <span data-ttu-id="4aa32-150">Однако передача больших блоков двоичных данных в виде текста является наименее эффективным методом для кодировки сообщений XML.</span><span class="sxs-lookup"><span data-stu-id="4aa32-150">However, transmitting large blocks of binary data as text is the least efficient method for encoding XML messages.</span></span>  
  
## <a name="example"></a><span data-ttu-id="4aa32-151">Пример</span><span class="sxs-lookup"><span data-stu-id="4aa32-151">Example</span></span>  
  
```xml  
<textMessageEncoding maxReadPoolSize="211"
                     maxWritePoolSize="2132"
                     messageVersion="Soap12Addressing10"
                     textEncoding="utf-8" />
```  
  
## <a name="see-also"></a><span data-ttu-id="4aa32-152">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="4aa32-152">See also</span></span>

- <xref:System.ServiceModel.Configuration.TextMessageEncodingElement>
- <xref:System.ServiceModel.Channels.CustomBinding>
- <xref:System.ServiceModel.Channels.MessageEncodingBindingElement>
- <xref:System.ServiceModel.Channels.TextMessageEncodingBindingElement>
- [<span data-ttu-id="4aa32-153">Выбор кодировщика сообщений</span><span class="sxs-lookup"><span data-stu-id="4aa32-153">Choosing a Message Encoder</span></span>](../../../wcf/feature-details/choosing-a-message-encoder.md)
- [<span data-ttu-id="4aa32-154">Message Encoding</span><span class="sxs-lookup"><span data-stu-id="4aa32-154">Message Encoding</span></span>](message-encoding.md)
- [<span data-ttu-id="4aa32-155">Привязки</span><span class="sxs-lookup"><span data-stu-id="4aa32-155">Bindings</span></span>](../../../wcf/bindings.md)
- [<span data-ttu-id="4aa32-156">Расширение привязок</span><span class="sxs-lookup"><span data-stu-id="4aa32-156">Extending Bindings</span></span>](../../../wcf/extending/extending-bindings.md)
- [<span data-ttu-id="4aa32-157">Пользовательские привязки</span><span class="sxs-lookup"><span data-stu-id="4aa32-157">Custom Bindings</span></span>](../../../wcf/extending/custom-bindings.md)
- [\<customBinding>](custombinding.md)
