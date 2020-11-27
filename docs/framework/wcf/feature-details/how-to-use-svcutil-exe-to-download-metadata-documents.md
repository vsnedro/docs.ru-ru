---
title: Практическое руководство. Использование Svcutil.exe для загрузки документов метаданных
description: Узнайте, как использовать Svcutil.exe для скачивания метаданных из выполняющихся служб и сохранения метаданных в локальные файлы.
ms.date: 03/30/2017
ms.assetid: 15524274-3167-4627-b722-d6cedb9fa8c6
ms.openlocfilehash: 449dd3023b5d688ed0de22e3651cccf16bee0c52
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/26/2020
ms.locfileid: "96280680"
---
# <a name="how-to-use-svcutilexe-to-download-metadata-documents"></a><span data-ttu-id="94212-103">Практическое руководство. Использование Svcutil.exe для загрузки документов метаданных</span><span class="sxs-lookup"><span data-stu-id="94212-103">How to: Use Svcutil.exe to Download Metadata Documents</span></span>

<span data-ttu-id="94212-104">Средство Svcutil.exe позволяет загружать метаданные из выполняющихся служб и сохранять эти метаданные в локальных файлах.</span><span class="sxs-lookup"><span data-stu-id="94212-104">You can use Svcutil.exe to download metadata from running services and to save the metadata to local files.</span></span> <span data-ttu-id="94212-105">Для схем URL-адресов HTTP и HTTPS Svcutil.exe пытается получить метаданные с помощью WS-MetadataExchange и [обнаружения веб-службы XML](/previous-versions/dotnet/netframework-4.0/fxx6cfx2(v=vs.100)).</span><span class="sxs-lookup"><span data-stu-id="94212-105">For HTTP and HTTPS URL schemes, Svcutil.exe attempts to retrieve metadata using WS-MetadataExchange and [XML Web Service Discovery](/previous-versions/dotnet/netframework-4.0/fxx6cfx2(v=vs.100)).</span></span> <span data-ttu-id="94212-106">Для всех остальных URL-схем средство Svcutil.exe использует только протокол WS-MetadataExchange.</span><span class="sxs-lookup"><span data-stu-id="94212-106">For all other URL schemes, Svcutil.exe uses only WS-MetadataExchange.</span></span>  
  
 <span data-ttu-id="94212-107">По умолчанию средство Svcutil.exe использует привязки, определенные в классе <xref:System.ServiceModel.Description.MetadataExchangeBindings>.</span><span class="sxs-lookup"><span data-stu-id="94212-107">By default, Svcutil.exe uses the bindings defined in the <xref:System.ServiceModel.Description.MetadataExchangeBindings> class.</span></span> <span data-ttu-id="94212-108">Чтобы настроить привязку, используемую для протокола WS-MetadataExchange, необходимо в файле конфигурации Svcutil.exe (svcutil.exe.config) настроить конечную точку клиента, которая бы использовала контракт `IMetadataExchange` и имя которой совпадало бы со схемой универсального кода ресурса (URI) адреса конечной точки метаданных.</span><span class="sxs-lookup"><span data-stu-id="94212-108">To configure the binding used for WS-MetadataExchange, you must define a client endpoint in the configuration file for Svcutil.exe (svcutil.exe.config) that uses the `IMetadataExchange` contract and that has the same name as the Uniform Resource Identifier (URI) scheme of the metadata endpoint address.</span></span>  
  
> [!CAUTION]
> <span data-ttu-id="94212-109">При запуске Svcutil.exe для получения метаданных для службы, которая предоставляет два разных контракта службы, каждая из которых содержит операцию с одним и тем же именем, Svcutil.exe выводит сообщение об ошибке "не удается получить метаданные из...." Например, если у вас есть служба, которая предоставляет контракт службы с именем `ICarService` , в котором есть операция `Get(Car c)` и та же служба предоставляет контракт службы с именем `IBookService` , который имеет операцию `Get(Book b)` .</span><span class="sxs-lookup"><span data-stu-id="94212-109">When running Svcutil.exe to get metadata for a service that exposes two different service contracts that each contain an operation of the same name, Svcutil.exe displays an error saying, "Cannot obtain Metadata from ...." For example, if you have a service that exposes a service contract called `ICarService` that has an operation `Get(Car c)` and the same service exposes a service contract called `IBookService` that has an operation `Get(Book b)`.</span></span> <span data-ttu-id="94212-110">Для обхода этой проблемы выполните одно из следующих действий.</span><span class="sxs-lookup"><span data-stu-id="94212-110">To work around this issue, do one of the following:</span></span>
>
> - <span data-ttu-id="94212-111">Переименуйте одну из операций.</span><span class="sxs-lookup"><span data-stu-id="94212-111">Rename one of the operations.</span></span>
> - <span data-ttu-id="94212-112">Задайте другое имя в свойстве <xref:System.ServiceModel.OperationContractAttribute.Name%2A>.</span><span class="sxs-lookup"><span data-stu-id="94212-112">Set the <xref:System.ServiceModel.OperationContractAttribute.Name%2A> to a different name.</span></span>
> - <span data-ttu-id="94212-113">Установите другое пространство имен для одной из операций с помощью свойства <xref:System.ServiceModel.ServiceContractAttribute.Namespace%2A>.</span><span class="sxs-lookup"><span data-stu-id="94212-113">Set one of the operations' namespaces to a different namespace using the <xref:System.ServiceModel.ServiceContractAttribute.Namespace%2A> property.</span></span>
  
