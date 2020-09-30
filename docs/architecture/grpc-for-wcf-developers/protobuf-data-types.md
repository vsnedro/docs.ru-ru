---
title: Protobuf скалярные типы данных — gRPC для разработчиков WCF
description: Сведения об основных и хорошо известных типах данных, которые protobuf и gRPC поддерживаются в .NET Core.
ms.date: 09/09/2019
ms.openlocfilehash: 5447067b953d257258950d020636e0b38245e20d
ms.sourcegitcommit: 665f8fc55258356f4d2f4a6585b750c974b26675
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/30/2020
ms.locfileid: "91573648"
---
# <a name="protobuf-scalar-data-types"></a><span data-ttu-id="5f416-103">Скалярные типы данных Protobuf</span><span class="sxs-lookup"><span data-stu-id="5f416-103">Protobuf scalar data types</span></span>

<span data-ttu-id="5f416-104">Буфер протокола (protobuf) поддерживает ряд собственных скалярных типов значений.</span><span class="sxs-lookup"><span data-stu-id="5f416-104">Protocol Buffer (Protobuf) supports a range of native scalar value types.</span></span> <span data-ttu-id="5f416-105">В следующей таблице перечислены все типы с эквивалентными им типами в C#.</span><span class="sxs-lookup"><span data-stu-id="5f416-105">The following table lists them all with their equivalent C# type:</span></span>

| <span data-ttu-id="5f416-106">Тип protobuf</span><span class="sxs-lookup"><span data-stu-id="5f416-106">Protobuf type</span></span> | <span data-ttu-id="5f416-107">Тип C#</span><span class="sxs-lookup"><span data-stu-id="5f416-107">C# type</span></span>      | <span data-ttu-id="5f416-108">Примечания</span><span class="sxs-lookup"><span data-stu-id="5f416-108">Notes</span></span> |
| ------------- | ------------ | ----- |
| `double`      | `double`     |       |
| `float`       | `float`      |       |
| `int32`       | `int`        | <span data-ttu-id="5f416-109">1</span><span class="sxs-lookup"><span data-stu-id="5f416-109">1</span></span>     |
| `int64`       | `long`       | <span data-ttu-id="5f416-110">1</span><span class="sxs-lookup"><span data-stu-id="5f416-110">1</span></span>     |
| `uint32`      | `uint`       |       |
| `uint64`      | `ulong`      |       |
| `sint32`      | `int`        | <span data-ttu-id="5f416-111">1</span><span class="sxs-lookup"><span data-stu-id="5f416-111">1</span></span>     |
| `sint64`      | `long`       | <span data-ttu-id="5f416-112">1</span><span class="sxs-lookup"><span data-stu-id="5f416-112">1</span></span>     |
| `fixed32`     | `uint`       | <span data-ttu-id="5f416-113">2</span><span class="sxs-lookup"><span data-stu-id="5f416-113">2</span></span>     |
| `fixed64`     | `ulong`      | <span data-ttu-id="5f416-114">2</span><span class="sxs-lookup"><span data-stu-id="5f416-114">2</span></span>     |
| `sfixed32`    | `int`        | <span data-ttu-id="5f416-115">2</span><span class="sxs-lookup"><span data-stu-id="5f416-115">2</span></span>     |
| `sfixed64`    | `long`       | <span data-ttu-id="5f416-116">2</span><span class="sxs-lookup"><span data-stu-id="5f416-116">2</span></span>     |
| `bool`        | `bool`       |       |
| `string`      | `string`     | <span data-ttu-id="5f416-117">3</span><span class="sxs-lookup"><span data-stu-id="5f416-117">3</span></span>     |
| `bytes`       | `ByteString` | <span data-ttu-id="5f416-118">4</span><span class="sxs-lookup"><span data-stu-id="5f416-118">4</span></span>     |

<span data-ttu-id="5f416-119">Примечания.</span><span class="sxs-lookup"><span data-stu-id="5f416-119">Notes:</span></span>

