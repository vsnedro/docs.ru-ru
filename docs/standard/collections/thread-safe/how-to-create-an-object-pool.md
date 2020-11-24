---
title: Создание пула объектов с помощью класса ConcurrentBag
ms.date: 05/01/2020
dev_langs:
- csharp
- vb
helpviewer_keywords:
- object pool, in .NET Framework
ms.assetid: 0480e7ff-b6f9-480e-a889-2ed4264d8372
ms.openlocfilehash: c593c9b2011814c49563939f1094b62cd252879c
ms.sourcegitcommit: 965a5af7918acb0a3fd3baf342e15d511ef75188
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/18/2020
ms.locfileid: "94822910"
---
# <a name="create-an-object-pool-by-using-a-concurrentbag"></a>Создание пула объектов с помощью класса ConcurrentBag

В этом примере показано, как использовать контейнер <xref:System.Collections.Concurrent.ConcurrentBag%601> для реализации пула объектов. Пулы объектов позволяют улучшить производительность приложения, когда требуется несколько экземпляров класса, которые "дорого" создавать или уничтожать. Когда клиентская программа запрашивает новый объект, сперва происходит поиск в пуле объектов ранее созданного и возвращенного в пул объекта. Новый объект создается, только если в пуле не нашлось нужного объекта.

<xref:System.Collections.Concurrent.ConcurrentBag%601> используется для хранения объектов, так как поддерживает быстрое добавление и удаление, особенно при добавлении и удалении элементов одним потоком. Этот пример можно расширить до построения на основе интерфейса <xref:System.Collections.Concurrent.IProducerConsumerCollection%601>, который реализует структура данных контейнера, например <xref:System.Collections.Concurrent.ConcurrentQueue%601> и <xref:System.Collections.Concurrent.ConcurrentStack%601>.

> [!TIP]
> В этой статье описывается написание собственной реализации пула объектов с базовым параллельным типом для хранения объектов, чтобы их можно было использовать повторно. Однако тип <xref:Microsoft.Extensions.ObjectPool.ObjectPool%601?displayProperty=nameWithType> уже существует в пространстве имен <xref:Microsoft.Extensions.ObjectPool?displayProperty=fullName>. Перед созданием собственной реализации, которая включает множество дополнительных функций, рекомендуется использовать доступный тип.

## <a name="example"></a>Пример

[!code-csharp[CDS#04](../../../../samples/snippets/csharp/VS_Snippets_Misc/cds/cs/objectpool.cs#04)]
[!code-vb[CDS#04](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/cds/vb/objectpool04.vb#04)]

## <a name="see-also"></a>См. также

- [Потокобезопасные коллекции](index.md)
