---
ms.openlocfilehash: d25c14f93da5fe8acf06269554fed30ddc6bc95d
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/01/2020
ms.locfileid: "85614753"
---
### <a name="operationcontextcurrent-may-return-null-when-called-in-a-using-clause"></a>OperationContext.Current может возвращать значение NULL при вызове в конструкции Using

#### <a name="details"></a>Подробнее

<xref:System.ServiceModel.OperationContext.Current?displayProperty=nameWithType> может возвращать `null` и создавать <xref:System.NullReferenceException>, если все следующие условия верны:

- Вы извлекаете значение свойства <xref:System.ServiceModel.OperationContext.Current?displayProperty=nameWithType> в методе, который возвращает <xref:System.Threading.Tasks.Task> или <xref:System.Threading.Tasks.Task%601>.
- Вы создаете экземпляр объекта <xref:System.ServiceModel.OperationContextScope> в конструкции `using`.
- Вы получаете значение свойства <xref:System.ServiceModel.OperationContext.Current?displayProperty=nameWithType> в `using statement`. Пример:

```csharp
using (new OperationContextScope(OperationContext.Current))
{
    // OperationContext.Current is null.
    OperationContext context = OperationContext.Current;

    // ...
}
```

#### <a name="suggestion"></a>Предложение

Чтобы устранить эту проблему, выполните следующие действия:

- Измените код таким образом, чтобы создать экземпляр объекта <xref:System.ServiceModel.OperationContext.Current%2A>, который не равен `null`:

    ```csharp
    OperationContext ocx = OperationContext.Current;
    using (new OperationContextScope(OperationContext.Current))
    {
        OperationContext.Current = new OperationContext(ocx.Channel);

        // ...
    }
    ```

- Установите последнее обновление для .NET Framework 4.6.2 или обновитесь до последней версии платформы .NET Framework. Это приведет к отключению потока <xref:System.Threading.ExecutionContext> в <xref:System.ServiceModel.OperationContext.Current?displayProperty=nameWithType> и восстановлению поведения приложений WCF в .NET Framework 4.6.1 и более ранних версий. Это поведение можно настраивать. Это эквивалентно добавлению следующего параметра приложения в файл конфигурации:

    ```xml
    <appSettings>
      <add key="Switch.System.ServiceModel.DisableOperationContextAsyncFlow" value="true" />
    </appSettings>
    ```

    Если это изменение нежелательно и приложение зависит от выполнения контекста при переходе между контекстами операции, этот поток можно включить следующим образом:

    ```xml
    <appSettings>
      <add key="Switch.System.ServiceModel.DisableOperationContextAsyncFlow" value="false" />
    </appSettings>
    ```

| name    | Значение       |
|:--------|:------------|
| Область   | Пограничный случай        |
| Version | 4.6.2       |
| Type    | Изменение целевой платформы |

#### <a name="affected-apis"></a>Затронутые API

- <xref:System.ServiceModel.OperationContext.Current?displayProperty=nameWithType>
