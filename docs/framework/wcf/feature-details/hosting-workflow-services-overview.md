---
title: Общие сведения о размещении служб рабочих процессов
ms.date: 03/30/2017
ms.assetid: 19f3704f-06bf-4eeb-8724-5224e02d7ead
ms.openlocfilehash: 150cb98ab3cef8231489219a16709344cbd19bd5
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/26/2020
ms.locfileid: "96242972"
---
# <a name="hosting-workflow-services-overview"></a>Общие сведения о размещении служб рабочих процессов

Для выполнения служб рабочего процесса они должны быть размещены. Класс <xref:System.ServiceModel.WorkflowServiceHost> представляет собой готовый узел размещения рабочих процессов, поддерживающий использование нескольких экземпляров, настройку и обмен сообщениями WCF (хотя от размещаемых рабочих процессов и не требуется обмена сообщениями).  Он также реализует сохраняемость, отслеживание и контроль за экземплярами через набор поведений службы.  Как и класс WCF <xref:System.ServiceModel.ServiceHost>, класс <xref:System.ServiceModel.WorkflowServiceHost> может быть резидентным в любом управляемом приложении .NET или размещаться на веб-сервере IIS / WAS (в виде файла XAMLX).  В этом разделе описано размещение службы рабочего процесса.  
  
## <a name="in-this-section"></a>в этом разделе  

 [Размещение службы рабочего процесса](hosting-workflow-services.md)  
 Описывает размещение служб рабочего процесса.  
  
 [Внутренние особенности размещения службы рабочего процесса](workflow-service-host-internals.md)  
 Описывает, как объект <xref:System.ServiceModel.WorkflowServiceHost> обрабатывает входящие сообщения.  
  
 [Расширяемость узла службы рабочих процессов](workflow-service-host-extensibility.md)  
 Описывает способы расширения функциональности узла службы рабочего процесса.  
  
 [Конечная точка элемента управления рабочего процесса](workflow-control-endpoint.md)  
 Описывает, как определить конечную точку, позволяющую создавать экземпляры рабочих процессов.
  
 [Практическое руководство. Как разместить службу рабочего процесса с помощью Windows Server App Fabric](how-to-host-a-workflow-service-with-windows-server-app-fabric.md)  
 Демонстрирует размещение существующей службы рабочего процесса в фабрике приложений Windows Server.  
  
 [Настройка WorkflowServiceHost](configuring-workflowservicehost.md)  
 Описывает управление сохраняемостью, отслеживанием, простоем и поведением необработанных исключений.  
  
## <a name="reference"></a>Справочник  

 <xref:System.ServiceModel.Activities.WorkflowServiceHost>  
  
 <xref:System.ServiceModel.Activities.WorkflowService>  
  
 <xref:System.ServiceModel.Activation.ServiceHostFactory>  
  
 <xref:System.ServiceModel.Activation.ServiceHostFactoryBase>  
  
 <xref:System.ServiceModel.Activation.WorkflowServiceHostFactory>  
  
## <a name="related-sections"></a>Связанные разделы  

 [Службы рабочего процесса](workflow-services.md)
