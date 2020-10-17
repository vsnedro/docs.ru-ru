---
ms.openlocfilehash: 8209c5336983bde13a698fbc68e6a099091071f7
ms.sourcegitcommit: a6bd4cad438fe479cbd112eae10f2cd449f06e40
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/08/2020
ms.locfileid: "91844514"
---
### <a name="jsonserializerdeserialize-requires-single-character-string"></a><span data-ttu-id="5bc8d-101">Для JsonSerializer.Deserialize требуется строка из одного символа</span><span class="sxs-lookup"><span data-stu-id="5bc8d-101">JsonSerializer.Deserialize requires single-character string</span></span>

<span data-ttu-id="5bc8d-102">Если параметр типа имеет значение <xref:System.Char>, строковый аргумент для <xref:System.Text.Json.JsonSerializer.Deserialize%60%601(System.String,System.Text.Json.JsonSerializerOptions)?displayProperty=nameWithType> должен содержать один символ для выполнения десериализации.</span><span class="sxs-lookup"><span data-stu-id="5bc8d-102">When the type parameter is <xref:System.Char>, the string argument to <xref:System.Text.Json.JsonSerializer.Deserialize%60%601(System.String,System.Text.Json.JsonSerializerOptions)?displayProperty=nameWithType> must contain a single character for deserialization to succeed.</span></span>

#### <a name="change-description"></a><span data-ttu-id="5bc8d-103">Описание изменений</span><span class="sxs-lookup"><span data-stu-id="5bc8d-103">Change description</span></span>

<span data-ttu-id="5bc8d-104">В предыдущих версиях .NET, если строка с несколькими символами передается в <xref:System.Text.Json.JsonSerializer.Deserialize%60%601(System.String,System.Text.Json.JsonSerializerOptions)?displayProperty=nameWithType> и параметр типа равен <xref:System.Char>, десериализация выполняется успешно, но десериализуется только первый символ.</span><span class="sxs-lookup"><span data-stu-id="5bc8d-104">In previous .NET versions, if you pass a multi-character string to <xref:System.Text.Json.JsonSerializer.Deserialize%60%601(System.String,System.Text.Json.JsonSerializerOptions)?displayProperty=nameWithType> and the type parameter is <xref:System.Char>, the deserialization succeeds and only the first character is deserialized.</span></span>

<span data-ttu-id="5bc8d-105">В .NET 5.0 и более поздних версиях, когда параметр типа равен <xref:System.Char>, передача любой, кроме односимвольной, строки приводит к вызову исключения <xref:System.Text.Json.JsonException>.</span><span class="sxs-lookup"><span data-stu-id="5bc8d-105">In .NET 5.0 and later, when the type parameter is <xref:System.Char>, passing anything other than a single-character string causes a <xref:System.Text.Json.JsonException> to be thrown.</span></span>

```csharp
// .NET Core 3.0 and 3.1: Returns the first character 'a'.
// .NET 5.0 and later: Throws JsonException because payload has more than one character.
JsonSerializer.Deserialize<char>("\"abc\"");

// Correct usage.
JsonSerializer.Deserialize<char>("\"a\"");
```

#### <a name="version-introduced"></a><span data-ttu-id="5bc8d-106">Представленная версия</span><span class="sxs-lookup"><span data-stu-id="5bc8d-106">Version introduced</span></span>

<span data-ttu-id="5bc8d-107">5.0</span><span class="sxs-lookup"><span data-stu-id="5bc8d-107">5.0</span></span>

#### <a name="reason-for-change"></a><span data-ttu-id="5bc8d-108">Причина изменения</span><span class="sxs-lookup"><span data-stu-id="5bc8d-108">Reason for change</span></span>

<span data-ttu-id="5bc8d-109"><xref:System.Text.Json.JsonSerializer.Deserialize%60%601(System.String,System.Text.Json.JsonSerializerOptions)?displayProperty=nameWithType> выполняет синтаксический анализ текста, представляющего одно значение JSON, в экземпляр типа, заданного параметром универсального типа.</span><span class="sxs-lookup"><span data-stu-id="5bc8d-109"><xref:System.Text.Json.JsonSerializer.Deserialize%60%601(System.String,System.Text.Json.JsonSerializerOptions)?displayProperty=nameWithType> parses text that represents a single JSON value into an instance of the type specified by the generic type parameter.</span></span> <span data-ttu-id="5bc8d-110">Синтаксический анализ должен выполняться только тогда, когда предоставленные полезные данные допустимы для указанного параметра универсального типа.</span><span class="sxs-lookup"><span data-stu-id="5bc8d-110">Parsing should only succeed when the provided payload is valid for the specified generic type parameter.</span></span> <span data-ttu-id="5bc8d-111">Для типа значения <xref:System.Char> допустимые полезные данные представляют собой строку из одного символа.</span><span class="sxs-lookup"><span data-stu-id="5bc8d-111">For a <xref:System.Char> value type, a valid payload is a single character string.</span></span>

#### <a name="recommended-action"></a><span data-ttu-id="5bc8d-112">Рекомендованное действие</span><span class="sxs-lookup"><span data-stu-id="5bc8d-112">Recommended action</span></span>

<span data-ttu-id="5bc8d-113">При синтаксическом анализе строки в тип <xref:System.Char> с помощью <xref:System.Text.Json.JsonSerializer.Deserialize%60%601(System.String,System.Text.Json.JsonSerializerOptions)?displayProperty=nameWithType>убедитесь, что строка состоит из одного символа.</span><span class="sxs-lookup"><span data-stu-id="5bc8d-113">When parsing a string into a <xref:System.Char> type using <xref:System.Text.Json.JsonSerializer.Deserialize%60%601(System.String,System.Text.Json.JsonSerializerOptions)?displayProperty=nameWithType>, make sure the string consists of a single character.</span></span>

#### <a name="category"></a><span data-ttu-id="5bc8d-114">Категория</span><span class="sxs-lookup"><span data-stu-id="5bc8d-114">Category</span></span>

<span data-ttu-id="5bc8d-115">Сериализация</span><span class="sxs-lookup"><span data-stu-id="5bc8d-115">Serialization</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="5bc8d-116">Затронутые API</span><span class="sxs-lookup"><span data-stu-id="5bc8d-116">Affected APIs</span></span>

- <xref:System.Text.Json.JsonSerializer.Deserialize%60%601(System.String,System.Text.Json.JsonSerializerOptions)?displayProperty=fullName>

<!--

#### Affected APIs

- `M:System.Text.Json.JsonSerializer.Deserialize``1(System.String,System.Text.Json.JsonSerializerOptions)`

-->