## <a name="to-download-metadata-using-svcutilexe"></a><span data-ttu-id="94212-114">Загрузка метаданных с помощью средства Svcutil.exe</span><span class="sxs-lookup"><span data-stu-id="94212-114">To download metadata using Svcutil.exe</span></span>  
  
1. <span data-ttu-id="94212-115">Найдите средство Svcutil.exe в следующей папке:</span><span class="sxs-lookup"><span data-stu-id="94212-115">Locate the Svcutil.exe tool at the following location:</span></span>  
  
     <span data-ttu-id="94212-116">C:\Program Files\Microsoft SDKs\Windows\v1.0.\bin</span><span class="sxs-lookup"><span data-stu-id="94212-116">C:\Program Files\Microsoft SDKs\Windows\v1.0.\bin</span></span>  
  
2. <span data-ttu-id="94212-117">Из командной строки запустите средство, используя следующий формат.</span><span class="sxs-lookup"><span data-stu-id="94212-117">At the command prompt, launch the tool using the following format.</span></span>  
  
    ```console
    svcutil.exe /t:metadata  <url>* | <epr>  
    ```  
  
     <span data-ttu-id="94212-118">Параметр `/t:metadata` необходимо указать, чтобы загружались метаданные.</span><span class="sxs-lookup"><span data-stu-id="94212-118">You must specify the `/t:metadata` option to download metadata.</span></span> <span data-ttu-id="94212-119">В противном случае будут созданы код и конфигурация клиента.</span><span class="sxs-lookup"><span data-stu-id="94212-119">Otherwise, client code and configuration are generated.</span></span>  
  
3. <span data-ttu-id="94212-120">Аргумент <`url`>указывает URL-адрес конечной точки службы, предоставляющей метаданные, или документ метаданных, размещенный в сети.</span><span class="sxs-lookup"><span data-stu-id="94212-120">The <`url`>argument specifies the URL to a service endpoint that provides metadata or to a metadata document hosted online.</span></span> <span data-ttu-id="94212-121">Аргумент <`epr`> указывает путь к XML-файлу, содержащему WS-Addressing `EndpointAddress` для конечной точки службы, которая поддерживает WS-MetadataExchange.</span><span class="sxs-lookup"><span data-stu-id="94212-121">The <`epr`> argument specifies the path to an XML file that contains a WS-Addressing `EndpointAddress` for a service endpoint that supports WS-MetadataExchange.</span></span>  
  
 <span data-ttu-id="94212-122">Дополнительные сведения об использовании этого средства для скачивания метаданных см. в разделе [средство служебной программы метаданных ServiceModel (Svcutil.exe)](../servicemodel-metadata-utility-tool-svcutil-exe.md).</span><span class="sxs-lookup"><span data-stu-id="94212-122">For more options about using this tool for metadata download, see [ServiceModel Metadata Utility Tool (Svcutil.exe)](../servicemodel-metadata-utility-tool-svcutil-exe.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="94212-123">Пример</span><span class="sxs-lookup"><span data-stu-id="94212-123">Example</span></span>  

 <span data-ttu-id="94212-124">Следующая команда позволяет загрузить документы с метаданными из выполняющейся службы.</span><span class="sxs-lookup"><span data-stu-id="94212-124">The following command downloads metadata documents from a running service.</span></span>  
  
```console
svcutil /t:metadata http://service/metadataEndpoint  
```  
  
## <a name="see-also"></a><span data-ttu-id="94212-125">См. также</span><span class="sxs-lookup"><span data-stu-id="94212-125">See also</span></span>

- [<span data-ttu-id="94212-126">Служебное средство ServiceModel Metadata Utility Tool (Svcutil.exe)</span><span class="sxs-lookup"><span data-stu-id="94212-126">ServiceModel Metadata Utility Tool (Svcutil.exe)</span></span>](../servicemodel-metadata-utility-tool-svcutil-exe.md)
