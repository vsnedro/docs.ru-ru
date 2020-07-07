---
title: Маршалинг различных типов массивов
description: Маршалирование различных типов массивов, например целых чисел по значению или по ссылке, целых чисел по значению (двумерные массивы), строк по значению и структур с целыми числами или строками.
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- marshaling, Arrays sample
- data marshaling, Arrays sample
ms.assetid: c5ac9920-5b6e-4dc9-bf2d-1f6f8ad3b0bf
ms.openlocfilehash: f1473c7917189f0b36c96b2adcf20005c5fd6b48
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.contentlocale: ru-RU
ms.lasthandoff: 07/01/2020
ms.locfileid: "85621500"
---
# <a name="marshaling-different-types-of-arrays"></a><span data-ttu-id="31202-103">Маршалинг различных типов массивов</span><span class="sxs-lookup"><span data-stu-id="31202-103">Marshaling Different Types of Arrays</span></span>
<span data-ttu-id="31202-104">Массив является ссылочным типом в управляемом коде, содержащим один или несколько элементов одного и того же типа.</span><span class="sxs-lookup"><span data-stu-id="31202-104">An array is a reference type in managed code that contains one or more elements of the same type.</span></span> <span data-ttu-id="31202-105">Несмотря на то, что массивы являются ссылочными типами, они передаются в неуправляемые функции в виде параметров In.</span><span class="sxs-lookup"><span data-stu-id="31202-105">Although arrays are reference types, they are passed as In parameters to unmanaged functions.</span></span> <span data-ttu-id="31202-106">Это поведение не согласуется со способом передачи управляемых массивов в управляемые объекты в виде параметров In/Out.</span><span class="sxs-lookup"><span data-stu-id="31202-106">This behavior is inconsistent with way managed arrays are passed to managed objects, which is as In/Out parameters.</span></span> <span data-ttu-id="31202-107">Подробнее см. в разделе [Копирование и закрепление](copying-and-pinning.md).</span><span class="sxs-lookup"><span data-stu-id="31202-107">For additional details, see [Copying and Pinning](copying-and-pinning.md).</span></span>  
  
 <span data-ttu-id="31202-108">В таблице ниже перечислены параметры маршалинга для массивов и описывается их использование.</span><span class="sxs-lookup"><span data-stu-id="31202-108">The following table lists marshaling options for arrays and describes their usage.</span></span>  
  
|<span data-ttu-id="31202-109">Массив</span><span class="sxs-lookup"><span data-stu-id="31202-109">Array</span></span>|<span data-ttu-id="31202-110">Описание</span><span class="sxs-lookup"><span data-stu-id="31202-110">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="31202-111">Целые числа по значению.</span><span class="sxs-lookup"><span data-stu-id="31202-111">Of integers by value.</span></span>|<span data-ttu-id="31202-112">Передает массив целых чисел в виде параметра In.</span><span class="sxs-lookup"><span data-stu-id="31202-112">Passes an array of integers as an In parameter.</span></span>|  
|<span data-ttu-id="31202-113">Целые числа по ссылке.</span><span class="sxs-lookup"><span data-stu-id="31202-113">Of integers by reference.</span></span>|<span data-ttu-id="31202-114">Передает массив целых чисел в виде параметра In/Out.</span><span class="sxs-lookup"><span data-stu-id="31202-114">Passes an array of integers as an In/Out parameter.</span></span>|  
|<span data-ttu-id="31202-115">Целые числа по значению (двухмерный массив).</span><span class="sxs-lookup"><span data-stu-id="31202-115">Of integers by value (two-dimensional).</span></span>|<span data-ttu-id="31202-116">Передает матрицу целых чисел в виде параметра In.</span><span class="sxs-lookup"><span data-stu-id="31202-116">Passes a matrix of integers as an In parameter.</span></span>|  
|<span data-ttu-id="31202-117">Строки по значению.</span><span class="sxs-lookup"><span data-stu-id="31202-117">Of strings by value.</span></span>|<span data-ttu-id="31202-118">Передает массив строк в виде параметра In.</span><span class="sxs-lookup"><span data-stu-id="31202-118">Passes an array of strings as an In parameter.</span></span>|  
|<span data-ttu-id="31202-119">Структуры с целыми числами.</span><span class="sxs-lookup"><span data-stu-id="31202-119">Of structures with integers.</span></span>|<span data-ttu-id="31202-120">Передает массив структур, содержащих целые числа, в виде параметра In/Out.</span><span class="sxs-lookup"><span data-stu-id="31202-120">Passes an array of structures that contain integers as an In parameter.</span></span>|  
|<span data-ttu-id="31202-121">Структуры со строками.</span><span class="sxs-lookup"><span data-stu-id="31202-121">Of structures with strings.</span></span>|<span data-ttu-id="31202-122">Передает массив структур, содержащих только строки, в виде параметра In или Out.</span><span class="sxs-lookup"><span data-stu-id="31202-122">Passes an array of structures that contain only strings as an In/Out parameter.</span></span> <span data-ttu-id="31202-123">Элементы массива можно изменять.</span><span class="sxs-lookup"><span data-stu-id="31202-123">Members of the array can be changed.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="31202-124">Пример</span><span class="sxs-lookup"><span data-stu-id="31202-124">Example</span></span>  
 <span data-ttu-id="31202-125">В этом примере показаны способы передачи массивов следующих типов:</span><span class="sxs-lookup"><span data-stu-id="31202-125">This sample demonstrates how to pass the following types of arrays:</span></span>  
  
