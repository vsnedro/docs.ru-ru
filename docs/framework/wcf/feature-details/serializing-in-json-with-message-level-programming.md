---
title: Сериализация в Json с помощью программирования на уровне сообщений
ms.date: 03/30/2017
ms.assetid: 5f940ba2-57ee-4c49-a779-957c5e7e71fa
ms.openlocfilehash: 8343f7a8aa3c01557aae7df420351fa318cbb4b5
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/26/2020
ms.locfileid: "96253938"
---
# <a name="serializing-in-json-with-message-level-programming"></a><span data-ttu-id="3b539-102">Сериализация в Json с помощью программирования на уровне сообщений</span><span class="sxs-lookup"><span data-stu-id="3b539-102">Serializing in Json with Message Level Programming</span></span>

<span data-ttu-id="3b539-103">WCF поддерживает сериализацию данных в формате JSON.</span><span class="sxs-lookup"><span data-stu-id="3b539-103">WCF supports serializing data in JSON format.</span></span> <span data-ttu-id="3b539-104">В этом разделе описывается, как в WCF выполнить сериализацию типов с помощью <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer>.</span><span class="sxs-lookup"><span data-stu-id="3b539-104">This topic describes how to tell WCF to serialize your types using the <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer>.</span></span>  
  
## <a name="typed-message-programming"></a><span data-ttu-id="3b539-105">Программирование типизированных сообщений</span><span class="sxs-lookup"><span data-stu-id="3b539-105">Typed Message Programming</span></span>  

 <span data-ttu-id="3b539-106"><xref:System.Runtime.Serialization.Json.DataContractJsonSerializer> используется, когда к операции службы применяется атрибут <xref:System.ServiceModel.Web.WebGetAttribute> или атрибут <xref:System.ServiceModel.Web.WebInvokeAttribute>.</span><span class="sxs-lookup"><span data-stu-id="3b539-106">The <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer> is used when the <xref:System.ServiceModel.Web.WebGetAttribute> or the <xref:System.ServiceModel.Web.WebInvokeAttribute> is applied to a service operation.</span></span> <span data-ttu-id="3b539-107">Оба атрибута позволяют задать формат запроса `RequestFormat` и формат ответа `ResponseFormat`.</span><span class="sxs-lookup"><span data-stu-id="3b539-107">Both of these attributes allow you to specify the `RequestFormat` and `ResponseFormat`.</span></span> <span data-ttu-id="3b539-108">Для использования JSON в запросах и ответах.</span><span class="sxs-lookup"><span data-stu-id="3b539-108">To use JSON for requests and responses.</span></span> <span data-ttu-id="3b539-109">Задайте для обоих свойств значение `WebMessageFormat.Json` .</span><span class="sxs-lookup"><span data-stu-id="3b539-109">set both of these to `WebMessageFormat.Json`.</span></span>  <span data-ttu-id="3b539-110">Чтобы использовать JSON, необходимо использовать <xref:System.ServiceModel.WebHttpBinding> , который автоматически настраивает <xref:System.ServiceModel.Description.WebHttpBehavior> .</span><span class="sxs-lookup"><span data-stu-id="3b539-110">In order to use JSON, you must use the <xref:System.ServiceModel.WebHttpBinding>, which automatically configures the <xref:System.ServiceModel.Description.WebHttpBehavior>.</span></span> <span data-ttu-id="3b539-111">Дополнительные сведения о сериализации WCF см. в разделе [сериализация и десериализация](serialization-and-deserialization.md).</span><span class="sxs-lookup"><span data-stu-id="3b539-111">For more information about WCF serialization, see [Serialization and Deserialization](serialization-and-deserialization.md).</span></span> <span data-ttu-id="3b539-112">Дополнительные сведения о JSON и WCF см. в разделе [служебная станция — введение в службы RESTful с помощью WCF](/archive/msdn-magazine/2009/january/service-station-an-introduction-to-restful-services-with-wcf).</span><span class="sxs-lookup"><span data-stu-id="3b539-112">For more information about JSON and WCF, see [Service Station - An Introduction To RESTful Services With WCF](/archive/msdn-magazine/2009/january/service-station-an-introduction-to-restful-services-with-wcf).</span></span>  
  
