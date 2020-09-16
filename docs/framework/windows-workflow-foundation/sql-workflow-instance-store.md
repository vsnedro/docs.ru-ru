---
title: Хранилище экземпляров рабочих процессов SQL
ms.date: 03/30/2017
ms.assetid: 8cd2f8a5-4bf8-46ea-8909-c7fdb314fabc
ms.openlocfilehash: 38cf83ebb8417009c6aa205aa29cd633d1232f0a
ms.sourcegitcommit: 27a15a55019f6b5f2733961738babe94aec0def3
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/15/2020
ms.locfileid: "90540236"
---
# <a name="sql-workflow-instance-store"></a>Хранилище экземпляров рабочих процессов SQL
[!INCLUDE[netfx_current_short](../../../includes/netfx-current-short-md.md)] поставляется вместе с хранилищем экземпляров рабочего процесса SQL, благодаря чему рабочие процессы могут сохранять сведения о состоянии экземпляров рабочих процессов в базах данных SQL Server 2005 или SQL Server 2008. Эта функция чаще всего реализуется в виде класса <xref:System.Activities.DurableInstancing.SqlWorkflowInstanceStore>, являющегося производным от абстрактного класса <xref:System.Runtime.DurableInstancing.InstanceStore> платформы сохраняемости. Компонент хранилища экземпляров рабочего процесса SQL состоит из поставщика сохраняемости SQL, являющегося конкретной реализацией API сохраняемости, используемой ведущим приложением для отправки команд сохраняемости в хранилище.  
  
 Хранилище экземпляров рабочего процесса SQL поддерживает как самостоятельно размещаемые рабочие процессы, так и службы рабочих процессов, которые используют <xref:System.Activities.WorkflowApplication> или <xref:System.ServiceModel.WorkflowServiceHost>, а также службы, размещаемые в WAS с использованием <xref:System.ServiceModel.WorkflowServiceHost>. Компонент хранилища экземпляров рабочего процесса SQL можно настроить на работу с самостоятельно размещаемыми службами программным образом, воспользовавшись предоставляемой компонентом объектной моделью. Настроить эту функцию для служб, размещенных в <xref:System.ServiceModel.WorkflowServiceHost>, можно как программным образом с использованием объектной модели, так и с использованием файла конфигурации XML.  
  
 Функция хранилища экземпляров рабочих процессов SQL (класс**SqlWorkflowInstanceStore** ) не реализует <xref:System.ServiceModel.Persistence.PersistenceProviderFactory> и поэтому не обеспечивает поддержку сохраняемости для устойчивых служб WCF, не являющихся рабочими процессами. Он также не реализует <xref:System.Workflow.Runtime.Hosting.WorkflowPersistenceService> и поэтому не обеспечивает поддержку сохраняемости для рабочих процессов версии 3.x. Этот компонент поддерживает сохраняемость только для рабочих процессов WF 4.0 (и более поздних версий) и служб Workflow Services. Компонент также не поддерживает базы данных, отличные от SQL Server 2005 и SQL Server 2008.  
  
 В подразделах этого раздела описываются свойства и возможности хранилища экземпляров рабочего процесса SQL, а также предоставляются подробные сведения о настройке хранилища.  
  
 Фабрика приложений (App Fabric) Windows Server предоставляет собственное хранилище экземпляров и инструментарий для упрощения настройки и использования хранилища. Дополнительные сведения см. в статье [хранилище экземпляров Windows Server App Fabric](/previous-versions/appfabric/ff383417(v=azure.10)). Дополнительные сведения о структуре приложений SQL Server базы данных сохраняемости см. в статье [app fabric SQL Server сохраняемость базы данных](/previous-versions/appfabric/ee790819(v=azure.10)) .  
  
## <a name="in-this-section"></a>в этом разделе  
  
- [Свойства хранилища экземпляров рабочего процесса SQL](properties-of-sql-workflow-instance-store.md)  
  
- [Практическое руководство. Включение сохраняемости для рабочих процессов и их служб в SQL](how-to-enable-sql-persistence-for-workflows-and-workflow-services.md)  
  
- [Активация экземпляров](instance-activation.md)  
  
- [Поддержка запросов](support-for-queries.md)  
  
- [Расширяемость хранилища](store-extensibility.md)  
  
- [Безопасность](security.md)  
  
- [База данных постоянного хранения SQL Server](sql-server-persistence-database.md)  
  
## <a name="see-also"></a>См. также

- [Образцы сохраняемости](/previous-versions/dotnet/netframework-4.0/dd699769(v=vs.100))