- <span data-ttu-id="31202-126">массив целых чисел по значению;</span><span class="sxs-lookup"><span data-stu-id="31202-126">Array of integers by value.</span></span>  
  
- <span data-ttu-id="31202-127">массив целых чисел, размер которого может быть изменен, по ссылке;</span><span class="sxs-lookup"><span data-stu-id="31202-127">Array of integers by reference, which can be resized.</span></span>  
  
- <span data-ttu-id="31202-128">многомерный массив (матрица) целых чисел по значению;</span><span class="sxs-lookup"><span data-stu-id="31202-128">Multidimensional array (matrix) of integers by value.</span></span>  
  
- <span data-ttu-id="31202-129">массив строк по значению;</span><span class="sxs-lookup"><span data-stu-id="31202-129">Array of strings by value.</span></span>  
  
- <span data-ttu-id="31202-130">массив структур с целыми числами;</span><span class="sxs-lookup"><span data-stu-id="31202-130">Array of structures with integers.</span></span>  
  
- <span data-ttu-id="31202-131">массив структур со строками.</span><span class="sxs-lookup"><span data-stu-id="31202-131">Array of structures with strings.</span></span>  
  
 <span data-ttu-id="31202-132">Если маршалинг массива по ссылке не выполняется явным образом, то по умолчанию он осуществляется в виде параметра In.</span><span class="sxs-lookup"><span data-stu-id="31202-132">Unless an array is explicitly marshaled by reference, the default behavior marshals the array as an In parameter.</span></span> <span data-ttu-id="31202-133">Это поведение можно изменить, применив явным образом атрибуты <xref:System.Runtime.InteropServices.InAttribute> и <xref:System.Runtime.InteropServices.OutAttribute> .</span><span class="sxs-lookup"><span data-stu-id="31202-133">You can change this behavior by applying the <xref:System.Runtime.InteropServices.InAttribute> and <xref:System.Runtime.InteropServices.OutAttribute> attributes explicitly.</span></span>  
  
 <span data-ttu-id="31202-134">В этом примере используются перечисленные ниже неуправляемые функции, показанные со своими исходными объявлениями.</span><span class="sxs-lookup"><span data-stu-id="31202-134">The Arrays sample uses the following unmanaged functions, shown with their original function declaration:</span></span>  
  
- <span data-ttu-id="31202-135">Функция**TestArrayOfInts** , экспортированная из PinvokeLib.dll.</span><span class="sxs-lookup"><span data-stu-id="31202-135">**TestArrayOfInts** exported from PinvokeLib.dll.</span></span>  
  
    ```cpp
    int TestArrayOfInts(int* pArray, int pSize);  
    ```  
  
- <span data-ttu-id="31202-136">Функция**TestRefArrayOfInts** , экспортированная из PinvokeLib.dll.</span><span class="sxs-lookup"><span data-stu-id="31202-136">**TestRefArrayOfInts** exported from PinvokeLib.dll.</span></span>  
  
    ```cpp
    int TestRefArrayOfInts(int** ppArray, int* pSize);  
    ```  
  
- <span data-ttu-id="31202-137">Функция**TestMatrixOfInts** , экспортированная из PinvokeLib.dll.</span><span class="sxs-lookup"><span data-stu-id="31202-137">**TestMatrixOfInts** exported from PinvokeLib.dll.</span></span>  
  
    ```cpp
    int TestMatrixOfInts(int pMatrix[][COL_DIM], int row);  
    ```  
  
- <span data-ttu-id="31202-138">Функция**TestArrayOfStrings** , экспортированная из PinvokeLib.dll.</span><span class="sxs-lookup"><span data-stu-id="31202-138">**TestArrayOfStrings** exported from PinvokeLib.dll.</span></span>  
  
    ```cpp
    int TestArrayOfStrings(char** ppStrArray, int size);  
    ```  
  
- <span data-ttu-id="31202-139">Функция**TestArrayOfStructs** , экспортированная из PinvokeLib.dll.</span><span class="sxs-lookup"><span data-stu-id="31202-139">**TestArrayOfStructs** exported from PinvokeLib.dll.</span></span>  
  
    ```cpp
    int TestArrayOfStructs(MYPOINT* pPointArray, int size);  
    ```  
  
