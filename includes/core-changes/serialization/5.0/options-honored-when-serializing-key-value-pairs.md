---
ms.openlocfilehash: 07980cf94d5de0173808da2ce44adb409fdd5419
ms.sourcegitcommit: 39b1d5f2978be15409c189a66ab30781d9082cd8
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/14/2020
ms.locfileid: "92050479"
---
### <a name="propertynamingpolicy-propertynamecaseinsensitive-and-encoder-options-are-honored-when-serializing-and-deserializing-key-value-pairs"></a><span data-ttu-id="64a1b-101">Параметры PropertyNamingPolicy, PropertyNameCaseInsensitive и Encoder учитываются при сериализации и десериализации пар "ключ-значение"</span><span class="sxs-lookup"><span data-stu-id="64a1b-101">PropertyNamingPolicy, PropertyNameCaseInsensitive, and Encoder options are honored when serializing and deserializing key-value pairs</span></span>

<span data-ttu-id="64a1b-102"><xref:System.Text.Json.JsonSerializer> теперь учитывает параметры <xref:System.Text.Json.JsonSerializerOptions.PropertyNamingPolicy> и <xref:System.Text.Json.JsonSerializerOptions.Encoder> при сериализации имен свойств <xref:System.Collections.Generic.KeyValuePair%602.Key> и <xref:System.Collections.Generic.KeyValuePair%602.Value> экземпляра <xref:System.Collections.Generic.KeyValuePair%602>.</span><span class="sxs-lookup"><span data-stu-id="64a1b-102"><xref:System.Text.Json.JsonSerializer> now honors the <xref:System.Text.Json.JsonSerializerOptions.PropertyNamingPolicy> and <xref:System.Text.Json.JsonSerializerOptions.Encoder> options when serializing the <xref:System.Collections.Generic.KeyValuePair%602.Key> and <xref:System.Collections.Generic.KeyValuePair%602.Value> property names of a <xref:System.Collections.Generic.KeyValuePair%602> instance.</span></span> <span data-ttu-id="64a1b-103">Кроме того, <xref:System.Text.Json.JsonSerializer> учитывает параметры <xref:System.Text.Json.JsonSerializerOptions.PropertyNamingPolicy> и <xref:System.Text.Json.JsonSerializerOptions.PropertyNameCaseInsensitive> при десериализации экземпляров <xref:System.Collections.Generic.KeyValuePair%602>.</span><span class="sxs-lookup"><span data-stu-id="64a1b-103">Additionally, <xref:System.Text.Json.JsonSerializer> honors the <xref:System.Text.Json.JsonSerializerOptions.PropertyNamingPolicy> and <xref:System.Text.Json.JsonSerializerOptions.PropertyNameCaseInsensitive> options when deserializing <xref:System.Collections.Generic.KeyValuePair%602> instances.</span></span>

#### <a name="change-description"></a><span data-ttu-id="64a1b-104">Описание изменений</span><span class="sxs-lookup"><span data-stu-id="64a1b-104">Change description</span></span>

##### <a name="serialization"></a><span data-ttu-id="64a1b-105">Сериализация</span><span class="sxs-lookup"><span data-stu-id="64a1b-105">Serialization</span></span>

