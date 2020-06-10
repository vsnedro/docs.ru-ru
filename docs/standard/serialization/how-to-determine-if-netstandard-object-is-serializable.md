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
ms.openlocfilehash: b6791ae0666aeb0ac02d8a38ca419d7de2b263cf
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/06/2020
ms.locfileid: "84289607"
---
# <a name="how-to-determine-if-a-net-standard-object-is-serializable"></a><span data-ttu-id="1f32b-103">Как определить сериализуемость объекта .NET Standard</span><span class="sxs-lookup"><span data-stu-id="1f32b-103">How to determine if a .NET Standard object is serializable</span></span>

<span data-ttu-id="1f32b-104">.NET Standard — это спецификация, определяющая типы и элементы, которые должны присутствовать в конкретных реализациях .NET, соответствующих этой версии стандарта.</span><span class="sxs-lookup"><span data-stu-id="1f32b-104">The .NET Standard is a specification that defines the types and members that must be present on specific .NET implementations that conform to that version of the standard.</span></span> <span data-ttu-id="1f32b-105">Однако .NET Standard не определяет, является ли тип сериализуемым.</span><span class="sxs-lookup"><span data-stu-id="1f32b-105">However, the .NET Standard does not define whether a type is serializable.</span></span> <span data-ttu-id="1f32b-106">Типы, определенные в библиотеке .NET Standard, не помечаются атрибутом <xref:System.SerializableAttribute>.</span><span class="sxs-lookup"><span data-stu-id="1f32b-106">The types defined in the .NET Standard Library are not marked with the <xref:System.SerializableAttribute> attribute.</span></span> <span data-ttu-id="1f32b-107">Но вместо этого некоторые реализации .NET, например .NET Framework и .NET Core, могут беспрепятственно определять, является ли конкретный тип сериализуемым.</span><span class="sxs-lookup"><span data-stu-id="1f32b-107">Instead, specific .NET implementations, such as the .NET Framework and .NET Core, are free to determine whether a particular type is serializable.</span></span>

<span data-ttu-id="1f32b-108">Если вы разработали библиотеку, предназначенную для .NET Standard, ваша библиотека может использоваться в любой реализации .NET, поддерживающей .NET Standard.</span><span class="sxs-lookup"><span data-stu-id="1f32b-108">If you've developed a library that targets the .NET Standard, your library can be consumed by any .NET implementation that supports the .NET Standard.</span></span> <span data-ttu-id="1f32b-109">Это означает, что вы не можете заранее знать, является ли конкретный тип сериализуемым. Вы сможете определить, является ли он сериализуемым, только во время выполнения.</span><span class="sxs-lookup"><span data-stu-id="1f32b-109">This means that you cannot know in advance whether a particular type is serializable; you can only determine whether it is serializable at run time.</span></span>

<span data-ttu-id="1f32b-110">Чтобы во время выполнения определить, является ли объект сериализуемым, получите значение свойства <xref:System.Type.IsSerializable> объекта <xref:System.Type>, который представляет тип этого объекта.</span><span class="sxs-lookup"><span data-stu-id="1f32b-110">You can determine whether an object is serializable at run time by retrieving the value of the <xref:System.Type.IsSerializable> property of a <xref:System.Type> object that represents that object's type.</span></span> <span data-ttu-id="1f32b-111">В следующем примере показано, как это делается.</span><span class="sxs-lookup"><span data-stu-id="1f32b-111">The following example provides one implementation.</span></span> <span data-ttu-id="1f32b-112">Определяется метод расширения `IsSerializable(Object)`, который указывает, может ли быть сериализован любой экземпляр <xref:System.Object>.</span><span class="sxs-lookup"><span data-stu-id="1f32b-112">It defines an `IsSerializable(Object)` extension method that indicates whether any <xref:System.Object> instance can be serialized.</span></span>

[!code-csharp[is-a-type-serializable](~/samples/snippets/standard/serialization/is-serializable/csharp/program.cs#2)]
[!code-vb[is-a-type-serializable](~/samples/snippets/standard/serialization/is-serializable/vb/library.vb#2)]

<span data-ttu-id="1f32b-113">Затем в этот метод можно передать любой объект, чтобы определить, можно ли его сериализовать и десериализовать в текущей реализации .NET, как показано в следующем примере:</span><span class="sxs-lookup"><span data-stu-id="1f32b-113">You can then pass any object to the method to determine whether it can be serialized and deserialized on the current .NET implementation, as the following example shows:</span></span>

[!code-csharp[test-is-a-type-serializable](~/samples/snippets/standard/serialization/is-serializable/csharp/program.cs#1)]
[!code-vb[test-is-a-type-serializable](~/samples/snippets/standard/serialization/is-serializable/vb/program.vb#1)]

## <a name="see-also"></a><span data-ttu-id="1f32b-114">См. также</span><span class="sxs-lookup"><span data-stu-id="1f32b-114">See also</span></span>

- [<span data-ttu-id="1f32b-115">Двоичная сериализация</span><span class="sxs-lookup"><span data-stu-id="1f32b-115">Binary serialization</span></span>](binary-serialization.md)
- <xref:System.SerializableAttribute?displayProperty=nameWithType>
- <xref:System.Type.IsSerializable?displayProperty=nameWithType>
