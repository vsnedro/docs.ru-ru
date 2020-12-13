---
ms.openlocfilehash: 83644b9205d650da68c910095dd1d22a14940c44
ms.sourcegitcommit: 9b877e160c326577e8aa5ead22a937110d80fa44
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/11/2020
ms.locfileid: "97366822"
---
### <a name="exclude-specific-symbols"></a>Исключить конкретные символы

Вы можете исключить из анализа определенные символы, например типы и методы. Например, чтобы указать, что правило не должно выполняться в каком-либо коде в типах с именем `MyType` , добавьте следующую пару "ключ-значение" в *editorconfig* -файл в проекте:

```ini
dotnet_code_quality.CAXXXX.excluded_symbol_names = MyType
```

Допустимые форматы имен символов в значении параметра (разделенные `|` ):

- Только имя символа (включает все символы с именем, независимо от содержащего его типа или пространства имен).
- Полные имена в [формате идентификатора документации](../../docs/csharp/programming-guide/xmldoc/processing-the-xml-file.md#id-strings)символа. Для каждого имени символа требуется префикс типа символа, например `M:` для методов, `T:` для типов и `N:` для пространств имен.
- `.ctor` для конструкторов и `.cctor` для статических конструкторов.

Примеры:

| Значение параметра | Сводка |
| --- | --- |
|`dotnet_code_quality.CAXXXX.excluded_symbol_names = MyType` | Соответствует всем символам с именем `MyType` . |
|`dotnet_code_quality.CAXXXX.excluded_symbol_names = MyType1|MyType2` | Соответствует всем символам с именем `MyType1` или `MyType2` . |
|`dotnet_code_quality.CAXXXX.excluded_symbol_names = M:NS.MyType.MyMethod(ParamType)` | Соответствует конкретному методу `MyMethod` с указанной полной сигнатурой. |
|`dotnet_code_quality.CAXXXX.excluded_symbol_names = M:NS1.MyType1.MyMethod1(ParamType)|M:NS2.MyType2.MyMethod2(ParamType)` | Соответствует конкретным методам `MyMethod1` и `MyMethod2` соответствующим полным сигнатурам. |