1. <span data-ttu-id="5f416-120">Стандартная кодировка для `int32` и `int64` неэффективна при работе со значениями со знаком.</span><span class="sxs-lookup"><span data-stu-id="5f416-120">The standard encoding for `int32` and `int64` is inefficient when you're working with signed values.</span></span> <span data-ttu-id="5f416-121">Если поле, скорее всего, содержит отрицательные числа, используйте `sint32` или `sint64` .</span><span class="sxs-lookup"><span data-stu-id="5f416-121">If your field is likely to contain negative numbers, use `sint32` or `sint64` instead.</span></span> <span data-ttu-id="5f416-122">Эти типы сопоставляются с `int` типами C# и `long` соответственно.</span><span class="sxs-lookup"><span data-stu-id="5f416-122">These types map to the C# `int` and `long` types, respectively.</span></span>
2. <span data-ttu-id="5f416-123">`fixed`Поля всегда используют одинаковое число байтов независимо от значения.</span><span class="sxs-lookup"><span data-stu-id="5f416-123">The `fixed` fields always use the same number of bytes no matter what the value is.</span></span> <span data-ttu-id="5f416-124">Такое поведение позволяет ускорить сериализацию и десериализацию для больших значений.</span><span class="sxs-lookup"><span data-stu-id="5f416-124">This behavior makes serialization and deserialization faster for larger values.</span></span>
3. <span data-ttu-id="5f416-125">Строки protobuf имеют кодировку UTF-8 (или 7-разрядный код ASCII).</span><span class="sxs-lookup"><span data-stu-id="5f416-125">Protobuf strings are UTF-8 (or 7-bit ASCII) encoded.</span></span> <span data-ttu-id="5f416-126">Длина закодированного байта не может превышать 2<sup>32</sup>.</span><span class="sxs-lookup"><span data-stu-id="5f416-126">The encoded length can't be greater than 2<sup>32</sup>.</span></span>
4. <span data-ttu-id="5f416-127">Среда выполнения protobuf предоставляет `ByteString` тип, который легко сопоставить с массивами C# и из них `byte[]` .</span><span class="sxs-lookup"><span data-stu-id="5f416-127">The Protobuf runtime provides a `ByteString` type that maps easily to and from C# `byte[]` arrays.</span></span>

## <a name="other-net-primitive-types"></a><span data-ttu-id="5f416-128">Другие типы-примитивы .NET</span><span class="sxs-lookup"><span data-stu-id="5f416-128">Other .NET primitive types</span></span>

### <a name="dates-and-times"></a><span data-ttu-id="5f416-129">Даты и время</span><span class="sxs-lookup"><span data-stu-id="5f416-129">Dates and times</span></span>

<span data-ttu-id="5f416-130">Собственные скалярные типы не предоставляют значения даты и времени, эквивалентные C# <xref:System.DateTimeOffset> , <xref:System.DateTime> и <xref:System.TimeSpan> .</span><span class="sxs-lookup"><span data-stu-id="5f416-130">The native scalar types don't provide for date and time values, equivalent to C#'s <xref:System.DateTimeOffset>, <xref:System.DateTime>, and <xref:System.TimeSpan>.</span></span> <span data-ttu-id="5f416-131">Эти типы можно указать с помощью некоторых расширений "хорошо известных типов Google".</span><span class="sxs-lookup"><span data-stu-id="5f416-131">You can specify these types by using some of Google's "Well Known Types" extensions.</span></span> <span data-ttu-id="5f416-132">Эти расширения обеспечивают поддержку создания кода и среды выполнения для сложных типов полей в поддерживаемых платформах.</span><span class="sxs-lookup"><span data-stu-id="5f416-132">These extensions provide code generation and runtime support for complex field types across the supported platforms.</span></span>

<span data-ttu-id="5f416-133">В следующей таблице показаны типы даты и времени.</span><span class="sxs-lookup"><span data-stu-id="5f416-133">The following table shows the date and time types:</span></span>

