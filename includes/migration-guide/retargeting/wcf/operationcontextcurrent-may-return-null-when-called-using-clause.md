---
ms.openlocfilehash: d25c14f93da5fe8acf06269554fed30ddc6bc95d
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.contentlocale: ru-RU
ms.lasthandoff: 07/01/2020
ms.locfileid: "85614753"
---
### <a name="operationcontextcurrent-may-return-null-when-called-in-a-using-clause"></a><span data-ttu-id="b0e48-101">OperationContext.Current может возвращать значение NULL при вызове в конструкции Using</span><span class="sxs-lookup"><span data-stu-id="b0e48-101">OperationContext.Current may return null when called in a using clause</span></span>

#### <a name="details"></a><span data-ttu-id="b0e48-102">Подробнее</span><span class="sxs-lookup"><span data-stu-id="b0e48-102">Details</span></span>

<span data-ttu-id="b0e48-103"><xref:System.ServiceModel.OperationContext.Current?displayProperty=nameWithType> может возвращать `null` и создавать <xref:System.NullReferenceException>, если все следующие условия верны:</span><span class="sxs-lookup"><span data-stu-id="b0e48-103"><xref:System.ServiceModel.OperationContext.Current?displayProperty=nameWithType> may return `null` and a <xref:System.NullReferenceException> may result if all of the following conditions are true:</span></span>

- <span data-ttu-id="b0e48-104">Вы извлекаете значение свойства <xref:System.ServiceModel.OperationContext.Current?displayProperty=nameWithType> в методе, который возвращает <xref:System.Threading.Tasks.Task> или <xref:System.Threading.Tasks.Task%601>.</span><span class="sxs-lookup"><span data-stu-id="b0e48-104">You retrieve the value of the <xref:System.ServiceModel.OperationContext.Current?displayProperty=nameWithType> property in a method that returns a <xref:System.Threading.Tasks.Task> or <xref:System.Threading.Tasks.Task%601>.</span></span>
- <span data-ttu-id="b0e48-105">Вы создаете экземпляр объекта <xref:System.ServiceModel.OperationContextScope> в конструкции `using`.</span><span class="sxs-lookup"><span data-stu-id="b0e48-105">You instantiate the <xref:System.ServiceModel.OperationContextScope> object in a `using` clause.</span></span>
- <span data-ttu-id="b0e48-106">Вы получаете значение свойства <xref:System.ServiceModel.OperationContext.Current?displayProperty=nameWithType> в `using statement`.</span><span class="sxs-lookup"><span data-stu-id="b0e48-106">You retrieve the value of the <xref:System.ServiceModel.OperationContext.Current?displayProperty=nameWithType> property within the `using statement`.</span></span> <span data-ttu-id="b0e48-107">Пример:</span><span class="sxs-lookup"><span data-stu-id="b0e48-107">For example:</span></span>

```csharp
using (new OperationContextScope(OperationContext.Current))
{
    // OperationContext.Current is null.
    OperationContext context = OperationContext.Current;

    // ...
}
```

#### <a name="suggestion"></a><span data-ttu-id="b0e48-108">Предложение</span><span class="sxs-lookup"><span data-stu-id="b0e48-108">Suggestion</span></span>

<span data-ttu-id="b0e48-109">Чтобы устранить эту проблему, выполните следующие действия:</span><span class="sxs-lookup"><span data-stu-id="b0e48-109">To address this issue, you can do the following:</span></span>

- <span data-ttu-id="b0e48-110">Измените код таким образом, чтобы создать экземпляр объекта <xref:System.ServiceModel.OperationContext.Current%2A>, который не равен `null`:</span><span class="sxs-lookup"><span data-stu-id="b0e48-110">Modify your code as follows to instantiate a new non- `null` <xref:System.ServiceModel.OperationContext.Current%2A> object:</span></span>

    ```csharp
    OperationContext ocx = OperationContext.Current;
    using (new OperationContextScope(OperationContext.Current))
    {
        OperationContext.Current = new OperationContext(ocx.Channel);

        // ...
    }
    ```

- <span data-ttu-id="b0e48-111">Установите последнее обновление для .NET Framework 4.6.2 или обновитесь до последней версии платформы .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="b0e48-111">Install the latest update to the .NET Framework 4.6.2, or upgrade to a later version of the .NET Framework.</span></span> <span data-ttu-id="b0e48-112">Это приведет к отключению потока <xref:System.Threading.ExecutionContext> в <xref:System.ServiceModel.OperationContext.Current?displayProperty=nameWithType> и восстановлению поведения приложений WCF в .NET Framework 4.6.1 и более ранних версий.</span><span class="sxs-lookup"><span data-stu-id="b0e48-112">This disables the flow of the <xref:System.Threading.ExecutionContext> in <xref:System.ServiceModel.OperationContext.Current?displayProperty=nameWithType> and restores the behavior of WCF applications in the .NET Framework 4.6.1 and earlier versions.</span></span> <span data-ttu-id="b0e48-113">Это поведение можно настраивать. Это эквивалентно добавлению следующего параметра приложения в файл конфигурации:</span><span class="sxs-lookup"><span data-stu-id="b0e48-113">This behavior is configurable; it is equivalent to adding the following app setting to your configuration file:</span></span>

    ```xml
    <appSettings>
      <add key="Switch.System.ServiceModel.DisableOperationContextAsyncFlow" value="true" />
    </appSettings>
    ```

    <span data-ttu-id="b0e48-114">Если это изменение нежелательно и приложение зависит от выполнения контекста при переходе между контекстами операции, этот поток можно включить следующим образом:</span><span class="sxs-lookup"><span data-stu-id="b0e48-114">If this change is undesirable and your application depends on execution context flowing between operation contexts, you can enable its flow as follows:</span></span>

    ```xml
    <appSettings>
      <add key="Switch.System.ServiceModel.DisableOperationContextAsyncFlow" value="false" />
    </appSettings>
    ```

| <span data-ttu-id="b0e48-115">name</span><span class="sxs-lookup"><span data-stu-id="b0e48-115">Name</span></span>    | <span data-ttu-id="b0e48-116">Значение</span><span class="sxs-lookup"><span data-stu-id="b0e48-116">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="b0e48-117">Область</span><span class="sxs-lookup"><span data-stu-id="b0e48-117">Scope</span></span>   | <span data-ttu-id="b0e48-118">Пограничный случай</span><span class="sxs-lookup"><span data-stu-id="b0e48-118">Edge</span></span>        |
| <span data-ttu-id="b0e48-119">Version</span><span class="sxs-lookup"><span data-stu-id="b0e48-119">Version</span></span> | <span data-ttu-id="b0e48-120">4.6.2</span><span class="sxs-lookup"><span data-stu-id="b0e48-120">4.6.2</span></span>       |
| <span data-ttu-id="b0e48-121">Type</span><span class="sxs-lookup"><span data-stu-id="b0e48-121">Type</span></span>    | <span data-ttu-id="b0e48-122">Изменение целевой платформы</span><span class="sxs-lookup"><span data-stu-id="b0e48-122">Retargeting</span></span> |

#### <a name="affected-apis"></a><span data-ttu-id="b0e48-123">Затронутые API</span><span class="sxs-lookup"><span data-stu-id="b0e48-123">Affected APIs</span></span>

- <xref:System.ServiceModel.OperationContext.Current?displayProperty=nameWithType>
