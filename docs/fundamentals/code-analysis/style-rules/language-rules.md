---
title: Правила языка для стиля кода
description: Узнайте о различных правилах стиля кода для использования конструкций языка C# и Visual Basic.
ms.date: 09/25/2020
ms.topic: reference
author: gewarren
ms.author: gewarren
dev_langs:
- CSharp
- VB
helpviewer_keywords:
- language code style rules [EditorConfig]
- language rules
- EditorConfig language conventions
ms.openlocfilehash: b77d9aa2a528a6cf540babd5e5acc148e48c489c
ms.sourcegitcommit: 721c3e4bdbb1ea0bb420818ec944c538fe5c513a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/01/2020
ms.locfileid: "96594164"
---
# <a name="language-rules"></a>Правила языка

Правила языка стиля кода влияют на использование различных конструкций языков программирования .NET, например модификаторов и круглых скобок. Правила делятся на следующие категории:

- [Правила стилей .NET](#net-style-rules): правила, применяемые к C# и Visual Basic. Имена параметров EditorConfig для этих правил начинаются с `dotnet_style_` префикса.
- [Правила для стилей c#](#c-style-rules). правила, относящиеся только к языку c#. Имена параметров EditorConfig для этих правил начинаются с `csharp_style_` префикса.
- [Правила стилей Visual Basic](#visual-basic-style-rules): правила, относящиеся только к Visual бсик Language. Имена параметров EditorConfig для этих правил начинаются с `visual_basic_style_` префикса.

## <a name="option-format"></a>Формат параметра

Параметры языковых правил можно указать в файле EditorConfig в следующем формате:

`option_name = value:severity`

- **Значение**: для каждого правила языка указывается значение, определяющее, следует ли предпочитать стиль. Многие правила принимают значение `true` (предпочитать этот стиль) или `false` (не предпочитать этот стиль). Другие правила принимают значения `when_on_single_line` или `never`.
- **Серьезность**. Вторая часть правила задает степень [серьезности](../configuration-options.md#severity-level) для правила. Спецификация серьезности в приведенном выше синтаксисе параметров учитывается только в Ideах разработки, таких как Visual Studio. Этот параметр не понимается компиляторами C# или VB, поэтому он не учитывается во время сборки. Вместо этого для применения правил стиля кода при сборке необходимо задать уровень серьезности с помощью синтаксиса конфигурации уровня серьезности на основе идентификатора правила для анализаторов. Синтаксис имеет вид `dotnet_diagnostic.<rule ID>.severity = <severity>`, например `dotnet_diagnostic.IDE0040.severity = silent`. См. дополнительные сведения на [сайте GitHub](https://github.com/dotnet/roslyn/issues/44201).

> [!TIP]
>
> Начиная с Visual Studio 2019 версии 16.3, в меню [Быстрые действия](/visualstudio/ide/quick-actions) можно настроить правила стиля кода после нарушения стиля. Дополнительные сведения см. [в разделе Автоматическая настройка стилей кода в Visual Studio](/visualstudio/ide/editorconfig-language-conventions#automatically-configure-code-styles-in-visual-studio).

## <a name="net-style-rules"></a>Правила стилей .NET

Правила стилей в этом разделе относятся как к C#, так и к Visual Basic.

- [Квалификаторы "this." и "Me."](ide0003-ide0009.md)
  - [dotnet_style_qualification_for_field](ide0003-ide0009.md#dotnet_style_qualification_for_field)
  - [dotnet_style_qualification_for_property](ide0003-ide0009.md#dotnet_style_qualification_for_property)
  - [dotnet_style_qualification_for_method](ide0003-ide0009.md#dotnet_style_qualification_for_method)
  - [dotnet_style_qualification_for_event](ide0003-ide0009.md#dotnet_style_qualification_for_event)
- [Ключевые слова языка вместо имен типов .NET Framework для ссылок на типы](ide0049.md)
  - [dotnet_style_predefined_type_for_locals_parameters_members](ide0049.md#dotnet_style_predefined_type_for_locals_parameters_members)
  - [dotnet_style_predefined_type_for_member_access](ide0049.md#dotnet_style_predefined_type_for_member_access)
- [Предпочтения для модификаторов](modifier-preferences.md#net-modifier-preferences)
  - [dotnet_style_require_accessibility_modifiers](ide0040.md#dotnet_style_require_accessibility_modifiers)
  - [csharp_preferred_modifier_order](ide0036.md#csharp_preferred_modifier_order)
  - [visual_basic_preferred_modifier_order](ide0036.md#visual_basic_preferred_modifier_order)
  - [dotnet_style_readonly_field](ide0044.md#dotnet_style_readonly_field)
- [Предпочтения относительно круглых скобок](ide0047-ide0048.md)
  - [dotnet_style_parentheses_in_arithmetic_binary_operators](ide0047-ide0048.md#dotnet_style_parentheses_in_arithmetic_binary_operators)
  - [dotnet_style_parentheses_in_relational_binary_operators](ide0047-ide0048.md#dotnet_style_parentheses_in_relational_binary_operators)
  - [dotnet_style_parentheses_in_other_binary_operators](ide0047-ide0048.md#dotnet_style_parentheses_in_other_binary_operators)
  - [dotnet_style_parentheses_in_other_operators](ide0047-ide0048.md#dotnet_style_parentheses_in_other_operators)
- [Настройки уровня выражений](expression-level-preferences.md#net-expression-level-preferences)
  - [dotnet_style_object_initializer](ide0017.md#dotnet_style_object_initializer)
  - [dotnet_style_collection_initializer](ide0028.md#dotnet_style_collection_initializer)
  - [dotnet_style_explicit_tuple_names](ide0033.md#dotnet_style_explicit_tuple_names)
  - [dotnet_style_prefer_inferred_tuple_names](ide0037.md#dotnet_style_prefer_inferred_tuple_names)
  - [dotnet_style_prefer_inferred_anonymous_type_member_names](ide0037.md#dotnet_style_prefer_inferred_anonymous_type_member_names)
  - [dotnet_style_prefer_auto_properties](ide0032.md#dotnet_style_prefer_auto_properties)
  - [dotnet_style_prefer_conditional_expression_over_assignment](ide0045.md#dotnet_style_prefer_conditional_expression_over_assignment)
  - [dotnet_style_prefer_conditional_expression_over_return](ide0046.md#dotnet_style_prefer_conditional_expression_over_return)
  - [dotnet_style_prefer_compound_assignment](ide0054-ide0074.md#dotnet_style_prefer_compound_assignment)
  - [dotnet_style_prefer_simplified_interpolation](ide0071.md#dotnet_style_prefer_simplified_interpolation)
  - [dotnet_style_prefer_simplified_boolean_expressions](ide0075.md#dotnet_style_prefer_simplified_boolean_expressions)
  - [Добавление недостающих вариантов в инструкцию Switch](ide0010.md) . это правило не имеет параметра стиля кода.
  - [Преобразовать анонимный тип в кортеж](ide0050.md) — это правило не имеет параметра стиля кода.
  - [Использовать "System. хэш. Combine"](ide0070.md) — это правило не имеет параметра стиля кода.
  - [Преобразовать "typeof" в "NameOf"](ide0082.md) — это правило не имеет параметра стиля кода.
- [Параметры проверки NULL](null-checking-preferences.md#net-null-checking-preferences)
  - [dotnet_style_coalesce_expression](ide0029-ide0030.md#dotnet_style_coalesce_expression)
  - [dotnet_style_null_propagation](ide0031.md#dotnet_style_null_propagation)
  - [dotnet_style_prefer_is_null_check_over_reference_equality_method](ide0041.md#dotnet_style_prefer_is_null_check_over_reference_equality_method)
- [Параметры заголовка файла](ide0073.md)
  - [file_header_template](ide0073.md#file_header_template)

## <a name="c-style-rules"></a>Правила стилей C#

Правила стилей в этом разделе применимы только к языку C#.

- [предпочтения "var"](ide0007-ide0008.md)
  - [csharp_style_var_for_built_in_types](ide0007-ide0008.md#csharp_style_var_for_built_in_types)
  - [csharp_style_var_when_type_is_apparent](ide0007-ide0008.md#csharp_style_var_when_type_is_apparent)
  - [csharp_style_var_elsewhere](ide0007-ide0008.md#csharp_style_var_elsewhere)
- [Элементы, воплощающие выражение](expression-bodied-members.md)
  - [csharp_style_expression_bodied_methods](ide0022.md#csharp_style_expression_bodied_methods)
  - [csharp_style_expression_bodied_constructors](ide0021.md#csharp_style_expression_bodied_constructors)
  - [csharp_style_expression_bodied_operators](ide0023-ide0024.md#csharp_style_expression_bodied_operators)
  - [csharp_style_expression_bodied_properties](ide0025.md#csharp_style_expression_bodied_properties)
  - [csharp_style_expression_bodied_indexers](ide0026.md#csharp_style_expression_bodied_indexers)
  - [csharp_style_expression_bodied_accessors](ide0027.md#csharp_style_expression_bodied_accessors)
  - [csharp_style_expression_bodied_lambdas](ide0053.md#csharp_style_expression_bodied_lambdas)
  - [csharp_style_expression_bodied_local_functions](ide0061.md#csharp_style_expression_bodied_local_functions)
- [Настройки соответствия шаблонов](pattern-matching-preferences.md)
  - [csharp_style_pattern_matching_over_is_with_cast_check](ide0020-ide0038.md#csharp_style_pattern_matching_over_is_with_cast_check)
  - [csharp_style_pattern_matching_over_as_with_null_check](ide0019.md#csharp_style_pattern_matching_over_as_with_null_check)
  - [csharp_style_prefer_switch_expression](ide0066.md#csharp_style_prefer_switch_expression)
  - [csharp_style_prefer_pattern_matching](ide0078.md#csharp_style_prefer_pattern_matching)
  - [csharp_style_prefer_not_pattern](ide0083.md#csharp_style_prefer_not_pattern)
- [Настройки уровня выражений](expression-level-preferences.md#c-expression-level-preferences)
  - [csharp_style_inlined_variable_declaration](ide0018.md#csharp_style_inlined_variable_declaration)
  - [csharp_prefer_simple_default_expression](ide0034.md#csharp_prefer_simple_default_expression)
  - [csharp_style_pattern_local_over_anonymous_function](ide0039.md#csharp_style_pattern_local_over_anonymous_function)
  - [csharp_style_deconstructed_variable_declaration](ide0042.md#csharp_style_deconstructed_variable_declaration)
  - [csharp_style_prefer_index_operator](ide0056.md#csharp_style_prefer_index_operator)
  - [csharp_style_prefer_range_operator](ide0057.md#csharp_style_prefer_range_operator)
  - [csharp_style_implicit_object_creation_when_type_is_apparent](ide0090.md#csharp_style_implicit_object_creation_when_type_is_apparent)
  - [Добавить недостающие варианты для переключения выражения](ide0072.md) . это правило не имеет параметра стиля кода.
- [Настройки проверки Null](null-checking-preferences.md#c-null-checking-preferences)
  - [csharp_style_throw_expression](ide0016.md#csharp_style_throw_expression)
  - [csharp_style_conditional_delegate_call](ide1005.md#csharp_style_conditional_delegate_call)
- [Настройки блока кода](code-block-preferences.md)
  - [csharp_prefer_braces](ide0011.md#csharp_prefer_braces)
  - [csharp_prefer_simple_using_statement](ide0063.md#csharp_prefer_simple_using_statement)
- [предпочтения директивы "using"](ide0065.md)
  - [csharp_using_directive_placement](ide0065.md#csharp_using_directive_placement)
- [Предпочтения для модификаторов](modifier-preferences.md#c-modifier-preferences)
  - [csharp_prefer_static_local_function](ide0062.md#csharp_prefer_static_local_function)
  - [Сделать поля структуры доступными для записи](ide0064.md) — это правило не имеет параметра стиля кода.

## <a name="visual-basic-style-rules"></a>Правила стилей Visual Basic

Правила стилей в этом разделе применимы только к языку Visual Basic.

- [Настройки соответствия шаблонов](pattern-matching-preferences.md)
  - [visual_basic_style_prefer_isnot_expression](ide0084.md#visual_basic_style_prefer_isnot_expression)

## <a name="see-also"></a>См. также

- [Правила, касающиеся ненужного кода](unnecessary-code-rules.md)
- [Правила форматирования](formatting-rules.md)
- [Правила именования](naming-rules.md)
- [Справочник по правилам стиля кода .NET](index.md)
