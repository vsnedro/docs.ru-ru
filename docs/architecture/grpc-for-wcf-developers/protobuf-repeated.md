---
title: Повторяющиеся поля для списков и массивов — gRPC для разработчиков WCF
description: Узнайте, как protobuf обрабатывает коллекции и как они связаны с коллекциями .NET.
ms.date: 09/09/2019
ms.openlocfilehash: 7320c76ddc58bcf5cd81150923e8cb635e510047
ms.sourcegitcommit: b9122d1af21898eaba81e990c70fef46fef74a8d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/26/2020
ms.locfileid: "88867507"
---
# <a name="repeated-fields-for-lists-and-arrays"></a><span data-ttu-id="4b29a-103">Повторяющиеся поля для списков и массивов</span><span class="sxs-lookup"><span data-stu-id="4b29a-103">Repeated fields for lists and arrays</span></span>

<span data-ttu-id="4b29a-104">Списки в буфере протокола (protobuf) указываются с помощью `repeated` ключевого слова prefix.</span><span class="sxs-lookup"><span data-stu-id="4b29a-104">You specify lists in Protocol Buffer (Protobuf) by using the `repeated` prefix keyword.</span></span> <span data-ttu-id="4b29a-105">В следующем примере показано, как создать список.</span><span class="sxs-lookup"><span data-stu-id="4b29a-105">The following example shows how to create a list:</span></span>

```protobuf
message Person {
    // Other fields elided
    repeated string aliases = 8;
}
```

<span data-ttu-id="4b29a-106">В созданном коде `repeated` поля представлены свойствами типа только для чтения, [`Google.Protobuf.Collections.RepeatedField<T>`][repeated-field] а не любым из встроенных типов коллекций .NET.</span><span class="sxs-lookup"><span data-stu-id="4b29a-106">In the generated code, `repeated` fields are represented by read-only properties of the [`Google.Protobuf.Collections.RepeatedField<T>`][repeated-field] type rather than any of the built-in .NET collection types.</span></span> <span data-ttu-id="4b29a-107">Этот тип реализует все стандартные интерфейсы коллекции .NET, такие как <xref:System.Collections.Generic.IList%601> и <xref:System.Collections.Generic.IEnumerable%601> .</span><span class="sxs-lookup"><span data-stu-id="4b29a-107">This type implements all the standard .NET collection interfaces, such as <xref:System.Collections.Generic.IList%601> and <xref:System.Collections.Generic.IEnumerable%601>.</span></span> <span data-ttu-id="4b29a-108">Поэтому можно легко использовать запросы LINQ или преобразовать их в массив или список.</span><span class="sxs-lookup"><span data-stu-id="4b29a-108">So you can use LINQ queries or convert it to an array or a list easily.</span></span>

<span data-ttu-id="4b29a-109">`RepeatedField<T>`Тип включает код, необходимый для сериализации и десериализации списка в двоичный формат сети.</span><span class="sxs-lookup"><span data-stu-id="4b29a-109">The `RepeatedField<T>` type includes the code required to serialize and deserialize the list to the binary wire format.</span></span>

[repeated-field]: https://developers.google.cn/protocol-buffers/docs/reference/csharp/class/google/protobuf/collections/repeated-field-t-

>[!div class="step-by-step"]
><span data-ttu-id="4b29a-110">[Назад](protobuf-nested-types.md)
>[Вперед](protobuf-reserved.md)</span><span class="sxs-lookup"><span data-stu-id="4b29a-110">[Previous](protobuf-nested-types.md)
[Next](protobuf-reserved.md)</span></span>
