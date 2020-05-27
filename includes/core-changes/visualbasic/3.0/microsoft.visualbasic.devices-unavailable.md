---
ms.openlocfilehash: a35de09b9a7bb9686433205359c3cc55954c29c3
ms.sourcegitcommit: 0926684d8d34f4c6b5acce58d2193db093cb9cf2
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/20/2020
ms.locfileid: "83721394"
---
### <a name="types-in-microsoftvisualbasicdevices-namespace-not-available"></a>Типы из пространства имен Microsoft.VisualBasic.Devices недоступны

Типы в пространстве имен <xref:Microsoft.VisualBasic.Devices?displayProperty=fullName> недоступны.

#### <a name="version-introduced"></a>Представленная версия

.NET Core 3.0 (предварительная версия 8)

#### <a name="change-description"></a>Описание изменений

Типы из пространства имен <xref:Microsoft.VisualBasic.Devices?displayProperty=fullName> были доступны в некоторых предварительных выпусках .NET Core 3.0. Начиная с предварительной версии 9 .NET Core 3.0, они больше не доступны.

Типы были удалены во избежание ненужных зависимостей сборок или критических изменений в последующих выпусках.

#### <a name="recommended-action"></a>Рекомендованное действие

Если в вашем коде применяются типы <xref:Microsoft.VisualBasic.Devices> и их члены, вы можете использовать соответствующий тип или член из библиотеки классов .NET. Например, возможности, эквивалентные классу <xref:Microsoft.VisualBasic.Devices.Clock?displayProperty=nameWithType>, предоставляются типами <xref:System.DateTime?displayProperty=nameWithType> и <xref:System.Environment?displayProperty=nameWithType>, а классу <xref:Microsoft.VisualBasic.Devices.Ports?displayProperty=nameWithType> — типами в пространстве имен <xref:System.IO.Ports?displayProperty=nameWithType>.

#### <a name="category"></a>Категория

Visual Basic

#### <a name="affected-apis"></a>Затронутые API

- <xref:Microsoft.VisualBasic.Devices?displayProperty=fullName>

<!--

#### Affected APIs

- `N:Microsoft.VisualBasic.Devices`

-->
