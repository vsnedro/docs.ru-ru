---
ms.openlocfilehash: ada458ffeeba95d4989507f90c789b159f359797
ms.sourcegitcommit: a69d548f90a03e105ee6701236c38390ecd9ccd1
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/14/2020
ms.locfileid: "90065171"
---
### <a name="ca1417-outattribute-on-string-parameter-for-pinvoke"></a>CA1417. OutAttribute в строковом параметре для P/Invoke

Правило [CA1417](/visualstudio/code-quality/ca1417) анализатора кода .NET включено по умолчанию начиная с .NET 5.0. Оно создает предупреждение сборки для любого определения метода [вызова неуправляемого кода (P/Invoke)](../../../../docs/standard/native-interop/pinvoke.md), в которых параметр <xref:System.String> передается по значению и отмечается с помощью <xref:System.Runtime.InteropServices.OutAttribute>.

#### <a name="change-description"></a>Описание изменений

Начиная с .NET 5.0, пакет SDK для .NET включает [анализаторы исходного кода .NET](../../../../docs/fundamentals/productivity/code-analysis.md). Некоторые из этих правил включены по умолчанию, включая [CA1417](/visualstudio/code-quality/ca1417). Если проект содержит код, нарушающий это правило и настроенный на обработку предупреждений как ошибок, это изменение может нарушить сборку.

Флаги правила CA1417 определения методов [P/Invoke](../../../../docs/standard/native-interop/pinvoke.md), в которых параметр <xref:System.String> отмечен атрибутом <xref:System.Runtime.InteropServices.OutAttribute> и передается по значению. Пример:

```csharp
[DllImport("MyLibrary")]
private static extern void PIMethod([Out] string s);
```

Среда выполнения .NET поддерживает таблицу, называемую пулом интернирования, которая содержит одну ссылку на каждую уникальную строку литерала в программе. Если интернированная строка, помеченная <xref:System.Runtime.InteropServices.OutAttribute>, передается по значению в метод P/Invoke, среду выполнения можно дестабилизировать. Дополнительные сведения об интернировании строк см. в разделе примечаний для <xref:System.String.Intern(System.String)?displayProperty=nameWithType>.

#### <a name="version-introduced"></a>Представленная версия

5.0, предварительная версия 8

#### <a name="recommended-action"></a>Рекомендованное действие

- Если необходимо выполнить маршалирование измененных строковых данных обратно в вызывающий объект, передайте строку по ссылке.

  ```csharp
  [DllImport("MyLibrary")]
  private static extern void PIMethod(out string s);
  ```

- Если вам не нужно маршалировать измененные строковые данные обратно вызывающему объекту, просто удалите <xref:System.Runtime.InteropServices.OutAttribute>.

  ```csharp
  [DllImport("MyLibrary")]
  private static extern void PIMethod(string s);
  ```

  Дополнительные сведения в разделе [CA1417](/visualstudio/code-quality/ca1417).

- Чтобы полностью отключить анализ кода, задайте для параметра `EnableNETAnalyzers` значение `false` в файле проекта. Дополнительные сведения см. в разделе [EnableNETAnalyzers](../../../../docs/core/project-sdk/msbuild-props.md#enablenetanalyzers).

#### <a name="category"></a>Категория

Анализ кода

#### <a name="affected-apis"></a>Затронутые API

Невозможно обнаружить с помощью анализа API.

<!--

#### Affected APIs

Not detectable via API analysis.

-->
