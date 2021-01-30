---
title: Правила именования стилей кода
description: Сведения о правилах стиля кода .NET для именования элементов кода.
ms.date: 09/25/2020
ms.topic: reference
author: gewarren
ms.author: gewarren
dev_langs:
- CSharp
- VB
f1_keywords:
- IDE1006
- naming rules
helpviewer_keywords:
- IDE1006
- naming code style rules [EditorConfig]
- naming rules
- EditorConfig naming conventions
ms.openlocfilehash: 1fce275204b729b4d23729ca432e06a5a249620d
ms.sourcegitcommit: 78eb25647b0c750cd80354ebd6ce83a60668e22c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/29/2021
ms.locfileid: "99065139"
---
# <a name="naming-rules"></a>Правила именования

В `.editorconfig` файле можно определить **правила именования** , определяющие, каким образом элементы кода языка программирования .NET &mdash; , такие как классы, свойства и методы, &mdash; должны называться. Например, можно указать, что открытые члены должны иметь прописные буквы или что закрытые поля должны начинаться с `_` .

Правило именования имеет три компонента:

* **Группа символов** группа &mdash; символов, к которой применяется правило.
* **Стиль именования** , связываемый с правилом.
* Уровень серьезности для применения соглашения.

## <a name="general-syntax"></a>Общий синтаксис

Чтобы определить правило именования, группу символов или стиль именования, задайте одно или несколько свойств с помощью следующего синтаксиса:

```ini
<kind>.<title>.<propertyName> = <propertyValue>
```

Каждое свойство должно быть задано только один раз, но некоторые параметры допускают несколько значений, разделенных запятыми.

Порядок свойств не имеет значения.

### \<kind>

**\<kind>** Указывает, какой тип элемента определяется &mdash; правилом именования, группой символов или стилем именования, &mdash; и должен быть одним из следующих:

| Установка свойства для | Использовать \<kind> значение | Пример |
| --- | --- | -- |
| Правило именования | `dotnet_naming_rule` | `dotnet_naming_rule.types_should_be_pascal_case.severity = suggestion` |
| Группа символов | `dotnet_naming_symbols` | `dotnet_naming_symbols.interface.applicable_kinds = interface` |
| Стиль именования | `dotnet_naming_style` | `dotnet_naming_style.pascal_case.capitalization = pascal_case` |

