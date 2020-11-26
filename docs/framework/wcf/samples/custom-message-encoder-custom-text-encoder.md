---
title: 'Пользовательский кодировщик сообщений: пользовательский кодировщик текста'
description: Используйте этот пример для реализации пользовательского кодировщика текстовых сообщений с помощью WCF. Этот кодировщик поддерживает все кодировки символов, поддерживаемые платформой, для взаимодействия.
ms.date: 03/30/2017
ms.assetid: 68ff5c74-3d33-4b44-bcae-e1d2f5dea0de
ms.openlocfilehash: 89f0bf09ba6408e24f642a67f2e7ac8243608dcb
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/26/2020
ms.locfileid: "96240970"
---
# <a name="custom-message-encoder-custom-text-encoder"></a><span data-ttu-id="3cb8a-104">Пользовательский кодировщик сообщений: пользовательский кодировщик текста</span><span class="sxs-lookup"><span data-stu-id="3cb8a-104">Custom Message Encoder: Custom Text Encoder</span></span>

<span data-ttu-id="3cb8a-105">В этом примере демонстрируется реализация пользовательского кодировщика текстовых сообщений с помощью Windows Communication Foundation (WCF).</span><span class="sxs-lookup"><span data-stu-id="3cb8a-105">This sample demonstrates how to implement a custom text message encoder using Windows Communication Foundation (WCF).</span></span>

> [!WARNING]
> <span data-ttu-id="3cb8a-106">Образцы уже могут быть установлены на компьютере.</span><span class="sxs-lookup"><span data-stu-id="3cb8a-106">The samples may already be installed on your machine.</span></span> <span data-ttu-id="3cb8a-107">Перед продолжением проверьте следующий каталог (по умолчанию).</span><span class="sxs-lookup"><span data-stu-id="3cb8a-107">Check for the following (default) directory before continuing.</span></span>
>
> `<InstallDrive>:\WF_WCF_Samples`
>
> <span data-ttu-id="3cb8a-108">Если этот каталог не существует, перейдите к [примерам Windows Communication Foundation (WCF) и Windows Workflow Foundation (WF) для .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) , чтобы скачать все Windows Communication Foundation (WCF) и [!INCLUDE[wf1](../../../../includes/wf1-md.md)] примеры.</span><span class="sxs-lookup"><span data-stu-id="3cb8a-108">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) to download all Windows Communication Foundation (WCF) and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="3cb8a-109">Этот образец расположен в следующем каталоге.</span><span class="sxs-lookup"><span data-stu-id="3cb8a-109">This sample is located in the following directory.</span></span>
>
> `<InstallDrive>:\WF_WCF_Samples\WCF\Extensibility\MessageEncoder\Text`