> [!IMPORTANT]
> <span data-ttu-id="3b539-113">Для использования с JSON требуется привязка <xref:System.ServiceModel.WebHttpBinding> и поведение <xref:System.ServiceModel.Description.WebHttpBehavior>, которые не поддерживают связь по протоколу SOAP.</span><span class="sxs-lookup"><span data-stu-id="3b539-113">Using JSON requires use of <xref:System.ServiceModel.WebHttpBinding> and <xref:System.ServiceModel.Description.WebHttpBehavior> which do not support SOAP communication.</span></span> <span data-ttu-id="3b539-114">Службы, взаимодействующие с, <xref:System.ServiceModel.WebHttpBinding> не поддерживают предоставление метаданных службы, поэтому вы не сможете использовать функциональные возможности Visual Studio Добавление ссылки на службу или программу командной строки Svcutil для создания прокси на стороне клиента.</span><span class="sxs-lookup"><span data-stu-id="3b539-114">Services that communicate with the <xref:System.ServiceModel.WebHttpBinding> do not support exposing service metadata so you will not be able to use Visual Studio’s Add Service Reference functionality or the svcutil command-line tool to generate a client-side proxy.</span></span> <span data-ttu-id="3b539-115">Дополнительные сведения о программном вызове служб, использующих <xref:System.ServiceModel.WebHttpBinding> , см. в разделе Использование [служб RESTFUL с WCF](/archive/blogs/pedram/how-to-consume-rest-services-with-wcf).</span><span class="sxs-lookup"><span data-stu-id="3b539-115">For more information how you can programmatically call services that use <xref:System.ServiceModel.WebHttpBinding>, see [How to Consume REST Services with WCF](/archive/blogs/pedram/how-to-consume-rest-services-with-wcf).</span></span>  
  
## <a name="untyped-message-programming"></a><span data-ttu-id="3b539-116">Программирование нетипизированных сообщений</span><span class="sxs-lookup"><span data-stu-id="3b539-116">Untyped Message Programming</span></span>  

 <span data-ttu-id="3b539-117">При работе напрямую с объектами нетипизированного сообщения следует явно задать свойства нетипизированного сообщения для его сериализации в виде JSON.</span><span class="sxs-lookup"><span data-stu-id="3b539-117">When working directly with untyped Message objects, you must explicitly set the properties on the untyped message to serialize it as JSON.</span></span> <span data-ttu-id="3b539-118">В следующем фрагменте кода показано, как это сделать.</span><span class="sxs-lookup"><span data-stu-id="3b539-118">The following code snippet shows how to do this.</span></span>  
  
```csharp
 Message response = Message.CreateMessage(  
                  MessageVersion.None,    // No SOAP message version  
                             "*",                     // SOAP action, ignored since this is JSON  
                             "Response string: JSON format specified", // Message body  
                             new DataContractJsonSerializer(typeof(string))); // Specify DataContractJsonSerializer  
      response.Properties.Add( WebBodyFormatMessageProperty.Name,
                    new WebBodyFormatMessageProperty(WebContentFormat.Json)); // Use JSON format  
```  
  
## <a name="see-also"></a><span data-ttu-id="3b539-119">См. также</span><span class="sxs-lookup"><span data-stu-id="3b539-119">See also</span></span>

- [<span data-ttu-id="3b539-120">Интеграция с AJAX и поддержка JSON</span><span class="sxs-lookup"><span data-stu-id="3b539-120">AJAX Integration and JSON Support</span></span>](ajax-integration-and-json-support.md)
- [<span data-ttu-id="3b539-121">Автономная сериализация JSON</span><span class="sxs-lookup"><span data-stu-id="3b539-121">Stand-Alone JSON Serialization</span></span>](stand-alone-json-serialization.md)
- [<span data-ttu-id="3b539-122">Сериализация JSON</span><span class="sxs-lookup"><span data-stu-id="3b539-122">JSON Serialization</span></span>](../samples/json-serialization.md)
