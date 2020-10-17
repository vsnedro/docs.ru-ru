---
ms.openlocfilehash: 5b49dcae45e44bfd9ec3e150ad25c3f21d62c18e
ms.sourcegitcommit: b59237ca4ec763969a0dd775a3f8f39f8c59fe24
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/12/2020
ms.locfileid: "91955345"
---
### <a name="jsonserializerserialize-throws-argumentnullexception-when-type-parameter-is-null"></a><span data-ttu-id="02499-101">JsonSerializer.Serialize вызывает исключение ArgumentNullException, если параметр типа имеет значение null</span><span class="sxs-lookup"><span data-stu-id="02499-101">JsonSerializer.Serialize throws ArgumentNullException when type parameter is null</span></span>

<span data-ttu-id="02499-102">Перегрузки <xref:System.Text.Json.JsonSerializer.Serialize%2A?displayProperty=nameWithType>, <xref:System.Text.Json.JsonSerializer.SerializeAsync%2A?displayProperty=nameWithType> и <xref:System.Text.Json.JsonSerializer.SerializeToUtf8Bytes%2A?displayProperty=nameWithType> с параметром <xref:System.Type> теперь вызывают исключение <xref:System.ArgumentNullException>, когда для параметра <xref:System.Type> передается значение `null`.</span><span class="sxs-lookup"><span data-stu-id="02499-102"><xref:System.Text.Json.JsonSerializer.Serialize%2A?displayProperty=nameWithType>, <xref:System.Text.Json.JsonSerializer.SerializeAsync%2A?displayProperty=nameWithType>, and <xref:System.Text.Json.JsonSerializer.SerializeToUtf8Bytes%2A?displayProperty=nameWithType> overloads that have a <xref:System.Type> parameter now throw an <xref:System.ArgumentNullException> whenever `null` is passed for the <xref:System.Type> parameter.</span></span>

#### <a name="change-description"></a><span data-ttu-id="02499-103">Описание изменений</span><span class="sxs-lookup"><span data-stu-id="02499-103">Change description</span></span>

<span data-ttu-id="02499-104">В .NET Core 3.1 перегрузки <xref:System.Text.Json.JsonSerializer.Serialize%2A?displayProperty=nameWithType>, <xref:System.Text.Json.JsonSerializer.SerializeAsync(System.IO.Stream,System.Object,System.Type,System.Text.Json.JsonSerializerOptions,System.Threading.CancellationToken)?displayProperty=nameWithType> и <xref:System.Text.Json.JsonSerializer.SerializeToUtf8Bytes(System.Object,System.Type,System.Text.Json.JsonSerializerOptions)?displayProperty=nameWithType>, имеющие параметр <xref:System.Type>, вызывают исключение <xref:System.ArgumentNullException> при передаче для параметра `Type inputType` значение `null`, но не в том случае, если параметр `Object value` также равен `null`.</span><span class="sxs-lookup"><span data-stu-id="02499-104">In .NET Core 3.1, the <xref:System.Text.Json.JsonSerializer.Serialize%2A?displayProperty=nameWithType>, <xref:System.Text.Json.JsonSerializer.SerializeAsync(System.IO.Stream,System.Object,System.Type,System.Text.Json.JsonSerializerOptions,System.Threading.CancellationToken)?displayProperty=nameWithType>, and <xref:System.Text.Json.JsonSerializer.SerializeToUtf8Bytes(System.Object,System.Type,System.Text.Json.JsonSerializerOptions)?displayProperty=nameWithType> overloads that have a <xref:System.Type> parameter throw an <xref:System.ArgumentNullException> when `null` is passed for the `Type inputType` parameter, but not if the `Object value` parameter is also `null`.</span></span> <span data-ttu-id="02499-105">Начиная с .NET 5.0 эти методы *всегда* вызывают исключение <xref:System.ArgumentNullException> при передаче для параметра <xref:System.Type> значения `null`.</span><span class="sxs-lookup"><span data-stu-id="02499-105">Starting in .NET 5.0, these methods *always* throw an <xref:System.ArgumentNullException> when `null` is passed for the <xref:System.Type> parameter.</span></span>