<span data-ttu-id="3cb8a-110"><xref:System.ServiceModel.Channels.TextMessageEncodingBindingElement>Платформа WCF поддерживает только кодировки Юникод UTF-8, UTF-16 и Big-endian с обратным порядком байтов.</span><span class="sxs-lookup"><span data-stu-id="3cb8a-110">The <xref:System.ServiceModel.Channels.TextMessageEncodingBindingElement> of WCF supports only the UTF-8, UTF-16 and big-endian Unicode encodings.</span></span> <span data-ttu-id="3cb8a-111">Кодировщик настраиваемых текстовых сообщений в этом примере поддерживает все кодировки символов, поддерживаемые платформой, которые могут потребоваться для взаимодействия.</span><span class="sxs-lookup"><span data-stu-id="3cb8a-111">The custom text message encoder in this sample supports all platform-supported character encodings that may be required for interoperability.</span></span> <span data-ttu-id="3cb8a-112">Пример состоит из клиентской консоли (exe), библиотеки служб (. dll), размещенной службы IIS (IIS), и библиотеки кодировщика текстовых сообщений (. dll).</span><span class="sxs-lookup"><span data-stu-id="3cb8a-112">The sample consists of a client console program (.exe), a service library (.dll) hosted by Internet Information Services (IIS), and a text message encoder library (.dll).</span></span> <span data-ttu-id="3cb8a-113">Служба реализует контракт, определяющий шаблон взаимодействия "запрос-ответ".</span><span class="sxs-lookup"><span data-stu-id="3cb8a-113">The service implements a contract that defines a request-reply communication pattern.</span></span> <span data-ttu-id="3cb8a-114">Контракт определяется интерфейсом `ICalculator`, который предоставляет математические операции (добавить, вычесть, умножить и разделить).</span><span class="sxs-lookup"><span data-stu-id="3cb8a-114">The contract is defined by the `ICalculator` interface, which exposes math operations (Add, Subtract, Multiply, and Divide).</span></span> <span data-ttu-id="3cb8a-115">Клиент осуществляет синхронные вызовы заданной математической операции, а служба отправляет в ответ результат.</span><span class="sxs-lookup"><span data-stu-id="3cb8a-115">The client makes synchronous requests to a given math operation and the service replies with the result.</span></span> <span data-ttu-id="3cb8a-116">Как клиент, так и служба используют кодировщик `CustomTextMessageEncoder` вместо кодировщика по умолчанию <xref:System.ServiceModel.Channels.TextMessageEncodingBindingElement>.</span><span class="sxs-lookup"><span data-stu-id="3cb8a-116">Both client and service uses the `CustomTextMessageEncoder` instead of the default <xref:System.ServiceModel.Channels.TextMessageEncodingBindingElement>.</span></span>

<span data-ttu-id="3cb8a-117">Реализация пользовательского кодировщика состоит из фабрики кодировщиков сообщений, кодировщика сообщений, элемента привязки кодировщика сообщений и обработчика конфигурации. При этом демонстрируются следующие операции.</span><span class="sxs-lookup"><span data-stu-id="3cb8a-117">The custom encoder implementation consists of a message encoder factory, a message encoder, a message encoding binding element and a configuration handler, and demonstrates the following:</span></span>

- <span data-ttu-id="3cb8a-118">Построение пользовательского кодировщика и фабрики кодировщика.</span><span class="sxs-lookup"><span data-stu-id="3cb8a-118">Building a custom encoder and encoder factory.</span></span>

- <span data-ttu-id="3cb8a-119">Создание элемента привязки для пользовательского кодировщика.</span><span class="sxs-lookup"><span data-stu-id="3cb8a-119">Creating a binding element for a custom encoder.</span></span>

- <span data-ttu-id="3cb8a-120">Использование конфигурации пользовательской привязки для интеграции элементов пользовательской привязки.</span><span class="sxs-lookup"><span data-stu-id="3cb8a-120">Using the custom binding configuration for integrating custom binding elements.</span></span>

- <span data-ttu-id="3cb8a-121">Разработка обработчика пользовательской конфигурации для обеспечения настройки элемента пользовательской привязки в файле.</span><span class="sxs-lookup"><span data-stu-id="3cb8a-121">Developing a custom configuration handler to allow file configuration of a custom binding element.</span></span>

## <a name="to-set-up-build-and-run-the-sample"></a><span data-ttu-id="3cb8a-122">Настройка, сборка и выполнение образца</span><span class="sxs-lookup"><span data-stu-id="3cb8a-122">To set up, build, and run the sample</span></span>

1. <span data-ttu-id="3cb8a-123">Установите ASP.NET 4,0 с помощью следующей команды.</span><span class="sxs-lookup"><span data-stu-id="3cb8a-123">Install ASP.NET 4.0 using the following command.</span></span>

    ```console
    %windir%\Microsoft.NET\Framework\v4.0.XXXXX\aspnet_regiis.exe /i /enable
    ```

2. <span data-ttu-id="3cb8a-124">Убедитесь, что вы выполнили [однократную процедуру настройки для Windows Communication Foundation примеров](one-time-setup-procedure-for-the-wcf-samples.md).</span><span class="sxs-lookup"><span data-stu-id="3cb8a-124">Ensure that you have performed the [One-Time Setup Procedure for the Windows Communication Foundation Samples](one-time-setup-procedure-for-the-wcf-samples.md).</span></span>

