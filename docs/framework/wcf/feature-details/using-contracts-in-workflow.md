---
title: Использование контрактов в рабочих процессах
ms.date: 03/30/2017
ms.assetid: 939c64e9-e7cc-4abc-b41e-27cfce1d7e50
ms.openlocfilehash: def100f9483ea9ac8bf1aa3285d76edccffb030a
ms.sourcegitcommit: cdb295dd1db589ce5169ac9ff096f01fd0c2da9d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/09/2020
ms.locfileid: "84595015"
---
# <a name="using-contracts-in-workflow"></a>Использование контрактов в рабочих процессах
При реализации службы выполняется определение числа контрактов, описывающих службу и данные, которые она отправляет и получает. Данные представлены в виде контрактов данных и контрактов сообщений. службы WCF и Workflow Services используют контракт данных и определения контрактов сообщений как часть описаний служб. Служба сама предоставляет метаданные (в форме WSDL) для описания операций службы. В WCF контракты службы и операций определяют службу и операции, которые она поддерживает. Однако в службе Workflow Service эти контракты являются частью самого бизнес-процесса, они представляются в метаданных процессом, называемым выводом контракта.  
  
## <a name="contract-inference"></a>Вывод контракта  
 При размещении службы рабочего процесса с использованием <xref:System.ServiceModel.Activities.WorkflowServiceHost> просматривается определение рабочего процесса и формируется контракт на основе набора действий по отправке и получению сообщений, обнаруженных в рабочем процессе. В частности, для создания контракта используются следующие действия и свойства:  
  
 <xref:System.ServiceModel.Activities.Receive> Действие  
  
- <xref:System.ServiceModel.Activities.Receive.ServiceContractName%2A>  
  
- <xref:System.ServiceModel.Activities.Receive.OperationName%2A>
  
- <xref:System.ServiceModel.Activities.Receive.Action%2A>

 <xref:System.ServiceModel.Activities.SendReply> Действие  
  
- <xref:System.ServiceModel.Activities.SendReply.Action%2A>  
  
 <xref:System.ServiceModel.Activities.TransactedReceiveScope> Действие  
  
 Конечным результатом вывода контракта является описание службы, использующее структуры данных, аналогичные структурам данных служб WCF и контрактов операций. Затем эти сведения используются для предоставления WSDL для службы рабочего процесса.  
  
## <a name="see-also"></a>Дополнительно

- [Службы рабочего процесса](workflow-services.md)
- [Действия обмена сообщениями](messaging-activities.md)
- [Практическое руководство. Как создать службу рабочего процесса с помощью действий обмена сообщениями](how-to-create-a-workflow-service-with-messaging-activities.md)
- [Практическое руководство. Создание службы рабочих процессов, использующей существующий контракт службы](../../windows-workflow-foundation/how-to-create-a-workflow-service-that-consumes-an-existing-service-contract.md)
