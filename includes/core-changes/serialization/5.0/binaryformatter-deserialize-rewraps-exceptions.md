---
ms.openlocfilehash: 2e9267b35c9389da017927aca2346190348265c9
ms.sourcegitcommit: ef50c99928183a0bba75e07b9f22895cd4c480f8
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/07/2020
ms.locfileid: "87919255"
---
### <a name="binaryformatterdeserialize-rewraps-some-exceptions-in-serializationexception"></a><span data-ttu-id="c3da5-101">Метод BinaryFormatter.Deserialize повторно изолирует некоторые исключения в классе SerializationException</span><span class="sxs-lookup"><span data-stu-id="c3da5-101">BinaryFormatter.Deserialize rewraps some exceptions in SerializationException</span></span>

<span data-ttu-id="c3da5-102">Метод <xref:System.Runtime.Serialization.Formatters.Binary.BinaryFormatter.Deserialize%2A?displayProperty=nameWithType> теперь заключает некоторые объекты исключений в <xref:System.Runtime.Serialization.SerializationException> перед передачей исключения обратно вызывающему объекту.</span><span class="sxs-lookup"><span data-stu-id="c3da5-102">The <xref:System.Runtime.Serialization.Formatters.Binary.BinaryFormatter.Deserialize%2A?displayProperty=nameWithType> method now rewraps some exception objects inside a <xref:System.Runtime.Serialization.SerializationException> before propagating the exception back to the caller.</span></span>

#### <a name="change-description"></a><span data-ttu-id="c3da5-103">Описание изменений</span><span class="sxs-lookup"><span data-stu-id="c3da5-103">Change description</span></span>

<span data-ttu-id="c3da5-104">Ранее метод <xref:System.Runtime.Serialization.Formatters.Binary.BinaryFormatter.Deserialize%2A?displayProperty=nameWithType> позволял использовать некоторые произвольные исключения, например <xref:System.ArgumentNullException>, для передачи стека соответствующим вызывающим объектам.</span><span class="sxs-lookup"><span data-stu-id="c3da5-104">Previously, the <xref:System.Runtime.Serialization.Formatters.Binary.BinaryFormatter.Deserialize%2A?displayProperty=nameWithType> method allowed some arbitrary exceptions, such as <xref:System.ArgumentNullException>, to propagate up the stack to its callers.</span></span>

<span data-ttu-id="c3da5-105">В .NET 5.0 и более поздних версиях метод <xref:System.Runtime.Serialization.Formatters.Binary.BinaryFormatter.Deserialize%2A?displayProperty=nameWithType> более агрессивно перехватывает исключения, вызываемые из-за недопустимых операций десериализации, и заключает их в <xref:System.Runtime.Serialization.SerializationException>.</span><span class="sxs-lookup"><span data-stu-id="c3da5-105">In .NET 5.0 and later, the <xref:System.Runtime.Serialization.Formatters.Binary.BinaryFormatter.Deserialize%2A?displayProperty=nameWithType> method more aggressively catches exceptions that occur due to invalid deserialization operations and wraps them in a <xref:System.Runtime.Serialization.SerializationException>.</span></span>

#### <a name="version-introduced"></a><span data-ttu-id="c3da5-106">Представленная версия</span><span class="sxs-lookup"><span data-stu-id="c3da5-106">Version introduced</span></span>

<span data-ttu-id="c3da5-107">5.0 Предварительная версия 1</span><span class="sxs-lookup"><span data-stu-id="c3da5-107">5.0 Preview 1</span></span>

#### <a name="recommended-action"></a><span data-ttu-id="c3da5-108">Рекомендованное действие</span><span class="sxs-lookup"><span data-stu-id="c3da5-108">Recommended action</span></span>

<span data-ttu-id="c3da5-109">В большинстве случаев никаких дополнительных действий от вас не требуется.</span><span class="sxs-lookup"><span data-stu-id="c3da5-109">In most cases, you don't need to take any action.</span></span> <span data-ttu-id="c3da5-110">Но если место вызова зависит от конкретного исключения, вы можете исключить его из <xref:System.Runtime.Serialization.SerializationException>, как показано в следующем примере.</span><span class="sxs-lookup"><span data-stu-id="c3da5-110">However, if your call site depends on a particular exception being thrown, you can unwrap the exception from the outer <xref:System.Runtime.Serialization.SerializationException>, as shown in the following example.</span></span>

```csharp
Stream inputStream = GetInputStream();
var formatter = new BinaryFormatter();

try
{
    object deserialized = formatter.Deserialize(inputStream);
}
catch (MyException myEx)
{
    // Handle 'myEx' here in case it was thrown directly.
}
catch (SerializationException serEx) when (serEx.InnerException is MyException myEx)
{
    // Handle 'myEx' here in case it was wrapped in SerializationException.
}
```

#### <a name="category"></a><span data-ttu-id="c3da5-111">Категория</span><span class="sxs-lookup"><span data-stu-id="c3da5-111">Category</span></span>

<span data-ttu-id="c3da5-112">Сериализация</span><span class="sxs-lookup"><span data-stu-id="c3da5-112">Serialization</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="c3da5-113">Затронутые API</span><span class="sxs-lookup"><span data-stu-id="c3da5-113">Affected APIs</span></span>

- <xref:System.Runtime.Serialization.Formatters.Binary.BinaryFormatter.Deserialize%2A?displayProperty=fullName>

<!--

#### Affected APIs

- `Overload:System.Runtime.Serialization.Formatters.Binary.BinaryFormatter.Deserialize`

-->
