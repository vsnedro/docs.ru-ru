---
ms.openlocfilehash: a806107456a65a4919592da9535a2617f677cfe0
ms.sourcegitcommit: cbacb5d2cebbf044547f6af6e74a9de866800985
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/05/2020
ms.locfileid: "89497908"
---
### <a name="wpf-dispatchersynchronizationcontextcreatecopy-now-returns-a-new-copy-instead-of-the-current-instance"></a>Метод DispatcherSynchronizationContext.CreateCopy WPF теперь возвращает новую копию вместо текущего экземпляра

#### <a name="details"></a>Подробнее

В .NET Framework 4 метод <xref:System.Windows.Threading.DispatcherSynchronizationContext.CreateCopy> возвращал ссылку на текущий экземпляр главным образом в качестве оптимизации производительности. В .NET Framework 4.5 он возвращает новый экземпляр, что позволяет впервые делать заключение о том, что одинаковые ссылки указывают на то, что выполняющийся поток находится в правильном контексте синхронизации.  Маловероятно, что будет затронут код, который проверяет подлинность этих ссылок, но в связи с изменением необходимо протестировать код, который вызывает <xref:System.Windows.Threading.DispatcherSynchronizationContext.CreateCopy>, в ходе миграции на .NET Framework 4.5 или более позднюю версию.

#### <a name="suggestion"></a>Предложение

Учитывайте, что <xref:System.Windows.Threading.DispatcherSynchronizationContext.CreateCopy> теперь возвращает новый объект <xref:System.Threading.SynchronizationContext?displayProperty=fullName>. Ранее код, который использовал эквивалентность ссылок, на самом деле не проверялся на нахождение в правильном контексте, но проверяется при создании в .NET Framework 4.5 или более поздних версиях.  Хотя маловероятно, что это приведет к серьезным проблемам, проверки путей к затронутому коду должно быть достаточно для определения проблемы.

| name    | Значение       |
|:--------|:------------|
| Область   |Дополнительный номер|
|Version|4.5|
|Type|Среда выполнения|

#### <a name="affected-apis"></a>Затронутые API

- <xref:System.Windows.Threading.DispatcherSynchronizationContext.CreateCopy?displayProperty=nameWithType>

<!--

#### Affected APIs

- `M:System.Windows.Threading.DispatcherSynchronizationContext.CreateCopy`

-->
