---
title: <webMessageEncoding>
ms.date: 03/30/2017
ms.assetid: 892ca485-e21a-4a44-8e40-633161ef6796
ms.openlocfilehash: 1cdce48f51b25732c256d3c867f1bba801ec4d8c
ms.sourcegitcommit: 27a15a55019f6b5f2733961738babe94aec0def3
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/15/2020
ms.locfileid: "90545458"
---
# \<webMessageEncoding>
<span data-ttu-id="c33de-101">Обеспечивает чтение и запись сообщений в виде обычного текста XML, сообщений в кодировке JSON (нотация объектов JavaScript), а также необработанного двоичного содержимого, используемого в привязке Windows Communication Foundation (WCF).</span><span class="sxs-lookup"><span data-stu-id="c33de-101">Enables plain-text XML, JavaScript Object Notation (JSON) message encodings and "raw" binary content to be read and written when used in a Windows Communication Foundation (WCF) binding.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<bindings>**](bindings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<customBinding>**](custombinding.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<binding>**\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<webMessageEncoding>**  
  
## <a name="syntax"></a><span data-ttu-id="c33de-102">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="c33de-102">Syntax</span></span>  
  
```xml  
<webMessageEncoding maxReadPoolSize="Integer"
                    maxWritePoolSize="Integer"
                    writeEncoding="UnicodeFffeTextEncoding/Utf16TextEncoding/Utf8TextEncoding" />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="c33de-103">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="c33de-103">Attributes and Elements</span></span>  
 <span data-ttu-id="c33de-104">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="c33de-104">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="c33de-105">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="c33de-105">Attributes</span></span>  
  
|<span data-ttu-id="c33de-106">Атрибут</span><span class="sxs-lookup"><span data-stu-id="c33de-106">Attribute</span></span>|<span data-ttu-id="c33de-107">Описание</span><span class="sxs-lookup"><span data-stu-id="c33de-107">Description</span></span>|  
|---------------|-----------------|  
|`maxReadPoolSize`|<span data-ttu-id="c33de-108">Количество сообщений, которые можно читать одновременно, не выделяя памяти для новых обработчиков чтения.</span><span class="sxs-lookup"><span data-stu-id="c33de-108">The amount of messages that can be read simultaneously without allocating new readers.</span></span> <span data-ttu-id="c33de-109">Пул больших размеров повышает устойчивость системы при всплесках активности за счет большего рабочего набора.</span><span class="sxs-lookup"><span data-stu-id="c33de-109">Larger pool sizes make the system more tolerant to activity spikes at the cost of a larger working set.</span></span> <span data-ttu-id="c33de-110">Значение по умолчанию - 64 обработчика чтения для каждого из внутренних кодировщиков (простой текст, JSON, двоичное содержимое).</span><span class="sxs-lookup"><span data-stu-id="c33de-110">The default is 64 readers for each of the inner encoders (text, JSON, and "raw").</span></span><br /><br /> <span data-ttu-id="c33de-111">Увеличение этого числа увеличивает объем используемой памяти, однако подготавливает кодировщик к резким увеличениям количества входящих сообщений, позволяя использовать уже созданные обработчики чтения из пула, а не создавать новые.</span><span class="sxs-lookup"><span data-stu-id="c33de-111">Increasing this number increases memory consumption, but prepares the encoder to deal with sudden bursts of incoming messages because it is able to use readers from the pool that are already created instead of creating new ones.</span></span>|  
|`maxWritePoolSize`|<span data-ttu-id="c33de-112">Количество сообщений, которые можно отправить одновременно, не выделяя памяти для новых обработчиков записи.</span><span class="sxs-lookup"><span data-stu-id="c33de-112">The amount of messages that can be sent simultaneously without allocating new writers.</span></span> <span data-ttu-id="c33de-113">Пул больших размеров повышает устойчивость системы при всплесках активности за счет большего рабочего набора.</span><span class="sxs-lookup"><span data-stu-id="c33de-113">Larger pool sizes make the system more tolerant to activity spikes at the cost of a larger working set.</span></span> <span data-ttu-id="c33de-114">Значение по умолчанию - 16 обработчиков записи для каждого из внутренних кодировщиков (простой текст, JSON, двоичное содержимое).</span><span class="sxs-lookup"><span data-stu-id="c33de-114">The default is 16 writers for each of the inner encoders (text, JSON, and "raw").</span></span><br /><br /> <span data-ttu-id="c33de-115">Увеличение этого числа увеличивает объем используемой памяти, однако подготавливает кодировщик к резким увеличениям количества исходящих сообщений, позволяя использовать уже созданные обработчики записи из пула, а не создавать новые.</span><span class="sxs-lookup"><span data-stu-id="c33de-115">Increasing this number increases memory consumption, but prepares the encoder to deal with sudden bursts of outgoing messages because it is able to use writers from the pool that are already created instead of creating new ones.</span></span>|  
|`writeEncoding`|<span data-ttu-id="c33de-116">Задает кодировку, используемую при отправке сообщений через привязку.</span><span class="sxs-lookup"><span data-stu-id="c33de-116">Specifies the character set encoding to be used for emitting messages on the binding.</span></span> <span data-ttu-id="c33de-117">Допустимые значения:</span><span class="sxs-lookup"><span data-stu-id="c33de-117">Valid values are:</span></span><br /><br /> <span data-ttu-id="c33de-118">-Уникодефффетекстенкодинг: кодировка с обратным порядком байтов Юникода.</span><span class="sxs-lookup"><span data-stu-id="c33de-118">-   UnicodeFffeTextEncoding: Unicode Big Endian encoding.</span></span><br /><span data-ttu-id="c33de-119">-Utf16TextEncoding: Кодировка Юникода.</span><span class="sxs-lookup"><span data-stu-id="c33de-119">-   Utf16TextEncoding: Unicode encoding.</span></span><br /><span data-ttu-id="c33de-120">-Utf8TextEncoding: 8-разрядная кодировка.</span><span class="sxs-lookup"><span data-stu-id="c33de-120">-   Utf8TextEncoding: 8-bit encoding.</span></span><br /><br /> <span data-ttu-id="c33de-121">Значение по умолчанию - Utf8TextEncoding.</span><span class="sxs-lookup"><span data-stu-id="c33de-121">The default is Utf8TextEncoding.</span></span> <span data-ttu-id="c33de-122">Это атрибут типа <xref:System.Text.Encoding>.</span><span class="sxs-lookup"><span data-stu-id="c33de-122">This attribute is of type <xref:System.Text.Encoding>.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="c33de-123">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="c33de-123">Child Elements</span></span>  
  
|<span data-ttu-id="c33de-124">Элемент</span><span class="sxs-lookup"><span data-stu-id="c33de-124">Element</span></span>|<span data-ttu-id="c33de-125">Описание</span><span class="sxs-lookup"><span data-stu-id="c33de-125">Description</span></span>|  
|-------------|-----------------|  
|[\<readerQuotas>](/previous-versions/dotnet/netframework-4.0/ms731325(v=vs.100))|<span data-ttu-id="c33de-126">Определяет ограничения по сложности сообщений SOAP, которые могут обрабатываться конечными точками, настроенными с использованием этой привязки.</span><span class="sxs-lookup"><span data-stu-id="c33de-126">Defines the constraints on the complexity of SOAP messages that can be processed by endpoints configured with this binding.</span></span> <span data-ttu-id="c33de-127">Это элемент типа <xref:System.ServiceModel.Configuration.XmlDictionaryReaderQuotasElement>.</span><span class="sxs-lookup"><span data-stu-id="c33de-127">This element is of type <xref:System.ServiceModel.Configuration.XmlDictionaryReaderQuotasElement>.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="c33de-128">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="c33de-128">Parent Elements</span></span>  
  
|<span data-ttu-id="c33de-129">Элемент</span><span class="sxs-lookup"><span data-stu-id="c33de-129">Element</span></span>|<span data-ttu-id="c33de-130">Описание</span><span class="sxs-lookup"><span data-stu-id="c33de-130">Description</span></span>|  
|-------------|-----------------|  
|[\<binding>](bindings.md)|<span data-ttu-id="c33de-131">Определяет все возможности пользовательской привязки.</span><span class="sxs-lookup"><span data-stu-id="c33de-131">Defines all binding capabilities of the custom binding.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="c33de-132">Примечания</span><span class="sxs-lookup"><span data-stu-id="c33de-132">Remarks</span></span>  
 <span data-ttu-id="c33de-133">Кодирование — это процесс преобразования сообщения в последовательность байтов.</span><span class="sxs-lookup"><span data-stu-id="c33de-133">Encoding is the process of transforming a message into a sequence of bytes.</span></span> <span data-ttu-id="c33de-134">Декодирование представляет собой обратный процесс.</span><span class="sxs-lookup"><span data-stu-id="c33de-134">Decoding is the reverse process.</span></span> <span data-ttu-id="c33de-135">Эти процессы требуют определения кодировки символов.</span><span class="sxs-lookup"><span data-stu-id="c33de-135">These processes require the specification of a character encoding.</span></span>  
  
 <span data-ttu-id="c33de-136">Элемент `webMessageEncoding` работает путем делегирования набору внутренних кодировщиков обработки кодировок XML (в формате обычного текста), JSON и двоичных данных.</span><span class="sxs-lookup"><span data-stu-id="c33de-136">The `webMessageEncoding` element works by delegating to a series of inner encoders to handle the plain-text XML and JSON encodings, and "raw" binary data.</span></span> <span data-ttu-id="c33de-137">Делегирование выполняется с помощью составного кодировщика сообщений.</span><span class="sxs-lookup"><span data-stu-id="c33de-137">This delegation is done by a composite message encoder.</span></span>  
  
 <span data-ttu-id="c33de-138">Этот элемент привязки и его составной кодировщик используются для управления кодировкой в тех сценариях, где не применяется обмен сообщениями по протоколу SOAP, используемый элементом `webHttpBinding`.</span><span class="sxs-lookup"><span data-stu-id="c33de-138">This binding element and its composite encoder are used to control the encoding in scenarios that do not use SOAP messaging used by the `webHttpBinding` element.</span></span> <span data-ttu-id="c33de-139">К таким сценариям относятся: Plain Old XML (POX), REST (Representational State Transfer), RSS (Really Simple Syndication), синдикация Atom и AJAX (Asynchronous JavaScript and XML).</span><span class="sxs-lookup"><span data-stu-id="c33de-139">These scenarios include "Plain Old XML" (POX), Representational State Transfer (REST), Really Simple Syndication (RSS) and Atom syndication, and Asynchronous JavaScript and XML (AJAX).</span></span> <span data-ttu-id="c33de-140">Составной кодировщик сообщений не поддерживает SOAP и WS-Addressing.</span><span class="sxs-lookup"><span data-stu-id="c33de-140">The composite message encoder does not support SOAP or WS-Addressing.</span></span>  
  
 <span data-ttu-id="c33de-141">В элементе привязки можно задать кодировку записи с помощью атрибута `writeEncoding`.</span><span class="sxs-lookup"><span data-stu-id="c33de-141">The binding element can be configured with a write character encoding by using the `writeEncoding` attribute.</span></span> <span data-ttu-id="c33de-142">Предоставленное значение <xref:System.Text.Encoding> задает поведение при записи для форматов JSON и XML в текстовом виде.</span><span class="sxs-lookup"><span data-stu-id="c33de-142">The supplied <xref:System.Text.Encoding> value specifies the behavior on write for the JSON and Textual XML cases.</span></span> <span data-ttu-id="c33de-143">Для чтения поддерживается любая допустимая кодировка сообщений и кодировка текста.</span><span class="sxs-lookup"><span data-stu-id="c33de-143">On read, any valid message encoding and text encoding is understood.</span></span>  
  
 <span data-ttu-id="c33de-144">Атрибуты `maxReadPoolSize` и `maxWritePoolSize` также могут использоваться для установки максимального количества выделяемых обработчиков чтения и записи соответственно.</span><span class="sxs-lookup"><span data-stu-id="c33de-144">`maxReadPoolSize` and `maxWritePoolSize` can also be used to set the maximum number of readers and writers to be allocated respectively.</span></span> <span data-ttu-id="c33de-145">По умолчанию выделяется 64 обработчика чтения и 16 обработчиков записи.</span><span class="sxs-lookup"><span data-stu-id="c33de-145">By default 64 readers and 16 writers are allocated.</span></span>  
  
 <span data-ttu-id="c33de-146">Ограничения сложности по умолчанию также устанавливаются с помощью [\<readerQuotas>](/previous-versions/dotnet/netframework-4.0/ms731325(v=vs.100)) элемента для защиты от атак типа "отказ в обслуживании" (DOS), которые пытаются использовать сложность сообщения для связывания ресурсов обработки конечных точек.</span><span class="sxs-lookup"><span data-stu-id="c33de-146">Default complexity constraints are also set using the [\<readerQuotas>](/previous-versions/dotnet/netframework-4.0/ms731325(v=vs.100)) element to protect against a class of denial of service (DOS) attacks that attempt to use message complexity to tie up endpoint processing resources.</span></span>  
  
## <a name="example"></a><span data-ttu-id="c33de-147">Пример</span><span class="sxs-lookup"><span data-stu-id="c33de-147">Example</span></span>  
  
```xml  
<webMessageEncoding maxReadPoolSize="256"
                    maxWritePoolSize="128"
                    messageVersion="None"
                    textEncoding="utf-8" />
```  
  
## <a name="see-also"></a><span data-ttu-id="c33de-148">См. также</span><span class="sxs-lookup"><span data-stu-id="c33de-148">See also</span></span>

- <xref:System.ServiceModel.Configuration.WebMessageEncodingElement>
- <xref:System.ServiceModel.Channels.CustomBinding>
- <xref:System.ServiceModel.Channels.MessageEncodingBindingElement>
- <xref:System.ServiceModel.Channels.WebMessageEncodingBindingElement>
- [<span data-ttu-id="c33de-149">Message Encoding</span><span class="sxs-lookup"><span data-stu-id="c33de-149">Message Encoding</span></span>](message-encoding.md)
- [<span data-ttu-id="c33de-150">Выбор кодировщика сообщений</span><span class="sxs-lookup"><span data-stu-id="c33de-150">Choosing a Message Encoder</span></span>](../../../wcf/feature-details/choosing-a-message-encoder.md)
- [<span data-ttu-id="c33de-151">Привязки</span><span class="sxs-lookup"><span data-stu-id="c33de-151">Bindings</span></span>](../../../wcf/bindings.md)
- [<span data-ttu-id="c33de-152">Расширение привязок</span><span class="sxs-lookup"><span data-stu-id="c33de-152">Extending Bindings</span></span>](../../../wcf/extending/extending-bindings.md)
- [<span data-ttu-id="c33de-153">Пользовательские привязки</span><span class="sxs-lookup"><span data-stu-id="c33de-153">Custom Bindings</span></span>](../../../wcf/extending/custom-bindings.md)
- [\<customBinding>](custombinding.md)