<span data-ttu-id="64a1b-106">В версиях .NET Core 3.x и версиях [пакета NuGet System.Text.Json](https://www.nuget.org/packages/System.Text.Json) с 4.6.0 по 4.7.2 свойства экземпляров <xref:System.Collections.Generic.KeyValuePair%602> всегда сериализуются точно как "ключ" и "значение", независимо от значений параметров <xref:System.Text.Json.JsonSerializerOptions.PropertyNamingPolicy?displayProperty=nameWithType> и <xref:System.Text.Json.JsonSerializerOptions.Encoder?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="64a1b-106">In .NET Core 3.x versions and in the 4.6.0-4.7.2 versions of the [System.Text.Json NuGet package](https://www.nuget.org/packages/System.Text.Json), the properties of <xref:System.Collections.Generic.KeyValuePair%602> instances are always serialized as "Key" and "Value" exactly, regardless of any <xref:System.Text.Json.JsonSerializerOptions.PropertyNamingPolicy?displayProperty=nameWithType> and <xref:System.Text.Json.JsonSerializerOptions.Encoder?displayProperty=nameWithType> options.</span></span> <span data-ttu-id="64a1b-107">В следующем примере кода показано, что имена свойств <xref:System.Collections.Generic.KeyValuePair%602.Key> и <xref:System.Collections.Generic.KeyValuePair%602.Value> *не* задаются в "верблюжьем" стиле, несмотря на то, что такое поведение предписывается действующей политикой именования свойств.</span><span class="sxs-lookup"><span data-stu-id="64a1b-107">The following code example shows how the <xref:System.Collections.Generic.KeyValuePair%602.Key> and <xref:System.Collections.Generic.KeyValuePair%602.Value> properties are *not* camel-cased after serialization, even though the specified property-naming policy dictates so.</span></span>

```csharp
var options = new JsonSerializerOptions { PropertyNamingPolicy = JsonNamingPolicy.CamelCase };
KeyValuePair<int, int> kvp = KeyValuePair.Create(1, 1);
Console.WriteLine(JsonSerializer.Serialize(kvp, options));
// Expected: {"key":1,"value":1}
// Actual: {"Key":1,"Value":1}
```

<span data-ttu-id="64a1b-108">Начиная с .NET 5.0 параметры <xref:System.Text.Json.JsonSerializerOptions.PropertyNamingPolicy> и <xref:System.Text.Json.JsonSerializerOptions.Encoder> учитываются при сериализации экземпляров <xref:System.Collections.Generic.KeyValuePair%602>.</span><span class="sxs-lookup"><span data-stu-id="64a1b-108">Starting in .NET 5.0, the <xref:System.Text.Json.JsonSerializerOptions.PropertyNamingPolicy> and <xref:System.Text.Json.JsonSerializerOptions.Encoder> options are honored when serializing <xref:System.Collections.Generic.KeyValuePair%602> instances.</span></span> <span data-ttu-id="64a1b-109">В следующем примере кода показано, что имена свойств <xref:System.Collections.Generic.KeyValuePair%602.Key> и <xref:System.Collections.Generic.KeyValuePair%602.Value> после сериализации задаются в "верблюжьем" стиле в соответствии с действующей политикой именования свойств.</span><span class="sxs-lookup"><span data-stu-id="64a1b-109">The following code example shows how the <xref:System.Collections.Generic.KeyValuePair%602.Key> and <xref:System.Collections.Generic.KeyValuePair%602.Value> properties are camel-cased after serialization, in accordance with the specified property-naming policy.</span></span>

```csharp
var options = new JsonSerializerOptions { PropertyNamingPolicy = JsonNamingPolicy.CamelCase };
KeyValuePair<int, int> kvp = KeyValuePair.Create(1, 1);
Console.WriteLine(JsonSerializer.Serialize(kvp, options));
// {"key":1,"value":1}
```

##### <a name="deserialization"></a><span data-ttu-id="64a1b-110">Десериализация</span><span class="sxs-lookup"><span data-stu-id="64a1b-110">Deserialization</span></span>

<span data-ttu-id="64a1b-111">В версиях .NET Core 3.x и версиях 4.7.x [пакета NuGet System.Text.Json](https://www.nuget.org/packages/System.Text.Json) возникает исключение <xref:System.Text.Json.JsonException>, если имена свойств JSON не задаются в точности как `Key` и `Value`, например, если они не начинаются с прописной буквы.</span><span class="sxs-lookup"><span data-stu-id="64a1b-111">In .NET Core 3.x versions and in the 4.7.x versions of the [System.Text.Json NuGet package](https://www.nuget.org/packages/System.Text.Json), a <xref:System.Text.Json.JsonException> is thrown when the JSON property names are not precisely `Key` and `Value`, for example, if they don't start with an uppercase letter.</span></span> <span data-ttu-id="64a1b-112">Исключение создается, даже если действующая политика именования свойств явно разрешает это.</span><span class="sxs-lookup"><span data-stu-id="64a1b-112">The exception is thrown even if a specified property-naming policy expressly permits it.</span></span>

```csharp
var options = new JsonSerializerOptions { PropertyNamingPolicy = JsonNamingPolicy.CamelCase };
string json = @"{""key"":1,""value"":1}";
// Throws JsonException.
JsonSerializer.Deserialize<KeyValuePair<int, int>>(json, options);
```

<span data-ttu-id="64a1b-113">Начиная с .NET 5.0 параметры <xref:System.Text.Json.JsonSerializerOptions.PropertyNamingPolicy> и <xref:System.Text.Json.JsonSerializerOptions.PropertyNameCaseInsensitive> учитываются при десериализации с использованием <xref:System.Text.Json.JsonSerializer>.</span><span class="sxs-lookup"><span data-stu-id="64a1b-113">Starting in .NET 5.0, the <xref:System.Text.Json.JsonSerializerOptions.PropertyNamingPolicy> and <xref:System.Text.Json.JsonSerializerOptions.PropertyNameCaseInsensitive> options are honored when deserializing using <xref:System.Text.Json.JsonSerializer>.</span></span> <span data-ttu-id="64a1b-114">Например, в следующем фрагменте кода показана успешная десериализация имен свойств <xref:System.Collections.Generic.KeyValuePair%602.Key> и <xref:System.Collections.Generic.KeyValuePair%602.Value> в нижнем регистре, поскольку это допускается действующей политикой именования свойств.</span><span class="sxs-lookup"><span data-stu-id="64a1b-114">For example, the following code snippet shows successful deserialization of lowercased <xref:System.Collections.Generic.KeyValuePair%602.Key> and <xref:System.Collections.Generic.KeyValuePair%602.Value> property names because the specified property-naming policy permits it.</span></span>

```csharp
var options = new JsonSerializerOptions { PropertyNamingPolicy = JsonNamingPolicy.CamelCase };
string json = @"{""key"":1,""value"":1}";

KeyValuePair<int, int> kvp = JsonSerializer.Deserialize<KeyValuePair<int, int>>(json);
Console.WriteLine(kvp.Key); // 1
Console.WriteLine(kvp.Value); // 1
```

<span data-ttu-id="64a1b-115">Чтобы обеспечить соответствие полезных данных, которые были сериализованы с использованием предыдущих версий, "ключ" и "значение" имеют особый регистр для сопоставления при десериализации.</span><span class="sxs-lookup"><span data-stu-id="64a1b-115">To accommodate payloads that were serialized with previous versions, "Key" and "Value" are special-cased to match when deserializing.</span></span> <span data-ttu-id="64a1b-116">Несмотря на то, что имена свойств <xref:System.Collections.Generic.KeyValuePair%602.Key> и <xref:System.Collections.Generic.KeyValuePair%602.Value> не заданы в "верблюжьем" стиле в соответствии с параметром <xref:System.Text.Json.JsonSerializerOptions.PropertyNamingPolicy> в следующем примере кода, они успешно десериализуются.</span><span class="sxs-lookup"><span data-stu-id="64a1b-116">Even though the <xref:System.Collections.Generic.KeyValuePair%602.Key> and <xref:System.Collections.Generic.KeyValuePair%602.Value> property names aren't camel-cased according to the in <xref:System.Text.Json.JsonSerializerOptions.PropertyNamingPolicy> option in the following code example, they deserialize successfully.</span></span>

```csharp
var options = new JsonSerializerOptions { PropertyNamingPolicy = JsonNamingPolicy.CamelCase };
string json = @"{""Key"":1,""Value"":1}";

KeyValuePair<int, int> kvp = JsonSerializer.Deserialize<KeyValuePair<int, int>>(json);
Console.WriteLine(kvp.Key); // 1
Console.WriteLine(kvp.Value); // 1
```

#### <a name="version-introduced"></a><span data-ttu-id="64a1b-117">Представленная версия</span><span class="sxs-lookup"><span data-stu-id="64a1b-117">Version introduced</span></span>

<span data-ttu-id="64a1b-118">5.0</span><span class="sxs-lookup"><span data-stu-id="64a1b-118">5.0</span></span>

#### <a name="reason-for-change"></a><span data-ttu-id="64a1b-119">Причина изменения</span><span class="sxs-lookup"><span data-stu-id="64a1b-119">Reason for change</span></span>

<span data-ttu-id="64a1b-120">Получено большое количество отзывов клиентов о необходимости учитывать <xref:System.Text.Json.JsonSerializerOptions.PropertyNamingPolicy>.</span><span class="sxs-lookup"><span data-stu-id="64a1b-120">Substantial customer feedback indicated that the <xref:System.Text.Json.JsonSerializerOptions.PropertyNamingPolicy> should be honored.</span></span> <span data-ttu-id="64a1b-121">Для полноты также учитываются параметры <xref:System.Text.Json.JsonSerializerOptions.PropertyNameCaseInsensitive> и <xref:System.Text.Json.JsonSerializerOptions.Encoder>, благодаря чему экземпляры <xref:System.Collections.Generic.KeyValuePair%602> обрабатываются так же, как и любой другой традиционный объект среды CLR (POCO).</span><span class="sxs-lookup"><span data-stu-id="64a1b-121">For completeness, the <xref:System.Text.Json.JsonSerializerOptions.PropertyNameCaseInsensitive> and <xref:System.Text.Json.JsonSerializerOptions.Encoder> options are also honored, so that <xref:System.Collections.Generic.KeyValuePair%602> instances are treated the same as any other plain old CLR object (POCO).</span></span>

#### <a name="recommended-action"></a><span data-ttu-id="64a1b-122">Рекомендованное действие</span><span class="sxs-lookup"><span data-stu-id="64a1b-122">Recommended action</span></span>

<span data-ttu-id="64a1b-123">Если это изменение нарушает работу, можно использовать [настраиваемый преобразователь](../../../../docs/standard/serialization/system-text-json-converters-how-to.md), который реализует нужную семантику.</span><span class="sxs-lookup"><span data-stu-id="64a1b-123">If this change is disruptive to you, you can use a [custom converter](../../../../docs/standard/serialization/system-text-json-converters-how-to.md) that implements the desired semantics.</span></span>

#### <a name="category"></a><span data-ttu-id="64a1b-124">Категория</span><span class="sxs-lookup"><span data-stu-id="64a1b-124">Category</span></span>

<span data-ttu-id="64a1b-125">Сериализация</span><span class="sxs-lookup"><span data-stu-id="64a1b-125">Serialization</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="64a1b-126">Затронутые API</span><span class="sxs-lookup"><span data-stu-id="64a1b-126">Affected APIs</span></span>

- <xref:System.Text.Json.JsonSerializer.Serialize%2A?displayProperty=fullName>
- <xref:System.Text.Json.JsonSerializer.SerializeToUtf8Bytes%2A?displayProperty=fullName>
- <xref:System.Text.Json.JsonSerializer.SerializeAsync%2A?displayProperty=fullName>
- <xref:System.Text.Json.JsonSerializer.Deserialize%2A?displayProperty=fullName>
- <xref:System.Text.Json.JsonSerializer.DeserializeAsync%2A?displayProperty=fullName>

<!--

#### Affected APIs

- `Overload:System.Text.Json.JsonSerializer.Serialize`
- `Overload:System.Text.Json.JsonSerializer.SerializeAsync`
- `Overload:System.Text.Json.JsonSerializer.SerializeToUtf8Bytes`
- `Overload:System.Text.Json.JsonSerializer.Deserialize`
- `Overload:System.Text.Json.JsonSerializer.DeserializeAsync`

-->
