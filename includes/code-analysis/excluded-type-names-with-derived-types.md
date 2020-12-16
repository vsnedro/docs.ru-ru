---
ms.openlocfilehash: 4125df1d64fe7f3f2eb1eb4a821ed46c8270c95f
ms.sourcegitcommit: d0990c1c1ab2f81908360f47eafa8db9aa165137
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/15/2020
ms.locfileid: "97531887"
---
### <a name="exclude-specific-types-and-their-derived-types"></a>Исключить определенные типы и их производные типы

Из анализа можно исключить определенные типы и их производные типы. Например, чтобы указать, что правило не должно выполняться для каких-либо методов в типах с именем `MyType` и производных типов, добавьте следующую пару "ключ-значение" в *editorconfig* -файл в проекте:

```ini
dotnet_code_quality.CAXXXX.excluded_type_names_with_derived_types = MyType
```

Допустимые форматы имен символов в значении параметра (разделенные `|` ):

- Только имя типа (включает все типы с именем, независимо от содержащего его типа или пространства имен).
- Полные имена в [формате идентификатора документации](../../docs/csharp/programming-guide/xmldoc/processing-the-xml-file.md#id-strings)символа с дополнительным `T:` префиксом.

Примеры:

| Значение параметра | Итоги |
| --- | --- |
|`dotnet_code_quality.CAXXXX.excluded_type_names_with_derived_types = MyType` | Соответствует всем типам с именем `MyType` и всем их производным типам. |
|`dotnet_code_quality.CAXXXX.excluded_type_names_with_derived_types = MyType1|MyType2` | Соответствует всем типам с именами `MyType1` или `MyType2` и всем производным от него типам. |
|`dotnet_code_quality.CAXXXX.excluded_type_names_with_derived_types = M:NS.MyType` | Соответствует определенному типу `MyType` с заданным полным именем и всеми производными от него типами. |
|`dotnet_code_quality.CAXXXX.excluded_type_names_with_derived_types = M:NS1.MyType1|M:NS2.MyType2` | Соответствует конкретным типам `MyType1` и `MyType2` с соответствующими полными именами и всем их производным типам. |
