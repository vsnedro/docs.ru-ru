---
ms.openlocfilehash: 92c03328414410d56a2ff5f445639757367b42c7
ms.sourcegitcommit: 9a4488a3625866335e83a20da5e9c5286b1f034c
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/15/2020
ms.locfileid: "83420436"
---
### <a name="processstartinfo-throws-invalidoperationexception-for-processes-you-didnt-start"></a>Process.StartInfo выдает исключение InvalidOperationException для процессов, которые не были запущены

Чтение свойства <xref:System.Diagnostics.Process.StartInfo?displayProperty=nameWithType> для процессов, которые не были запущены кодом, приводит к возникновению <xref:System.InvalidOperationException>.

#### <a name="change-description"></a>Описание изменений

В .NET Framework обращение к свойству <xref:System.Diagnostics.Process.StartInfo?displayProperty=nameWithType> для процессов, которые не были запущены кодом, возвращает пустой объект <xref:System.Diagnostics.ProcessStartInfo>. Пустой объект содержит значения по умолчанию для всех его свойств, кроме <xref:System.Diagnostics.ProcessStartInfo.EnvironmentVariables>.

Начиная с .NET Core 1.0, при чтении свойства <xref:System.Diagnostics.Process.StartInfo?displayProperty=nameWithType> для процесса, который не был запущен (путем вызова <xref:System.Diagnostics.Process.Start%2A?displayProperty=nameWithType>) возникает исключение <xref:System.InvalidOperationException>.

#### <a name="version-introduced"></a>Представленная версия

1.0

#### <a name="recommended-action"></a>Рекомендованное действие

Не обращайтесь к свойству <xref:System.Diagnostics.Process.StartInfo?displayProperty=nameWithType> для процессов, которые не были запущены кодом. Например, не считывайте это свойство для процессов, возвращаемых <xref:System.Diagnostics.Process.GetProcesses%2A?displayProperty=nameWithType>.

#### <a name="category"></a>Категория

Библиотеки Core .NET

#### <a name="affected-apis"></a>Затронутые API

- <xref:System.Diagnostics.Process.StartInfo?displayProperty=fullName>

<!--

#### Affected APIs

- `P:System.Diagnostics.Process.StartInfo`

-->
