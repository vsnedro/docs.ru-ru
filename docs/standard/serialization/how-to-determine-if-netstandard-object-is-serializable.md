---
title: Как определить сериализуемость объекта .NET Standard
description: Показывается, как определить, может ли тип .NET Standard быть сериализован во время выполнения.
ms.date: 10/20/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- serializing objects
- objects, serializing steps
ms.openlocfilehash: 9f7ab8a824b9687f68382a5edc342536289c5d09
ms.sourcegitcommit: 74d05613d6c57106f83f82ce8ee71176874ea3f0
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/03/2020
ms.locfileid: "93282320"
---
# <a name="how-to-determine-if-a-net-standard-object-is-serializable"></a><span data-ttu-id="d8db7-103">Как определить сериализуемость объекта .NET Standard</span><span class="sxs-lookup"><span data-stu-id="d8db7-103">How to determine if a .NET Standard object is serializable</span></span>

<span data-ttu-id="d8db7-104">.NET Standard — это спецификация, определяющая типы и элементы, которые должны присутствовать в конкретных реализациях .NET, соответствующих этой версии стандарта.</span><span class="sxs-lookup"><span data-stu-id="d8db7-104">.NET Standard is a specification that defines the types and members that must be present on specific .NET implementations that conform to that version of the standard.</span></span> <span data-ttu-id="d8db7-105">Однако .NET Standard не определяет, является ли тип сериализуемым.</span><span class="sxs-lookup"><span data-stu-id="d8db7-105">However, .NET Standard does not define whether a type is serializable.</span></span> <span data-ttu-id="d8db7-106">Типы, определенные в библиотеке .NET Standard, не помечаются атрибутом <xref:System.SerializableAttribute>.</span><span class="sxs-lookup"><span data-stu-id="d8db7-106">The types defined in the .NET Standard Library are not marked with the <xref:System.SerializableAttribute> attribute.</span></span> <span data-ttu-id="d8db7-107">Но вместо этого некоторые реализации .NET, например .NET Framework и .NET Core, могут легко определять, является ли конкретный тип сериализуемым.</span><span class="sxs-lookup"><span data-stu-id="d8db7-107">Instead, specific .NET implementations, such as .NET Framework and .NET Core, are free to determine whether a particular type is serializable.</span></span>

<span data-ttu-id="d8db7-108">Если вы разработали библиотеку, предназначенную для .NET Standard, ваша библиотека может использоваться в любой реализации .NET, поддерживающей .NET Standard.</span><span class="sxs-lookup"><span data-stu-id="d8db7-108">If you've developed a library that targets .NET Standard, your library can be consumed by any .NET implementation that supports .NET Standard.</span></span> <span data-ttu-id="d8db7-109">Это означает, что вы не можете заранее знать, является ли конкретный тип сериализуемым. Вы сможете определить, является ли он сериализуемым, только во время выполнения.</span><span class="sxs-lookup"><span data-stu-id="d8db7-109">This means that you cannot know in advance whether a particular type is serializable; you can only determine whether it is serializable at run time.</span></span>

<span data-ttu-id="d8db7-110">Чтобы во время выполнения определить, является ли объект сериализуемым, получите значение свойства <xref:System.Type.IsSerializable> объекта <xref:System.Type>, который представляет тип этого объекта.</span><span class="sxs-lookup"><span data-stu-id="d8db7-110">You can determine whether an object is serializable at run time by retrieving the value of the <xref:System.Type.IsSerializable> property of a <xref:System.Type> object that represents that object's type.</span></span> <span data-ttu-id="d8db7-111">В следующем примере показано, как это делается.</span><span class="sxs-lookup"><span data-stu-id="d8db7-111">The following example provides one implementation.</span></span> <span data-ttu-id="d8db7-112">Определяется метод расширения `IsSerializable(Object)`, который указывает, может ли быть сериализован любой экземпляр <xref:System.Object>.</span><span class="sxs-lookup"><span data-stu-id="d8db7-112">It defines an `IsSerializable(Object)` extension method that indicates whether any <xref:System.Object> instance can be serialized.</span></span>

[!code-csharp[is-a-type-serializable](~/samples/snippets/standard/serialization/is-serializable/csharp/program.cs#2)]
[!code-vb[is-a-type-serializable](~/samples/snippets/standard/serialization/is-serializable/vb/library.vb#2)]

<span data-ttu-id="d8db7-113">Затем в этот метод можно передать любой объект, чтобы определить, можно ли его сериализовать и десериализовать в текущей реализации .NET, как показано в следующем примере:</span><span class="sxs-lookup"><span data-stu-id="d8db7-113">You can then pass any object to the method to determine whether it can be serialized and deserialized on the current .NET implementation, as the following example shows:</span></span>

[!code-csharp[test-is-a-type-serializable](~/samples/snippets/standard/serialization/is-serializable/csharp/program.cs#1)]
[!code-vb[test-is-a-type-serializable](~/samples/snippets/standard/serialization/is-serializable/vb/program.vb#1)]

## <a name="see-also"></a><span data-ttu-id="d8db7-114">См. также</span><span class="sxs-lookup"><span data-stu-id="d8db7-114">See also</span></span>

- [<span data-ttu-id="d8db7-115">Двоичная сериализация</span><span class="sxs-lookup"><span data-stu-id="d8db7-115">Binary serialization</span></span>](binary-serialization.md)
- <xref:System.SerializableAttribute?displayProperty=nameWithType>
- <xref:System.Type.IsSerializable?displayProperty=nameWithType>