3. <span data-ttu-id="3cb8a-125">Чтобы выполнить сборку решения, следуйте инструкциям в разделе [Создание примеров Windows Communication Foundation](building-the-samples.md).</span><span class="sxs-lookup"><span data-stu-id="3cb8a-125">To build the solution, follow the instructions in [Building the Windows Communication Foundation Samples](building-the-samples.md).</span></span>

4. <span data-ttu-id="3cb8a-126">Чтобы запустить пример в конфигурации с одним или несколькими компьютерами, следуйте инструкциям в разделе [выполнение примеров Windows Communication Foundation](running-the-samples.md).</span><span class="sxs-lookup"><span data-stu-id="3cb8a-126">To run the sample in a single- or cross-machine configuration, follow the instructions in [Running the Windows Communication Foundation Samples](running-the-samples.md).</span></span>

## <a name="message-encoder-factory-and-the-message-encoder"></a><span data-ttu-id="3cb8a-127">Фабрика кодировщика сообщений и кодировщик сообщений</span><span class="sxs-lookup"><span data-stu-id="3cb8a-127">Message Encoder Factory and the Message Encoder</span></span>

<span data-ttu-id="3cb8a-128">При открытии <xref:System.ServiceModel.ServiceHost> или канала клиента компонент времени разработки `CustomTextMessageBindingElement` создает фабрику `CustomTextMessageEncoderFactory`.</span><span class="sxs-lookup"><span data-stu-id="3cb8a-128">When the <xref:System.ServiceModel.ServiceHost> or the client channel is opened, the design time component `CustomTextMessageBindingElement` creates the `CustomTextMessageEncoderFactory`.</span></span> <span data-ttu-id="3cb8a-129">Фабрика создает кодировщик `CustomTextMessageEncoder`.</span><span class="sxs-lookup"><span data-stu-id="3cb8a-129">The factory creates the `CustomTextMessageEncoder`.</span></span> <span data-ttu-id="3cb8a-130">Кодировщик сообщений работает как в режиме буферизации, так и в режиме потоковой передачи.</span><span class="sxs-lookup"><span data-stu-id="3cb8a-130">The message encoder operates both in the streaming mode and the buffered mode.</span></span> <span data-ttu-id="3cb8a-131">Он использует классы <xref:System.Xml.XmlReader> и <xref:System.Xml.XmlWriter> для чтения и записи сообщений соответственно.</span><span class="sxs-lookup"><span data-stu-id="3cb8a-131">It uses the <xref:System.Xml.XmlReader> and <xref:System.Xml.XmlWriter> to read and write the messages respectively.</span></span> <span data-ttu-id="3cb8a-132">В отличие от оптимизированных средств чтения и записи XML WCF, которые поддерживают только кодировку UTF-8, UTF-16 и Юникод с обратным порядком байтов, эти средства чтения и записи поддерживают всю поддерживаемую платформой кодирование.</span><span class="sxs-lookup"><span data-stu-id="3cb8a-132">As opposed to the optimized XML readers and writers of WCF that support only UTF-8, UTF-16 and big-endian Unicode, these readers and writers support all platform-supported encoding.</span></span>

<span data-ttu-id="3cb8a-133">В следующем примере кода показан кодировщик CustomTextMessageEncoder.</span><span class="sxs-lookup"><span data-stu-id="3cb8a-133">The following code example shows the CustomTextMessageEncoder.</span></span>

