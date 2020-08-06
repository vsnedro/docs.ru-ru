---
title: Руководство по программированию на C#. Индексаторы в интерфейсах
description: В C# можно объявлять индексаторы для интерфейса. Узнайте, чем методы доступа индексаторов интерфейса отличаются от методов доступа индексаторов класса.
ms.date: 02/08/2020
helpviewer_keywords:
- indexers [C#], in interfaces
- accessors [C#], indexers
ms.assetid: e16b54bd-4a83-4f52-bd75-65819fca79e8
ms.openlocfilehash: ec77843bdf3181a543bd6c02cfb034b21ded1ae7
ms.sourcegitcommit: 6f58a5f75ceeb936f8ee5b786e9adb81a9a3bee9
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/28/2020
ms.locfileid: "87303105"
---
# <a name="indexers-in-interfaces-c-programming-guide"></a><span data-ttu-id="9a039-104">Индексаторы в интерфейсах (Руководство по программированию в C#)</span><span class="sxs-lookup"><span data-stu-id="9a039-104">Indexers in Interfaces (C# Programming Guide)</span></span>

<span data-ttu-id="9a039-105">Индексаторы можно объявлять для [интерфейса](../../language-reference/keywords/interface.md).</span><span class="sxs-lookup"><span data-stu-id="9a039-105">Indexers can be declared on an [interface](../../language-reference/keywords/interface.md).</span></span> <span data-ttu-id="9a039-106">Методы доступа индексаторов интерфейса отличаются от методов доступа индексаторов [класса](../../language-reference/keywords/class.md) следующим образом:</span><span class="sxs-lookup"><span data-stu-id="9a039-106">Accessors of interface indexers differ from the accessors of [class](../../language-reference/keywords/class.md) indexers in the following ways:</span></span>

- <span data-ttu-id="9a039-107">Методы доступа интерфейса не используют модификаторы.</span><span class="sxs-lookup"><span data-stu-id="9a039-107">Interface accessors do not use modifiers.</span></span>
- <span data-ttu-id="9a039-108">Метод доступа интерфейса обычно не имеет тела.</span><span class="sxs-lookup"><span data-stu-id="9a039-108">An interface accessor typically does not have a body.</span></span>

<span data-ttu-id="9a039-109">Методы доступа нужны, чтобы указать, доступен ли индексатор для чтения и записи, только для чтения или только для записи.</span><span class="sxs-lookup"><span data-stu-id="9a039-109">The purpose of the accessor is to indicate whether the indexer is read-write, read-only, or write-only.</span></span> <span data-ttu-id="9a039-110">Вы можете предоставить реализацию для индексатора, определенного в интерфейсе, но это случается редко.</span><span class="sxs-lookup"><span data-stu-id="9a039-110">You may provide an implementation for an indexer defined in an interface, but this is rare.</span></span> <span data-ttu-id="9a039-111">Индексаторы обычно определяют API для доступа к полям данных, а поля данных не могут быть определены в интерфейсе.</span><span class="sxs-lookup"><span data-stu-id="9a039-111">Indexers typically define an API to access data fields, and data fields cannot be defined in an interface.</span></span>

<span data-ttu-id="9a039-112">Ниже показан пример метода доступа индексатора для интерфейса:</span><span class="sxs-lookup"><span data-stu-id="9a039-112">The following is an example of an interface indexer accessor:</span></span>

[!code-csharp[DefineInterface](~/samples/snippets/csharp/interfaces/indexers.cs#DefineIndexer)]

<span data-ttu-id="9a039-113">Сигнатура индексатора должна отличаться от сигнатур любых других индексаторов, объявленных в том же интерфейсе.</span><span class="sxs-lookup"><span data-stu-id="9a039-113">The signature of an indexer must differ from the signatures of all other indexers declared in the same interface.</span></span>

## <a name="example"></a><span data-ttu-id="9a039-114">Пример</span><span class="sxs-lookup"><span data-stu-id="9a039-114">Example</span></span>

<span data-ttu-id="9a039-115">Следующий пример демонстрирует реализацию индексаторов интерфейса.</span><span class="sxs-lookup"><span data-stu-id="9a039-115">The following example shows how to implement interface indexers.</span></span>

[!code-csharp[Implement](~/samples/snippets/csharp/interfaces/indexers.cs#ImplementInterface)]

[!code-csharp[DefineInterface](~/samples/snippets/csharp/interfaces/indexers.cs#ExampleCode)]

<span data-ttu-id="9a039-116">В приведенном выше примере можно использовать явную реализацию члена интерфейса с помощью полного имени члена интерфейса.</span><span class="sxs-lookup"><span data-stu-id="9a039-116">In the preceding example, you could use the explicit interface member implementation by using the fully qualified name of the interface member.</span></span> <span data-ttu-id="9a039-117">Пример</span><span class="sxs-lookup"><span data-stu-id="9a039-117">For example</span></span>

```csharp
string IIndexInterface.this[int index]
{
}
```

<span data-ttu-id="9a039-118">Тем не менее полное имя требуется только в целях устранения неоднозначности, если класс реализует более одного интерфейса с одинаковой сигнатурой индексатора.</span><span class="sxs-lookup"><span data-stu-id="9a039-118">However, the fully qualified name is only needed to avoid ambiguity when the class is implementing more than one interface with the same indexer signature.</span></span> <span data-ttu-id="9a039-119">Например, если класс `Employee` реализует два интерфейса (`ICitizen` и `IEmployee`), оба из которых имеют одинаковую сигнатуру индексатора, требуется явная реализация члена интерфейса.</span><span class="sxs-lookup"><span data-stu-id="9a039-119">For example, if an `Employee` class is implementing two interfaces, `ICitizen` and `IEmployee`, and both interfaces have the same indexer signature, the explicit interface member implementation is necessary.</span></span> <span data-ttu-id="9a039-120">Это значит, что потребуется следующее объявление индексатора:</span><span class="sxs-lookup"><span data-stu-id="9a039-120">That is, the following indexer declaration:</span></span>

```csharp
string IEmployee.this[int index]
{
}
```

<span data-ttu-id="9a039-121">реализует индексатор в интерфейсе `IEmployee`, тогда как следующее объявление:</span><span class="sxs-lookup"><span data-stu-id="9a039-121">implements the indexer on the `IEmployee` interface, while the following declaration:</span></span>

```csharp
string ICitizen.this[int index]
{
}
```

<span data-ttu-id="9a039-122">реализует индексатор в интерфейсе `ICitizen`.</span><span class="sxs-lookup"><span data-stu-id="9a039-122">implements the indexer on the `ICitizen` interface.</span></span>

## <a name="see-also"></a><span data-ttu-id="9a039-123">См. также</span><span class="sxs-lookup"><span data-stu-id="9a039-123">See also</span></span>

- [<span data-ttu-id="9a039-124">Руководство по программированию на C#</span><span class="sxs-lookup"><span data-stu-id="9a039-124">C# Programming Guide</span></span>](../index.md)
- [<span data-ttu-id="9a039-125">Индексаторы</span><span class="sxs-lookup"><span data-stu-id="9a039-125">Indexers</span></span>](./index.md)
- [<span data-ttu-id="9a039-126">Свойства</span><span class="sxs-lookup"><span data-stu-id="9a039-126">Properties</span></span>](../classes-and-structs/properties.md)
- [<span data-ttu-id="9a039-127">Интерфейсы</span><span class="sxs-lookup"><span data-stu-id="9a039-127">Interfaces</span></span>](../interfaces/index.md)
