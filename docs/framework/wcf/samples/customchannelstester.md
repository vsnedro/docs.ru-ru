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
# <a name="customchannelstester"></a>CustomChannelsTester
`CustomChannelsTester` - это средство, позволяющее проверять реализации пользовательских каналов на соответствие набору предопределенных контрактов службы. Можно выбрать набор контрактов службы и передать его средству с помощью XML-файла. Затем средство создает службу и клиента, использующих реализации пользовательского канала во время обмена сообщениями.  
  
### <a name="to-build-the-tool"></a>Построение средства  
  
1. Чтобы выполнить сборку решения, следуйте инструкциям в разделе [Создание примеров Windows Communication Foundation](building-the-samples.md).  
  
2. При построении решения создаются три файла: CustomChannelsTester.exe, TestSpec.xml и SampleRun.cmd. Файл Самплерун. cmd содержит образец командной строки, который показывает, как использовать это средство для проверки образца [Transport: UDP](transport-udp.md) .  
  
### <a name="to-run-the-tool"></a>Запуск средства  
  
- В командной строке введите следующую команду.  
  
    ```console  
    CustomChannelsTester.exe /binding:YourCustomBindngName /dll:TheAssemblyWhereThisTypeisDefined /testspec:XmlFileNameWhichContainsTestOptions  
    ```  
  
     Необходимо использовать параметр `/binding`.  
  
     `/dll`требуется, если "Binding" не является предоставляемой системой привязкой, предоставляемой Windows Communication Foundation (WCF).  
  
     Аргумент `/testspec` является необязательным.  
  
     В результате создаются сервер и клиенты на основе спецификаций теста и привязки.  
  
     Выполняет клиент и сервер и возвращает результаты.  
  
     Далее приведен пример XML-кода для описания спецификаций теста (testspec.xml).  
  
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
