---
ms.openlocfilehash: dcc64fe651b219ff1416c0afcdb4c6d275160f4b
ms.sourcegitcommit: 88fbb019b84c2d044d11fb4f6004aec07f2b25b1
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/05/2021
ms.locfileid: "97911546"
---
### <a name="change-in-default-value-of-useshellexecute"></a>Изменение значения по умолчанию для UseShellExecute

<xref:System.Diagnostics.ProcessStartInfo.UseShellExecute?displayProperty=nameWithType> имеет значение `false` по умолчанию в .NET Core. В .NET Framework его значение по умолчанию — `true`.

#### <a name="change-description"></a>Описание изменений

<xref:System.Diagnostics.Process.Start%2A?displayProperty=nameWithType> позволяет запускать приложение напрямую, например с помощью кода, как `Process.Start("mspaint.exe")`, запускающего Paint. Это также позволяет косвенно запускать связанное приложение, если для <xref:System.Diagnostics.ProcessStartInfo.UseShellExecute?displayProperty=nameWithType> установлено значение `true`. В .NET Framework значением по умолчанию для <xref:System.Diagnostics.ProcessStartInfo.UseShellExecute?displayProperty=nameWithType> является `true`, что означает, что такой код как `Process.Start("mytextfile.txt")` будет запускать Блокнот, если вы связали файлы *.txt* с этим редактором. Чтобы предотвратить косвенный запуск приложения на .NET Framework, необходимо явно установить `false` на <xref:System.Diagnostics.ProcessStartInfo.UseShellExecute?displayProperty=nameWithType>. В .NET Core значением по умолчанию для <xref:System.Diagnostics.ProcessStartInfo.UseShellExecute?displayProperty=nameWithType> является значение `false`. Это означает, что связанные по умолчанию приложения не запускаются при вызове `Process.Start`.

Следующие свойства <xref:System.Diagnostics.ProcessStartInfo?displayProperty=nameWithType> работают только в том случае, если <xref:System.Diagnostics.ProcessStartInfo.UseShellExecute?displayProperty=nameWithType> имеет значение `true`:

- <xref:System.Diagnostics.ProcessStartInfo.CreateNoWindow?displayProperty=nameWithType>
- <xref:System.Diagnostics.ProcessStartInfo.ErrorDialog?displayProperty=nameWithType>
- <xref:System.Diagnostics.ProcessStartInfo.Verb?displayProperty=nameWithType>
- <xref:System.Diagnostics.ProcessStartInfo.WindowStyle?displayProperty=nameWithType>.

Это изменение введено в .NET Core для повышения производительности. Как правило, <xref:System.Diagnostics.Process.Start%2A?displayProperty=nameWithType> используется для непосредственного запуска приложения. Запуск приложения напрямую не требует затрагивания оболочки Windows и влечет за собой соответствующие расходы на производительность. Чтобы ускорить этот вариант по умолчанию, .NET Core изменяет значение по умолчанию <xref:System.Diagnostics.ProcessStartInfo.UseShellExecute?displayProperty=nameWithType> на `false`. При необходимости вы можете выбрать более медленный путь.

#### <a name="version-introduced"></a>Представленная версия

2.1

> [!NOTE]
> В более ранних версиях .NET Core `UseShellExecute` не был внедрен для Windows.

#### <a name="recommended-action"></a>Рекомендованное действие

Если приложение полагается на прежнее поведение, вызовите <xref:System.Diagnostics.Process.Start(System.Diagnostics.ProcessStartInfo)?displayProperty=nameWithType>, указав для параметра <xref:System.Diagnostics.ProcessStartInfo.UseShellExecute> значение `true` в объекте <xref:System.Diagnostics.ProcessStartInfo>.

#### <a name="category"></a>Категория

Библиотеки Core .NET

#### <a name="affected-apis"></a>Затронутые API

- <xref:System.Diagnostics.Process.Start%2A?displayProperty=nameWithType>
- <xref:System.Diagnostics.ProcessStartInfo?displayProperty=nameWithType>

<!--

#### Affected APIs

- `Overload:System.Diagnostics.Process.Start`
- `M:System.Diagnostics.ProcessStartInfo`

-->
