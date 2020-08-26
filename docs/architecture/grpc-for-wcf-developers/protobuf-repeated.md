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
# <a name="repeated-fields-for-lists-and-arrays"></a>Повторяющиеся поля для списков и массивов

Списки в буфере протокола (protobuf) указываются с помощью `repeated` ключевого слова prefix. В следующем примере показано, как создать список.

```protobuf
message Person {
    // Other fields elided
    repeated string aliases = 8;
}
```

В созданном коде `repeated` поля представлены свойствами типа только для чтения, [`Google.Protobuf.Collections.RepeatedField<T>`][repeated-field] а не любым из встроенных типов коллекций .NET. Этот тип реализует все стандартные интерфейсы коллекции .NET, такие как <xref:System.Collections.Generic.IList%601> и <xref:System.Collections.Generic.IEnumerable%601> . Поэтому можно легко использовать запросы LINQ или преобразовать их в массив или список.

`RepeatedField<T>`Тип включает код, необходимый для сериализации и десериализации списка в двоичный формат сети.

[repeated-field]: https://developers.google.cn/protocol-buffers/docs/reference/csharp/class/google/protobuf/collections/repeated-field-t-

>[!div class="step-by-step"]
>[Назад](protobuf-nested-types.md)
>[Вперед](protobuf-reserved.md)
