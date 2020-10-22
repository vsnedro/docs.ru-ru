---
ms.openlocfilehash: 80d13609f1b02ae0ac875b2028e745670bb8f503
ms.sourcegitcommit: 39b1d5f2978be15409c189a66ab30781d9082cd8
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/14/2020
ms.locfileid: "92050574"
---
### <a name="frameworkdescriptions-value-is-net-instead-of-net-core"></a>Значение FrameworkDescription изменено с .NET Core на .NET

<xref:System.Runtime.InteropServices.RuntimeInformation.FrameworkDescription?displayProperty=nameWithType> теперь возвращает ".NET" вместо ".NET Core".

#### <a name="change-description"></a>Описание изменений

В предыдущих версиях .NET <xref:System.Runtime.InteropServices.RuntimeInformation.FrameworkDescription?displayProperty=nameWithType> возвращает ".NET Core" в составе строки описания, например `.NET Core 3.1.1`.

Начиная с .NET 5.0 <xref:System.Runtime.InteropServices.RuntimeInformation.FrameworkDescription?displayProperty=nameWithType> возвращает ".NET" в составе строки описания, например `.NET 5.0.0`.

#### <a name="reason-for-change"></a>Причина изменения

В .NET 5 в качестве краткого моникера целевой платформы вместо `netcoreapp` используется `net`. В целях обеспечения согласованности также было обновлено описание платформы. Это изменение носит косметический характер, так как `FrameworkName` кодируется только в свойстве <xref:System.Runtime.InteropServices.RuntimeInformation.FrameworkDescription?displayProperty=nameWithType>.

#### <a name="version-introduced"></a>Представленная версия

5.0

#### <a name="recommended-action"></a>Рекомендованное действие

Обновите код, в котором выполняется поиск ".NET Core" в строке, возвращаемой <xref:System.Runtime.InteropServices.RuntimeInformation.FrameworkDescription>.

#### <a name="category"></a>Категория

Библиотеки Core .NET

#### <a name="affected-apis"></a>Затронутые API

- <xref:System.Runtime.InteropServices.RuntimeInformation.FrameworkDescription?displayProperty=fullName>

<!--

#### Affected APIs

- `P:System.Runtime.InteropServices.RuntimeInformation.FrameworkDescription`

-->