```csharp
public class CustomTextMessageEncoder : MessageEncoder
{
    private CustomTextMessageEncoderFactory factory;
    private XmlWriterSettings writerSettings;
    private string contentType;

    public CustomTextMessageEncoder(CustomTextMessageEncoderFactory factory)
    {
        this.factory = factory;

        this.writerSettings = new XmlWriterSettings();
        this.writerSettings.Encoding = Encoding.GetEncoding(factory.CharSet);
        this.contentType = $"{this.factory.MediaType}; charset={this.writerSettings.Encoding.HeaderName}";
    }

    public override string ContentType
    {
        get
        {
            return this.contentType;
        }
    }

    public override string MediaType
    {
        get
        {
            return factory.MediaType;
        }
    }

    public override MessageVersion MessageVersion
    {
        get
        {
            return this.factory.MessageVersion;
        }
    }

    public override Message ReadMessage(ArraySegment<byte> buffer, BufferManager bufferManager, string contentType)
    {
        byte[] msgContents = new byte[buffer.Count];
        Array.Copy(buffer.Array, buffer.Offset, msgContents, 0, msgContents.Length);
        bufferManager.ReturnBuffer(buffer.Array);

        MemoryStream stream = new MemoryStream(msgContents);
        return ReadMessage(stream, int.MaxValue);
    }

    public override Message ReadMessage(Stream stream, int maxSizeOfHeaders, string contentType)
    {
        XmlReader reader = XmlReader.Create(stream);
        return Message.CreateMessage(reader, maxSizeOfHeaders, this.MessageVersion);
    }

    public override ArraySegment<byte> WriteMessage(Message message, int maxMessageSize, BufferManager bufferManager, int messageOffset)
    {
        MemoryStream stream = new MemoryStream();
        XmlWriter writer = XmlWriter.Create(stream, this.writerSettings);
        message.WriteMessage(writer);
        writer.Close();

        byte[] messageBytes = stream.GetBuffer();
        int messageLength = (int)stream.Position;
        stream.Close();

        int totalLength = messageLength + messageOffset;
        byte[] totalBytes = bufferManager.TakeBuffer(totalLength);
        Array.Copy(messageBytes, 0, totalBytes, messageOffset, messageLength);

        ArraySegment<byte> byteArray = new ArraySegment<byte>(totalBytes, messageOffset, messageLength);
        return byteArray;
    }

    public override void WriteMessage(Message message, Stream stream)
    {
        XmlWriter writer = XmlWriter.Create(stream, this.writerSettings);
        message.WriteMessage(writer);
        writer.Close();
    }
}
```

<span data-ttu-id="3cb8a-134">В следующем примере кода показано, как построить фабрику кодировщиков сообщений.</span><span class="sxs-lookup"><span data-stu-id="3cb8a-134">The following code example shows how to build the message encoder factory.</span></span>

```csharp
public class CustomTextMessageEncoderFactory : MessageEncoderFactory
{
    private MessageEncoder encoder;
    private MessageVersion version;
    private string mediaType;
    private string charSet;

    internal CustomTextMessageEncoderFactory(string mediaType, string charSet,
        MessageVersion version)
    {
        this.version = version;
        this.mediaType = mediaType;
        this.charSet = charSet;
        this.encoder = new CustomTextMessageEncoder(this);
    }

    public override MessageEncoder Encoder
    {
        get
        {
            return this.encoder;
        }
    }

    public override MessageVersion MessageVersion
    {
        get
        {
            return this.version;
        }
    }

    internal string MediaType
    {
        get
        {
            return this.mediaType;
        }
    }

    internal string CharSet
    {
        get
        {
            return this.charSet;
        }
    }
}
```

## <a name="message-encoding-binding-element"></a><span data-ttu-id="3cb8a-135">Элемент привязки кодирования сообщений</span><span class="sxs-lookup"><span data-stu-id="3cb8a-135">Message Encoding Binding Element</span></span>

<span data-ttu-id="3cb8a-136">Элементы привязки позволяют настроить стек времени выполнения WCF.</span><span class="sxs-lookup"><span data-stu-id="3cb8a-136">The binding elements allow the configuration of the WCF run-time stack.</span></span> <span data-ttu-id="3cb8a-137">Чтобы использовать пользовательский кодировщик сообщений в приложении WCF, требуется элемент привязки, который создает фабрику кодировщиков сообщений с соответствующими параметрами на соответствующем уровне в стеке времени выполнения.</span><span class="sxs-lookup"><span data-stu-id="3cb8a-137">To use the custom message encoder in a WCF application, a binding element is required that creates the message encoder factory with the appropriate settings at the appropriate level in the run-time stack.</span></span>

