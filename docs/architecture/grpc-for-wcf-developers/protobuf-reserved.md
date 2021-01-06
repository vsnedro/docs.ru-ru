---
title: Зарезервированные поля protobuf — gRPC для разработчиков WCF
description: Сведения о зарезервированных полях для обеспечения совместимости между версиями.
ms.date: 12/15/2020
ms.openlocfilehash: d82043d619c5b3b81091ae4ea381e4778c1cf6ba
ms.sourcegitcommit: 655f8a16c488567dfa696fc0b293b34d3c81e3df
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/06/2021
ms.locfileid: "97938524"
---
# <a name="protobuf-reserved-fields"></a>Зарезервированные поля Protobuf

Гарантии обратной совместимости в буфере протокола (protobuf) полагаются на номера полей, которые всегда представляют один и тот же элемент данных. Если поле удаляется из сообщения в новой версии службы, этот номер поля никогда не следует использовать повторно. Это поведение можно применить с помощью `reserved` ключевого слова.

Если `displayName` поля и `marketId` были удалены из `Stock` сообщения, определенного ранее, их номера полей должны быть зарезервированы, как показано в следующем примере.

```protobuf
syntax "proto3";

message Stock {

    reserved 3, 4;
    int32 id = 1;
    string symbol = 2;

}
```

Также можно использовать `reserved` ключевое слово в качестве заполнителя для полей, которые могут быть добавлены в будущем. Можно выразить смежные номера полей как диапазон с помощью `to` ключевого слова.

```protobuf
syntax "proto3";

message Info {

    reserved 2, 9 to 11, 15;
    // ...
}
```

>[!div class="step-by-step"]
>[Назад](protobuf-repeated.md)
>[Вперед](protobuf-any-oneof.md)
