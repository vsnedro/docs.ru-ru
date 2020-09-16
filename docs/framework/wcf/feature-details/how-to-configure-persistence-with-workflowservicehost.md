---
title: Практическое руководство. Как настроить сохраняемость с помощью WorkflowServiceHost
ms.date: 03/30/2017
ms.assetid: e31cd4df-13a3-4a9a-9be8-5243e0055356
ms.openlocfilehash: 93397923154d780ed3b714bf0bb95c15bc71bbfb
ms.sourcegitcommit: 27a15a55019f6b5f2733961738babe94aec0def3
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/15/2020
ms.locfileid: "90556314"
---
# <a name="how-to-configure-persistence-with-workflowservicehost"></a><span data-ttu-id="62844-102">Практическое руководство. Как настроить сохраняемость с помощью WorkflowServiceHost</span><span class="sxs-lookup"><span data-stu-id="62844-102">How to: Configure Persistence with WorkflowServiceHost</span></span>
<span data-ttu-id="62844-103">В данном разделе описывается способ настройки функции хранилища экземпляров рабочих процессов SQL для включения сохраняемости рабочих процессов, размещенных в <xref:System.ServiceModel.Activities.WorkflowServiceHost>, с помощью файла конфигурации.</span><span class="sxs-lookup"><span data-stu-id="62844-103">This topic describes how to configure the SQL Workflow Instance Store feature to enable persistence for workflows hosted in <xref:System.ServiceModel.Activities.WorkflowServiceHost> by using a configuration file.</span></span> <span data-ttu-id="62844-104">Перед использованием возможности хранилища экземпляров рабочих процессов SQL необходимо создать базу данных SQL, которая используется для хранения экземпляров рабочих процессов.</span><span class="sxs-lookup"><span data-stu-id="62844-104">Before using the SQL Workflow Instance Store feature you must create a SQL database that is used to persist workflow instances.</span></span> <span data-ttu-id="62844-105">Дополнительные сведения см. [в разделе инструкции. Включение сохраняемости SQL для рабочих процессов и служб рабочих](../../windows-workflow-foundation/how-to-enable-sql-persistence-for-workflows-and-workflow-services.md)процессов.</span><span class="sxs-lookup"><span data-stu-id="62844-105">For more information, see [How to: Enable SQL Persistence for Workflows and Workflow Services](../../windows-workflow-foundation/how-to-enable-sql-persistence-for-workflows-and-workflow-services.md).</span></span>  
  
### <a name="to-configure-the-sql-workflow-instance-store-in-configuration"></a><span data-ttu-id="62844-106">Настройка хранилища экземпляров рабочих процессов SQL в конфигурации</span><span class="sxs-lookup"><span data-stu-id="62844-106">To Configure the SQL Workflow Instance Store in Configuration</span></span>  
  