| <span data-ttu-id="5f416-134">Тип C#</span><span class="sxs-lookup"><span data-stu-id="5f416-134">C# type</span></span> | <span data-ttu-id="5f416-135">Хорошо известный тип protobuf</span><span class="sxs-lookup"><span data-stu-id="5f416-135">Protobuf well-known type</span></span> |
| ------- | ------------------------ |
| `DateTimeOffset` | `google.protobuf.Timestamp` |
| `DateTime` | `google.protobuf.Timestamp` |
| `TimeSpan` | `google.protobuf.Duration` |

```protobuf  
syntax = "proto3"

import "google/protobuf/duration.proto";  
import "google/protobuf/timestamp.proto";

message Meeting {

    string subject = 1;
    google.protobuf.Timestamp time = 2;
    google.protobuf.Duration duration = 3;

}  
```

<span data-ttu-id="5f416-136">Созданные свойства в классе C# не являются типами даты и времени .NET.</span><span class="sxs-lookup"><span data-stu-id="5f416-136">The generated properties in the C# class aren't the .NET date and time types.</span></span> <span data-ttu-id="5f416-137">Свойства используют классы `Timestamp` и `Duration` в пространстве имен `Google.Protobuf.WellKnownTypes`.</span><span class="sxs-lookup"><span data-stu-id="5f416-137">The properties use the `Timestamp` and `Duration` classes in the `Google.Protobuf.WellKnownTypes` namespace.</span></span> <span data-ttu-id="5f416-138">Эти классы предоставляют методы для преобразования в `DateTimeOffset`, `DateTime` и `TimeSpan`.</span><span class="sxs-lookup"><span data-stu-id="5f416-138">These classes provide methods for converting to and from `DateTimeOffset`, `DateTime`, and `TimeSpan`.</span></span>

```csharp
// Create Timestamp and Duration from .NET DateTimeOffset and TimeSpan
var meeting = new Meeting
{
    Time = Timestamp.FromDateTimeOffset(meetingTime), // also FromDateTime()
    Duration = Duration.FromTimeSpan(meetingLength)
};

// Convert Timestamp and Duration to .NET DateTimeOffset and TimeSpan
DateTimeOffset time = meeting.Time.ToDateTimeOffset();
TimeSpan? duration = meeting.Duration?.ToTimeSpan();
```

> [!NOTE]
> <span data-ttu-id="5f416-139">Тип `Timestamp` работает с временем в формате UTC.</span><span class="sxs-lookup"><span data-stu-id="5f416-139">The `Timestamp` type works with UTC times.</span></span> <span data-ttu-id="5f416-140">Значения `DateTimeOffset` всегда имеют нулевое смещение, а свойство `DateTime.Kind` всегда имеет значение `DateTimeKind.Utc`.</span><span class="sxs-lookup"><span data-stu-id="5f416-140">`DateTimeOffset` values always have an offset of zero, and the `DateTime.Kind` property is always `DateTimeKind.Utc`.</span></span>

### <a name="systemguid"></a><span data-ttu-id="5f416-141">System.Guid</span><span class="sxs-lookup"><span data-stu-id="5f416-141">System.Guid</span></span>

<span data-ttu-id="5f416-142">Protobuf напрямую не поддерживает <xref:System.Guid> тип, известный как `UUID` на других платформах.</span><span class="sxs-lookup"><span data-stu-id="5f416-142">Protobuf doesn't directly support the <xref:System.Guid> type, known as `UUID` on other platforms.</span></span> <span data-ttu-id="5f416-143">Для него не существует хорошо известного типа.</span><span class="sxs-lookup"><span data-stu-id="5f416-143">There's no well-known type for it.</span></span>

