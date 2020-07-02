---
ms.openlocfilehash: dd7d3e445772e4b5ec148576ccd1374d56e251bd
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/01/2020
ms.locfileid: "85614784"
---
### <a name="deadlock-may-result-when-using-reentrant-services"></a>При использовании реентерабельных служб может возникнуть взаимоблокировка

#### <a name="details"></a>Подробнее

В реентерабельной службе может возникнуть взаимоблокировка, которая ограничивает экземпляры службы одним потоком выполнения за раз. Службы, в которых может возникнуть это проблема, имеют следующий <xref:System.ServiceModel.ServiceBehaviorAttribute> в коде:

```csharp
[ServiceBehavior(ConcurrencyMode = ConcurrencyMode.Reentrant)]
```

#### <a name="suggestion"></a>Предложение

Чтобы устранить эту проблему, выполните следующие действия:

- Установите для режима параллелизма службы <xref:System.ServiceModel.ConcurrencyMode.Single?displayProperty=nameWithType> или &lt;System.ServiceModel.ConcurrencyMode.Multiple?displayProperty=nameWithType&gt;. Пример:

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