1. <span data-ttu-id="62844-107">Свойства хранилища экземпляров рабочих процессов SQL можно настроить с помощью объекта <xref:System.ServiceModel.Activities.Description.SqlWorkflowInstanceStoreBehavior> - поведения службы, позволяющего менять параметры с помощью конфигурации XML.</span><span class="sxs-lookup"><span data-stu-id="62844-107">The properties of the SQL workflow instance store can be configured through the <xref:System.ServiceModel.Activities.Description.SqlWorkflowInstanceStoreBehavior>, a service behavior that allows you to change the settings through XML configuration.</span></span> <span data-ttu-id="62844-108">В следующем примере конфигурации показано, как настроить хранилище экземпляров рабочих процессов SQL с помощью `sqlWorkflowInstanceStore` элемента поведения <> в файле конфигурации.</span><span class="sxs-lookup"><span data-stu-id="62844-108">The following configuration example shows how to configure the SQL workflow instance store by using the <`sqlWorkflowInstanceStore`> behavior element in a configuration file.</span></span>  
  
    ```xml  
    <serviceBehaviors>  
        <behavior name="">  
            <sqlWorkflowInstanceStore
                 connectionString="provider=System.Data.SqlClient;Data Source=(local);Initial Catalog=DefaultPersistenceProviderDb;Integrated Security=True;Async=true"  
                 instanceEncodingOption="GZip | None"  
                 instanceCompletionAction="DeleteAll | DeleteNothing"  
                 instanceLockedExceptionAction="NoRetry | SimpleRetry | AggressiveRetry"  
                 hostLockRenewalPeriod="00:00:30"
                 runnableInstancesDetectionPeriod="00:00:05">  
            </sqlWorkflowInstanceStore>  
        </behavior>  
    </serviceBehaviors>  
    ```  
  
     <span data-ttu-id="62844-109">Дополнительные сведения о настройке хранилища экземпляров рабочих процессов SQL см. [в разделе инструкции. Включение сохраняемости SQL для рабочих процессов и служб рабочих](../../windows-workflow-foundation/how-to-enable-sql-persistence-for-workflows-and-workflow-services.md)процессов.</span><span class="sxs-lookup"><span data-stu-id="62844-109">For more information about how to configure the SQL workflow instance store, see [How to: Enable SQL Persistence for Workflows and Workflow Services](../../windows-workflow-foundation/how-to-enable-sql-persistence-for-workflows-and-workflow-services.md).</span></span> <span data-ttu-id="62844-110">Дополнительные сведения об отдельных параметрах `sqlWorkflowInstanceStore` элемента поведения <> см. в разделе [хранилище экземпляров рабочих процессов SQL](../../windows-workflow-foundation/sql-workflow-instance-store.md).</span><span class="sxs-lookup"><span data-stu-id="62844-110">For more information about the individual settings for the <`sqlWorkflowInstanceStore`> behavior element, see [SQL Workflow Instance Store](../../windows-workflow-foundation/sql-workflow-instance-store.md).</span></span> <span data-ttu-id="62844-111">Фабрика приложений Windows Server имеет собственное хранилище сохраняемости.</span><span class="sxs-lookup"><span data-stu-id="62844-111">Windows Server App Fabric provides its own persistence store.</span></span> <span data-ttu-id="62844-112">Дополнительные сведения см. в статье [сохраняемость в Windows Server App Fabric](/previous-versions/appfabric/ee677272(v=azure.10)).</span><span class="sxs-lookup"><span data-stu-id="62844-112">For more information, see [Windows Server App Fabric Persistence](/previous-versions/appfabric/ee677272(v=azure.10)).</span></span>  
  
    > [!NOTE]
    > <span data-ttu-id="62844-113">В предыдущем примере конфигурации используется упрощенная конфигурация.</span><span class="sxs-lookup"><span data-stu-id="62844-113">The preceding configuration example uses simplified configuration.</span></span> <span data-ttu-id="62844-114">Дополнительные сведения см. в разделе [упрощенная конфигурация](../simplified-configuration.md) .</span><span class="sxs-lookup"><span data-stu-id="62844-114">For more information, see [Simplified Configuration](../simplified-configuration.md)</span></span>  
  
### <a name="to-configure-the-sql-workflow-instance-store-in-code"></a><span data-ttu-id="62844-115">Настройка хранилища экземпляров рабочих процессов SQL в коде</span><span class="sxs-lookup"><span data-stu-id="62844-115">To Configure the SQL Workflow Instance Store in Code</span></span>  
  
