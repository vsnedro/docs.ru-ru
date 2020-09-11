---
ms.openlocfilehash: f61cf21f9f30662cc8e383bb3aeb5c642f1665b8
ms.sourcegitcommit: cbacb5d2cebbf044547f6af6e74a9de866800985
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/05/2020
ms.locfileid: "89496276"
---
### <a name="deadlock-may-result-when-using-reentrant-services"></a><span data-ttu-id="3adf8-101">При использовании реентерабельных служб может возникнуть взаимоблокировка</span><span class="sxs-lookup"><span data-stu-id="3adf8-101">Deadlock may result when using Reentrant services</span></span>

#### <a name="details"></a><span data-ttu-id="3adf8-102">Подробнее</span><span class="sxs-lookup"><span data-stu-id="3adf8-102">Details</span></span>

<span data-ttu-id="3adf8-103">В реентерабельной службе может возникнуть взаимоблокировка, которая ограничивает экземпляры службы одним потоком выполнения за раз.</span><span class="sxs-lookup"><span data-stu-id="3adf8-103">A deadlock may result in a Reentrant service, which restricts instances of the service to one thread of execution at a time.</span></span> <span data-ttu-id="3adf8-104">Службы, в которых может возникнуть это проблема, имеют следующий <xref:System.ServiceModel.ServiceBehaviorAttribute> в коде:</span><span class="sxs-lookup"><span data-stu-id="3adf8-104">Services prone to encounter this problem will have the following <xref:System.ServiceModel.ServiceBehaviorAttribute> in their code:</span></span>

```csharp
[ServiceBehavior(ConcurrencyMode = ConcurrencyMode.Reentrant)]
```

#### <a name="suggestion"></a><span data-ttu-id="3adf8-105">Предложение</span><span class="sxs-lookup"><span data-stu-id="3adf8-105">Suggestion</span></span>

<span data-ttu-id="3adf8-106">Чтобы устранить эту проблему, выполните следующие действия:</span><span class="sxs-lookup"><span data-stu-id="3adf8-106">To address this issue, you can do the following:</span></span>

- <span data-ttu-id="3adf8-107">Задайте для режима параллелизма службы значение <xref:System.ServiceModel.ConcurrencyMode.Single?displayProperty=nameWithType> или <xref:System.ServiceModel.ConcurrencyMode.Multiple?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="3adf8-107">Set the service's concurrency mode to <xref:System.ServiceModel.ConcurrencyMode.Single?displayProperty=nameWithType> or <xref:System.ServiceModel.ConcurrencyMode.Multiple?displayProperty=nameWithType>.</span></span> <span data-ttu-id="3adf8-108">Пример:</span><span class="sxs-lookup"><span data-stu-id="3adf8-108">For example:</span></span>

```csharp
[ServiceBehavior(ConcurrencyMode = ConcurrencyMode.Reentrant)]
```

- <span data-ttu-id="3adf8-109">Установите последнее обновление для .NET Framework 4.6.2 или обновитесь до последней версии платформы .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="3adf8-109">Install the latest update to the .NET Framework 4.6.2, or upgrade to a later version of the .NET Framework.</span></span> <span data-ttu-id="3adf8-110">Это приведет к отключению потока <xref:System.Threading.ExecutionContext> в <xref:System.ServiceModel.OperationContext.Current?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="3adf8-110">This disables the flow of the <xref:System.Threading.ExecutionContext> in <xref:System.ServiceModel.OperationContext.Current?displayProperty=nameWithType>.</span></span> <span data-ttu-id="3adf8-111">Это поведение можно настраивать. Это эквивалентно добавлению следующего параметра приложения в файл конфигурации:</span><span class="sxs-lookup"><span data-stu-id="3adf8-111">This behavior is configurable; it is equivalent to adding the following app setting to your configuration file:</span></span>

```xml
<appSettings>
  <add key="Switch.System.ServiceModel.DisableOperationContextAsyncFlow" value="true" />
</appSettings>
```

<span data-ttu-id="3adf8-112">Значение `Switch.System.ServiceModel.DisableOperationContextAsyncFlow` нельзя устанавливать на `false` для реентерабельных служб.</span><span class="sxs-lookup"><span data-stu-id="3adf8-112">The value of `Switch.System.ServiceModel.DisableOperationContextAsyncFlow` should never be set to `false` for Reentrant services.</span></span>

| <span data-ttu-id="3adf8-113">name</span><span class="sxs-lookup"><span data-stu-id="3adf8-113">Name</span></span>    | <span data-ttu-id="3adf8-114">Значение</span><span class="sxs-lookup"><span data-stu-id="3adf8-114">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="3adf8-115">Область</span><span class="sxs-lookup"><span data-stu-id="3adf8-115">Scope</span></span>   | <span data-ttu-id="3adf8-116">Дополнительный номер</span><span class="sxs-lookup"><span data-stu-id="3adf8-116">Minor</span></span>       |
| <span data-ttu-id="3adf8-117">Version</span><span class="sxs-lookup"><span data-stu-id="3adf8-117">Version</span></span> | <span data-ttu-id="3adf8-118">4.6.2</span><span class="sxs-lookup"><span data-stu-id="3adf8-118">4.6.2</span></span>       |
| <span data-ttu-id="3adf8-119">Type</span><span class="sxs-lookup"><span data-stu-id="3adf8-119">Type</span></span>    | <span data-ttu-id="3adf8-120">Изменение целевой платформы</span><span class="sxs-lookup"><span data-stu-id="3adf8-120">Retargeting</span></span> |

#### <a name="affected-apis"></a><span data-ttu-id="3adf8-121">Затронутые API</span><span class="sxs-lookup"><span data-stu-id="3adf8-121">Affected APIs</span></span>

- <xref:System.ServiceModel.ServiceBehaviorAttribute?displayProperty=nameWithType>
- <xref:System.ServiceModel.ConcurrencyMode.Reentrant?displayProperty=nameWithType>
