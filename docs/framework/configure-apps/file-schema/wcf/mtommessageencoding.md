---
title: <mtomMessageEncoding>
ms.date: 03/30/2017
ms.assetid: 7865d171-cd1e-430a-8421-39cc13541d1b
ms.openlocfilehash: 76b83381849b8519c1b758ef52c6d5c3f682f9b7
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/24/2020
ms.locfileid: "91204636"
---
# \<mtomMessageEncoding>

<span data-ttu-id="4be95-101">Определяет метод шифрования и управления версиями сообщений для сообщений, использующих механизм оптимизации передачи сообщений SOAP (MTOM).</span><span class="sxs-lookup"><span data-stu-id="4be95-101">Specifies the encoding and message versioning used for SOAP Message Transmission Optimization Mechanism (MTOM) based messages.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<bindings>**](bindings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<customBinding>**](custombinding.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<binding>**\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<mtomMessageEncoding>**  
  
## <a name="syntax"></a><span data-ttu-id="4be95-102">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="4be95-102">Syntax</span></span>  
  
```xml  
<mtomMessageEncoding maxBufferSize="Integer"
                     maxReadPoolSize="Integer"
                     maxWritePoolSize="Integer"
                     messageVersion="Soap11Addressing1/Soap12Addressing10"
                     writeEncoding="UnicodeFffeTextEncoding/Utf16TextEncoding/Utf8TextEncoding" />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="4be95-103">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="4be95-103">Attributes and Elements</span></span>  

 <span data-ttu-id="4be95-104">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="4be95-104">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="4be95-105">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="4be95-105">Attributes</span></span>  
  
|<span data-ttu-id="4be95-106">Атрибут</span><span class="sxs-lookup"><span data-stu-id="4be95-106">Attribute</span></span>|<span data-ttu-id="4be95-107">Описание</span><span class="sxs-lookup"><span data-stu-id="4be95-107">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="4be95-108">maxBufferSize</span><span class="sxs-lookup"><span data-stu-id="4be95-108">maxBufferSize</span></span>|<span data-ttu-id="4be95-109">Целое число, задающее максимальный допустимый размер буфера.</span><span class="sxs-lookup"><span data-stu-id="4be95-109">An integer that specifies the maximum size of the buffer that can be used.</span></span>|  
|<span data-ttu-id="4be95-110">maxReadPoolSize</span><span class="sxs-lookup"><span data-stu-id="4be95-110">maxReadPoolSize</span></span>|<span data-ttu-id="4be95-111">Целое число, задающее количество сообщений, которые можно читать одновременно, не выделяя памяти для новых модулей чтения.</span><span class="sxs-lookup"><span data-stu-id="4be95-111">An integer that specifies how many messages can be read simultaneously without allocating new readers.</span></span> <span data-ttu-id="4be95-112">Пул больших размеров повышает устойчивость системы при всплесках активности за счет большего рабочего набора.</span><span class="sxs-lookup"><span data-stu-id="4be95-112">Larger pool sizes make the system more tolerant to activity spikes at the cost of a larger working set.</span></span> <span data-ttu-id="4be95-113">Значение по умолчанию — 64.</span><span class="sxs-lookup"><span data-stu-id="4be95-113">The default is 64.</span></span>|  
|<span data-ttu-id="4be95-114">maxWritePoolSize</span><span class="sxs-lookup"><span data-stu-id="4be95-114">maxWritePoolSize</span></span>|<span data-ttu-id="4be95-115">Целое число, задающее количество сообщений, которые можно отправлять одновременно, не выделяя памяти для новых модулей записи.</span><span class="sxs-lookup"><span data-stu-id="4be95-115">An integer that specifies how many messages can be sent simultaneously without allocating new writers.</span></span> <span data-ttu-id="4be95-116">Пул больших размеров повышает устойчивость системы при всплесках активности за счет большего рабочего набора.</span><span class="sxs-lookup"><span data-stu-id="4be95-116">Larger pool sizes make the system more tolerant to activity spikes at the cost of a larger working set.</span></span> <span data-ttu-id="4be95-117">Значение по умолчанию равно 16.</span><span class="sxs-lookup"><span data-stu-id="4be95-117">The default is 16.</span></span>|  
|<span data-ttu-id="4be95-118">messageVersion</span><span class="sxs-lookup"><span data-stu-id="4be95-118">messageVersion</span></span>|<span data-ttu-id="4be95-119">Задает версию SOAP сообщений, отправленных с помощью привязки.</span><span class="sxs-lookup"><span data-stu-id="4be95-119">Specifies the SOAP version of the messages sent using the binding.</span></span> <span data-ttu-id="4be95-120">Допустимы следующие значения:</span><span class="sxs-lookup"><span data-stu-id="4be95-120">Valid values are</span></span><br /><br /> <span data-ttu-id="4be95-121">- Soap11Addressing1</span><span class="sxs-lookup"><span data-stu-id="4be95-121">-   Soap11Addressing1</span></span><br /><span data-ttu-id="4be95-122">- Soap12Addressing10</span><span class="sxs-lookup"><span data-stu-id="4be95-122">-   Soap12Addressing10</span></span><br /><br /> <span data-ttu-id="4be95-123">Значение по умолчанию - Soap12Addressing10.</span><span class="sxs-lookup"><span data-stu-id="4be95-123">The default is Soap12Addressing10.</span></span> <span data-ttu-id="4be95-124">Это атрибут типа <xref:System.ServiceModel.Channels.MessageVersion>.</span><span class="sxs-lookup"><span data-stu-id="4be95-124">This attribute is of type <xref:System.ServiceModel.Channels.MessageVersion>.</span></span>|  
|<span data-ttu-id="4be95-125">writeEncoding</span><span class="sxs-lookup"><span data-stu-id="4be95-125">writeEncoding</span></span>|<span data-ttu-id="4be95-126">Задает кодировку, используемую при отправке сообщений через привязку.</span><span class="sxs-lookup"><span data-stu-id="4be95-126">Specifies the character set encoding to be used for emitting messages on the binding.</span></span> <span data-ttu-id="4be95-127">Допустимы следующие значения:</span><span class="sxs-lookup"><span data-stu-id="4be95-127">Valid values are</span></span><br /><br /> <span data-ttu-id="4be95-128">-Уникодефффетекстенкодинг: Юникод байтов кодировка</span><span class="sxs-lookup"><span data-stu-id="4be95-128">-   UnicodeFffeTextEncoding: Unicode BigEndian encoding</span></span><br /><span data-ttu-id="4be95-129">-Utf16TextEncoding: Кодировка Юникода</span><span class="sxs-lookup"><span data-stu-id="4be95-129">-   Utf16TextEncoding: Unicode encoding</span></span><br /><span data-ttu-id="4be95-130">-Utf8TextEncoding: 8-разрядная кодировка</span><span class="sxs-lookup"><span data-stu-id="4be95-130">-   Utf8TextEncoding: 8-bit encoding</span></span><br /><br /> <span data-ttu-id="4be95-131">Значение по умолчанию - Utf8TextEncoding.</span><span class="sxs-lookup"><span data-stu-id="4be95-131">The default is Utf8TextEncoding.</span></span> <span data-ttu-id="4be95-132">Это атрибут типа <xref:System.Text.Encoding>.</span><span class="sxs-lookup"><span data-stu-id="4be95-132">This attribute is of type <xref:System.Text.Encoding>.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="4be95-133">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="4be95-133">Child Elements</span></span>  
  
|<span data-ttu-id="4be95-134">Элемент</span><span class="sxs-lookup"><span data-stu-id="4be95-134">Element</span></span>|<span data-ttu-id="4be95-135">Описание</span><span class="sxs-lookup"><span data-stu-id="4be95-135">Description</span></span>|  
|-------------|-----------------|  
|[\<readerQuotas>](/previous-versions/dotnet/netframework-4.0/ms731325(v=vs.100))|<span data-ttu-id="4be95-136">Определяет ограничения по сложности сообщений SOAP, которые могут обрабатываться конечными точками, настроенными с использованием этой привязки.</span><span class="sxs-lookup"><span data-stu-id="4be95-136">Defines the constraints on the complexity of SOAP messages that can be processed by endpoints configured with this binding.</span></span> <span data-ttu-id="4be95-137">Это элемент типа <xref:System.ServiceModel.Configuration.XmlDictionaryReaderQuotasElement>.</span><span class="sxs-lookup"><span data-stu-id="4be95-137">This element is of type <xref:System.ServiceModel.Configuration.XmlDictionaryReaderQuotasElement>.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="4be95-138">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="4be95-138">Parent Elements</span></span>  
  
|<span data-ttu-id="4be95-139">Элемент</span><span class="sxs-lookup"><span data-stu-id="4be95-139">Element</span></span>|<span data-ttu-id="4be95-140">Описание</span><span class="sxs-lookup"><span data-stu-id="4be95-140">Description</span></span>|  
|-------------|-----------------|  
|[\<binding>](bindings.md)|<span data-ttu-id="4be95-141">Определяет все возможности пользовательской привязки.</span><span class="sxs-lookup"><span data-stu-id="4be95-141">Defines all binding capabilities of the custom binding.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="4be95-142">Remarks</span><span class="sxs-lookup"><span data-stu-id="4be95-142">Remarks</span></span>  

 <span data-ttu-id="4be95-143">Кодирование — это процесс преобразования сообщения в последовательность байтов.</span><span class="sxs-lookup"><span data-stu-id="4be95-143">Encoding is the process of transforming a message into a sequence of bytes.</span></span> <span data-ttu-id="4be95-144">Декодирование представляет собой обратный процесс.</span><span class="sxs-lookup"><span data-stu-id="4be95-144">Decoding is the reverse process.</span></span> <span data-ttu-id="4be95-145">В Windows Communication Foundation (WCF) имеется три типа кодирования для сообщений SOAP: Text, Binary и MTOM.</span><span class="sxs-lookup"><span data-stu-id="4be95-145">Windows Communication Foundation (WCF) includes three types of encoding for SOAP messages: Text, Binary and Message Transmission Optimization Mechanism (MTOM).</span></span>  
  
 <span data-ttu-id="4be95-146">Элемент `MtomMessageEncoding` указывает кодировку символов, управление версиями сообщений и другие параметры для сообщений, использующих кодировку MTOM.</span><span class="sxs-lookup"><span data-stu-id="4be95-146">The `MtomMessageEncoding` element specifies the character encoding and message versioning and other settings used for messages using a Message Transmission Optimization Mechanism (MTOM) encoding.</span></span> <span data-ttu-id="4be95-147">MTOM - это эффективный способ передачи двоичных данных в сообщениях WCF.</span><span class="sxs-lookup"><span data-stu-id="4be95-147">MTOM is an efficient technology for transmitting binary data in WCF messages.</span></span> <span data-ttu-id="4be95-148">Кодировщик MTOM пытается сохранить баланс между эффективностью и совместимостью.</span><span class="sxs-lookup"><span data-stu-id="4be95-148">The MTOM encoder attempts to create a balance between efficiency and interoperability.</span></span> <span data-ttu-id="4be95-149">При кодировке MTOM большая часть XML-кода передается в текстовой форме, однако выполняется оптимизация больших блоков двоичных данных путем передачи их в исходном виде, без преобразования их в базовый формат base64.</span><span class="sxs-lookup"><span data-stu-id="4be95-149">The MTOM encoding transmits most XML in textual form, but optimizes large blocks of binary data by transmitting them as-is, without conversion to their base64 encoded format.</span></span>  
  
## <a name="example"></a><span data-ttu-id="4be95-150">Пример</span><span class="sxs-lookup"><span data-stu-id="4be95-150">Example</span></span>  
  
```xml  
<mtomMessageEncoding maxReadPoolSize="211"
                     maxWritePoolSize="2132"
                     messageVersion="Soap11Addressing10"
                     textEncoding="utf-8" />
```  
  
## <a name="see-also"></a><span data-ttu-id="4be95-151">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="4be95-151">See also</span></span>

- <xref:System.ServiceModel.Configuration.MtomMessageEncodingElement>
- <xref:System.ServiceModel.Channels.CustomBinding>
- <xref:System.ServiceModel.Channels.MessageEncodingBindingElement>
- <xref:System.ServiceModel.Channels.MtomMessageEncodingBindingElement>
- [<span data-ttu-id="4be95-152">Message Encoding</span><span class="sxs-lookup"><span data-stu-id="4be95-152">Message Encoding</span></span>](message-encoding.md)
- [<span data-ttu-id="4be95-153">Выбор кодировщика сообщений</span><span class="sxs-lookup"><span data-stu-id="4be95-153">Choosing a Message Encoder</span></span>](../../../wcf/feature-details/choosing-a-message-encoder.md)
- [<span data-ttu-id="4be95-154">Привязки</span><span class="sxs-lookup"><span data-stu-id="4be95-154">Bindings</span></span>](../../../wcf/bindings.md)
- [<span data-ttu-id="4be95-155">Расширение привязок</span><span class="sxs-lookup"><span data-stu-id="4be95-155">Extending Bindings</span></span>](../../../wcf/extending/extending-bindings.md)
- [<span data-ttu-id="4be95-156">Пользовательские привязки</span><span class="sxs-lookup"><span data-stu-id="4be95-156">Custom Bindings</span></span>](../../../wcf/extending/custom-bindings.md)
- [\<customBinding>](custombinding.md)