<span data-ttu-id="02499-106">Поведение в .NET Core 3.1:</span><span class="sxs-lookup"><span data-stu-id="02499-106">Behavior in .NET Core 3.1:</span></span>

```csharp
// Returns a string with value "null".
JsonSerializer.Serialize(null, null);

// Returns a byte array with value "null".
JsonSerializer.SerializeToUtf8Bytes(null, null);
```

<span data-ttu-id="02499-107">Поведение в .NET 5.0 и более поздних версиях:</span><span class="sxs-lookup"><span data-stu-id="02499-107">Behavior in .NET 5.0 and later:</span></span>

```csharp
// Throws ArgumentNullException: "Value cannot be null. (Parameter 'inputType')".
JsonSerializer.Serialize(null, null);

// Throws ArgumentNullException: "Value cannot be null. (Parameter 'inputType')".
JsonSerializer.SerializeToUtf8Bytes(null, null);
```

#### <a name="version-introduced"></a><span data-ttu-id="02499-108">Представленная версия</span><span class="sxs-lookup"><span data-stu-id="02499-108">Version introduced</span></span>

<span data-ttu-id="02499-109">5.0</span><span class="sxs-lookup"><span data-stu-id="02499-109">5.0</span></span>

#### <a name="reason-for-change"></a><span data-ttu-id="02499-110">Причина изменения</span><span class="sxs-lookup"><span data-stu-id="02499-110">Reason for change</span></span>

<span data-ttu-id="02499-111">Передача для параметра `Type inputType` значения `null` неприемлемо и всегда должно вызывать исключение <xref:System.ArgumentNullException>.</span><span class="sxs-lookup"><span data-stu-id="02499-111">Passing in `null` for the `Type inputType` parameter is unacceptable and should always throw an <xref:System.ArgumentNullException>.</span></span>

#### <a name="recommended-action"></a><span data-ttu-id="02499-112">Рекомендованное действие</span><span class="sxs-lookup"><span data-stu-id="02499-112">Recommended action</span></span>

<span data-ttu-id="02499-113">Убедитесь, что вы не передаете для параметра `Type inputType` этих методов значение `null`.</span><span class="sxs-lookup"><span data-stu-id="02499-113">Make sure that you are not passing `null` for the `Type inputType` parameter of these methods.</span></span>

#### <a name="category"></a><span data-ttu-id="02499-114">Категория</span><span class="sxs-lookup"><span data-stu-id="02499-114">Category</span></span>

<span data-ttu-id="02499-115">Сериализация</span><span class="sxs-lookup"><span data-stu-id="02499-115">Serialization</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="02499-116">Затронутые API</span><span class="sxs-lookup"><span data-stu-id="02499-116">Affected APIs</span></span>

- <xref:System.Text.Json.JsonSerializer.Serialize(System.Object,System.Type,System.Text.Json.JsonSerializerOptions)?displayProperty=fullName>
- <xref:System.Text.Json.JsonSerializer.Serialize(System.Text.Json.Utf8JsonWriter,System.Object,System.Type,System.Text.Json.JsonSerializerOptions)?displayProperty=fullName>
- <xref:System.Text.Json.JsonSerializer.SerializeAsync(System.IO.Stream,System.Object,System.Type,System.Text.Json.JsonSerializerOptions,System.Threading.CancellationToken)?displayProperty=fullName>
- <xref:System.Text.Json.JsonSerializer.SerializeToUtf8Bytes(System.Object,System.Type,System.Text.Json.JsonSerializerOptions)?displayProperty=fullName>

<!--

#### Affected APIs

- `M:System.Text.Json.JsonSerializer.Serialize(System.Object,System.Type,System.Text.Json.JsonSerializerOptions)`
- `M:System.Text.Json.JsonSerializer.Serialize(System.Text.Json.Utf8JsonWriter,System.Object,System.Type,System.Text.Json.JsonSerializerOptions)`
- `M:System.Text.Json.JsonSerializer.SerializeAsync(System.IO.Stream,System.Object,System.Type,System.Text.Json.JsonSerializerOptions,System.Threading.CancellationToken)`
- `M:System.Text.Json.JsonSerializer.SerializeToUtf8Bytes(System.Object,System.Type,System.Text.Json.JsonSerializerOptions)`

-->