<span data-ttu-id="5f416-144">Лучшим подходом является обработку `Guid` значений в виде `string` поля с использованием стандартного `8-4-4-4-12` шестнадцатеричного формата (например, `45a9fda3-bd01-47a9-8460-c1cd7484b0b3` ).</span><span class="sxs-lookup"><span data-stu-id="5f416-144">The best approach is to handle `Guid` values as a `string` field, by using the standard `8-4-4-4-12` hexadecimal format (for example, `45a9fda3-bd01-47a9-8460-c1cd7484b0b3`).</span></span> <span data-ttu-id="5f416-145">Все языки и платформы могут анализировать этот формат.</span><span class="sxs-lookup"><span data-stu-id="5f416-145">All languages and platforms can parse that format.</span></span>

<span data-ttu-id="5f416-146">Не используйте `bytes` поле для `Guid` значений.</span><span class="sxs-lookup"><span data-stu-id="5f416-146">Don't use a `bytes` field for `Guid` values.</span></span> <span data-ttu-id="5f416-147">Проблемы с *порядок следования байтов* ([Определение Википедии](https://en.wikipedia.org/wiki/Endianness)) могут привести к непредсказуемому поведению, когда protobuf взаимодействует с другими платформами, такими как Java.</span><span class="sxs-lookup"><span data-stu-id="5f416-147">Problems with *endianness* ([Wikipedia definition](https://en.wikipedia.org/wiki/Endianness)) can result in erratic behavior when Protobuf is interacting with other platforms, such as Java.</span></span>

### <a name="nullable-types"></a><span data-ttu-id="5f416-148">Типы, допускающие значение NULL</span><span class="sxs-lookup"><span data-stu-id="5f416-148">Nullable types</span></span>

<span data-ttu-id="5f416-149">При создании кода protobuf для C# используются собственные типы, например `int` для `int32`.</span><span class="sxs-lookup"><span data-stu-id="5f416-149">The Protobuf code generation for C# uses the native types, such as `int` for `int32`.</span></span> <span data-ttu-id="5f416-150">Поэтому значения всегда включаются и не могут иметь значение null.</span><span class="sxs-lookup"><span data-stu-id="5f416-150">So the values are always included and can't be null.</span></span>

<span data-ttu-id="5f416-151">Для значений, для которых требуется явное значение null, например использование `int?` в коде C#, protobuf "хорошо известные типы" включает оболочки, компилируемые в типы C#, допускающие значение null.</span><span class="sxs-lookup"><span data-stu-id="5f416-151">For values that require explicit null, such as using `int?` in your C# code, Protobuf's "Well Known Types" include wrappers that are compiled to nullable C# types.</span></span> <span data-ttu-id="5f416-152">Чтобы использовать их, импортируйте `wrappers.proto` в `.proto` файл следующим образом:</span><span class="sxs-lookup"><span data-stu-id="5f416-152">To use them, import `wrappers.proto` into your `.proto` file, like this:</span></span>

```protobuf  
syntax = "proto3"

import "google/protobuf/wrappers.proto"

message Person {

    ...
    google.protobuf.Int32Value age = 5;

}
```

<span data-ttu-id="5f416-153">Protobuf будет использовать простой `T?` (например, `int?` ) для созданного свойства сообщения.</span><span class="sxs-lookup"><span data-stu-id="5f416-153">Protobuf will use the simple `T?` (for example, `int?`) for the generated message property.</span></span>

<span data-ttu-id="5f416-154">В следующей таблице приведен полный список типов оболочек с эквивалентным им типом C#.</span><span class="sxs-lookup"><span data-stu-id="5f416-154">The following table shows the complete list of wrapper types with their equivalent C# type:</span></span>

| <span data-ttu-id="5f416-155">Тип C#</span><span class="sxs-lookup"><span data-stu-id="5f416-155">C# type</span></span>   | <span data-ttu-id="5f416-156">Оболочка хорошо известного типа</span><span class="sxs-lookup"><span data-stu-id="5f416-156">Well Known Type wrapper</span></span>       |
| --------- | ----------------------------- |
| `double?` | `google.protobuf.DoubleValue` |
| `float?`  | `google.protobuf.FloatValue`  |
| `int?`    | `google.protobuf.Int32Value`  |
| `long?`   | `google.protobuf.Int64Value`  |
| `uint?`   | `google.protobuf.UInt32Value` |
| `ulong?`  | `google.protobuf.UInt64Value` |

