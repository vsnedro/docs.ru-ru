---
title: Параметры конфигурации правила качества кода
description: Узнайте, как указать дополнительные параметры конфигурации для правил качества кода.
ms.date: 09/24/2020
ms.topic: conceptual
no-loc:
- EditorConfig
ms.openlocfilehash: 2721d4e8fda6012b304637477c3618ee0ff2ea18
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2021
ms.locfileid: "99752071"
---
# <a name="code-quality-rule-configuration-options"></a>Параметры конфигурации правила качества кода

Правила *качества кода* имеют дополнительные параметры конфигурации, помимо [настройки серьезности](configuration-options.md#severity-level). Например, каждый анализатор качества кода можно настроить для применения только к отдельным частям базы кода. Эти параметры указываются путем добавления пар "ключ-значение" в тот же [EditorConfig](https://editorconfig.org) файл, где указываются уровни серьезности правила и общие параметры редактора.

## <a name="option-scopes"></a>Области параметров

Каждый вариант уточнения можно настроить для всех правил, для категории правил (например, для безопасности или проектирования) или для конкретного правила.

### <a name="all-rules"></a>Все правила

Ниже приведен синтаксис для настройки параметра для *всех* правил.

|Синтаксис|Пример|
|-|-|
| dotnet_code_quality. OptionName = OptionValue | `dotnet_code_quality.api_surface = public` |

### <a name="category-of-rules"></a>Категория правил

Ниже приведен синтаксис для настройки параметра для [ *категории* правил](categories.md) .

|Синтаксис|Пример|
|-|-|
| dotnet_code_quality. Рулекатегори. OptionName = OptionValue | `dotnet_code_quality.Naming.api_surface = public` |

### <a name="specific-rule"></a>Конкретное правило

Ниже приведен синтаксис для настройки параметра для *конкретного* правила.

|Синтаксис|Пример|
|-|-|
| dotnet_code_quality. RuleId. OptionName = OptionValue | `dotnet_code_quality.CA1040.api_surface = public` |

## <a name="options"></a>Параметры

В этом разделе перечислены некоторые из доступных параметров. Полный список доступных параметров см. в разделе [Конфигурация анализатора](https://github.com/dotnet/roslyn-analyzers/blob/master/docs/Analyzer%20Configuration.md).

### <a name="api_surface"></a>api_surface

| Описание | Допустимые значения | Значение по умолчанию | Настраиваемые правила |
| - | - | - | - |
| Какая часть области API для анализа | `public`<br/>`internal` либо `friend`<br/>`private`<br/>`all`<br/><br/>Несколько значений следует разделять запятой (,) | `public` | [CA1000](quality-rules/ca1000.md) [CA1003](quality-rules/ca1003.md) [CA1008](quality-rules/ca1008.md) [CA1010](quality-rules/ca1010.md)<br/>[CA1012](quality-rules/ca1012.md) [CA1024](quality-rules/ca1024.md) [CA1027](quality-rules/ca1027.md) [CA1028](quality-rules/ca1028.md)<br/>[CA1030](quality-rules/ca1030.md) [CA1036](quality-rules/ca1036.md) [CA1040](quality-rules/ca1040.md) [CA1041](quality-rules/ca1041.md)<br/>[CA1043](quality-rules/ca1043.md) [CA1044](quality-rules/ca1044.md) [CA1051](quality-rules/ca1051.md) [CA1052](quality-rules/ca1052.md)<br/>[CA1054](quality-rules/ca1054.md) [CA1055](quality-rules/ca1055.md) [CA1056](quality-rules/ca1056.md) [CA1058](quality-rules/ca1058.md)<br/>[CA1063](quality-rules/ca1063.md) [CA1708](quality-rules/ca1708.md) [CA1710](quality-rules/ca1710.md) [CA1711](quality-rules/ca1711.md)<br/>[CA1714](quality-rules/ca1714.md) [CA1715](quality-rules/ca1715.md) [CA1716](quality-rules/ca1716.md) [CA1717](quality-rules/ca1717.md)<br/>[CA1720](quality-rules/ca1720.md) [CA1721](quality-rules/ca1721.md) [CA1725](quality-rules/ca1725.md) [CA1801](quality-rules/ca1801.md)<br/>[CA1802](quality-rules/ca1802.md) [CA1815](quality-rules/ca1815.md) [CA1819](quality-rules/ca1819.md) [CA2217](quality-rules/ca2217.md)<br/>[CA2225](quality-rules/ca2225.md) [CA2226](quality-rules/ca2226.md) [CA2231](quality-rules/ca2231.md) [CA2234](quality-rules/ca2234.md)<br/>|

### <a name="exclude_async_void_methods"></a>exclude_async_void_methods

| Описание | Допустимые значения | Значение по умолчанию | Настраиваемые правила |
| - | - | - | - |
| Следует ли игнорировать асинхронные методы, которые не возвращают значение | `true`<br/>`false` | `false` | [CA2007](quality-rules/ca2007.md) |

> [!NOTE]
> Этот параметр был назван `skip_async_void_methods` в более ранней версии.

### <a name="exclude_single_letter_type_parameters"></a>exclude_single_letter_type_parameters

| Описание | Допустимые значения | Значение по умолчанию | Настраиваемые правила |
| - | - | - | - |
| Следует ли исключить из правила [Параметры типа](../../csharp/programming-guide/generics/generic-type-parameters.md) с одним символом, например `S` в `Collection<S>` | `true`<br/>`false` | `false` | [CA1715](quality-rules/ca1715.md) |

> [!NOTE]
> Этот параметр был назван `allow_single_letter_type_parameters` в более ранней версии.

### <a name="output_kind"></a>output_kind

| Описание | Допустимые значения | Значение по умолчанию | Настраиваемые правила |
| - | - | - | - |
| Указывает, что код в проекте, который создает сборку этого типа, должен быть проанализирован | Одно или несколько полей <xref:Microsoft.CodeAnalysis.OutputKind> перечисления<br/><br/>Несколько значений следует разделять запятой (,) | Все типы выходных данных | [CA2007](quality-rules/ca2007.md) |

### <a name="required_modifiers"></a>required_modifiers

| Описание | Допустимые значения | Значение по умолчанию | Настраиваемые правила |
| - | - | - | - |
| Указывает обязательные модификаторы для API, которые необходимо проанализировать | Одно или несколько значений из приведенной ниже таблицы допустимых модификаторов<br/><br/>Несколько значений следует разделять запятой (,) | Зависит от каждого правила | [CA1802](quality-rules/ca1802.md) |

| Разрешенный модификатор | Итоги |
| --- | --- |
| `none` | Нет требования к модификатору |
| `static` либо `Shared` | Должен быть объявлен как `static` ( `Shared` в Visual Basic) |
| `const` | Должен быть объявлен как `const` |
| `readonly` | Должен быть объявлен как `readonly` |
| `abstract` | Должен быть объявлен как `abstract` |
| `virtual` | Должен быть объявлен как `virtual` |
| `override` | Должен быть объявлен как `override` |
| `sealed` | Должен быть объявлен как `sealed` |
| `extern` | Должен быть объявлен как `extern` |
| `async` | Должен быть объявлен как `async` |

### <a name="exclude_extension_method_this_parameter"></a>exclude_extension_method_this_parameter

| Описание | Допустимые значения | Значение по умолчанию | Настраиваемые правила |
| - | - | - | - |
| Пропускать ли анализ для `this` параметра методов расширения | `true`<br/>`false` | `false` | [CA1062](quality-rules/ca1062.md) |

### <a name="null_check_validation_methods"></a>null_check_validation_methods

| Описание | Допустимые значения | Значение по умолчанию | Настраиваемые правила |
| - | - | - | - |
| Имена методов проверки со значением NULL, которые проверяют, что аргументы, передаваемые в метод, не равны NULL. | Допустимые форматы имен методов (разделенные `|` ):<br/> — Только имя метода (включает все методы с именем, независимо от содержащего его типа или пространства имен).<br/> — Полные имена в [формате идентификатора документации](https://github.com/dotnet/csharplang/blob/master/spec/documentation-comments.md#id-string-format)символа с необязательным `M:` префиксом | None | [CA1062](quality-rules/ca1062.md) |

### <a name="additional_string_formatting_methods"></a>additional_string_formatting_methods

| Описание | Допустимые значения | Значение по умолчанию | Настраиваемые правила |
| - | - | - | - |
| Имена дополнительных методов форматирования строк | Допустимые форматы имен методов (разделенные `|` ):<br/> — Только имя метода (включает все методы с именем, независимо от содержащего его типа или пространства имен).<br/> — Полные имена в [формате идентификатора документации](/dotnet/csharp/language-reference/language-specification/documentation-comments#id-string-format)символа с необязательным `M:` префиксом | None | [CA2241](quality-rules/ca2241.md) |

### <a name="excluded_type_names_with_derived_types"></a>excluded_type_names_with_derived_types

| Описание | Допустимые значения | Значение по умолчанию | Настраиваемые правила |
| - | - | - | - |
| Имена типов, в которых тип и все его производные типы исключаются для анализа | Допустимые форматы имен символов (разделенные `|` ):<br/> — Только имя типа (включает все типы с именем, независимо от содержащего его типа или пространства имен).<br/> — Полные имена в [формате идентификатора документации](/dotnet/csharp/language-reference/language-specification/documentation-comments#id-string-format)символа с необязательным `T:` префиксом | None | [CA1303](quality-rules/ca1303.md) |

### <a name="excluded_symbol_names"></a>excluded_symbol_names

| Описание | Допустимые значения | Значение по умолчанию | Настраиваемые правила |
| - | - | - | - |
| Имена символов, исключаемых для анализа | Допустимые форматы имен символов (разделенные `|` ):<br/> — Только имя символа (включает все символы с именем, независимо от содержащего его типа или пространства имен).<br/> — Полные имена в [формате идентификатора документации](/dotnet/csharp/language-reference/language-specification/documentation-comments#id-string-format)символа. Для каждого имени символа требуется префикс вида символа, например `M:` префикс для методов, `T:` префикс для типов и `N:` префикс для пространств имен.<br/> - `.ctor` для конструкторов и `.cctor` для статических конструкторов | None | [CA1062](quality-rules/ca1062.md) [CA1303](quality-rules/ca1303.md) [CA2000](quality-rules/ca2000.md) [CA2100](quality-rules/ca2100.md) [CA2301](quality-rules/ca2301.md) [CA2302](quality-rules/ca2302.md)<br/>[CA2311](quality-rules/ca2311.md) [CA2312](quality-rules/ca2312.md) [CA2321](quality-rules/ca2321.md) [CA2322](quality-rules/ca2322.md) [CA2327](quality-rules/ca2327.md) [CA2328](quality-rules/ca2328.md)<br/>[CA2329](quality-rules/ca2329.md) [CA2330](quality-rules/ca2330.md) [CA3001](quality-rules/ca3001.md) [CA3002](quality-rules/ca3002.md) [CA3003](quality-rules/ca3003.md) [CA3004](quality-rules/ca3004.md)<br/>[CA3005](quality-rules/ca3005.md) [CA3006](quality-rules/ca3006.md) [CA3007](quality-rules/ca3007.md) [CA3008](quality-rules/ca3008.md) [CA3009](quality-rules/ca3009.md) [CA3010](quality-rules/ca3010.md)<br/>[CA3011](quality-rules/ca3011.md) [CA3012](quality-rules/ca3012.md) [CA5361](quality-rules/ca5361.md) CA5376 CA5377 [CA5378](quality-rules/ca5378.md)<br/>[CA5380](quality-rules/ca5380.md) [CA5381](quality-rules/ca5381.md) CA5382 CA5383 CA5384 CA5387<br/>CA5388 [CA5389](quality-rules/ca5389.md) CA5390 |

### <a name="disallowed_symbol_names"></a>disallowed_symbol_names

| Описание | Допустимые значения | Значение по умолчанию | Настраиваемые правила |
| - | - | - | - |
| Имена символов, запрещенных в контексте анализа | Допустимые форматы имен символов (разделенные `|` ):<br/> — Только имя символа (включает все символы с именем, независимо от содержащего его типа или пространства имен).<br/> — Полные имена в [формате идентификатора документации](/dotnet/csharp/language-reference/language-specification/documentation-comments#id-string-format)символа. Для каждого имени символа требуется префикс вида символа, например `M:` префикс для методов, `T:` префикс для типов и `N:` префикс для пространств имен.<br/> - `.ctor` для конструкторов и `.cctor` для статических конструкторов | None | [CA1031](quality-rules/ca1031.md) |
