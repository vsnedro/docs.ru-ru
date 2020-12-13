---
ms.openlocfilehash: 150882f3e4c9ff7abe811e09da94b8141de75778
ms.sourcegitcommit: 9b877e160c326577e8aa5ead22a937110d80fa44
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/11/2020
ms.locfileid: "97366845"
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

| Значение параметра | Сводка |
| --- | --- |
|`dotnet_code_quality.CAXXXX.excluded_type_names_with_derived_types = MyType` | Соответствует всем типам с именем `MyType` и всем их производным типам. |
|`dotnet_code_quality.CAXXXX.excluded_type_names_with_derived_types = MyType1|MyType2` | Соответствует всем типам с именами `MyType1` или `MyType2` и всем производным от него типам. |
|`dotnet_code_quality.CAXXXX.excluded_type_names_with_derived_types = M:NS.MyType` | Соответствует определенному типу `MyType` с заданным полным именем и всеми производными от него типами. |
|`dotnet_code_quality.CAXXXX.excluded_type_names_with_derived_types = M:NS1.MyType1|M:NS2.MyType2` | Соответствует конкретным типам `MyType1` и `MyType2` с соответствующими полными именами и всем их производным типам. |