<span data-ttu-id="3cb8a-138">Класс `CustomTextMessageBindingElement` является производным от базового класса <xref:System.ServiceModel.Channels.BindingElement> и наследует от класса <xref:System.ServiceModel.Channels.MessageEncodingBindingElement>.</span><span class="sxs-lookup"><span data-stu-id="3cb8a-138">The `CustomTextMessageBindingElement` derives from the <xref:System.ServiceModel.Channels.BindingElement> base class and inherits from the <xref:System.ServiceModel.Channels.MessageEncodingBindingElement> class.</span></span> <span data-ttu-id="3cb8a-139">Это позволяет другим компонентам WCF распознать этот элемент привязки как элемент привязки кодирования сообщений.</span><span class="sxs-lookup"><span data-stu-id="3cb8a-139">This allows other WCF components to recognize this binding element as being a message encoding binding element.</span></span> <span data-ttu-id="3cb8a-140">Реализация <xref:System.ServiceModel.Channels.MessageEncodingBindingElement.CreateMessageEncoderFactory%2A> возвращает экземпляр соответствующей фабрики кодировщиков сообщений с соответствующими параметрами.</span><span class="sxs-lookup"><span data-stu-id="3cb8a-140">The implementation of <xref:System.ServiceModel.Channels.MessageEncodingBindingElement.CreateMessageEncoderFactory%2A> returns an instance of the matching message encoder factory with appropriate settings.</span></span>

<span data-ttu-id="3cb8a-141">Элемент `CustomTextMessageBindingElement` предоставляет параметры для `MessageVersion`, `ContentType` и `Encoding` через свойства.</span><span class="sxs-lookup"><span data-stu-id="3cb8a-141">The `CustomTextMessageBindingElement` exposes settings for `MessageVersion`, `ContentType`, and `Encoding` through properties.</span></span> <span data-ttu-id="3cb8a-142">Кодировщик поддерживает версии Soap11Addressing и Soap12Addressing1.</span><span class="sxs-lookup"><span data-stu-id="3cb8a-142">The encoder supports both Soap11Addressing and Soap12Addressing1 versions.</span></span> <span data-ttu-id="3cb8a-143">Значение по умолчанию - Soap11Addressing1.</span><span class="sxs-lookup"><span data-stu-id="3cb8a-143">The default is Soap11Addressing1.</span></span> <span data-ttu-id="3cb8a-144">Значение по умолчанию `ContentType` - "text/xml".</span><span class="sxs-lookup"><span data-stu-id="3cb8a-144">The default value of the `ContentType` is "text/xml".</span></span> <span data-ttu-id="3cb8a-145">Свойство `Encoding` позволяет задать значение требуемой кодировки символов.</span><span class="sxs-lookup"><span data-stu-id="3cb8a-145">The `Encoding` property allows you to set the value of the desired character encoding.</span></span> <span data-ttu-id="3cb8a-146">В примере клиента и службы используется кодировка символов ISO-8859-1 (Latin1), которая не поддерживается в <xref:System.ServiceModel.Channels.TextMessageEncodingBindingElement> WCF.</span><span class="sxs-lookup"><span data-stu-id="3cb8a-146">The sample client and service uses the ISO-8859-1 (Latin1) character encoding, which is not supported by the <xref:System.ServiceModel.Channels.TextMessageEncodingBindingElement> of WCF.</span></span>

<span data-ttu-id="3cb8a-147">В следующем коде показано, как программным способом создать привязку, использующую пользовательский кодировщик текстовых сообщений.</span><span class="sxs-lookup"><span data-stu-id="3cb8a-147">The following code shows how to programmatically create the binding using the custom text message encoder.</span></span>

```csharp
ICollection<BindingElement> bindingElements = new List<BindingElement>();
HttpTransportBindingElement httpBindingElement = new HttpTransportBindingElement();
CustomTextMessageBindingElement textBindingElement = new CustomTextMessageBindingElement();
bindingElements.Add(textBindingElement);
bindingElements.Add(httpBindingElement);
CustomBinding binding = new CustomBinding(bindingElements);
```