1. <span data-ttu-id="62844-116">Свойства хранилища экземпляров рабочих процессов SQL можно настроить с помощью объекта <xref:System.ServiceModel.Activities.Description.SqlWorkflowInstanceStoreBehavior>, определяющего поведение службы, позволяющее менять параметры с помощью кода.</span><span class="sxs-lookup"><span data-stu-id="62844-116">The properties of the SQL workflow instance store can be configured through the <xref:System.ServiceModel.Activities.Description.SqlWorkflowInstanceStoreBehavior>, a service behavior that allows you to change the settings through code.</span></span> <span data-ttu-id="62844-117">В следующем примере показано, как настроить хранилище экземпляров рабочих процессов SQL с помощью элемента поведения <xref:System.ServiceModel.Activities.Description.SqlWorkflowInstanceStoreBehavior> в коде.</span><span class="sxs-lookup"><span data-stu-id="62844-117">The following example shows how to configure the SQL workflow instance store by using the <xref:System.ServiceModel.Activities.Description.SqlWorkflowInstanceStoreBehavior> behavior element in a code</span></span>  
  
    ```csharp  
    host.Description.Behaviors.Add(new SqlWorkflowInstanceStoreBehavior  
    {  
       ConnectionString = "provider=System.Data.SqlClient;Data Source=(local);Initial Catalog=DefaultPersistenceProviderDb;Integrated Security=True;Async=true",  
       InstanceEncodingOption = "GZip | None",  
       InstanceCompletionAction = "DeleteAll | DeleteNothing",  
       InstanceLockedExceptionAction = "NoRetry | SimpleRetry | AggressiveRetry",  
       HostLockRenewalPeriod = new TimeSpan(00, 00, 30),  
       RunnableInstancesDetectionPeriod = new TimeSpan(00, 00, 05)  
    });  
    ```  
  
     <span data-ttu-id="62844-118">Дополнительные сведения о настройке хранилища экземпляров рабочих процессов SQL см. [в разделе инструкции. Включение сохраняемости SQL для рабочих процессов и служб рабочих](../../windows-workflow-foundation/how-to-enable-sql-persistence-for-workflows-and-workflow-services.md)процессов.</span><span class="sxs-lookup"><span data-stu-id="62844-118">For more information about how to configure the SQL workflow instance store, see [How to: Enable SQL Persistence for Workflows and Workflow Services](../../windows-workflow-foundation/how-to-enable-sql-persistence-for-workflows-and-workflow-services.md).</span></span> <span data-ttu-id="62844-119">Дополнительные сведения об отдельных параметрах <xref:System.ServiceModel.Activities.Description.SqlWorkflowInstanceStoreBehavior> элемента Behavior см. в разделе [хранилище экземпляров рабочих процессов SQL](../../windows-workflow-foundation/sql-workflow-instance-store.md).</span><span class="sxs-lookup"><span data-stu-id="62844-119">For more information about the individual settings for the <xref:System.ServiceModel.Activities.Description.SqlWorkflowInstanceStoreBehavior> behavior element, see [SQL Workflow Instance Store](../../windows-workflow-foundation/sql-workflow-instance-store.md).</span></span> <span data-ttu-id="62844-120">Фабрика приложений Windows Server имеет собственное хранилище сохраняемости.</span><span class="sxs-lookup"><span data-stu-id="62844-120">Windows Server App Fabric provides its own persistence store.</span></span> <span data-ttu-id="62844-121">Дополнительные сведения см. в статье [сохраняемость в Windows Server App Fabric](/previous-versions/appfabric/ee677272(v=azure.10)).</span><span class="sxs-lookup"><span data-stu-id="62844-121">For more information, see [Windows Server App Fabric Persistence](/previous-versions/appfabric/ee677272(v=azure.10)).</span></span>  
  
    > [!NOTE]
    > <span data-ttu-id="62844-122">В предыдущем примере конфигурации используется упрощенная конфигурация.</span><span class="sxs-lookup"><span data-stu-id="62844-122">The preceding configuration example uses simplified configuration.</span></span> <span data-ttu-id="62844-123">Дополнительные сведения см. в разделе [упрощенная конфигурация](../simplified-configuration.md) .</span><span class="sxs-lookup"><span data-stu-id="62844-123">For more information, see [Simplified Configuration](../simplified-configuration.md)</span></span>  
  
     <span data-ttu-id="62844-124">Пример настройки сохраняемости программным способом см. в разделе [Включение сохраняемости для рабочих процессов и служб рабочих](../../windows-workflow-foundation/how-to-enable-persistence-for-workflows-and-workflow-services.md)процессов.</span><span class="sxs-lookup"><span data-stu-id="62844-124">For an example of how to configure persistence programmatically see [How to: Enable Persistence for Workflows and Workflow Services](../../windows-workflow-foundation/how-to-enable-persistence-for-workflows-and-workflow-services.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="62844-125">См. также</span><span class="sxs-lookup"><span data-stu-id="62844-125">See also</span></span>

- [<span data-ttu-id="62844-126">Службы рабочего процесса</span><span class="sxs-lookup"><span data-stu-id="62844-126">Workflow Services</span></span>](workflow-services.md)
- [<span data-ttu-id="62844-127">Сохраняемость рабочего процесса</span><span class="sxs-lookup"><span data-stu-id="62844-127">Workflow Persistence</span></span>](../../windows-workflow-foundation/workflow-persistence.md)
- <span data-ttu-id="62844-128">[Сохраняемость Windows Server App Fabric](/previous-versions/appfabric/ee677272(v=azure.10))</span><span class="sxs-lookup"><span data-stu-id="62844-128">[Windows Server App Fabric Persistence](/previous-versions/appfabric/ee677272(v=azure.10))</span></span>
