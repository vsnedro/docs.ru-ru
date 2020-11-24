---
title: Практическое руководство. Создание конструктора копий (руководство по программированию на C#)
description: Узнайте, как создать конструктор копий в C#, который принимает экземпляр класса и возвращает новый экземпляр со значениями входных данных.
ms.date: 07/20/2015
helpviewer_keywords:
- C# Language, copy constructor
- copy constructor [C#]
ms.topic: how-to
ms.custom: contperfq2
ms.assetid: fba899b5-fc41-428e-a745-3ebdbf37990a
ms.openlocfilehash: 85899d2de05312be921199387cc1155fa8e9d2f1
ms.sourcegitcommit: 30e9e11dfd90112b8eec6406186ba3533f21eba1
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2020
ms.locfileid: "95098987"
---
# <a name="how-to-write-a-copy-constructor-c-programming-guide"></a><span data-ttu-id="7eb8e-103">Практическое руководство. Создание конструктора копий (руководство по программированию на C#)</span><span class="sxs-lookup"><span data-stu-id="7eb8e-103">How to write a copy constructor (C# Programming Guide)</span></span>

<span data-ttu-id="7eb8e-104">В C# не предусмотрен конструктор копии для объектов, однако его можно написать самостоятельно.</span><span class="sxs-lookup"><span data-stu-id="7eb8e-104">C# doesn't provide a copy constructor for objects, but you can write one yourself.</span></span>  
  
## <a name="example"></a><span data-ttu-id="7eb8e-105">Пример</span><span class="sxs-lookup"><span data-stu-id="7eb8e-105">Example</span></span>  

 <span data-ttu-id="7eb8e-106">В следующем примере [класс](../../language-reference/keywords/class.md)`Person` определяет конструктор копии, который использует экземпляр `Person`в качестве аргумента.</span><span class="sxs-lookup"><span data-stu-id="7eb8e-106">In the following example, the `Person`[class](../../language-reference/keywords/class.md) defines a copy constructor that takes, as its argument, an instance of `Person`.</span></span> <span data-ttu-id="7eb8e-107">Значения свойств аргумента присваиваются свойствам нового экземпляра `Person`.</span><span class="sxs-lookup"><span data-stu-id="7eb8e-107">The values of the properties of the argument are assigned to the properties of the new instance of `Person`.</span></span> <span data-ttu-id="7eb8e-108">Код содержит дополнительный конструктор копии, который отправляет свойства `Name` и `Age` экземпляра, который необходимо скопировать конструктору экземпляра класса.</span><span class="sxs-lookup"><span data-stu-id="7eb8e-108">The code contains an alternative copy constructor that sends the `Name` and `Age` properties of the instance that you want to copy to the instance constructor of the class.</span></span>  
  
 [!code-csharp[csProgGuideObjects#16](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideObjects/CS/Objects.cs#16)]  
  
## <a name="see-also"></a><span data-ttu-id="7eb8e-109">См. также</span><span class="sxs-lookup"><span data-stu-id="7eb8e-109">See also</span></span>

- <xref:System.ICloneable>
- [<span data-ttu-id="7eb8e-110">Руководство по программированию на C#</span><span class="sxs-lookup"><span data-stu-id="7eb8e-110">C# Programming Guide</span></span>](../index.md)
- [<span data-ttu-id="7eb8e-111">Классы и структуры</span><span class="sxs-lookup"><span data-stu-id="7eb8e-111">Classes and Structs</span></span>](./index.md)
- [<span data-ttu-id="7eb8e-112">Конструкторы</span><span class="sxs-lookup"><span data-stu-id="7eb8e-112">Constructors</span></span>](./constructors.md)
- [<span data-ttu-id="7eb8e-113">Методы завершения</span><span class="sxs-lookup"><span data-stu-id="7eb8e-113">Finalizers</span></span>](./destructors.md)