Каждый тип &mdash; [правила именования](#naming-rule-properties)определений, [группы символов](#symbol-group-properties)или [стиля именования](#naming-style-properties) &mdash; имеет собственные Поддерживаемые свойства, как описано в следующих разделах.

### \<title>

**\<title>** описательное имя, которое связывает несколько параметров свойств с одним определением. Например, следующие свойства создают два определения группы символов, `interface` и `types` для каждого из них установлены два свойства.

```ini
dotnet_naming_symbols.interface.applicable_kinds = interface
dotnet_naming_symbols.interface.applicable_accessibilities = public, internal, private, protected, protected_internal, private_protected

dotnet_naming_symbols.types.applicable_kinds = class, struct, interface, enum, delegate
dotnet_naming_symbols.types.applicable_accessibilities = public, internal, private, protected, protected_internal, private_protected
```

## <a name="naming-rule-properties"></a>Свойства правила именования

Чтобы правило вступило в силу, требуются все свойства правил именования.

| Свойство | Описание |
| -- | -- |
| `symbols` | Заголовок группы символов; правило именования будет применено к символам в этой группе |
| `style` | Заголовок стиля именования, который должен быть связан с этим правилом |
| `severity` |  Задает серьезность, с которой будет принудительно применяться правило именования. Задайте для связанного значения один из доступных [уровней серьезности](../configuration-options.md#severity-level). <sup>1</sup> |

**Примечания.**

1. Спецификация серьезности в правиле именования учитывается только в Ideах разработки, таких как Visual Studio. Этот параметр не понимается компиляторами C# или VB, поэтому он не учитывается во время сборки. Чтобы применить правила стиля именования к сборке, следует задать уровень серьезности с помощью [конфигурации серьезности правила кода](#rule-id-ide1006-naming-rule-violation). См. дополнительные сведения на [сайте GitHub](https://github.com/dotnet/roslyn/issues/44201).

## <a name="symbol-group-properties"></a>Свойства группы символов

Для групп символов можно задать следующие свойства, чтобы ограничить набор символов, включаемых в группу. Чтобы указать несколько значений для одного свойства, разделяйте значения запятой.

| Свойство | Описание | Допустимые значения | Обязательно |
| -- | -- | -- | -- |
| `applicable_kinds` | Виды символов в группе <sup>1</sup> | `*` (используйте это значение, чтобы указать все символы)<br/>`namespace`<br/>`class`<br/>`struct`<br/>`interface`<br/>`enum`<br/>`property`<br/>`method`<br/>`field`<br/>`event`<br/>`delegate`<br/>`parameter`<br/>`type_parameter`<br/>`local`<br/>`local_function` | Да |
| `applicable_accessibilities` | Уровни доступности символов в группе | `*` (используйте это значение, чтобы указать все уровни доступа)<br/>`public`<br/>`internal` или `friend`<br/>`private`<br/>`protected`<br/>`protected_internal` или `protected_friend`<br/>`private_protected`<br/>`local` (для символов, определенных в методе) | Да |
| `required_modifiers` | Сопоставлять только символы со _всеми_ указанными модификаторами <sup>2</sup> | `abstract` или `must_inherit`<br/>`async`<br/>`const`<br/>`readonly`<br/>`static` или `shared` <sup>3</sup> | Нет |

**Примечания.**

1. В настоящее время элементы кортежа не поддерживаются в `applicable_kinds` .
2. Группа символов соответствует _всем_ модификаторам в `required_modifiers` свойстве.  Если опустить это свойство, для совпадения не требуются специальные модификаторы. Это означает, что модификаторы символов не оказывают влияния на применение этого правила.
3. Если группа имеет `static` свойство или `shared` в `required_modifiers` свойстве, Группа также будет включать `const` символы, так как они являются неявными `static` / `Shared` . Однако если вы не хотите `static` применять правило именования к `const` символам, можно создать новое правило именования с группой символов `const` .

## <a name="naming-style-properties"></a>Именование свойств стиля

Стиль именования определяет соглашения, которые необходимо применить к правилу. Например:

* С прописной буквы `PascalCase`
* Начинается с `m_`
* Заканчивается на `_g`
* Разделять слова с помощью `__`

Для стиля именования можно задать следующие свойства.

| Свойство | Описание | Допустимые значения | Обязательно |
| -- | -- | -- | -- |
| `capitalization` | Стиль капитализации для слов внутри символа | `pascal_case`<br/>`camel_case`<br/>`first_word_upper`<br/>`all_upper`<br/>`all_lower` | Да<sup>1</sup> |
| `required_prefix` | Должно начинаться с этих символов | | Нет |
| `required_suffix` | Должен заканчиваться этими символами | | Нет |
| `word_separator` | Слова внутри символа должны быть разделены этим символом | | Нет |

**Примечания.**

1. Указать регистр букв для стиля именования обязательно, в противном случае ваш стиль может игнорироваться.

## <a name="rule-order"></a>Порядок правил

Порядок, в котором правила именования определяются в файле EditorConfig, не имеет значения. Правила именования автоматически упорядочиваются в соответствии с определением самих правил. [Расширение языковой службы EditorConfig](https://marketplace.visualstudio.com/items?itemName=MadsKristensen.EditorConfig) может анализировать файл EditorConfig и сообщать о случаях, когда порядок правил в файле отличается от того, который будет использоваться компилятором во время выполнения.

> [!NOTE]
>
> Если вы используете более раннюю версию Visual Studio, чем Visual Studio 2019 версии 16,2, правила именования должны быть упорядочены от наиболее специфичных к наименее конкретных в файле EditorConfig. Применяться будет только первое обнаруженное правило. Но при наличии множества *свойств* правил с одним и тем же именем приоритет будет иметь последнее обнаруженное свойство с таким именем. См. подробнее об [иерархии файлов и приоритетности](/visualstudio/ide/create-portable-custom-editor-options#file-hierarchy-and-precedence).

## <a name="default-naming-styles"></a>Стили именования по умолчанию

Если не указать никаких пользовательских правил именования, используются следующие стили по умолчанию:

- Для классов, структур, перечислений, свойств и событий со специальными параметрами `public`, `private`, `internal`, `protected` или `protected_internal` по умолчанию используется стиль именования Pascal.

- Для интерфейсов со специальными параметрами `public`, `private`, `internal`, `protected` или `protected_internal` по умолчанию используется стиль именования Pascal с обязательным префиксом **I**.

## <a name="code-rule-id-ide1006-naming-rule-violation"></a><a name="rule-id-ide1006-naming-rule-violation"></a>Идентификатор правила кода: `IDE1006 (Naming rule violation)`

Все параметры именования имеют идентификатор `IDE1006` и заголовок правила `Naming rule violation` . Серьезность нарушений именования можно настроить глобально в файле EditorConfig, используя следующий синтаксис:

```ini
dotnet_diagnostic.IDE1006.severity = <severity value>
```

Значение серьезности должно быть `warning` или `error` [принудительно применено при сборке](../overview.md#code-style-analysis). Все возможные значения серьезности см. в разделе [уровень серьезности](../configuration-options.md#severity-level).

## <a name="example"></a>Пример

Ниже представлен файл *EDITORCONFIG* с соглашением об именовании, в котором указано, что общедоступные свойства, методы, поля, события и делегаты должны начинаться с прописной буквы. Обратите внимание, что это соглашение об именовании указывает несколько типов символов, к которым применяется правило, через запятую.

```ini
[*.{cs,vb}]

# Defining the 'public_symbols' symbol group
dotnet_naming_symbols.public_symbols.applicable_kinds           = property,method,field,event,delegate
dotnet_naming_symbols.public_symbols.applicable_accessibilities = public
dotnet_naming_symbols.public_symbols.required_modifiers         = readonly

# Defining the `first_word_upper_case_style` naming style
dotnet_naming_style.first_word_upper_case_style.capitalization = first_word_upper

# Defining the `public_members_must_be_capitalized` naming rule, by setting the symbol group to the 'public symbols' symbol group,
dotnet_naming_rule.public_members_must_be_capitalized.symbols   = public_symbols
# setting the naming style to the `first_word_upper_case_style` naming style,
dotnet_naming_rule.public_members_must_be_capitalized.style    = first_word_upper_case_style
# and setting the severity.
dotnet_naming_rule.public_members_must_be_capitalized.severity = suggestion
```

## <a name="see-also"></a>См. также раздел

- [Правила языка](language-rules.md)
- [Правила форматирования](formatting-rules.md)
- [Правила именования Roslyn](https://github.com/dotnet/roslyn/blob/master/.editorconfig#L63)
- [Справочник по правилам стиля кода .NET](index.md)
