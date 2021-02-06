---
description: 'Дополнительные сведения о: использование контрактов в рабочем процессе'
title: Использование контрактов в рабочих процессах
ms.date: 03/30/2017
ms.assetid: 939c64e9-e7cc-4abc-b41e-27cfce1d7e50
ms.openlocfilehash: d1ef5a4c494643d521a5fe045ff87c0cbeb34db1
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2021
ms.locfileid: "99632221"
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
  
## <a name="see-also"></a>См. также

- [Службы рабочего процесса](workflow-services.md)
- [Действия обмена сообщениями](messaging-activities.md)
- [Практическое руководство. Как создать службу рабочего процесса с помощью действий обмена сообщениями](how-to-create-a-workflow-service-with-messaging-activities.md)
- [Практическое руководство. Создание службы рабочих процессов, использующей существующий контракт службы](../../windows-workflow-foundation/how-to-create-a-workflow-service-that-consumes-an-existing-service-contract.md)