<span data-ttu-id="5f416-157">Хорошо известные типы `Timestamp` и `Duration` представлены в .NET как классы.</span><span class="sxs-lookup"><span data-stu-id="5f416-157">The well-known types `Timestamp` and `Duration` are represented in .NET as classes.</span></span> <span data-ttu-id="5f416-158">В C# 8 и более поздних версиях можно использовать ссылочные типы, допускающие значение null.</span><span class="sxs-lookup"><span data-stu-id="5f416-158">In C# 8 and beyond, you can use nullable reference types.</span></span> <span data-ttu-id="5f416-159">Но при преобразовании в или. важно проверить наличие значения NULL в свойствах этих типов `DateTimeOffset` `TimeSpan` .</span><span class="sxs-lookup"><span data-stu-id="5f416-159">But it's important to check for null on properties of those types when you're converting to `DateTimeOffset` or `TimeSpan`.</span></span>

## <a name="decimals"></a><span data-ttu-id="5f416-160">Десятичные знаки</span><span class="sxs-lookup"><span data-stu-id="5f416-160">Decimals</span></span>

<span data-ttu-id="5f416-161">Protobuf изначально не поддерживает тип .NET `decimal`, просто `double` и `float`.</span><span class="sxs-lookup"><span data-stu-id="5f416-161">Protobuf doesn't natively support the .NET `decimal` type, just `double` and `float`.</span></span> <span data-ttu-id="5f416-162">В проекте protobuf есть текущее обсуждение о возможности добавления стандартного `Decimal` типа к хорошо известным типам с поддержкой платформы для языков и платформ, поддерживающих эту возможность.</span><span class="sxs-lookup"><span data-stu-id="5f416-162">There's an ongoing discussion in the Protobuf project about the possibility of adding a standard `Decimal` type to the well-known types, with platform support for languages and frameworks that support it.</span></span> <span data-ttu-id="5f416-163">Однако к настоящему моменту еще ничего не реализовано.</span><span class="sxs-lookup"><span data-stu-id="5f416-163">Nothing has been implemented yet.</span></span>

<span data-ttu-id="5f416-164">Можно создать определение сообщения, представляющее `decimal` тип, который будет работать для безопасного сериализации между клиентами и серверами .NET.</span><span class="sxs-lookup"><span data-stu-id="5f416-164">It's possible to create a message definition to represent the `decimal` type that would work for safe serialization between .NET clients and servers.</span></span> <span data-ttu-id="5f416-165">Однако разработчикам на других платформах следует понимать, какой формат используется, и реализовать свою собственную обработку.</span><span class="sxs-lookup"><span data-stu-id="5f416-165">But developers on other platforms would have to understand the format being used and implement their own handling for it.</span></span>

### <a name="creating-a-custom-decimal-type-for-protobuf"></a><span data-ttu-id="5f416-166">Создание настраиваемого десятичного типа для protobuf</span><span class="sxs-lookup"><span data-stu-id="5f416-166">Creating a custom decimal type for Protobuf</span></span>

<span data-ttu-id="5f416-167">Простая реализация может быть аналогична нестандартному `Money` типу, используемому некоторыми API-интерфейсами Google, без `currency` поля.</span><span class="sxs-lookup"><span data-stu-id="5f416-167">A simple implementation might be similar to the nonstandard `Money` type that some Google APIs use, without the `currency` field.</span></span>

```protobuf
package CustomTypes;

// Example: 12345.6789 -> { units = 12345, nanos = 678900000 }
message DecimalValue {

    // Whole units part of the amount
    int64 units = 1;

    // Nano units of the amount (10^-9)
    // Must be same sign as units
    sfixed32 nanos = 2;
}
```

