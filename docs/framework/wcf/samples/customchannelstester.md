---
title: CustomChannelsTester
ms.date: 03/30/2017
ms.assetid: ee1fa307-98b1-4647-8860-2e9217ba6082
ms.openlocfilehash: 9123167e0f97592592765f7b4a4aa768064fc173
ms.sourcegitcommit: cdb295dd1db589ce5169ac9ff096f01fd0c2da9d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/09/2020
ms.locfileid: "84596608"
---
# <a name="customchannelstester"></a><span data-ttu-id="48a2f-102">CustomChannelsTester</span><span class="sxs-lookup"><span data-stu-id="48a2f-102">CustomChannelsTester</span></span>
<span data-ttu-id="48a2f-103">`CustomChannelsTester` - это средство, позволяющее проверять реализации пользовательских каналов на соответствие набору предопределенных контрактов службы.</span><span class="sxs-lookup"><span data-stu-id="48a2f-103">The `CustomChannelsTester` is a tool that you can use to test your custom channel implementations against a set of predefined service contracts.</span></span> <span data-ttu-id="48a2f-104">Можно выбрать набор контрактов службы и передать его средству с помощью XML-файла.</span><span class="sxs-lookup"><span data-stu-id="48a2f-104">You can select the set of service contracts and pass it to the tool using an XML file.</span></span> <span data-ttu-id="48a2f-105">Затем средство создает службу и клиента, использующих реализации пользовательского канала во время обмена сообщениями.</span><span class="sxs-lookup"><span data-stu-id="48a2f-105">The tool then generates the service and client that exercises your custom channel implementations during message exchange.</span></span>  
  
### <a name="to-build-the-tool"></a><span data-ttu-id="48a2f-106">Построение средства</span><span class="sxs-lookup"><span data-stu-id="48a2f-106">To build the tool</span></span>  
  
1. <span data-ttu-id="48a2f-107">Чтобы выполнить сборку решения, следуйте инструкциям в разделе [Создание примеров Windows Communication Foundation](building-the-samples.md).</span><span class="sxs-lookup"><span data-stu-id="48a2f-107">To build the solution, follow the instructions in [Building the Windows Communication Foundation Samples](building-the-samples.md).</span></span>  
  
2. <span data-ttu-id="48a2f-108">При построении решения создаются три файла: CustomChannelsTester.exe, TestSpec.xml и SampleRun.cmd.</span><span class="sxs-lookup"><span data-stu-id="48a2f-108">Building the solution generates three files: CustomChannelsTester.exe, TestSpec.xml and SampleRun.cmd.</span></span> <span data-ttu-id="48a2f-109">Файл Самплерун. cmd содержит образец командной строки, который показывает, как использовать это средство для проверки образца [Transport: UDP](transport-udp.md) .</span><span class="sxs-lookup"><span data-stu-id="48a2f-109">The file SampleRun.cmd has a sample command line that shows how to use this tool to test the [Transport: UDP](transport-udp.md) sample.</span></span>  
  
### <a name="to-run-the-tool"></a><span data-ttu-id="48a2f-110">Запуск средства</span><span class="sxs-lookup"><span data-stu-id="48a2f-110">To run the tool</span></span>  
  
- <span data-ttu-id="48a2f-111">В командной строке введите следующую команду.</span><span class="sxs-lookup"><span data-stu-id="48a2f-111">At the command prompt type the following command:</span></span>  
  
    ```console  
    CustomChannelsTester.exe /binding:YourCustomBindngName /dll:TheAssemblyWhereThisTypeisDefined /testspec:XmlFileNameWhichContainsTestOptions  
    ```  
  
     <span data-ttu-id="48a2f-112">Необходимо использовать параметр `/binding`.</span><span class="sxs-lookup"><span data-stu-id="48a2f-112">Using the `/binding` option is required.</span></span>  
  
     <span data-ttu-id="48a2f-113">`/dll`требуется, если "Binding" не является предоставляемой системой привязкой, предоставляемой Windows Communication Foundation (WCF).</span><span class="sxs-lookup"><span data-stu-id="48a2f-113">`/dll` is required if "binding" is not a system-provided binding provided by Windows Communication Foundation (WCF).</span></span>  
  
     <span data-ttu-id="48a2f-114">Аргумент `/testspec` является необязательным.</span><span class="sxs-lookup"><span data-stu-id="48a2f-114">`/testspec` is optional.</span></span>  
  
     <span data-ttu-id="48a2f-115">В результате создаются сервер и клиенты на основе спецификаций теста и привязки.</span><span class="sxs-lookup"><span data-stu-id="48a2f-115">This creates server and clients based on the test specifications and the binding.</span></span>  
  
     <span data-ttu-id="48a2f-116">Выполняет клиент и сервер и возвращает результаты.</span><span class="sxs-lookup"><span data-stu-id="48a2f-116">Executes the client and server and returns the results.</span></span>  
  
     <span data-ttu-id="48a2f-117">Далее приведен пример XML-кода для описания спецификаций теста (testspec.xml).</span><span class="sxs-lookup"><span data-stu-id="48a2f-117">The following is the sample XML for the description of the test specifications (testspec.xml):</span></span>  
  
    ```xml  
    <TestSpec xmlns="http://WCF/TestSpec" xmlns:msdata="urn:schemas-microsoft-com:xml-msdata"
    xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" >  
    <ServiceContract>  
    <!-- Test a contract which has oneway / twoway operations. If you set ExpandAll = true, both types of contracts are tested -->    <IsOneWay ExpandAll="true">true</IsOneWay>  
    <!-- Test a contract with Asynchronous / Synchronous Operations-->  
        <IsAsync>false</IsAsync>
    <!-- Test a sessionful / sessionless contract-->
        <IsSession ExpandAll="true">true</IsSession>  
    <!-- If the Service Contract includes a CallBack Contract-->
        <IsCallBack ExpandAll="true">true</IsCallBack>  
    </ServiceContract>  
    <TestDetails>  
    <!-- Name of the machine that runs the server - required if you want to run the test crossmachine-->  
        <ServerName>ReplaceThisWithTheServerMachineName</ServerName>  
    <!-- Port Number - Optional-->  
        <Port>8000</Port>  
    <!--URI for the callBack address for the client. The client will receive the messages from the server on this address in case of a CallBack Contract-->  
        <ClientCallBackAddress/>
    <!-- Duration (in sec) after the server has started, it times out - optional(default = 300sec) -->  
        <ServerTimeout>300</ServerTimeout>  
    <!-- Duration (in sec) before the Client initializes -optional(default = 60sec) -->  
        <ClientTimeout>60</ClientTimeout>  
    <!-- Number of clients for each service - optional(default = 1) -->  
        <NumberOfClients>1</NumberOfClients>  
    <!-- Number of messages each client sends to the service - optional(default = 1) -->  
        <MessagesPerClient>1</MessagesPerClient>  
    </TestDetails>  
    </TestSpec>  
    ```  
