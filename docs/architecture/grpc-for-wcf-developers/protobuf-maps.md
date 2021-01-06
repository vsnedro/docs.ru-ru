---
title: Карты protobuf для словарей — gRPC для разработчиков WCF
description: Узнайте, как использовать карты protobuf для представления типов словарей в .NET.
ms.date: 12/15/2020
ms.openlocfilehash: d38270d4bc320cf1f758080c18843ed1d716b350
ms.sourcegitcommit: 655f8a16c488567dfa696fc0b293b34d3c81e3df
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/06/2021
ms.locfileid: "97938550"
---
# <a name="protobuf-maps-for-dictionaries"></a>Карты Protobuf для словарей

Важно иметь возможность представлять произвольные коллекции именованных значений в сообщениях. В .NET это действие обычно обрабатывается с помощью типов словаря. Эквивалентом <xref:System.Collections.Generic.IDictionary%602> типа .NET в буфере протокола (protobuf) является `map<key_type, value_type>` тип. В этом разделе показано, как объявить `map` тип в protobuf и как использовать созданный код.

```protobuf
message StockPrices {
    map<string, double> prices = 1;
}
```

В созданном коде `map` поля представлены свойствами типа, доступные только для чтения [`Google.Protobuf.Collections.MapField<TKey, TValue>`][map-field] . Этот тип реализует стандартные интерфейсы коллекции .NET, включая <xref:System.Collections.Generic.IDictionary%602> .

Поля карт не могут повторяться непосредственно в определении сообщения. Однако можно создать вложенное сообщение, содержащее карту и использовать `repeated` тип сообщения, как показано в следующем примере:

```protobuf
message Order {
    message Attributes {
        map<string, string> values = 1;
    }
    repeated Attributes attributes = 1;
}
```

## <a name="using-mapfield-properties-in-code"></a>Использование свойств Мапфиелд в коде

`MapField`Свойства, созданные из `map` полей, доступны только для чтения и никогда не будут `null` . Чтобы задать свойство Map, используйте `Add(IDictionary<TKey,TValue> values)` метод для свойства Empty, `MapField` чтобы скопировать значения из любого словаря .NET.

```csharp
public Order CreateOrder(Dictionary<string, string> attributes)
{
    var order = new Order();
    order.Attributes.Add(attributes);
    return order;
}
```

## <a name="further-reading"></a>Дополнительные материалы

Дополнительные сведения о protobuf см. в официальной [документации protobuf](https://developers.google.com/protocol-buffers/docs/overview).

[map-field]: https://developers.google.cn/protocol-buffers/docs/reference/csharp/class/google/protobuf/collections/map-field-t-key-t-value-

>[!div class="step-by-step"]
>[Назад](protobuf-enums.md)
>[Вперед](wcf-services-to-grpc-comparison.md)