<span data-ttu-id="5f416-168">Поле `nanos` представляет значения из `0.999_999_999` в `-0.999_999_999`.</span><span class="sxs-lookup"><span data-stu-id="5f416-168">The `nanos` field represents values from `0.999_999_999` to `-0.999_999_999`.</span></span> <span data-ttu-id="5f416-169">Например, значение `decimal` `1.5m` будет представлено как `{ units = 1, nanos = 500_000_000 }`.</span><span class="sxs-lookup"><span data-stu-id="5f416-169">For example, the `decimal` value `1.5m` would be represented as `{ units = 1, nanos = 500_000_000 }`.</span></span> <span data-ttu-id="5f416-170">Именно поэтому в поле `nanos` в этом примере используется тип `sfixed32`, который более эффективно кодируется, чем `int32` для больших значений.</span><span class="sxs-lookup"><span data-stu-id="5f416-170">This is why the `nanos` field in this example uses the `sfixed32` type, which encodes more efficiently than `int32` for larger values.</span></span> <span data-ttu-id="5f416-171">Если поле `units` имеет отрицательное значение, поле `nanos` также должно быть отрицательным.</span><span class="sxs-lookup"><span data-stu-id="5f416-171">If the `units` field is negative, the `nanos` field should also be negative.</span></span>

> [!NOTE]
> <span data-ttu-id="5f416-172">Существует несколько других алгоритмов кодирования значений `decimal` в виде строк байтов, но это сообщение проще понять, чем любое из них.</span><span class="sxs-lookup"><span data-stu-id="5f416-172">There are multiple other algorithms for encoding `decimal` values as byte strings, but this message is easier to understand than any of them.</span></span> <span data-ttu-id="5f416-173">На значения не влияют порядок следования байтов на разных платформах.</span><span class="sxs-lookup"><span data-stu-id="5f416-173">The values are not affected by endianness on different platforms.</span></span>

<span data-ttu-id="5f416-174">Преобразование между этим типом и типом BCL `decimal` может быть реализовано в C# следующим образом:</span><span class="sxs-lookup"><span data-stu-id="5f416-174">Conversion between this type and the BCL `decimal` type might be implemented in C# like this:</span></span>

```csharp
namespace CustomTypes
{
    public partial class DecimalValue
    {
        private const decimal NanoFactor = 1_000_000_000;
        public DecimalValue(long units, int nanos)
        {
            Units = units;
            Nanos = nanos;
        }

        public long Units { get; }
        public int Nanos { get; }

        public static implicit operator decimal(CustomTypes.DecimalValue grpcDecimal)
        {
            return grpcDecimal.Units + grpcDecimal.Nanos / NanoFactor;
        }

        public static implicit operator CustomTypes.DecimalValue(decimal value)
        {
            var units = decimal.ToInt64(value);
            var nanos = decimal.ToInt32((value - units) * NanoFactor);
            return new CustomTypes.DecimalValue(units, nanos);
        }
    }
}
```

> [!IMPORTANT]
> <span data-ttu-id="5f416-175">При использовании пользовательских типов сообщений, таких как это, *необходимо* документировать их с помощью комментариев в `.proto` .</span><span class="sxs-lookup"><span data-stu-id="5f416-175">Whenever you use custom message types like this, you *must* document them with comments in `.proto`.</span></span> <span data-ttu-id="5f416-176">Другие разработчики могут затем реализовать преобразование в эквивалентный тип и из него на своем языке или в собственной платформе.</span><span class="sxs-lookup"><span data-stu-id="5f416-176">Other developers can then implement conversion to and from the equivalent type in their own language or framework.</span></span>

>[!div class="step-by-step"]
><span data-ttu-id="5f416-177">[Назад](protobuf-messages.md)
>[Вперед](protobuf-nested-types.md)</span><span class="sxs-lookup"><span data-stu-id="5f416-177">[Previous](protobuf-messages.md)
[Next](protobuf-nested-types.md)</span></span>
