---
description: 'Дополнительные сведения: сопоставитель закладок для конечной точки WorkflowHostingEndpoint'
title: Арбитр закладок для конечной точки WorkflowHostingEndpoint
ms.date: 03/30/2017
ms.assetid: 97fd5816-935e-4625-ad04-e6f6befa07de
ms.openlocfilehash: fc2a21a33560452b141069e88b4d7ff816712d96
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2021
ms.locfileid: "99653814"
---
# <a name="bookmark-resolver-for-workflowhostingendpoint"></a>Арбитр закладок для конечной точки WorkflowHostingEndpoint

В этом образце показано использование <xref:System.ServiceModel.Activities.WorkflowHostingEndpoint> с <xref:System.ServiceModel.Activities.WorkflowServiceHost> для создания экземпляров рабочего процесса.  
  
## <a name="demonstrates"></a>Что демонстрирует  

 <xref:System.ServiceModel.Activities.WorkflowHostingEndpoint>, <xref:System.ServiceModel.Activities.WorkflowServiceHost>  
  
## <a name="discussion"></a>Разговор  

 Этот образец использует <xref:System.ServiceModel.Activities.WorkflowHostingEndpoint> для создания экземпляров рабочих процессов, размещенных с помощью <xref:System.ServiceModel.Activities.WorkflowServiceHost>. <xref:System.ServiceModel.Activities.WorkflowHostingEndpoint> - точка расширения для <xref:System.ServiceModel.Activities.WorkflowServiceHost>, которую можно использовать в следующих сценариях:  
  
- Создание новых экземпляров рабочего процесса.  
  
- Возобновление закладок в экземпляре рабочего процесса, размещенного в <xref:System.ServiceModel.Activities.WorkflowServiceHost>.  
  
 В приведенном образце точки расширения представлен контракт на выполнение операций, создающих рабочий процесс и возвращающих идентификатор экземпляра или создающих экземпляр с конкретным идентификатором. В приведенном образце консольного приложения создается экземпляр <xref:System.ServiceModel.Activities.WorkflowServiceHost>, определяющий рабочий процесс, и к узлу добавляется `CreationEndpoint`. Затем в конечной точке вызывается операция `Create`, чтобы создать новый экземпляр рабочего процесса.  
  
#### <a name="to-set-up-build-and-run-the-sample"></a>Настройка, сборка и выполнение образца  
  
1. Создайте решение.  
  
2. Запустите приложение. При создании экземпляра рабочего процесса на консоли `CreationEndpoint` выводится сообщение, содержащее идентификатор экземпляра. Сообщение "Hello World!" распечатывается экземпляром рабочего процесса.  
  
> [!IMPORTANT]
> Образцы уже могут быть установлены на компьютере. Перед продолжением проверьте следующий каталог (по умолчанию).  
>
> `<InstallDrive>:\WF_WCF_Samples`  
>
> Если этот каталог не существует, перейдите к [примерам Windows Communication Foundation (WCF) и Windows Workflow Foundation (WF) для платформа .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) , чтобы скачать все Windows Communication Foundation (WCF) и [!INCLUDE[wf1](../../../../includes/wf1-md.md)] примеры. Этот образец расположен в следующем каталоге.  
>
> `<InstallDrive>:\WF_WCF_Samples\WF\Basic\Execution\CreationEndpoint`
