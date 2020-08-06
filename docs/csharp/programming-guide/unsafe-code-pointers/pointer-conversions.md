---
title: Руководство по программированию на C#. Преобразования указателей
description: Сведения о преобразованиях указателей. Просмотрите таблицы явных и неявных преобразований указателей и примеры кода, а также ознакомьтесь с дополнительными ресурсами.
ms.date: 07/20/2015
helpviewer_keywords:
- pointers [C#], conversions
ms.assetid: f0e87502-477a-4ede-a31f-7a3e262e46fb
ms.openlocfilehash: c39be5cb52964abbea5bc5636c6fa74d8411a331
ms.sourcegitcommit: 552b4b60c094559db9d8178fa74f5bafaece0caf
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/29/2020
ms.locfileid: "87382091"
---
# <a name="pointer-conversions-c-programming-guide"></a><span data-ttu-id="d3c31-104">Преобразования указателей (Руководство по программированию на C#)</span><span class="sxs-lookup"><span data-stu-id="d3c31-104">Pointer Conversions (C# Programming Guide)</span></span>
<span data-ttu-id="d3c31-105">В следующей таблице приведены предопределенные неявные преобразования указателей.</span><span class="sxs-lookup"><span data-stu-id="d3c31-105">The following table shows the predefined implicit pointer conversions.</span></span> <span data-ttu-id="d3c31-106">Неявные преобразования могут выполняться во многих ситуациях, включая вызов методов и операторы назначения.</span><span class="sxs-lookup"><span data-stu-id="d3c31-106">Implicit conversions might occur in many situations, including method invoking and assignment statements.</span></span>  
  
## <a name="implicit-pointer-conversions"></a><span data-ttu-id="d3c31-107">Неявные преобразования указателей</span><span class="sxs-lookup"><span data-stu-id="d3c31-107">Implicit pointer conversions</span></span>  
  
|<span data-ttu-id="d3c31-108">Исходный тип</span><span class="sxs-lookup"><span data-stu-id="d3c31-108">From</span></span>|<span data-ttu-id="d3c31-109">Кому</span><span class="sxs-lookup"><span data-stu-id="d3c31-109">To</span></span>|  
|----------|--------|  
|<span data-ttu-id="d3c31-110">Любой тип указателя</span><span class="sxs-lookup"><span data-stu-id="d3c31-110">Any pointer type</span></span>|<span data-ttu-id="d3c31-111">void\*</span><span class="sxs-lookup"><span data-stu-id="d3c31-111">void\*</span></span>|  
|<span data-ttu-id="d3c31-112">null</span><span class="sxs-lookup"><span data-stu-id="d3c31-112">null</span></span>|<span data-ttu-id="d3c31-113">Любой тип указателя</span><span class="sxs-lookup"><span data-stu-id="d3c31-113">Any pointer type</span></span>|  
  
 <span data-ttu-id="d3c31-114">Явное преобразование указателя используется для выполнения преобразований, для которых отсутствует неявное преобразование, с помощью выражения приведения.</span><span class="sxs-lookup"><span data-stu-id="d3c31-114">Explicit pointer conversion is used to perform conversions, for which there is no implicit conversion, by using a cast expression.</span></span> <span data-ttu-id="d3c31-115">Эти преобразования показаны в следующей таблице.</span><span class="sxs-lookup"><span data-stu-id="d3c31-115">The following table shows these conversions.</span></span>  
  
## <a name="explicit-pointer-conversions"></a><span data-ttu-id="d3c31-116">Явные преобразования указателей</span><span class="sxs-lookup"><span data-stu-id="d3c31-116">Explicit pointer conversions</span></span>  
  
|<span data-ttu-id="d3c31-117">Исходный тип</span><span class="sxs-lookup"><span data-stu-id="d3c31-117">From</span></span>|<span data-ttu-id="d3c31-118">Кому</span><span class="sxs-lookup"><span data-stu-id="d3c31-118">To</span></span>|  
|----------|--------|  
|<span data-ttu-id="d3c31-119">Любой тип указателя</span><span class="sxs-lookup"><span data-stu-id="d3c31-119">Any pointer type</span></span>|<span data-ttu-id="d3c31-120">Любой другой тип указателя</span><span class="sxs-lookup"><span data-stu-id="d3c31-120">Any other pointer type</span></span>|  
|<span data-ttu-id="d3c31-121">sbyte, byte, short, ushort, int, uint, long или ulong</span><span class="sxs-lookup"><span data-stu-id="d3c31-121">sbyte, byte, short, ushort, int, uint, long, or ulong</span></span>|<span data-ttu-id="d3c31-122">Любой тип указателя</span><span class="sxs-lookup"><span data-stu-id="d3c31-122">Any pointer type</span></span>|  
|<span data-ttu-id="d3c31-123">Любой тип указателя</span><span class="sxs-lookup"><span data-stu-id="d3c31-123">Any pointer type</span></span>|<span data-ttu-id="d3c31-124">sbyte, byte, short, ushort, int, uint, long или ulong</span><span class="sxs-lookup"><span data-stu-id="d3c31-124">sbyte, byte, short, ushort, int, uint, long, or ulong</span></span>|  
  
## <a name="example"></a><span data-ttu-id="d3c31-125">Пример</span><span class="sxs-lookup"><span data-stu-id="d3c31-125">Example</span></span>  
 <span data-ttu-id="d3c31-126">В следующем примере указатель на `int` преобразуется в указатель на `byte`.</span><span class="sxs-lookup"><span data-stu-id="d3c31-126">In the following example, a pointer to `int` is converted to a pointer to `byte`.</span></span> <span data-ttu-id="d3c31-127">Обратите внимание, что указатель указывает на наименьший адресуемый байт переменной.</span><span class="sxs-lookup"><span data-stu-id="d3c31-127">Notice that the pointer points to the lowest addressed byte of the variable.</span></span> <span data-ttu-id="d3c31-128">При последовательном увеличении результата до размера `int` (4 байта) можно отобразить оставшиеся байты переменной.</span><span class="sxs-lookup"><span data-stu-id="d3c31-128">When you successively increment the result, up to the size of `int` (4 bytes), you can display the remaining bytes of the variable.</span></span>  
  
 [!code-csharp[csProgGuidePointers#3](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuidePointers/CS/Pointers2.cs#3)]  
  
 [!code-csharp[csProgGuidePointers#4](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuidePointers/CS/Pointers.cs#4)]  
  
## <a name="see-also"></a><span data-ttu-id="d3c31-129">См. также</span><span class="sxs-lookup"><span data-stu-id="d3c31-129">See also</span></span>

- [<span data-ttu-id="d3c31-130">Руководство по программированию на C#</span><span class="sxs-lookup"><span data-stu-id="d3c31-130">C# Programming Guide</span></span>](../index.md)
- [<span data-ttu-id="d3c31-131">Типы указателей</span><span class="sxs-lookup"><span data-stu-id="d3c31-131">Pointer types</span></span>](pointer-types.md)
- [<span data-ttu-id="d3c31-132">Ссылочные типы</span><span class="sxs-lookup"><span data-stu-id="d3c31-132">Reference types</span></span>](../../language-reference/keywords/reference-types.md)
- [<span data-ttu-id="d3c31-133">Типы значений</span><span class="sxs-lookup"><span data-stu-id="d3c31-133">Value types</span></span>](../../language-reference/builtin-types/value-types.md)
- [<span data-ttu-id="d3c31-134">unsafe</span><span class="sxs-lookup"><span data-stu-id="d3c31-134">unsafe</span></span>](../../language-reference/keywords/unsafe.md)
- [<span data-ttu-id="d3c31-135">Оператор fixed</span><span class="sxs-lookup"><span data-stu-id="d3c31-135">fixed Statement</span></span>](../../language-reference/keywords/fixed-statement.md)
- [<span data-ttu-id="d3c31-136">stackalloc</span><span class="sxs-lookup"><span data-stu-id="d3c31-136">stackalloc</span></span>](../../language-reference/operators/stackalloc.md)
