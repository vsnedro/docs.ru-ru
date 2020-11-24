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
# <a name="create-an-object-pool-by-using-a-concurrentbag"></a><span data-ttu-id="b3f22-102">Создание пула объектов с помощью класса ConcurrentBag</span><span class="sxs-lookup"><span data-stu-id="b3f22-102">Create an object pool by using a ConcurrentBag</span></span>

<span data-ttu-id="b3f22-103">В этом примере показано, как использовать контейнер <xref:System.Collections.Concurrent.ConcurrentBag%601> для реализации пула объектов.</span><span class="sxs-lookup"><span data-stu-id="b3f22-103">This example shows how to use a <xref:System.Collections.Concurrent.ConcurrentBag%601> to implement an object pool.</span></span> <span data-ttu-id="b3f22-104">Пулы объектов позволяют улучшить производительность приложения, когда требуется несколько экземпляров класса, которые "дорого" создавать или уничтожать.</span><span class="sxs-lookup"><span data-stu-id="b3f22-104">Object pools can improve application performance in situations where you require multiple instances of a class and the class is expensive to create or destroy.</span></span> <span data-ttu-id="b3f22-105">Когда клиентская программа запрашивает новый объект, сперва происходит поиск в пуле объектов ранее созданного и возвращенного в пул объекта.</span><span class="sxs-lookup"><span data-stu-id="b3f22-105">When a client program requests a new object, the object pool first attempts to provide one that has already been created and returned to the pool.</span></span> <span data-ttu-id="b3f22-106">Новый объект создается, только если в пуле не нашлось нужного объекта.</span><span class="sxs-lookup"><span data-stu-id="b3f22-106">If none is available, only then is a new object created.</span></span>

<span data-ttu-id="b3f22-107"><xref:System.Collections.Concurrent.ConcurrentBag%601> используется для хранения объектов, так как поддерживает быстрое добавление и удаление, особенно при добавлении и удалении элементов одним потоком.</span><span class="sxs-lookup"><span data-stu-id="b3f22-107">The <xref:System.Collections.Concurrent.ConcurrentBag%601> is used to store the objects because it supports fast insertion and removal, especially when the same thread is both adding and removing items.</span></span> <span data-ttu-id="b3f22-108">Этот пример можно расширить до построения на основе интерфейса <xref:System.Collections.Concurrent.IProducerConsumerCollection%601>, который реализует структура данных контейнера, например <xref:System.Collections.Concurrent.ConcurrentQueue%601> и <xref:System.Collections.Concurrent.ConcurrentStack%601>.</span><span class="sxs-lookup"><span data-stu-id="b3f22-108">This example could be further augmented to be built around a <xref:System.Collections.Concurrent.IProducerConsumerCollection%601>, which the bag data structure implements, as do <xref:System.Collections.Concurrent.ConcurrentQueue%601> and <xref:System.Collections.Concurrent.ConcurrentStack%601>.</span></span>

> [!TIP]
> <span data-ttu-id="b3f22-109">В этой статье описывается написание собственной реализации пула объектов с базовым параллельным типом для хранения объектов, чтобы их можно было использовать повторно.</span><span class="sxs-lookup"><span data-stu-id="b3f22-109">This article defines how to write your own implementation of an object pool with an underlying concurrent type to store objects for reuse.</span></span> <span data-ttu-id="b3f22-110">Однако тип <xref:Microsoft.Extensions.ObjectPool.ObjectPool%601?displayProperty=nameWithType> уже существует в пространстве имен <xref:Microsoft.Extensions.ObjectPool?displayProperty=fullName>.</span><span class="sxs-lookup"><span data-stu-id="b3f22-110">However, the <xref:Microsoft.Extensions.ObjectPool.ObjectPool%601?displayProperty=nameWithType> type already exists under the <xref:Microsoft.Extensions.ObjectPool?displayProperty=fullName> namespace.</span></span> <span data-ttu-id="b3f22-111">Перед созданием собственной реализации, которая включает множество дополнительных функций, рекомендуется использовать доступный тип.</span><span class="sxs-lookup"><span data-stu-id="b3f22-111">Consider using the available type before creating your own implementation, which includes many additional features.</span></span>

## <a name="example"></a><span data-ttu-id="b3f22-112">Пример</span><span class="sxs-lookup"><span data-stu-id="b3f22-112">Example</span></span>

[!code-csharp[CDS#04](../../../../samples/snippets/csharp/VS_Snippets_Misc/cds/cs/objectpool.cs#04)]
[!code-vb[CDS#04](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/cds/vb/objectpool04.vb#04)]

## <a name="see-also"></a><span data-ttu-id="b3f22-113">См. также</span><span class="sxs-lookup"><span data-stu-id="b3f22-113">See also</span></span>

- [<span data-ttu-id="b3f22-114">Потокобезопасные коллекции</span><span class="sxs-lookup"><span data-stu-id="b3f22-114">Thread-Safe Collections</span></span>](index.md)