## <a name="adding-metadata-support-to-the-message-encoding-binding-element"></a><span data-ttu-id="3cb8a-148">Добавление поддержки метаданных в элемент привязки кодирования сообщений</span><span class="sxs-lookup"><span data-stu-id="3cb8a-148">Adding Metadata Support to the Message Encoding Binding Element</span></span>

<span data-ttu-id="3cb8a-149">Любой тип, унаследованный от класса <xref:System.ServiceModel.Channels.MessageEncodingBindingElement>, отвечает за обновление версии привязки протокола SOAP в документе WSDL, созданном для службы.</span><span class="sxs-lookup"><span data-stu-id="3cb8a-149">Any type that derives from <xref:System.ServiceModel.Channels.MessageEncodingBindingElement> is responsible for updating the version of the SOAP binding in the WSDL document generated for the service.</span></span> <span data-ttu-id="3cb8a-150">Этого можно добиться, реализовав метод `ExportEndpoint` в интерфейсе <xref:System.ServiceModel.Description.IWsdlExportExtension>, а затем изменив созданный язык WSDL.</span><span class="sxs-lookup"><span data-stu-id="3cb8a-150">This is done by implementing the `ExportEndpoint` method on the <xref:System.ServiceModel.Description.IWsdlExportExtension> interface and then modifying the generated WSDL.</span></span> <span data-ttu-id="3cb8a-151">В этом образце `CustomTextMessageBindingElement` использует логику экспорта WSDL из `TextMessageEncodingBindingElement`.</span><span class="sxs-lookup"><span data-stu-id="3cb8a-151">In this sample, the `CustomTextMessageBindingElement` uses the WSDL export logic from the `TextMessageEncodingBindingElement`.</span></span>

<span data-ttu-id="3cb8a-152">В этом образце конфигурация клиента настраивается вручную.</span><span class="sxs-lookup"><span data-stu-id="3cb8a-152">For this sample, the client configuration is hand configured.</span></span> <span data-ttu-id="3cb8a-153">Для создания конфигурации клиента нельзя использовать средство Svcutil.exe, так как элемент `CustomTextMessageBindingElement` не экспортирует утверждение политики для описания своего поведения.</span><span class="sxs-lookup"><span data-stu-id="3cb8a-153">You cannot use Svcutil.exe to generate the client configuration because the `CustomTextMessageBindingElement` does not export a policy assertion to describe its behavior.</span></span> <span data-ttu-id="3cb8a-154">Обычно необходимо реализовать интерфейс <xref:System.ServiceModel.Description.IPolicyExportExtension> в пользовательском элементе привязки для экспорта пользовательского утверждения политики, которое описывает поведение или возможности, реализуемые элементом привязки.</span><span class="sxs-lookup"><span data-stu-id="3cb8a-154">You should generally implement the <xref:System.ServiceModel.Description.IPolicyExportExtension> interface on a custom binding element to export a custom policy assertion that describes the behavior or capability implemented by the binding element.</span></span> <span data-ttu-id="3cb8a-155">Пример экспорта утверждения политики для пользовательского элемента привязки см. в примере [Transport: UDP](transport-udp.md) .</span><span class="sxs-lookup"><span data-stu-id="3cb8a-155">For an example of how to export a policy assertion for a custom binding element, see the [Transport: UDP](transport-udp.md) sample.</span></span>

## <a name="message-encoding-binding-configuration-handler"></a><span data-ttu-id="3cb8a-156">Обработчик конфигурации привязки кодировщика сообщений</span><span class="sxs-lookup"><span data-stu-id="3cb8a-156">Message Encoding Binding Configuration Handler</span></span>

