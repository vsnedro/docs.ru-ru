---
ms.openlocfilehash: c7500550cd9714a9788a7dea68af04823f000f7f
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/01/2020
ms.locfileid: "85614797"
---
### <a name="stack-traces-obtained-when-using-portable-pdbs-now-include-source-file-and-line-information-if-requested"></a>Трассировки стека, полученные при использовании переносимых PDB-файлов, теперь включают сведения об исходном файле и строке по запросу

#### <a name="details"></a>Подробнее

Начиная с .NET Framework 4.7.2 трассировки стека, полученные при использовании переносимых PDB-файлов, включают сведения об исходном файле и строке по запросу. В версиях до .NET Framework 4.7.2 сведения об исходном файле и строке были недоступны при использовании переносимых PDB-файлов, даже по явному запросу.

#### <a name="suggestion"></a>Предложение

Для приложений, предназначенных для .NET Framework 4.7.2, можно отказаться от вывода сведений об исходном файле и строке при использовании переносимых PDB-файлов, если это нежелательно, добавив следующую строку в раздел `<runtime>` файла `app.config`:

```xml
<runtime>
  <AppContextSwitchOverrides value="Switch.System.Diagnostics.IgnorePortablePDBsInStackTraces=true" />
</runtime>
```

Для приложений, которые предназначены для более ранних версий .NET Framework, но выполняются в .NET Framework 4.7.2 или более поздней версии, можно включить вывод сведений об исходном файле и строке при использовании переносимых PDB-файлов, добавив следующую строку в раздел `<runtime>` файла `app.config`:

```xml
<runtime>
  <AppContextSwitchOverrides value="Switch.System.Diagnostics.IgnorePortablePDBsInStackTraces=false" />
</runtime>
```

| name    | Значение       |
|:--------|:------------|
| Область   | Пограничный случай        |
| Version | 4.7.2       |
| Type    | Изменение целевой платформы |

#### <a name="affected-apis"></a>Затронутые API

- <xref:System.Diagnostics.StackTrace.%23ctor(System.Boolean)>
- <xref:System.Diagnostics.StackTrace.%23ctor(System.Exception,System.Boolean)>
- <xref:System.Diagnostics.StackTrace.%23ctor(System.Exception,System.Int32,System.Boolean)>
