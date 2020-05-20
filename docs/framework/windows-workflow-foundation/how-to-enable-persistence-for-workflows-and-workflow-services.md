---
title: Практическое руководство. Включение сохраняемости для рабочих процессов и служб рабочих процессов
description: Узнайте, как настроить хранилище экземпляров рабочих процессов SQL, чтобы включить сохраняемость для рабочих процессов и служб рабочих процессов программным способом и с помощью файла конфигурации.
ms.date: 03/30/2017
ms.assetid: 2b1c8bf3-9866-45a4-b06d-ee562393e503
ms.openlocfilehash: 31fe6e3f06989e9a42254747565342cf97e4b9f1
ms.sourcegitcommit: 9a4488a3625866335e83a20da5e9c5286b1f034c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/15/2020
ms.locfileid: "83421518"
---
# <a name="how-to-enable-persistence-for-workflows-and-workflow-services"></a>Практическое руководство. Включение сохраняемости для рабочих процессов и служб рабочих процессов

В этом разделе описывается процесс включения сохраняемости для рабочих процессов и служб рабочих процессов.

## <a name="enable-persistence-for-workflows"></a>Включение сохраняемости для рабочих процессов

Хранилище экземпляров можно связать с **WorkflowApplication** с помощью <xref:System.Activities.WorkflowApplication.InstanceStore%2A> свойства <xref:System.Activities.WorkflowApplication> класса. Метод <xref:System.Activities.WorkflowApplication.Persist%2A> сохраняет рабочий процесс в хранилище экземпляров, связанном с приложением. Метод <xref:System.Activities.WorkflowApplication.Unload%2A> сохраняет рабочий процесс в хранилище экземпляров, а затем выгружает экземпляр из памяти. Метод **Load** загружает рабочий процесс в память, используя данные рабочего процесса, хранящиеся в хранилище сохраняемости экземпляра.

Метод **Persist** выполняет следующие действия:

1. Приостанавливает работу планировщика рабочих процессов и ждет перехода рабочего процесса в состояние бездействия.

2. Сохраняет рабочий процесс в хранилище сохраняемости.

3. Возобновляет работу планировщика рабочих процессов.

 Метод **unload** выполняет следующие действия:

1. Приостанавливает работу планировщика рабочих процессов и ждет перехода рабочего процесса в состояние бездействия.

2. Сохраняет рабочий процесс в хранилище сохраняемости.

3. Удаляет экземпляр рабочего процесса из памяти.

Методы **PERSISTED** и **unload** будут блокироваться, пока рабочий процесс находится в зоне без сохранения, пока рабочий процесс не выполнит выход из зоны без сохранения. Метод продолжает работу, выполняя операции сохранения или выгрузки после выхода из зоны несохраняемости. Если зона несохраняемости не завершается до истечения времени ожидания или если процесс сохраняемости занимает слишком много времени, формируется исключение TimeoutException.

## <a name="enable-persistence-for-workflow-services-in-code"></a>Включение сохраняемости для служб Workflow Services в коде

Элемент **дураблеинстанЦингоптионс** <xref:System.ServiceModel.WorkflowServiceHost> класса имеет свойство **InstanceStore** , с помощью которого можно связать хранилище экземпляров с **WorkflowServiceHost**.

```csharp
// wsh is an instance of WorkflowServiceHost class
wsh.DurableInstancingOptions.InstanceStore = new SqlWorkflowInstanceStore();
```

При открытии **WorkflowServiceHost** автоматически включается сохранение, если **дураблеинстанЦингоптионс. InstanceStore** не имеет значение null.

Как правило, поведение службы предоставляет хранилище конкретного экземпляра для использования с узлом службы рабочего процесса с помощью свойства **InstanceStore** . Например, Склворкфловинстанцесторебехавиор создает экземпляр **SqlWorkflowInstanceStore**, настраивает его и присваивает его **дураблеинстанЦингоптионс. InstanceStore**.

## <a name="enable-persistence-for-workflow-services-using-an-application-configuration-file"></a>Включение сохраняемости для служб Workflow Services с помощью файла конфигурации приложения

Сохраняемость можно включить с помощью файла конфигурации приложения, добавив следующий код в файл app.config или web.config.

```xml
<configuration>
  <system.serviceModel>
    <behaviors>
      <serviceBehaviors>
        <behavior name="myBehavior">
          <sqlWorkflowInstanceStore connectionString="Data Source=myDatabaseServer;Initial Catalog=myPersistenceDatabase" />
        </behavior>
      </serviceBehaviors>
    </behaviors>
  </system.serviceModel>
</configuration>
```
