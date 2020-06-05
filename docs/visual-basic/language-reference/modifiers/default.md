---
title: Значение по умолчанию
ms.date: 07/20/2015
f1_keywords:
- vb.Default
helpviewer_keywords:
- defaults, properties
- properties [Visual Basic], default
- default properties, in Visual Basic
- Default keyword [Visual Basic]
- default properties
ms.assetid: 45fce9b9-d212-4b2d-ab86-6e359b8b57af
ms.openlocfilehash: 0c2808795d6fcbad7892369fd7f460ebf0406093
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/04/2020
ms.locfileid: "84372976"
---
# <a name="default-visual-basic"></a><span data-ttu-id="160a3-102">Default (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="160a3-102">Default (Visual Basic)</span></span>
<span data-ttu-id="160a3-103">Определяет свойство как свойство по умолчанию для класса, структуры или интерфейса.</span><span class="sxs-lookup"><span data-stu-id="160a3-103">Identifies a property as the default property of its class, structure, or interface.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="160a3-104">Комментарии</span><span class="sxs-lookup"><span data-stu-id="160a3-104">Remarks</span></span>  
 <span data-ttu-id="160a3-105">Класс, структура или интерфейс могут обозначать не более одного из своих свойств как *свойство по умолчанию*, если это свойство принимает по крайней мере один параметр.</span><span class="sxs-lookup"><span data-stu-id="160a3-105">A class, structure, or interface can designate at most one of its properties as the *default property*, provided that property takes at least one parameter.</span></span> <span data-ttu-id="160a3-106">Если код создает ссылку на класс или структуру без указания члена, Visual Basic разрешает эту ссылку на свойство по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="160a3-106">If code makes a reference to a class or structure without specifying a member, Visual Basic resolves that reference to the default property.</span></span>  
  
 <span data-ttu-id="160a3-107">Свойства по умолчанию могут привести к небольшому сокращению количества символов в исходном коде, но они могут усложнить чтение кода.</span><span class="sxs-lookup"><span data-stu-id="160a3-107">Default properties can result in a small reduction in source code-characters, but they can make your code more difficult to read.</span></span> <span data-ttu-id="160a3-108">Если вызывающий код не знаком с классом или структурой, то при создании ссылки на имя класса или структуры он не может определить, обращается ли эта ссылка к самому классу или структуре, или к свойству по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="160a3-108">If the calling code is not familiar with your class or structure, when it makes a reference to the class or structure name it cannot be certain whether that reference accesses the class or structure itself, or a default property.</span></span> <span data-ttu-id="160a3-109">Это может привести к ошибкам компилятора или незначительным логическим ошибкам времени выполнения.</span><span class="sxs-lookup"><span data-stu-id="160a3-109">This can lead to compiler errors or subtle run-time logic errors.</span></span>  
  
 <span data-ttu-id="160a3-110">Можно немного уменьшить вероятность ошибок свойств по умолчанию, всегда используя [оператор Option строго](../statements/option-strict-statement.md) , чтобы задать для проверки типа компилятора значение `On` .</span><span class="sxs-lookup"><span data-stu-id="160a3-110">You can somewhat reduce the chance of default property errors by always using the [Option Strict Statement](../statements/option-strict-statement.md) to set compiler type checking to `On`.</span></span>  
  
 <span data-ttu-id="160a3-111">Если вы планируете использовать в коде предопределенный класс или структуру, необходимо определить, имеет ли он свойство по умолчанию, и, если да, то, какое имя имеет значение.</span><span class="sxs-lookup"><span data-stu-id="160a3-111">If you are planning to use a predefined class or structure in your code, you must determine whether it has a default property, and if so, what its name is.</span></span>  
  
 <span data-ttu-id="160a3-112">Из-за этих недостатков рекомендуется не определять свойства по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="160a3-112">Because of these disadvantages, you should consider not defining default properties.</span></span> <span data-ttu-id="160a3-113">Для удобочитаемости кода следует также рассмотреть возможность явной ссылки на все свойства, даже свойства по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="160a3-113">For code readability, you should also consider always referring to all properties explicitly, even default properties.</span></span>  
  
 <span data-ttu-id="160a3-114">`Default`Модификатор можно использовать в этом контексте:</span><span class="sxs-lookup"><span data-stu-id="160a3-114">The `Default` modifier can be used in this context:</span></span>  
  
 [<span data-ttu-id="160a3-115">Property Statement</span><span class="sxs-lookup"><span data-stu-id="160a3-115">Property Statement</span></span>](../statements/property-statement.md)  
  
## <a name="see-also"></a><span data-ttu-id="160a3-116">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="160a3-116">See also</span></span>

- [<span data-ttu-id="160a3-117">Практическое руководство. Объявление и вызов свойства по умолчанию в Visual Basic</span><span class="sxs-lookup"><span data-stu-id="160a3-117">How to: Declare and Call a Default Property in Visual Basic</span></span>](../../programming-guide/language-features/procedures/how-to-declare-and-call-a-default-property.md)
- [<span data-ttu-id="160a3-118">Ключевые слова</span><span class="sxs-lookup"><span data-stu-id="160a3-118">Keywords</span></span>](../keywords/index.md)
