---
title: Настройка сериализации в службе рабочего процесса
ms.date: 03/30/2017
ms.assetid: aa70b290-a2ee-4c3c-90ea-d0a7665096ae
ms.openlocfilehash: d1cda33c8a469b4a54b6d282b99c07b23e91543e
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/26/2020
ms.locfileid: "96284203"
---
# <a name="configuring-serialization-in-a-workflow-service"></a>Настройка сериализации в службе рабочего процесса

Службы рабочих процессов являются службами Windows Communication Foundation (WCF) и поэтому могут использовать либо параметр <xref:System.Runtime.Serialization.DataContractSerializer> (по умолчанию), либо <xref:System.Xml.Serialization.XmlSerializer> . При написании кода служб, отличных от служб рабочих процессов, тип используемого сериализатора задается применительно к контракту службы или операции. При создании служб рабочих процессов WCF эти контракты не указываются в коде, а создаются во время выполнения путем вывода контракта. Дополнительные сведения о выводе контракта см.  [в разделе Использование контрактов в рабочем процессе](using-contracts-in-workflow.md).  Сериализатор определяется с помощью свойства <xref:System.ServiceModel.Activities.Receive.SerializerOption%2A>. Оно задается в конструкторе, как показано на следующем рисунке.  
  
 ![Задание свойства Сериализероптион в окне "Свойства".](./media/configuring-serialization-in-a-workflow-service/setting-serializer-property.png)  
  
 Сериализатор можно также задать в коде, как показано в следующем примере.  
  
```csharp  
Receive approveExpense = new Receive  
            {  
                OperationName = "ApproveExpense",  
                CanCreateInstance = true,  
                ServiceContractName = "FinanceService",  
                SerializerOption = SerializerOption.DataContractSerializer,  
                Content = ReceiveContent.Create(new OutArgument<Expense>(expense))  
            };  
```  
  
  Для служб рабочего процесса можно также указать известные типы. Дополнительные сведения об известных типах см. в разделе [Data Contract известные типы](data-contract-known-types.md). Известные типы можно указать в конструкторе или в коде. Чтобы указать известные типы в конструкторе, нажмите кнопку с многоточием рядом со свойством Кновнтипес в **окне Свойства** для <xref:System.ServiceModel.Activities.Receive> действия, как показано на следующем рисунке.
  
 ![Снимок экрана: диалоговое окно Свойства Кновнтипес.](./media/configuring-serialization-in-a-workflow-service/known-types-properties.png)  
  
 Откроется редактор коллекций типов, который позволяет искать и указывать известные типы.  
  
 ![Снимок экрана редактора коллекций типов.](./media/configuring-serialization-in-a-workflow-service/type-collection-editor.gif)  
  
 Щелкните ссылку **Добавить новый тип** и с помощью раскрывающегося списка выберите или найдите тип для добавления в коллекцию известные типы. Для указания известных типов в коде используется свойство <xref:System.ServiceModel.Activities.Receive.KnownTypes%2A>, как показано в следующем примере:  
  
```csharp
Receive approveExpense = new Receive  
            {  
                OperationName = "ApproveExpense",  
                CanCreateInstance = true,  
                ServiceContractName = "FinanceService",  
                SerializerOption = SerializerOption.DataContractSerializer,  
                Content = ReceiveContent.Create(new OutArgument<Expense>(expense))  
            };  
            approveExpense.KnownTypes.Add(typeof(Travel));  
            approveExpense.KnownTypes.Add(typeof(Meal));  
```
