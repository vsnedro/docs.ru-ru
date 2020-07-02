---
ms.openlocfilehash: a3ba42868577ac20ea2e082f90fc4973a1bfe108
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/01/2020
ms.locfileid: "85622379"
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
