---
ms.openlocfilehash: f61cf21f9f30662cc8e383bb3aeb5c642f1665b8
ms.sourcegitcommit: cbacb5d2cebbf044547f6af6e74a9de866800985
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/05/2020
ms.locfileid: "89496276"
---
### <a name="deadlock-may-result-when-using-reentrant-services"></a>При использовании реентерабельных служб может возникнуть взаимоблокировка

#### <a name="details"></a>Подробнее

В реентерабельной службе может возникнуть взаимоблокировка, которая ограничивает экземпляры службы одним потоком выполнения за раз. Службы, в которых может возникнуть это проблема, имеют следующий <xref:System.ServiceModel.ServiceBehaviorAttribute> в коде:

```csharp
[ServiceBehavior(ConcurrencyMode = ConcurrencyMode.Reentrant)]
```

#### <a name="suggestion"></a>Предложение

Чтобы устранить эту проблему, выполните следующие действия:

- Задайте для режима параллелизма службы значение <xref:System.ServiceModel.ConcurrencyMode.Single?displayProperty=nameWithType> или <xref:System.ServiceModel.ConcurrencyMode.Multiple?displayProperty=nameWithType>. Пример:

```csharp
[ServiceBehavior(ConcurrencyMode = ConcurrencyMode.Reentrant)]
```

- Установите последнее обновление для .NET Framework 4.6.2 или обновитесь до последней версии платформы .NET Framework. Это приведет к отключению потока <xref:System.Threading.ExecutionContext> в <xref:System.ServiceModel.OperationContext.Current?displayProperty=nameWithType>. Это поведение можно настраивать. Это эквивалентно добавлению следующего параметра приложения в файл конфигурации:

```xml
<appSettings>
  <add key="Switch.System.ServiceModel.DisableOperationContextAsyncFlow" value="true" />
</appSettings>
```

Значение `Switch.System.ServiceModel.DisableOperationContextAsyncFlow` нельзя устанавливать на `false` для реентерабельных служб.

| name    | Значение       |
|:--------|:------------|
| Область   | Дополнительный номер       |
| Version | 4.6.2       |
| Type    | Изменение целевой платформы |

#### <a name="affected-apis"></a>Затронутые API

- <xref:System.ServiceModel.ServiceBehaviorAttribute?displayProperty=nameWithType>
- <xref:System.ServiceModel.ConcurrencyMode.Reentrant?displayProperty=nameWithType>