<span data-ttu-id="3cb8a-157">В предыдущем разделе показано, как использовать пользовательский кодировщик текстовых сообщений программно.</span><span class="sxs-lookup"><span data-stu-id="3cb8a-157">The previous section shows how to use the custom text message encoder programmatically.</span></span> <span data-ttu-id="3cb8a-158">`CustomTextMessageEncodingBindingSection` реализует обработчик конфигурации, позволяющий задать использование пользовательского кодировщика текстовых сообщений в файле конфигурации.</span><span class="sxs-lookup"><span data-stu-id="3cb8a-158">The `CustomTextMessageEncodingBindingSection` implements a configuration handler that allows you to specify the use of a custom text message encoder within a configuration file.</span></span> <span data-ttu-id="3cb8a-159">Класс `CustomTextMessageEncodingBindingSection` является производным от класса <xref:System.ServiceModel.Configuration.BindingElementExtensionElement> .</span><span class="sxs-lookup"><span data-stu-id="3cb8a-159">The `CustomTextMessageEncodingBindingSection` class derives from the <xref:System.ServiceModel.Configuration.BindingElementExtensionElement> class.</span></span> <span data-ttu-id="3cb8a-160">Свойство `BindingElementType` информирует систему конфигурации о типе элемента привязки, который следует создать для этого раздела.</span><span class="sxs-lookup"><span data-stu-id="3cb8a-160">The `BindingElementType` property informs the configuration system of the type of binding element to create for this section.</span></span>

<span data-ttu-id="3cb8a-161">Все параметры, определенные элементом `CustomTextMessageBindingElement`, представляются в виде свойств в разделе `CustomTextMessageEncodingBindingSection`.</span><span class="sxs-lookup"><span data-stu-id="3cb8a-161">All of the settings defined by `CustomTextMessageBindingElement` are exposed as the properties in the `CustomTextMessageEncodingBindingSection`.</span></span> <span data-ttu-id="3cb8a-162">Атрибут <xref:System.Configuration.ConfigurationPropertyAttribute> помогает при сопоставлении атрибутов элемента конфигурации со свойствами и при задании значений по умолчанию, если атрибут не задан.</span><span class="sxs-lookup"><span data-stu-id="3cb8a-162">The <xref:System.Configuration.ConfigurationPropertyAttribute> assists in mapping the configuration element attributes to the properties and setting default values if the attribute is not set.</span></span> <span data-ttu-id="3cb8a-163">После того как значения из конфигурации загружены и применены к свойствам нужного типа, вызывается метод <xref:System.ServiceModel.Configuration.BindingElementExtensionElement.CreateBindingElement%2A>, который преобразует свойства в конкретный экземпляр элемента привязки.</span><span class="sxs-lookup"><span data-stu-id="3cb8a-163">After the values from configuration are loaded and applied to the properties of the type, the <xref:System.ServiceModel.Configuration.BindingElementExtensionElement.CreateBindingElement%2A> method is called, which converts the properties into a concrete instance of a binding element.</span></span>

<span data-ttu-id="3cb8a-164">Этот обработчик конфигурации сопоставляет следующее представление в файле App.config или Web.config для службы или клиента.</span><span class="sxs-lookup"><span data-stu-id="3cb8a-164">This configuration handler maps to the following representation in the App.config or Web.config for the service or client.</span></span>

```xml
<customTextMessageEncoding encoding="utf-8" contentType="text/xml" messageVersion="Soap11Addressing1" />
```

<span data-ttu-id="3cb8a-165">В образце используется кодировка ISO-8859-1.</span><span class="sxs-lookup"><span data-stu-id="3cb8a-165">The sample uses the ISO-8859-1 encoding.</span></span>

<span data-ttu-id="3cb8a-166">Для использования этого обработчика конфигурации его необходимо зарегистрировать с помощью приведенного ниже элемента конфигурации.</span><span class="sxs-lookup"><span data-stu-id="3cb8a-166">To use this configuration handler it must be registered using the following configuration element.</span></span>

```xml
<extensions>
    <bindingElementExtensions>
        <add name="customTextMessageEncoding" type="
Microsoft.ServiceModel.Samples.CustomTextMessageEncodingBindingSection,
                  CustomTextMessageEncoder" />
    </bindingElementExtensions>
</extensions>
```
