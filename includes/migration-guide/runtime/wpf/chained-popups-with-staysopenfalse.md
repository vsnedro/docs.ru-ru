---
ms.openlocfilehash: 7bf5f7e8a49acc2918dd0d68a1c54a5c277091b0
ms.sourcegitcommit: cbacb5d2cebbf044547f6af6e74a9de866800985
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/05/2020
ms.locfileid: "89496664"
---
### <a name="chained-popups-with-staysopenfalse"></a>Связанные всплывающие окна с StaysOpen=False

#### <a name="details"></a>Подробнее

Всплывающее окно с StaysOpen=False должно закрываться при щелчке за пределами всплывающего окна. Если несколько таких всплывающих окон связаны по цепочке (например, одно содержит другое), возникает множество проблем, в том числе следующие:<ul><li>Откройте два уровня и щелкните вне окна P2, но внутри окна P1.  Ничего не происходит.</li><li>Откройте два уровня и щелкните вне окна P1.  Оба всплывающих окна закроются.</li><li>Откройте и закройте два уровня.  Теперь попытайтесь снова открыть окно P2.  Ничего не происходит.</li><li>Попробуйте открыть три уровня.  Это невозможно.  (В зависимости от места щелчка, либо ничего не происходит, либо первые два уровня закрываются.) Теперь поведение окон в этих и других случаях исправлено.</li></ul>

| name    | Значение       |
|:--------|:------------|
| Область   |Пограничный случай|
|Version|4.7.1|
|Type|Среда выполнения|

#### <a name="affected-apis"></a>Затронутые API

- <xref:System.Windows.Controls.Primitives.Popup.StaysOpen?displayProperty=nameWithType>

<!--

#### Affected APIs

- `P:System.Windows.Controls.Primitives.Popup.StaysOpen`

-->
