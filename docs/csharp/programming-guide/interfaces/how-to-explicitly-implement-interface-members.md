---
title: Руководство по программированию на C#. Явная реализация элементов интерфейса
description: Сведения о явной реализации элементов интерфейса при программировании на C#. Доступ к членам осуществляется посредством экземпляра интерфейса.
ms.date: 07/20/2015
helpviewer_keywords:
- interfaces [C#], explicitly implementing
ms.assetid: 514cde76-f981-474e-8b40-9493619f899c
ms.openlocfilehash: 35b512ff6cbee1dd942f5b3476db660481808297
ms.sourcegitcommit: 6f58a5f75ceeb936f8ee5b786e9adb81a9a3bee9
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/28/2020
ms.locfileid: "87303079"
---
# <a name="how-to-explicitly-implement-interface-members-c-programming-guide"></a><span data-ttu-id="91e75-104">Руководство по программированию на C#. Явная реализация элементов интерфейса</span><span class="sxs-lookup"><span data-stu-id="91e75-104">How to explicitly implement interface members (C# Programming Guide)</span></span>
<span data-ttu-id="91e75-105">В этом примере объявляются [интерфейс](../../language-reference/keywords/interface.md)`IDimensions` и класс `Box`, который явно реализует члены интерфейса `GetLength` и `GetWidth`.</span><span class="sxs-lookup"><span data-stu-id="91e75-105">This example declares an [interface](../../language-reference/keywords/interface.md), `IDimensions`, and a class, `Box`, which explicitly implements the interface members `GetLength` and `GetWidth`.</span></span> <span data-ttu-id="91e75-106">Доступ к членам осуществляется посредством экземпляра интерфейса `dimensions`.</span><span class="sxs-lookup"><span data-stu-id="91e75-106">The members are accessed through the interface instance `dimensions`.</span></span>  
  
## <a name="example"></a><span data-ttu-id="91e75-107">Пример</span><span class="sxs-lookup"><span data-stu-id="91e75-107">Example</span></span>  
 [!code-csharp[csProgGuideInheritance#8](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideInheritance/CS/Inheritance.cs#8)]  
  
## <a name="robust-programming"></a><span data-ttu-id="91e75-108">Отказоустойчивость</span><span class="sxs-lookup"><span data-stu-id="91e75-108">Robust Programming</span></span>  
  
- <span data-ttu-id="91e75-109">Обратите внимание, что следующие строки в методе `Main` закомментированы, поскольку при их компиляции возникнут ошибки.</span><span class="sxs-lookup"><span data-stu-id="91e75-109">Notice that the following lines, in the `Main` method, are commented out because they would produce compilation errors.</span></span> <span data-ttu-id="91e75-110">Член интерфейса, реализованный явным образом, недоступен из экземпляра [класса](../../language-reference/keywords/class.md):</span><span class="sxs-lookup"><span data-stu-id="91e75-110">An interface member that is explicitly implemented cannot be accessed from a [class](../../language-reference/keywords/class.md) instance:</span></span>  
  
     [!code-csharp[csProgGuideInheritance#45](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideInheritance/CS/Inheritance.cs#45)]  
  
- <span data-ttu-id="91e75-111">Также обратите внимание, что следующие строки в методе `Main` успешно выводят на печать размеры поля, поскольку методы вызываются из экземпляра интерфейса:</span><span class="sxs-lookup"><span data-stu-id="91e75-111">Notice also that the following lines, in the `Main` method, successfully print out the dimensions of the box because the methods are being called from an instance of the interface:</span></span>  
  
     [!code-csharp[csProgGuideInheritance#46](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideInheritance/CS/Inheritance.cs#46)]  
  
## <a name="see-also"></a><span data-ttu-id="91e75-112">См. также</span><span class="sxs-lookup"><span data-stu-id="91e75-112">See also</span></span>

- [<span data-ttu-id="91e75-113">Руководство по программированию на C#</span><span class="sxs-lookup"><span data-stu-id="91e75-113">C# Programming Guide</span></span>](../index.md)
- [<span data-ttu-id="91e75-114">Классы и структуры</span><span class="sxs-lookup"><span data-stu-id="91e75-114">Classes and Structs</span></span>](../classes-and-structs/index.md)
- [<span data-ttu-id="91e75-115">Интерфейсы</span><span class="sxs-lookup"><span data-stu-id="91e75-115">Interfaces</span></span>](./index.md)
- [<span data-ttu-id="91e75-116">Практическое руководство. Явная реализация членов двух интерфейсов</span><span class="sxs-lookup"><span data-stu-id="91e75-116">How to explicitly implement members of two interfaces</span></span>](./how-to-explicitly-implement-members-of-two-interfaces.md)