- <span data-ttu-id="31202-140">Функция**TestArrayOfStructs2** , экспортированная из PinvokeLib.dll.</span><span class="sxs-lookup"><span data-stu-id="31202-140">**TestArrayOfStructs2** exported from PinvokeLib.dll.</span></span>  
  
    ```cpp
    int TestArrayOfStructs2 (MYPERSON* pPersonArray, int size);  
    ```  
  
 <span data-ttu-id="31202-141">[PinvokeLib.dll](marshaling-data-with-platform-invoke.md#pinvokelibdll) — это пользовательская неуправляемая библиотека, содержащая реализации ранее описанных функций и две переменные структуры: **MYPOINT** и **MYPERSON**.</span><span class="sxs-lookup"><span data-stu-id="31202-141">[PinvokeLib.dll](marshaling-data-with-platform-invoke.md#pinvokelibdll) is a custom unmanaged library that contains implementations for the previously listed functions and two structure variables, **MYPOINT** and **MYPERSON**.</span></span> <span data-ttu-id="31202-142">Структуры содержат следующие элементы:</span><span class="sxs-lookup"><span data-stu-id="31202-142">The structures contain the following elements:</span></span>  
  
```cpp
typedef struct _MYPOINT  
{  
   int x;
   int y;
} MYPOINT;  
  
typedef struct _MYPERSON  
{  
   char* first;
   char* last;
} MYPERSON;  
```  
  
 <span data-ttu-id="31202-143">В этом примере структуры `MyPoint` и `MyPerson` содержат внедренные типы.</span><span class="sxs-lookup"><span data-stu-id="31202-143">In this sample, the `MyPoint` and `MyPerson` structures contain embedded types.</span></span> <span data-ttu-id="31202-144">Чтобы гарантировать последовательное размещение членов в памяти в порядке их появления, применяется атрибут <xref:System.Runtime.InteropServices.StructLayoutAttribute> .</span><span class="sxs-lookup"><span data-stu-id="31202-144">The <xref:System.Runtime.InteropServices.StructLayoutAttribute> attribute is set to ensure that the members are arranged in memory sequentially, in the order in which they appear.</span></span>  
  
 <span data-ttu-id="31202-145">Класс `NativeMethods` содержит набор методов, вызываемых классом `App` .</span><span class="sxs-lookup"><span data-stu-id="31202-145">The `NativeMethods` class contains a set of methods called by the `App` class.</span></span> <span data-ttu-id="31202-146">Конкретные сведения о передаче массивов см. в комментариях к приведенному ниже примеру.</span><span class="sxs-lookup"><span data-stu-id="31202-146">For specific details about passing arrays, see the comments in the following sample.</span></span> <span data-ttu-id="31202-147">Массив, который является ссылочным типом, по умолчанию передается в виде параметра In.</span><span class="sxs-lookup"><span data-stu-id="31202-147">An array, which is a reference type, is passed as an In parameter by default.</span></span> <span data-ttu-id="31202-148">Чтобы вызывающий объект мог получать результаты, необходимо явным образом применить атрибуты **InAttribute** и **OutAttribute** к аргументу, содержащему массив.</span><span class="sxs-lookup"><span data-stu-id="31202-148">For the caller to receive the results, **InAttribute** and **OutAttribute** must be applied explicitly to the argument containing the array.</span></span>  
  
### <a name="declaring-prototypes"></a><span data-ttu-id="31202-149">Объявление прототипов</span><span class="sxs-lookup"><span data-stu-id="31202-149">Declaring Prototypes</span></span>  
 [!code-csharp[Conceptual.Interop.Marshaling#31](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.interop.marshaling/cs/arrays.cs#31)]
 [!code-vb[Conceptual.Interop.Marshaling#31](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.interop.marshaling/vb/arrays.vb#31)]  
  
### <a name="calling-functions"></a><span data-ttu-id="31202-150">Вызов функций</span><span class="sxs-lookup"><span data-stu-id="31202-150">Calling Functions</span></span>  
 [!code-csharp[Conceptual.Interop.Marshaling#32](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.interop.marshaling/cs/arrays.cs#32)]
 [!code-vb[Conceptual.Interop.Marshaling#32](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.interop.marshaling/vb/arrays.vb#32)]  
  
## <a name="see-also"></a><span data-ttu-id="31202-151">См. также</span><span class="sxs-lookup"><span data-stu-id="31202-151">See also</span></span>

- [<span data-ttu-id="31202-152">Типы данных в вызове неуправляемого кода</span><span class="sxs-lookup"><span data-stu-id="31202-152">Platform invoke data types</span></span>](marshaling-data-with-platform-invoke.md#platform-invoke-data-types)
- [<span data-ttu-id="31202-153">Создание прототипов в управляемом коде</span><span class="sxs-lookup"><span data-stu-id="31202-153">Creating Prototypes in Managed Code</span></span>](creating-prototypes-in-managed-code.md)
