---
ms.openlocfilehash: a133c2ea48df11915f8708029c70549e8a1ccefd
ms.sourcegitcommit: cbacb5d2cebbf044547f6af6e74a9de866800985
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/05/2020
ms.locfileid: "89496438"
---
### <a name="wpf-windows-are-rendered-without-clipping-when-extending-outside-a-single-monitor"></a>Окна WPF отображаются без обрезки, если изображение выходит за пределы одного монитора

#### <a name="details"></a>Подробнее

В .NET Framework 4.6 на компьютере под управлением Windows 8 и более поздних версий все содержимое окна выводится без обрезки, если изображение выходит за пределы одного экрана при использовании нескольких мониторов. Это отличается от предыдущих версий .NET Framework, где окна WPF обрезались, если выходили за пределы одного экрана.

#### <a name="suggestion"></a>Предложение

Это поведение (отсутствие или наличие обрезки) можно задать явным образом с помощью элемента <code>&lt;EnableMultiMonitorDisplayClipping&gt;</code> в <code>&lt;appSettings&gt;</code> в файле конфигурации приложения или задав свойство <code>EnableMultiMonitorDisplayClipping</code> при запуске приложения.

| name    | Значение       |
|:--------|:------------|
| Область   |Дополнительный номер|
|Version|4.6|
|Type|Среда выполнения|

#### <a name="affected-apis"></a>Затронутые API

Невозможно обнаружить с помощью анализа API.

<!--

#### Affected APIs

Not detectable via API analysis.

-->
