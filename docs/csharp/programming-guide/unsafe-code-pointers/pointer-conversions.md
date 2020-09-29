---
title: Руководство по программированию на C#. Преобразования указателей
description: Сведения о преобразованиях указателей. Просмотрите таблицы явных и неявных преобразований указателей и примеры кода, а также ознакомьтесь с дополнительными ресурсами.
ms.date: 07/20/2015
helpviewer_keywords:
- pointers [C#], conversions
ms.assetid: f0e87502-477a-4ede-a31f-7a3e262e46fb
ms.openlocfilehash: 7a37c4e9f6333c00c7842df0fdaf353df516974d
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/24/2020
ms.locfileid: "91205078"
---
# <a name="pointer-conversions-c-programming-guide"></a><span data-ttu-id="b8924-104">Преобразования указателей (Руководство по программированию на C#)</span><span class="sxs-lookup"><span data-stu-id="b8924-104">Pointer Conversions (C# Programming Guide)</span></span>

<span data-ttu-id="b8924-105">В следующей таблице приведены предопределенные неявные преобразования указателей.</span><span class="sxs-lookup"><span data-stu-id="b8924-105">The following table shows the predefined implicit pointer conversions.</span></span> <span data-ttu-id="b8924-106">Неявные преобразования могут выполняться во многих ситуациях, включая вызов методов и операторы назначения.</span><span class="sxs-lookup"><span data-stu-id="b8924-106">Implicit conversions might occur in many situations, including method invoking and assignment statements.</span></span>  
  
## <a name="implicit-pointer-conversions"></a><span data-ttu-id="b8924-107">Неявные преобразования указателей</span><span class="sxs-lookup"><span data-stu-id="b8924-107">Implicit pointer conversions</span></span>  
  
|<span data-ttu-id="b8924-108">Исходный тип</span><span class="sxs-lookup"><span data-stu-id="b8924-108">From</span></span>|<span data-ttu-id="b8924-109">Кому</span><span class="sxs-lookup"><span data-stu-id="b8924-109">To</span></span>|  
|----------|--------|  
|<span data-ttu-id="b8924-110">Любой тип указателя</span><span class="sxs-lookup"><span data-stu-id="b8924-110">Any pointer type</span></span>|<span data-ttu-id="b8924-111">void\*</span><span class="sxs-lookup"><span data-stu-id="b8924-111">void\*</span></span>|  
|<span data-ttu-id="b8924-112">null</span><span class="sxs-lookup"><span data-stu-id="b8924-112">null</span></span>|<span data-ttu-id="b8924-113">Любой тип указателя</span><span class="sxs-lookup"><span data-stu-id="b8924-113">Any pointer type</span></span>|  
  
 <span data-ttu-id="b8924-114">Явное преобразование указателя используется для выполнения преобразований, для которых отсутствует неявное преобразование, с помощью выражения приведения.</span><span class="sxs-lookup"><span data-stu-id="b8924-114">Explicit pointer conversion is used to perform conversions, for which there is no implicit conversion, by using a cast expression.</span></span> <span data-ttu-id="b8924-115">Эти преобразования показаны в следующей таблице.</span><span class="sxs-lookup"><span data-stu-id="b8924-115">The following table shows these conversions.</span></span>  
  
## <a name="explicit-pointer-conversions"></a><span data-ttu-id="b8924-116">Явные преобразования указателей</span><span class="sxs-lookup"><span data-stu-id="b8924-116">Explicit pointer conversions</span></span>  
  
|<span data-ttu-id="b8924-117">Исходный тип</span><span class="sxs-lookup"><span data-stu-id="b8924-117">From</span></span>|<span data-ttu-id="b8924-118">Кому</span><span class="sxs-lookup"><span data-stu-id="b8924-118">To</span></span>|  
|----------|--------|  
|<span data-ttu-id="b8924-119">Любой тип указателя</span><span class="sxs-lookup"><span data-stu-id="b8924-119">Any pointer type</span></span>|<span data-ttu-id="b8924-120">Любой другой тип указателя</span><span class="sxs-lookup"><span data-stu-id="b8924-120">Any other pointer type</span></span>|  
|<span data-ttu-id="b8924-121">sbyte, byte, short, ushort, int, uint, long или ulong</span><span class="sxs-lookup"><span data-stu-id="b8924-121">sbyte, byte, short, ushort, int, uint, long, or ulong</span></span>|<span data-ttu-id="b8924-122">Любой тип указателя</span><span class="sxs-lookup"><span data-stu-id="b8924-122">Any pointer type</span></span>|  
|<span data-ttu-id="b8924-123">Любой тип указателя</span><span class="sxs-lookup"><span data-stu-id="b8924-123">Any pointer type</span></span>|<span data-ttu-id="b8924-124">sbyte, byte, short, ushort, int, uint, long или ulong</span><span class="sxs-lookup"><span data-stu-id="b8924-124">sbyte, byte, short, ushort, int, uint, long, or ulong</span></span>|  
  
## <a name="example"></a><span data-ttu-id="b8924-125">Пример</span><span class="sxs-lookup"><span data-stu-id="b8924-125">Example</span></span>  

 <span data-ttu-id="b8924-126">В следующем примере указатель на `int` преобразуется в указатель на `byte`.</span><span class="sxs-lookup"><span data-stu-id="b8924-126">In the following example, a pointer to `int` is converted to a pointer to `byte`.</span></span> <span data-ttu-id="b8924-127">Обратите внимание, что указатель указывает на наименьший адресуемый байт переменной.</span><span class="sxs-lookup"><span data-stu-id="b8924-127">Notice that the pointer points to the lowest addressed byte of the variable.</span></span> <span data-ttu-id="b8924-128">При последовательном увеличении результата до размера `int` (4 байта) можно отобразить оставшиеся байты переменной.</span><span class="sxs-lookup"><span data-stu-id="b8924-128">When you successively increment the result, up to the size of `int` (4 bytes), you can display the remaining bytes of the variable.</span></span>  
  
 [!code-csharp[csProgGuidePointers#3](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuidePointers/CS/Pointers2.cs#3)]  
  
 [!code-csharp[csProgGuidePointers#4](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuidePointers/CS/Pointers.cs#4)]  
  
## <a name="see-also"></a><span data-ttu-id="b8924-129">См. также</span><span class="sxs-lookup"><span data-stu-id="b8924-129">See also</span></span>

- [<span data-ttu-id="b8924-130">Руководство по программированию на C#</span><span class="sxs-lookup"><span data-stu-id="b8924-130">C# Programming Guide</span></span>](../index.md)
- [<span data-ttu-id="b8924-131">Типы указателей</span><span class="sxs-lookup"><span data-stu-id="b8924-131">Pointer types</span></span>](pointer-types.md)
- [<span data-ttu-id="b8924-132">Ссылочные типы</span><span class="sxs-lookup"><span data-stu-id="b8924-132">Reference types</span></span>](../../language-reference/keywords/reference-types.md)
- [<span data-ttu-id="b8924-133">Типы значений</span><span class="sxs-lookup"><span data-stu-id="b8924-133">Value types</span></span>](../../language-reference/builtin-types/value-types.md)
- [<span data-ttu-id="b8924-134">unsafe</span><span class="sxs-lookup"><span data-stu-id="b8924-134">unsafe</span></span>](../../language-reference/keywords/unsafe.md)
- [<span data-ttu-id="b8924-135">Оператор fixed</span><span class="sxs-lookup"><span data-stu-id="b8924-135">fixed Statement</span></span>](../../language-reference/keywords/fixed-statement.md)
- [<span data-ttu-id="b8924-136">stackalloc</span><span class="sxs-lookup"><span data-stu-id="b8924-136">stackalloc</span></span>](../../language-reference/operators/stackalloc.md)
