---
ms.openlocfilehash: d6405573e476ce18513938b500041adefbeeef1b
ms.sourcegitcommit: cbacb5d2cebbf044547f6af6e74a9de866800985
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/05/2020
ms.locfileid: "89496693"
---
### <a name="ribbongroup-background-is-set-to-transparent-in-localized-builds"></a>В локализованных сборках для RibbonGroup устанавливается прозрачный фон

#### <a name="details"></a>Подробнее

Фон <xref:System.Windows.Controls.Ribbon.RibbonGroup?displayProperty=fullName> в локализованных сборках всегда закрашивается с использованием прозрачной кисти, что ухудшает восприятие пользовательского интерфейса. Решение приведено в исправлении WPF в .NET Framework 4.7, где были обновлены локализованные ресурсы для <xref:System.Windows.Controls.Ribbon.RibbonGroup?displayProperty=fullName>, благодаря чему гарантируется выбор правильной кисти.

#### <a name="suggestion"></a>Предложение

Выполните обновление до .NET Framework 4.7.

| name    | Значение       |
|:--------|:------------|
| Область   |Пограничный случай|
|Version|4.6.2|
|Type|Среда выполнения|

#### <a name="affected-apis"></a>Затронутые API

Невозможно обнаружить с помощью анализа API.

<!--

#### Affected APIs

Not detectable via API analysis.

-->
