---
title: Критическое изменение. Не являющиеся открытыми конструкторы без параметров не используются для десериализации
description: Узнайте о критическом изменении в .NET 5.0, где не являющиеся открытыми конструкторы без параметров больше не используются для десериализации с помощью JsonSerializer.
ms.date: 10/18/2020
ms.openlocfilehash: a2ea54b6a76692dae7d6e01b06b11218d66b1cd7
ms.sourcegitcommit: 4d5e25a46aa7cd0d29b4b9227b92987354d444c4
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/26/2021
ms.locfileid: "98794704"
---
# <a name="non-public-parameterless-constructors-not-used-for-deserialization"></a>Не являющиеся открытыми конструкторы без параметров не используются для десериализации

Чтобы гарантировать согласованность, во всех поддерживаемых моникерах целевой платформы (TFM) не являющиеся открытыми конструкторы без параметров больше не используются для десериализации с помощью <xref:System.Text.Json.JsonSerializer> по умолчанию.

## <a name="change-description"></a>Описание изменений

Поведение отдельных [пакетов NuGet System.Text.Json](https://www.nuget.org/packages/System.Text.Json/), которые поддерживают .NET Standard 2.0 и более поздних версий (версии с 4.6.0 по 4.7.2), согласуется со встроенным поведением в .NET Core 3.0 и 3.1. В .NET Core 3. x внутренние и закрытые конструкторы можно использовать для десериализации. В отдельных пакетах не допускаются конструкторы, не являющиеся открытыми, и создается исключение <xref:System.MissingMethodException>, если не определен открытый конструктор без параметров.

Начиная с .NET 5.0 и версии 5.0.0 пакета NuGet System.Text.Json согласовано поведение между пакетом NuGet и встроенными API. Сериализатор по умолчанию игнорирует не являющиеся открытыми конструкторы, в том числе конструкторы без параметров. Сериализатор использует для десериализации один из следующих конструкторов:

- Открытый конструктор, помеченный атрибутом <xref:System.Text.Json.Serialization.JsonConstructorAttribute>.
- Открытый конструктор без параметров.
- Открытый параметризованный конструктор (если это единственный открытый конструктор).

Если ни один из этих конструкторов не доступен, при попытке десериализовать тип возникает исключение <xref:System.NotSupportedException>.

## <a name="version-introduced"></a>Представленная версия

5.0

## <a name="reason-for-change"></a>Причина изменения

- Принудительно обеспечить согласованное поведение между всеми моникерами целевой платформы (TFM), для которых создается <xref:System.Text.Json?displayProperty=fullName> (.NET Core 3.0 и более поздних версий и .NET Standard 2.0)
- Поскольку <xref:System.Text.Json.JsonSerializer> не должен выполнять вызовы к не являющейся открытой контактной зоне типа, будь то конструктор, свойство или поле.

## <a name="recommended-action"></a>Рекомендованное действие

- Если вы являетесь владельцем типа и это целесообразно, сделайте конструктор без параметров открытым.
- В противном случае реализуйте для типа <xref:System.Text.Json.Serialization.JsonConverter%601> и обеспечьте контроль десериализации. Можно вызвать конструктор, не являющийся открытым, из реализации <xref:System.Text.Json.Serialization.JsonConverter%601>, если это разрешено правилами специальных возможностей C# для этого сценария.

## <a name="affected-apis"></a>Затронутые API

- <xref:System.Text.Json.JsonSerializer.Deserialize%2A?displayProperty=fullName>
- <xref:System.Text.Json.JsonSerializer.DeserializeAsync%2A?displayProperty=fullName>

<!--

### Affected APIs

- `Overload:System.Text.Json.JsonSerializer.Deserialize`
- `Overload:System.Text.Json.JsonSerializer.DeserializeAsync`

### Category

Serialization

-->
