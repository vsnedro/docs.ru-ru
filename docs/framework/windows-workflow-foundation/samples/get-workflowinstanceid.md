---
title: Получение GetWorkflowInstanceId
ms.date: 03/30/2017
ms.assetid: bd7eea3b-1c28-4b84-9a67-003bc553aa81
ms.openlocfilehash: db06b30f24a2d620406b3e6a35bba3a1fca70a9c
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/26/2020
ms.locfileid: "96251559"
---
# <a name="get-workflowinstanceid"></a>Получение GetWorkflowInstanceId

В этом образце показывается, как можно использовать пользовательское действие `GetWorkflowInstanceId` для возвращения идентификатора экземпляра рабочего процесса.  
  
## <a name="demonstrates"></a>Что демонстрирует  

 Разработка пользовательского действия, метод доступа к экземпляру рабочего процесса.  
  
## <a name="discussion"></a>Разговор  

 Для получения идентификатора экземпляра выполняющегося рабочего процесса необходимо написать код. Если необходимо написать полностью декларативный рабочий процесс, то требуется действие, возвращающее идентификатор экземпляра рабочего процесса, что позволит ссылаться на это действие в рабочем процессе в полностью декларативной манере. Доступ к идентификатору экземпляра требуется во многих случаях, например при ведении журнала с целью аудита или при осуществлении корреляции на уровне приложения с предоставлением идентификатора экземпляра клиенту для последующего создания ассоциации (например, при использовании этого действия в действии SendReply).  
  
 Действие `GetWorkflowInstanceId` реализуется как <xref:System.Activities.CodeActivity%601>, поскольку оно должно возвращать значение типа <xref:System.Guid> и должно иметь доступ к контексту <xref:System.Activities.CodeActivityContext> для получения идентификатора экземпляра рабочего процесса. Его реализация производится достаточно просто.  
  
```csharp  
public sealed class GetWorkflowInstanceId : CodeActivity<Guid>  
{  
    protected override Guid Execute(CodeActivityContext context)  
    {  
        return context.WorkflowInstanceId;  
    }  
}
```  
  
> [!IMPORTANT]
> Образцы уже могут быть установлены на компьютере. Перед продолжением проверьте следующий каталог (по умолчанию).  
>
> `<InstallDrive>:\WF_WCF_Samples`  
>
> Если этот каталог не существует, перейдите к [примерам Windows Communication Foundation (WCF) и Windows Workflow Foundation (WF) для .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) , чтобы скачать все Windows Communication Foundation (WCF) и [!INCLUDE[wf1](../../../../includes/wf1-md.md)] примеры. Этот образец расположен в следующем каталоге.  
>
> `<InstallDrive>:\WF_WCF_Samples\WF\Scenario\ActivityLibrary\GetWorkflowInstanceId`
