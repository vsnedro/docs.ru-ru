---
title: Маршалинг классов, структур и объединений
description: Узнайте, как маршалировать классы, структуры и объединения. Просмотрите примеры маршалирования классов, структур с вложенными структурами, массивами структур и объединений.
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- data marshaling, classes
- marshaling, unions
- marshaling, structures
- marshaling, samples
- data marshaling, structures
- platform invoke, marshaling data
- marshaling, classes
- data marshaling, unions
- data marshaling, samples
- data marshaling, platform invoke
- marshaling, platform invoke
ms.assetid: 027832a2-9b43-4fd9-9b45-7f4196261a4e
ms.openlocfilehash: 5e616b5bb513939cadd8fe5c72675ba0b6e070a3
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.contentlocale: ru-RU
ms.lasthandoff: 07/01/2020
ms.locfileid: "85621526"
---
# <a name="marshaling-classes-structures-and-unions"></a><span data-ttu-id="5adc2-104">Маршалинг классов, структур и объединений</span><span class="sxs-lookup"><span data-stu-id="5adc2-104">Marshaling Classes, Structures, and Unions</span></span>

<span data-ttu-id="5adc2-105">Классы и структуры в .NET Framework похожи.</span><span class="sxs-lookup"><span data-stu-id="5adc2-105">Classes and structures are similar in the .NET Framework.</span></span> <span data-ttu-id="5adc2-106">И те и другие могут иметь поля, свойства и события.</span><span class="sxs-lookup"><span data-stu-id="5adc2-106">Both can have fields, properties, and events.</span></span> <span data-ttu-id="5adc2-107">Они также могут иметь статические и нестатические методы.</span><span class="sxs-lookup"><span data-stu-id="5adc2-107">They can also have static and nonstatic methods.</span></span> <span data-ttu-id="5adc2-108">Примечательным отличием является то, что структуры являются типами значений, а классы — ссылочными типами.</span><span class="sxs-lookup"><span data-stu-id="5adc2-108">One notable difference is that structures are value types and classes are reference types.</span></span>

<span data-ttu-id="5adc2-109">В таблице ниже представлены варианты маршалинга классов, структур и объединений, описывается их применение и приводятся ссылки на соответствующие примеры вызова неуправляемого кода.</span><span class="sxs-lookup"><span data-stu-id="5adc2-109">The following table lists marshaling options for classes, structures, and unions; describes their usage; and provides a link to the corresponding platform invoke sample.</span></span>

|<span data-ttu-id="5adc2-110">Type</span><span class="sxs-lookup"><span data-stu-id="5adc2-110">Type</span></span>|<span data-ttu-id="5adc2-111">Описание</span><span class="sxs-lookup"><span data-stu-id="5adc2-111">Description</span></span>|<span data-ttu-id="5adc2-112">Пример</span><span class="sxs-lookup"><span data-stu-id="5adc2-112">Sample</span></span>|
|----------|-----------------|------------|
|<span data-ttu-id="5adc2-113">Класс по значению.</span><span class="sxs-lookup"><span data-stu-id="5adc2-113">Class by value.</span></span>|<span data-ttu-id="5adc2-114">Передает класс с целочисленными членами в качестве параметра In или Out (как и в случае управляемого класса).</span><span class="sxs-lookup"><span data-stu-id="5adc2-114">Passes a class with integer members as an In/Out parameter, like the managed case.</span></span>|[<span data-ttu-id="5adc2-115">Пример SysTime</span><span class="sxs-lookup"><span data-stu-id="5adc2-115">SysTime sample</span></span>](#systime-sample)|
|<span data-ttu-id="5adc2-116">Структура по значению.</span><span class="sxs-lookup"><span data-stu-id="5adc2-116">Structure by value.</span></span>|<span data-ttu-id="5adc2-117">Передает структуры в качестве параметров In.</span><span class="sxs-lookup"><span data-stu-id="5adc2-117">Passes structures as In parameters.</span></span>|[<span data-ttu-id="5adc2-118">Пример структур</span><span class="sxs-lookup"><span data-stu-id="5adc2-118">Structures sample</span></span>](#structures-sample)|
|<span data-ttu-id="5adc2-119">Структура по ссылке.</span><span class="sxs-lookup"><span data-stu-id="5adc2-119">Structure by reference.</span></span>|<span data-ttu-id="5adc2-120">Передает структуры в качестве параметров In и Out.</span><span class="sxs-lookup"><span data-stu-id="5adc2-120">Passes structures as In/Out parameters.</span></span>|<span data-ttu-id="5adc2-121">[Пример OSInfo](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/795sy883(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="5adc2-121">[OSInfo sample](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/795sy883(v=vs.100))</span></span>|
|<span data-ttu-id="5adc2-122">Структура с вложенными структурами (выровненная).</span><span class="sxs-lookup"><span data-stu-id="5adc2-122">Structure with nested structures (flattened).</span></span>|<span data-ttu-id="5adc2-123">Передает класс, представляющий структуру с вложенными структурами, в неуправляемую функцию.</span><span class="sxs-lookup"><span data-stu-id="5adc2-123">Passes a class that represents a structure with nested structures in the unmanaged function.</span></span> <span data-ttu-id="5adc2-124">Структура выравнивается в одну большую структуру в управляемом прототипе.</span><span class="sxs-lookup"><span data-stu-id="5adc2-124">The structure is flattened to one big structure in the managed prototype.</span></span>|[<span data-ttu-id="5adc2-125">Пример FindFile</span><span class="sxs-lookup"><span data-stu-id="5adc2-125">FindFile sample</span></span>](#findfile-sample)|
|<span data-ttu-id="5adc2-126">Структура с указателем на другую структуру.</span><span class="sxs-lookup"><span data-stu-id="5adc2-126">Structure with a pointer to another structure.</span></span>|<span data-ttu-id="5adc2-127">Передает структуру, содержащую указатель на другую структуру в качестве члена.</span><span class="sxs-lookup"><span data-stu-id="5adc2-127">Passes a structure that contains a pointer to a second structure as a member.</span></span>|[<span data-ttu-id="5adc2-128">Пример структур</span><span class="sxs-lookup"><span data-stu-id="5adc2-128">Structures Sample</span></span>](#structures-sample)|
|<span data-ttu-id="5adc2-129">Массив структур с целочисленными значениями по значению.</span><span class="sxs-lookup"><span data-stu-id="5adc2-129">Array of structures with integers by value.</span></span>|<span data-ttu-id="5adc2-130">Передает массив структур, содержащих только целые числа, в виде параметра In или Out.</span><span class="sxs-lookup"><span data-stu-id="5adc2-130">Passes an array of structures that contain only integers as an In/Out parameter.</span></span> <span data-ttu-id="5adc2-131">Элементы массива можно изменять.</span><span class="sxs-lookup"><span data-stu-id="5adc2-131">Members of the array can be changed.</span></span>|[<span data-ttu-id="5adc2-132">Пример массивов</span><span class="sxs-lookup"><span data-stu-id="5adc2-132">Arrays Sample</span></span>](marshaling-different-types-of-arrays.md)|
|<span data-ttu-id="5adc2-133">Массив структур с целочисленными значениями и строками по ссылке.</span><span class="sxs-lookup"><span data-stu-id="5adc2-133">Array of structures with integers and strings by reference.</span></span>|<span data-ttu-id="5adc2-134">Передает массив структур, содержащих целые числа и строки, в качестве параметра Out.</span><span class="sxs-lookup"><span data-stu-id="5adc2-134">Passes an array of structures that contain integers and strings as an Out parameter.</span></span> <span data-ttu-id="5adc2-135">Вызываемая функция выделяет память под массив.</span><span class="sxs-lookup"><span data-stu-id="5adc2-135">The called function allocates memory for the array.</span></span>|[<span data-ttu-id="5adc2-136">Пример OutArrayOfStructs</span><span class="sxs-lookup"><span data-stu-id="5adc2-136">OutArrayOfStructs Sample</span></span>](#outarrayofstructs-sample)|
|<span data-ttu-id="5adc2-137">Объединения с типами значений.</span><span class="sxs-lookup"><span data-stu-id="5adc2-137">Unions with value types.</span></span>|<span data-ttu-id="5adc2-138">Передает объединения с типами значений (целочисленными и двойной точности).</span><span class="sxs-lookup"><span data-stu-id="5adc2-138">Passes unions with value types (integer and double).</span></span>|[<span data-ttu-id="5adc2-139">Пример объединений</span><span class="sxs-lookup"><span data-stu-id="5adc2-139">Unions sample</span></span>](#unions-sample)|
|<span data-ttu-id="5adc2-140">Объединения со смешанными типами.</span><span class="sxs-lookup"><span data-stu-id="5adc2-140">Unions with mixed types.</span></span>|<span data-ttu-id="5adc2-141">Передает объединения со смешанными типами (целое число и строка).</span><span class="sxs-lookup"><span data-stu-id="5adc2-141">Passes unions with mixed types (integer and string).</span></span>|[<span data-ttu-id="5adc2-142">Пример объединений</span><span class="sxs-lookup"><span data-stu-id="5adc2-142">Unions sample</span></span>](#unions-sample)|
|<span data-ttu-id="5adc2-143">Структура с макетом, зависящим от платформы.</span><span class="sxs-lookup"><span data-stu-id="5adc2-143">Struct with platform-specific layout.</span></span>|<span data-ttu-id="5adc2-144">Передает тип с определениями собственной упаковки.</span><span class="sxs-lookup"><span data-stu-id="5adc2-144">Passes a type with native-packing definitions.</span></span>|[<span data-ttu-id="5adc2-145">Пример платформы</span><span class="sxs-lookup"><span data-stu-id="5adc2-145">Platform sample</span></span>](#platform-sample)|
|<span data-ttu-id="5adc2-146">Значения Null в структуре.</span><span class="sxs-lookup"><span data-stu-id="5adc2-146">Null values in structure.</span></span>|<span data-ttu-id="5adc2-147">Передает пустую ссылку (**Nothing** в Visual Basic) вместо ссылки на тип значения.</span><span class="sxs-lookup"><span data-stu-id="5adc2-147">Passes a null reference (**Nothing** in Visual Basic) instead of a reference to a value type.</span></span>|<span data-ttu-id="5adc2-148">[Пример HandleRef](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.0/hc662t8k(v=vs.85))</span><span class="sxs-lookup"><span data-stu-id="5adc2-148">[HandleRef sample](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.0/hc662t8k(v=vs.85))</span></span>|

## <a name="structures-sample"></a><span data-ttu-id="5adc2-149">Пример структур</span><span class="sxs-lookup"><span data-stu-id="5adc2-149">Structures sample</span></span>

<span data-ttu-id="5adc2-150">В этом примере показан способ передачи структуры, указывающей на вторую структуру, передачи структуры с внедренной структурой и передачи структуры с внедренным массивом.</span><span class="sxs-lookup"><span data-stu-id="5adc2-150">This sample demonstrates how to pass a structure that points to a second structure, pass a structure with an embedded structure, and pass a structure with an embedded array.</span></span>  
  
<span data-ttu-id="5adc2-151">В примере используются следующие неуправляемые функции, показанные с исходными объявлениями:</span><span class="sxs-lookup"><span data-stu-id="5adc2-151">The Structs sample uses the following unmanaged functions, shown with their original function declaration:</span></span>

- <span data-ttu-id="5adc2-152">функция **TestStructInStruct**, экспортированная из PinvokeLib.dll;</span><span class="sxs-lookup"><span data-stu-id="5adc2-152">**TestStructInStruct** exported from PinvokeLib.dll.</span></span>

    ```cpp
    int TestStructInStruct(MYPERSON2* pPerson2);
    ```

- <span data-ttu-id="5adc2-153">функция **TestStructInStruct3**, экспортированная из PinvokeLib.dll;</span><span class="sxs-lookup"><span data-stu-id="5adc2-153">**TestStructInStruct3** exported from PinvokeLib.dll.</span></span>

    ```cpp
    void TestStructInStruct3(MYPERSON3 person3);
    ```

- <span data-ttu-id="5adc2-154">функция **TestArrayInStruct**, экспортированная из PinvokeLib.dll.</span><span class="sxs-lookup"><span data-stu-id="5adc2-154">**TestArrayInStruct** exported from PinvokeLib.dll.</span></span>

    ```cpp
    void TestArrayInStruct(MYARRAYSTRUCT* pStruct);
    ```

<span data-ttu-id="5adc2-155">[PinvokeLib.dll](marshaling-data-with-platform-invoke.md#pinvokelibdll) — это пользовательская неуправляемая библиотека, содержащая реализацию вышеуказанных функций и четырех структур: **MYPERSON**, **MYPERSON2**, **MYPERSON3** и **MYARRAYSTRUCT**.</span><span class="sxs-lookup"><span data-stu-id="5adc2-155">[PinvokeLib.dll](marshaling-data-with-platform-invoke.md#pinvokelibdll) is a custom unmanaged library that contains implementations for the previously listed functions and four structures: **MYPERSON**, **MYPERSON2**, **MYPERSON3**, and **MYARRAYSTRUCT**.</span></span> <span data-ttu-id="5adc2-156">Эти структуры содержат следующие элементы:</span><span class="sxs-lookup"><span data-stu-id="5adc2-156">These structures contain the following elements:</span></span>

```cpp
typedef struct _MYPERSON
{
   char* first;
   char* last;
} MYPERSON, *LP_MYPERSON;

typedef struct _MYPERSON2
{
   MYPERSON* person;
   int age;
} MYPERSON2, *LP_MYPERSON2;

typedef struct _MYPERSON3
{
   MYPERSON person;
   int age;
} MYPERSON3;

typedef struct _MYARRAYSTRUCT
{
   bool flag;
   int vals[ 3 ];
} MYARRAYSTRUCT;
```

<span data-ttu-id="5adc2-157">Управляемые структуры `MyPerson`, `MyPerson2`, `MyPerson3` и `MyArrayStruct` обладают следующими характеристиками:</span><span class="sxs-lookup"><span data-stu-id="5adc2-157">The managed `MyPerson`, `MyPerson2`, `MyPerson3`, and `MyArrayStruct` structures have the following characteristic:</span></span>

- <span data-ttu-id="5adc2-158">Структура `MyPerson` содержит только члены-строки.</span><span class="sxs-lookup"><span data-stu-id="5adc2-158">`MyPerson` contains only string members.</span></span> <span data-ttu-id="5adc2-159">Поле [CharSet](specifying-a-character-set.md) задает формат строк ANSI при передаче строки в неуправляемую функцию.</span><span class="sxs-lookup"><span data-stu-id="5adc2-159">The [CharSet](specifying-a-character-set.md) field sets the strings to ANSI format when passed to the unmanaged function.</span></span>

- <span data-ttu-id="5adc2-160">`MyPerson2` содержит указатель **IntPtr** на структуру `MyPerson`.</span><span class="sxs-lookup"><span data-stu-id="5adc2-160">`MyPerson2` contains an **IntPtr** to the `MyPerson` structure.</span></span> <span data-ttu-id="5adc2-161">Тип **IntPtr** заменяет исходный указатель на неуправляемую структуру, так как приложения .NET Framework не используют указатели, если код не помечен как **небезопасный**.</span><span class="sxs-lookup"><span data-stu-id="5adc2-161">The **IntPtr** type replaces the original pointer to the unmanaged structure because .NET Framework applications do not use pointers unless the code is marked **unsafe**.</span></span>

- <span data-ttu-id="5adc2-162">Структура `MyPerson3` содержит структуру `MyPerson` в качестве внедренной.</span><span class="sxs-lookup"><span data-stu-id="5adc2-162">`MyPerson3` contains `MyPerson` as an embedded structure.</span></span> <span data-ttu-id="5adc2-163">Внедренную структуру можно выровнять путем помещения ее элементов прямо в основную структуру, или ее можно оставить внедренной, как показано в примере.</span><span class="sxs-lookup"><span data-stu-id="5adc2-163">A structure embedded within another structure can be flattened by placing the elements of the embedded structure directly into the main structure, or it can be left as an embedded structure, as is done in this sample.</span></span>

- <span data-ttu-id="5adc2-164">Структура `MyArrayStruct` содержит массив целочисленных значений.</span><span class="sxs-lookup"><span data-stu-id="5adc2-164">`MyArrayStruct` contains an array of integers.</span></span> <span data-ttu-id="5adc2-165">Атрибут <xref:System.Runtime.InteropServices.MarshalAsAttribute> задает для перечисления <xref:System.Runtime.InteropServices.UnmanagedType> значение **ByValArray**, которое используется для указания количества элементов в массиве.</span><span class="sxs-lookup"><span data-stu-id="5adc2-165">The <xref:System.Runtime.InteropServices.MarshalAsAttribute> attribute sets the <xref:System.Runtime.InteropServices.UnmanagedType> enumeration value to **ByValArray**, which is used to indicate the number of elements in the array.</span></span>

<span data-ttu-id="5adc2-166">Для всех структур в этом примере применяется атрибут <xref:System.Runtime.InteropServices.StructLayoutAttribute>, гарантирующий последовательное размещение элементов в памяти в порядке их появления.</span><span class="sxs-lookup"><span data-stu-id="5adc2-166">For all structures in this sample, the <xref:System.Runtime.InteropServices.StructLayoutAttribute> attribute is applied to ensure that the members are arranged in memory sequentially, in the order in which they appear.</span></span>

<span data-ttu-id="5adc2-167">Класс `NativeMethods` содержит управляемые прототипы методов `TestStructInStruct`, `TestStructInStruct3` и `TestArrayInStruct`, вызываемые классом `App`.</span><span class="sxs-lookup"><span data-stu-id="5adc2-167">The `NativeMethods` class contains managed prototypes for the `TestStructInStruct`, `TestStructInStruct3`, and `TestArrayInStruct` methods called by the `App` class.</span></span> <span data-ttu-id="5adc2-168">Каждый прототип объявляет один параметр указанным ниже способом.</span><span class="sxs-lookup"><span data-stu-id="5adc2-168">Each prototype declares a single parameter, as follows:</span></span>

- <span data-ttu-id="5adc2-169">`TestStructInStruct` объявляет в качестве своего параметра ссылку на тип `MyPerson2`.</span><span class="sxs-lookup"><span data-stu-id="5adc2-169">`TestStructInStruct` declares a reference to type `MyPerson2` as its parameter.</span></span>

- <span data-ttu-id="5adc2-170">`TestStructInStruct3` в качестве своего параметра объявляет тип `MyPerson3` и передает параметр по значению.</span><span class="sxs-lookup"><span data-stu-id="5adc2-170">`TestStructInStruct3` declares type `MyPerson3` as its parameter and passes the parameter by value.</span></span>

- <span data-ttu-id="5adc2-171">`TestArrayInStruct` объявляет в качестве своего параметра ссылку на тип `MyArrayStruct`.</span><span class="sxs-lookup"><span data-stu-id="5adc2-171">`TestArrayInStruct` declares a reference to type `MyArrayStruct` as its parameter.</span></span>

<span data-ttu-id="5adc2-172">Структуры, выступающие в роли аргументов методов, передаются по значению, если параметр не содержит ключевого слова **ref** (**ByRef** в Visual Basic).</span><span class="sxs-lookup"><span data-stu-id="5adc2-172">Structures as arguments to methods are passed by value unless the parameter contains the **ref** (**ByRef** in Visual Basic) keyword.</span></span> <span data-ttu-id="5adc2-173">Например, метод `TestStructInStruct` передает в неуправляемый код ссылку (значение адреса) на объект типа `MyPerson2`.</span><span class="sxs-lookup"><span data-stu-id="5adc2-173">For example, the `TestStructInStruct` method passes a reference (the value of an address) to an object of type `MyPerson2` to unmanaged code.</span></span> <span data-ttu-id="5adc2-174">Для работы со структурой, на которую указывает `MyPerson2`, в примере с помощью методов <xref:System.Runtime.InteropServices.Marshal.AllocCoTaskMem%2A?displayProperty=nameWithType> и <xref:System.Runtime.InteropServices.Marshal.SizeOf%2A?displayProperty=nameWithType> создается буфер заданного размера и возвращается его адрес.</span><span class="sxs-lookup"><span data-stu-id="5adc2-174">To manipulate the structure that `MyPerson2` points to, the sample creates a buffer of a specified size and returns its address by combining the <xref:System.Runtime.InteropServices.Marshal.AllocCoTaskMem%2A?displayProperty=nameWithType> and <xref:System.Runtime.InteropServices.Marshal.SizeOf%2A?displayProperty=nameWithType> methods.</span></span> <span data-ttu-id="5adc2-175">Далее в неуправляемый буфер копируется содержимое управляемой структуры.</span><span class="sxs-lookup"><span data-stu-id="5adc2-175">Next, the sample copies the content of the managed structure to the unmanaged buffer.</span></span> <span data-ttu-id="5adc2-176">Наконец, используются метод <xref:System.Runtime.InteropServices.Marshal.PtrToStructure%2A?displayProperty=nameWithType> для маршалинга данных из неуправляемого буфера в управляемый объект и метод <xref:System.Runtime.InteropServices.Marshal.FreeCoTaskMem%2A?displayProperty=nameWithType> для освобождения неуправляемого блока памяти.</span><span class="sxs-lookup"><span data-stu-id="5adc2-176">Finally, the sample uses the <xref:System.Runtime.InteropServices.Marshal.PtrToStructure%2A?displayProperty=nameWithType> method to marshal data from the unmanaged buffer to a managed object and the <xref:System.Runtime.InteropServices.Marshal.FreeCoTaskMem%2A?displayProperty=nameWithType> method to free the unmanaged block of memory.</span></span>

### <a name="declaring-prototypes"></a><span data-ttu-id="5adc2-177">Объявление прототипов</span><span class="sxs-lookup"><span data-stu-id="5adc2-177">Declaring Prototypes</span></span>

[!code-cpp[Conceptual.Interop.Marshaling#23](~/samples/snippets/cpp/VS_Snippets_CLR/conceptual.interop.marshaling/cpp/structures.cpp#23)]
[!code-csharp[Conceptual.Interop.Marshaling#23](~/samples/snippets/csharp/VS_Snippets_CLR/conceptual.interop.marshaling/cs/structures.cs#23)]
[!code-vb[Conceptual.Interop.Marshaling#23](~/samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.interop.marshaling/vb/structures.vb#23)]

### <a name="calling-functions"></a><span data-ttu-id="5adc2-178">Вызов функций</span><span class="sxs-lookup"><span data-stu-id="5adc2-178">Calling Functions</span></span>

[!code-cpp[Conceptual.Interop.Marshaling#24](~/samples/snippets/cpp/VS_Snippets_CLR/conceptual.interop.marshaling/cpp/structures.cpp#24)]
[!code-csharp[Conceptual.Interop.Marshaling#24](~/samples/snippets/csharp/VS_Snippets_CLR/conceptual.interop.marshaling/cs/structures.cs#24)]
[!code-vb[Conceptual.Interop.Marshaling#24](~/samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.interop.marshaling/vb/structures.vb#24)]

## <a name="findfile-sample"></a><span data-ttu-id="5adc2-179">пример FindFile</span><span class="sxs-lookup"><span data-stu-id="5adc2-179">FindFile sample</span></span>

<span data-ttu-id="5adc2-180">В этом примере показан способ передачи структуры, содержащей другую, внедренную структуру, в неуправляемую функцию.</span><span class="sxs-lookup"><span data-stu-id="5adc2-180">This sample demonstrates how to pass a structure that contains a second, embedded structure to an unmanaged function.</span></span> <span data-ttu-id="5adc2-181">Также показано, как с помощью атрибута <xref:System.Runtime.InteropServices.MarshalAsAttribute> объявить массив фиксированной длины внутри структуры.</span><span class="sxs-lookup"><span data-stu-id="5adc2-181">It also demonstrates how to use the <xref:System.Runtime.InteropServices.MarshalAsAttribute> attribute to declare a fixed-length array within the structure.</span></span> <span data-ttu-id="5adc2-182">В этом примере элементы внедренной структуры добавляются в родительскую структуру.</span><span class="sxs-lookup"><span data-stu-id="5adc2-182">In this sample, the embedded structure elements are added to the parent structure.</span></span> <span data-ttu-id="5adc2-183">Пример внедренной структуры (не преобразованной в плоскую структуру) см. в разделе [Пример структур](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/eadtsekz(v=vs.100)).</span><span class="sxs-lookup"><span data-stu-id="5adc2-183">For a sample of an embedded structure that is not flattened, see [Structures Sample](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/eadtsekz(v=vs.100)).</span></span>

<span data-ttu-id="5adc2-184">В примере FindFile используются следующие неуправляемые функции, показанные с исходными объявлениями:</span><span class="sxs-lookup"><span data-stu-id="5adc2-184">The FindFile sample uses the following unmanaged function, shown with its original function declaration:</span></span>

- <span data-ttu-id="5adc2-185">функция **FindFirstFile**, экспортированная из Kernel32.dll.</span><span class="sxs-lookup"><span data-stu-id="5adc2-185">**FindFirstFile** exported from Kernel32.dll.</span></span>

    ```cpp
    HANDLE FindFirstFile(LPCTSTR lpFileName, LPWIN32_FIND_DATA lpFindFileData);
    ```

<span data-ttu-id="5adc2-186">Исходная структура, переданная в функцию, содержит следующие элементы:</span><span class="sxs-lookup"><span data-stu-id="5adc2-186">The original structure passed to the function contains the following elements:</span></span>

```cpp
typedef struct _WIN32_FIND_DATA
{
  DWORD    dwFileAttributes;
  FILETIME ftCreationTime;
  FILETIME ftLastAccessTime;
  FILETIME ftLastWriteTime;
  DWORD    nFileSizeHigh;
  DWORD    nFileSizeLow;
  DWORD    dwReserved0;
  DWORD    dwReserved1;
  TCHAR    cFileName[ MAX_PATH ];
  TCHAR    cAlternateFileName[ 14 ];
} WIN32_FIND_DATA, *PWIN32_FIND_DATA;
```

<span data-ttu-id="5adc2-187">В этом примере класс `FindData` содержит члены данных, соответствующие каждому элементу исходной и внедренной структур.</span><span class="sxs-lookup"><span data-stu-id="5adc2-187">In this sample, the `FindData` class contains a corresponding data member for each element of the original structure and the embedded structure.</span></span> <span data-ttu-id="5adc2-188">Вместо двух исходных символьных буферов класс подставляет строки.</span><span class="sxs-lookup"><span data-stu-id="5adc2-188">In place of two original character buffers, the class substitutes strings.</span></span> <span data-ttu-id="5adc2-189">Атрибут **MarshalAsAttribute** задает для перечисления <xref:System.Runtime.InteropServices.UnmanagedType> значение **ByValTStr**, которое используется для идентификации встроенных символьных массивов фиксированной длины в неуправляемых структурах.</span><span class="sxs-lookup"><span data-stu-id="5adc2-189">**MarshalAsAttribute** sets the <xref:System.Runtime.InteropServices.UnmanagedType> enumeration to **ByValTStr**, which is used to identify the inline, fixed-length character arrays that appear within the unmanaged structures.</span></span>

<span data-ttu-id="5adc2-190">Класс `NativeMethods` содержит управляемый прототип метода `FindFirstFile`, передающий класс `FindData` в качестве параметра.</span><span class="sxs-lookup"><span data-stu-id="5adc2-190">The `NativeMethods` class contains a managed prototype of the `FindFirstFile` method, which passes the `FindData` class as a parameter.</span></span> <span data-ttu-id="5adc2-191">Этот параметр должен быть объявлен с атрибутами <xref:System.Runtime.InteropServices.InAttribute> и <xref:System.Runtime.InteropServices.OutAttribute>, так как классы, являющиеся ссылочными типами, по умолчанию передаются как параметры In.</span><span class="sxs-lookup"><span data-stu-id="5adc2-191">The parameter must be declared with the <xref:System.Runtime.InteropServices.InAttribute> and <xref:System.Runtime.InteropServices.OutAttribute> attributes because classes, which are reference types, are passed as In parameters by default.</span></span>

### <a name="declaring-prototypes"></a><span data-ttu-id="5adc2-192">Объявление прототипов</span><span class="sxs-lookup"><span data-stu-id="5adc2-192">Declaring Prototypes</span></span>

[!code-cpp[Conceptual.Interop.Marshaling#17](~/samples/snippets/cpp/VS_Snippets_CLR/conceptual.interop.marshaling/cpp/findfile.cpp#17)]
[!code-csharp[Conceptual.Interop.Marshaling#17](~/samples/snippets/csharp/VS_Snippets_CLR/conceptual.interop.marshaling/cs/findfile.cs#17)]
[!code-vb[Conceptual.Interop.Marshaling#17](~/samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.interop.marshaling/vb/findfile.vb#17)]

### <a name="calling-functions"></a><span data-ttu-id="5adc2-193">Вызов функций</span><span class="sxs-lookup"><span data-stu-id="5adc2-193">Calling Functions</span></span>

[!code-cpp[Conceptual.Interop.Marshaling#18](~/samples/snippets/cpp/VS_Snippets_CLR/conceptual.interop.marshaling/cpp/findfile.cpp#18)]
[!code-csharp[Conceptual.Interop.Marshaling#18](~/samples/snippets/csharp/VS_Snippets_CLR/conceptual.interop.marshaling/cs/findfile.cs#18)]
 [!code-vb[Conceptual.Interop.Marshaling#18](~/samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.interop.marshaling/vb/findfile.vb#18)]

## <a name="unions-sample"></a><span data-ttu-id="5adc2-194">пример Unions</span><span class="sxs-lookup"><span data-stu-id="5adc2-194">Unions sample</span></span>

<span data-ttu-id="5adc2-195">В этом примере показан способ передачи структур, содержащих только типы значений, а также структур, содержащих тип значения и строку, в качестве параметров в неуправляемую функцию, ожидающую объединения.</span><span class="sxs-lookup"><span data-stu-id="5adc2-195">This sample demonstrates how to pass structures containing only value types, and structures containing a value type and a string as parameters to an unmanaged function expecting a union.</span></span> <span data-ttu-id="5adc2-196">Объединение представляет собой ячейку памяти, которая может совместно использоваться двумя и более переменными.</span><span class="sxs-lookup"><span data-stu-id="5adc2-196">A union represents a memory location that can be shared by two or more variables.</span></span>

<span data-ttu-id="5adc2-197">В примере используются следующие неуправляемые функции, показанные с исходными объявлениями:</span><span class="sxs-lookup"><span data-stu-id="5adc2-197">The Unions sample uses the following unmanaged function, shown with its original function declaration:</span></span>

- <span data-ttu-id="5adc2-198">функция **TestUnion**, экспортированная из PinvokeLib.dll.</span><span class="sxs-lookup"><span data-stu-id="5adc2-198">**TestUnion** exported from PinvokeLib.dll.</span></span>

    ```cpp
    void TestUnion(MYUNION u, int type);
    ```

<span data-ttu-id="5adc2-199">[PinvokeLib.dll](marshaling-data-with-platform-invoke.md#pinvokelibdll) — это пользовательская неуправляемая библиотека, содержащая реализацию указанной выше функции и два объединения: **MYUNION** и **MYUNION2**.</span><span class="sxs-lookup"><span data-stu-id="5adc2-199">[PinvokeLib.dll](marshaling-data-with-platform-invoke.md#pinvokelibdll) is a custom unmanaged library that contains an implementation for the previously listed function and two unions, **MYUNION** and **MYUNION2**.</span></span> <span data-ttu-id="5adc2-200">Объединение содержит следующие элементы:</span><span class="sxs-lookup"><span data-stu-id="5adc2-200">The unions contain the following elements:</span></span>

```cpp
union MYUNION
{
    int number;
    double d;
}

union MYUNION2
{
    int i;
    char str[128];
};
```

<span data-ttu-id="5adc2-201">В управляемом коде объединения определяются как структуры.</span><span class="sxs-lookup"><span data-stu-id="5adc2-201">In managed code, unions are defined as structures.</span></span> <span data-ttu-id="5adc2-202">Структура `MyUnion` в качестве своих членов содержит два типа значений: целочисленный и число двойной точности.</span><span class="sxs-lookup"><span data-stu-id="5adc2-202">The `MyUnion` structure contains two value types as its members: an integer and a double.</span></span> <span data-ttu-id="5adc2-203">Для управления точным положением каждого члена данных задается атрибут <xref:System.Runtime.InteropServices.StructLayoutAttribute>.</span><span class="sxs-lookup"><span data-stu-id="5adc2-203">The <xref:System.Runtime.InteropServices.StructLayoutAttribute> attribute is set to control the precise position of each data member.</span></span> <span data-ttu-id="5adc2-204">Атрибут <xref:System.Runtime.InteropServices.FieldOffsetAttribute> предоставляет физическое положение полей внутри неуправляемого представления объединения.</span><span class="sxs-lookup"><span data-stu-id="5adc2-204">The <xref:System.Runtime.InteropServices.FieldOffsetAttribute> attribute provides the physical position of fields within the unmanaged representation of a union.</span></span> <span data-ttu-id="5adc2-205">Обратите внимание, что значения смещения у обоих членов одинаковы, что позволяет членам определять один и тот же участок памяти.</span><span class="sxs-lookup"><span data-stu-id="5adc2-205">Notice that both members have the same offset values, so the members can define the same piece of memory.</span></span>

<span data-ttu-id="5adc2-206">Объединения `MyUnion2_1` и `MyUnion2_2` содержат тип значения (целое число) и строку соответственно.</span><span class="sxs-lookup"><span data-stu-id="5adc2-206">`MyUnion2_1` and `MyUnion2_2` contain a value type (integer) and a string, respectively.</span></span> <span data-ttu-id="5adc2-207">В управляемом коде типы значений и ссылочные типы не могут перекрываться.</span><span class="sxs-lookup"><span data-stu-id="5adc2-207">In managed code, value types and reference types are not permitted to overlap.</span></span> <span data-ttu-id="5adc2-208">Чтобы при вызове одной и той же неуправляемой функции вызывающий объект мог использовать оба типа, в этом примере применяется перегрузка метода.</span><span class="sxs-lookup"><span data-stu-id="5adc2-208">This sample uses method overloading to enable the caller to use both types when calling the same unmanaged function.</span></span> <span data-ttu-id="5adc2-209">Структура `MyUnion2_1` задана явным образом и имеет точное значение смещения.</span><span class="sxs-lookup"><span data-stu-id="5adc2-209">The layout of `MyUnion2_1` is explicit and has a precise offset value.</span></span> <span data-ttu-id="5adc2-210">Напротив, `MyUnion2_2` имеет последовательную структуру, так как структуры, заданные явным образом, нельзя использовать со ссылочными типами.</span><span class="sxs-lookup"><span data-stu-id="5adc2-210">In contrast, `MyUnion2_2` has a sequential layout, because explicit layouts are not permitted with reference types.</span></span> <span data-ttu-id="5adc2-211">Атрибут <xref:System.Runtime.InteropServices.MarshalAsAttribute> задает для перечисления <xref:System.Runtime.InteropServices.UnmanagedType> значение **ByValTStr**, которое используется для идентификации встроенных символьных массивов фиксированной длины в неуправляемом представлении объединения.</span><span class="sxs-lookup"><span data-stu-id="5adc2-211">The <xref:System.Runtime.InteropServices.MarshalAsAttribute> attribute sets the <xref:System.Runtime.InteropServices.UnmanagedType> enumeration to **ByValTStr**, which is used to identify the inline, fixed-length character arrays that appear within the unmanaged representation of the union.</span></span>

<span data-ttu-id="5adc2-212">Класс `NativeMethods` содержит прототипы для методов `TestUnion` и `TestUnion2`.</span><span class="sxs-lookup"><span data-stu-id="5adc2-212">The `NativeMethods` class contains the prototypes for the `TestUnion` and `TestUnion2` methods.</span></span> <span data-ttu-id="5adc2-213">`TestUnion2` перегружается для объявления `MyUnion2_1` или `MyUnion2_2` в качестве параметров.</span><span class="sxs-lookup"><span data-stu-id="5adc2-213">`TestUnion2` is overloaded to declare `MyUnion2_1` or `MyUnion2_2` as parameters.</span></span>

### <a name="declaring-prototypes"></a><span data-ttu-id="5adc2-214">Объявление прототипов</span><span class="sxs-lookup"><span data-stu-id="5adc2-214">Declaring Prototypes</span></span>

[!code-cpp[Conceptual.Interop.Marshaling#28](~/samples/snippets/cpp/VS_Snippets_CLR/conceptual.interop.marshaling/cpp/unions.cpp#28)]
[!code-csharp[Conceptual.Interop.Marshaling#28](~/samples/snippets/csharp/VS_Snippets_CLR/conceptual.interop.marshaling/cs/unions.cs#28)]
[!code-vb[Conceptual.Interop.Marshaling#28](~/samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.interop.marshaling/vb/unions.vb#28)]

### <a name="calling-functions"></a><span data-ttu-id="5adc2-215">Вызов функций</span><span class="sxs-lookup"><span data-stu-id="5adc2-215">Calling Functions</span></span>

[!code-cpp[Conceptual.Interop.Marshaling#29](~/samples/snippets/cpp/VS_Snippets_CLR/conceptual.interop.marshaling/cpp/unions.cpp#29)]
[!code-csharp[Conceptual.Interop.Marshaling#29](~/samples/snippets/csharp/VS_Snippets_CLR/conceptual.interop.marshaling/cs/unions.cs#29)]
[!code-vb[Conceptual.Interop.Marshaling#29](~/samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.interop.marshaling/vb/unions.vb#29)]

## <a name="platform-sample"></a><span data-ttu-id="5adc2-216">Пример платформы</span><span class="sxs-lookup"><span data-stu-id="5adc2-216">Platform sample</span></span>

<span data-ttu-id="5adc2-217">В некоторых сценариях макеты `struct` и `union` могут различаться в зависимости от целевой платформы.</span><span class="sxs-lookup"><span data-stu-id="5adc2-217">In some scenarios, `struct` and `union` layouts can differ depending on the targeted platform.</span></span> <span data-ttu-id="5adc2-218">Например, рассмотрим тип [`STRRET`](/windows/win32/api/shtypes/ns-shtypes-strret) при определении в сценарии COM:</span><span class="sxs-lookup"><span data-stu-id="5adc2-218">For example, consider the [`STRRET`](/windows/win32/api/shtypes/ns-shtypes-strret) type when defined in a COM scenario:</span></span>

```c++
#include <pshpack8.h> /* Defines the packing of the struct */
typedef struct _STRRET
    {
    UINT uType;
    /* [switch_is][switch_type] */ union
        {
        /* [case()][string] */ LPWSTR pOleStr;
        /* [case()] */ UINT uOffset;
        /* [case()] */ char cStr[ 260 ];
        }  DUMMYUNIONNAME;
    }  STRRET;
#include <poppack.h>
```

<span data-ttu-id="5adc2-219">Приведенный выше `struct` объявляется с заголовками Windows, которые влияют на макет памяти типа.</span><span class="sxs-lookup"><span data-stu-id="5adc2-219">The above `struct` is declared with Windows' headers that influence the memory layout of the type.</span></span> <span data-ttu-id="5adc2-220">При определении в управляемой среде эти сведения о макете необходимы для правильного взаимодействия с машинным кодом.</span><span class="sxs-lookup"><span data-stu-id="5adc2-220">When defined in a managed environment, these layout details are needed to properly interoperate with native code.</span></span>

<span data-ttu-id="5adc2-221">Правильное управляемое определение этого типа в 32-разрядном процессе имеет следующий вид:</span><span class="sxs-lookup"><span data-stu-id="5adc2-221">The correct managed definition of this type in a 32-bit process is:</span></span>

``` CSharp
[StructLayout(LayoutKind.Explicit, Size = 264)]
public struct STRRET_32
{
    [FieldOffset(0)]
    public uint uType;

    [FieldOffset(4)]
    public IntPtr pOleStr;

    [FieldOffset(4)]
    public uint uOffset;

    [FieldOffset(4)]
    public IntPtr cStr;
}
```

<span data-ttu-id="5adc2-222">В 64-разрядном процессе размеры смещений полей *и* различаются.</span><span class="sxs-lookup"><span data-stu-id="5adc2-222">On a 64-bit process, the size *and* field offsets are different.</span></span> <span data-ttu-id="5adc2-223">Правильный макет:</span><span class="sxs-lookup"><span data-stu-id="5adc2-223">The correct layout is:</span></span>

``` CSharp
[StructLayout(LayoutKind.Explicit, Size = 272)]
public struct STRRET_64
{
    [FieldOffset(0)]
    public uint uType;

    [FieldOffset(8)]
    public IntPtr pOleStr;

    [FieldOffset(8)]
    public uint uOffset;

    [FieldOffset(8)]
    public IntPtr cStr;
}
```

<span data-ttu-id="5adc2-224">Неправильный выбор собственного макета в сценарии взаимодействия может привести к возникновению случайных сбоев или, что еще хуже, к неправильным вычислениям.</span><span class="sxs-lookup"><span data-stu-id="5adc2-224">Failure to properly consider the native layout in an interop scenario can result in random crashes or worse, incorrect computations.</span></span>

<span data-ttu-id="5adc2-225">По умолчанию сборки .NET могут работать как в 32-разрядной, так и в 64-разрядной версии среды выполнения .NET.</span><span class="sxs-lookup"><span data-stu-id="5adc2-225">By default, .NET assemblies can run in both a 32-bit and 64-bit version of the .NET runtime.</span></span> <span data-ttu-id="5adc2-226">Приложение должно ожидать от среды выполнения решения о том, какое из предыдущих определений использовать.</span><span class="sxs-lookup"><span data-stu-id="5adc2-226">The app must wait until run time to decide which of the previous definitions to use.</span></span>

<span data-ttu-id="5adc2-227">В следующем фрагменте кода показан пример выбора между 32-разрядным и 64-разрядным определением в среде выполнения.</span><span class="sxs-lookup"><span data-stu-id="5adc2-227">The following code snippet shows an example of how to choose between the 32-bit and 64-bit definition at run time.</span></span>

```CSharp
if (IntPtr.Size == 8)
{
    // Use the STRRET_64 definition
}
else
{
    Debug.Assert(IntPtr.Size == 4);
    // Use the STRRET_32 definition
}
```

## <a name="systime-sample"></a><span data-ttu-id="5adc2-228">Пример SysTime</span><span class="sxs-lookup"><span data-stu-id="5adc2-228">SysTime sample</span></span>

<span data-ttu-id="5adc2-229">В этом примере показано, как передать указатель на класс в неуправляемую функцию, ожидающую указатель на структуру.</span><span class="sxs-lookup"><span data-stu-id="5adc2-229">This sample demonstrates how to pass a pointer to a class to an unmanaged function that expects a pointer to a structure.</span></span>

<span data-ttu-id="5adc2-230">В примере используется следующая неуправляемая функция, показанная с исходным объявлением:</span><span class="sxs-lookup"><span data-stu-id="5adc2-230">The SysTime sample uses the following unmanaged function, shown with its original function declaration:</span></span>

- <span data-ttu-id="5adc2-231">функция **GetSystemTime**, экспортированная из Kernel32.dll.</span><span class="sxs-lookup"><span data-stu-id="5adc2-231">**GetSystemTime** exported from Kernel32.dll.</span></span>

    ```cpp
    VOID GetSystemTime(LPSYSTEMTIME lpSystemTime);
    ```

<span data-ttu-id="5adc2-232">Исходная структура, переданная в функцию, содержит следующие элементы:</span><span class="sxs-lookup"><span data-stu-id="5adc2-232">The original structure passed to the function contains the following elements:</span></span>

```cpp
typedef struct _SYSTEMTIME {
    WORD wYear;
    WORD wMonth;
    WORD wDayOfWeek;
    WORD wDay;
    WORD wHour;
    WORD wMinute;
    WORD wSecond;
    WORD wMilliseconds;
} SYSTEMTIME, *PSYSTEMTIME;
```

<span data-ttu-id="5adc2-233">В этом примере класс `SystemTime` содержит элементы исходной структуры, представленные в виде членов класса.</span><span class="sxs-lookup"><span data-stu-id="5adc2-233">In this sample, the `SystemTime` class contains the elements of the original structure represented as class members.</span></span> <span data-ttu-id="5adc2-234">Чтобы гарантировать последовательное размещение членов в памяти в порядке их появления, применяется атрибут <xref:System.Runtime.InteropServices.StructLayoutAttribute> .</span><span class="sxs-lookup"><span data-stu-id="5adc2-234">The <xref:System.Runtime.InteropServices.StructLayoutAttribute> attribute is set to ensure that the members are arranged in memory sequentially, in the order in which they appear.</span></span>

<span data-ttu-id="5adc2-235">Класс `NativeMethods` содержит управляемый прототип метода `GetSystemTime`, который по умолчанию передает класс `SystemTime` в качестве параметра In или Out.</span><span class="sxs-lookup"><span data-stu-id="5adc2-235">The `NativeMethods` class contains a managed prototype of the `GetSystemTime` method, which passes the `SystemTime` class as an In/Out parameter by default.</span></span> <span data-ttu-id="5adc2-236">Этот параметр должен быть объявлен с атрибутами <xref:System.Runtime.InteropServices.InAttribute> и <xref:System.Runtime.InteropServices.OutAttribute>, так как классы, являющиеся ссылочными типами, по умолчанию передаются как параметры In.</span><span class="sxs-lookup"><span data-stu-id="5adc2-236">The parameter must be declared with the <xref:System.Runtime.InteropServices.InAttribute> and <xref:System.Runtime.InteropServices.OutAttribute> attributes because classes, which are reference types, are passed as In parameters by default.</span></span> <span data-ttu-id="5adc2-237">Чтобы вызывающий объект получал результаты, необходимо явным образом применить [атрибуты направления](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/77e6taeh(v=vs.100)).</span><span class="sxs-lookup"><span data-stu-id="5adc2-237">For the caller to receive the results, these [directional attributes](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/77e6taeh(v=vs.100)) must be applied explicitly.</span></span> <span data-ttu-id="5adc2-238">Класс `App` создает экземпляр класса `SystemTime` и осуществляет доступ к его полям данных.</span><span class="sxs-lookup"><span data-stu-id="5adc2-238">The `App` class creates a new instance of the `SystemTime` class and accesses its data fields.</span></span>

### <a name="code-samples"></a><span data-ttu-id="5adc2-239">Примеры кода</span><span class="sxs-lookup"><span data-stu-id="5adc2-239">Code Samples</span></span>

[!code-cpp[Conceptual.Interop.Marshaling#25](~/samples/snippets/cpp/VS_Snippets_CLR/conceptual.interop.marshaling/cpp/systime.cpp#25)]
[!code-csharp[Conceptual.Interop.Marshaling#25](~/samples/snippets/csharp/VS_Snippets_CLR/conceptual.interop.marshaling/cs/systime.cs#25)]
[!code-vb[Conceptual.Interop.Marshaling#25](~/samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.interop.marshaling/vb/systime.vb#25)]

## <a name="outarrayofstructs-sample"></a><span data-ttu-id="5adc2-240">Пример OutArrayOfStructs</span><span class="sxs-lookup"><span data-stu-id="5adc2-240">OutArrayOfStructs sample</span></span>

<span data-ttu-id="5adc2-241">В этом примере показано, как передать в неуправляемую функцию массив структур, содержащий целочисленные значения и строки, в виде параметров Out.</span><span class="sxs-lookup"><span data-stu-id="5adc2-241">This sample shows how to pass an array of structures that contains integers and strings as Out parameters to an unmanaged function.</span></span>

<span data-ttu-id="5adc2-242">В этом примере демонстрируется, как вызывать собственную функцию с помощью класса <xref:System.Runtime.InteropServices.Marshal> и небезопасного кода.</span><span class="sxs-lookup"><span data-stu-id="5adc2-242">This sample demonstrates how to call a native function by using the <xref:System.Runtime.InteropServices.Marshal> class and by using unsafe code.</span></span>

<span data-ttu-id="5adc2-243">В примере используются функции-оболочки и вызовы неуправляемого кода, определенные в библиотеке [PinvokeLib.dll](marshaling-data-with-platform-invoke.md#pinvokelibdll) и содержащиеся в исходных файлах.</span><span class="sxs-lookup"><span data-stu-id="5adc2-243">This sample uses a wrapper functions and platform invokes defined in [PinvokeLib.dll](marshaling-data-with-platform-invoke.md#pinvokelibdll), also provided in the source files.</span></span> <span data-ttu-id="5adc2-244">В нем используется функция `TestOutArrayOfStructs` и структура `MYSTRSTRUCT2`.</span><span class="sxs-lookup"><span data-stu-id="5adc2-244">It uses the `TestOutArrayOfStructs` function and the `MYSTRSTRUCT2` structure.</span></span> <span data-ttu-id="5adc2-245">Структура содержит следующие элементы:</span><span class="sxs-lookup"><span data-stu-id="5adc2-245">The structure contains the following elements:</span></span>

```cpp
typedef struct _MYSTRSTRUCT2
{
   char* buffer;
   UINT size;
} MYSTRSTRUCT2;
```

<span data-ttu-id="5adc2-246">Класс `MyStruct` содержит строковый объект из символов ANSI.</span><span class="sxs-lookup"><span data-stu-id="5adc2-246">The `MyStruct` class contains a string object of ANSI characters.</span></span> <span data-ttu-id="5adc2-247">Поле <xref:System.Runtime.InteropServices.DllImportAttribute.CharSet> определяет формат ANSI.</span><span class="sxs-lookup"><span data-stu-id="5adc2-247">The <xref:System.Runtime.InteropServices.DllImportAttribute.CharSet> field specifies ANSI format.</span></span> <span data-ttu-id="5adc2-248">`MyUnsafeStruct` — это структура, содержащая тип <xref:System.IntPtr> вместо строки.</span><span class="sxs-lookup"><span data-stu-id="5adc2-248">`MyUnsafeStruct`, is a structure containing an <xref:System.IntPtr> type instead of a string.</span></span>

<span data-ttu-id="5adc2-249">Класс `NativeMethods` содержит перегруженный метод прототипа `TestOutArrayOfStructs`.</span><span class="sxs-lookup"><span data-stu-id="5adc2-249">The `NativeMethods` class contains the overloaded `TestOutArrayOfStructs` prototype method.</span></span> <span data-ttu-id="5adc2-250">Если в качестве параметра метод объявляет указатель, класс должен быть помечен зарезервированным словом `unsafe`.</span><span class="sxs-lookup"><span data-stu-id="5adc2-250">If a method declares a pointer as a parameter, the class should be marked with the `unsafe` keyword.</span></span> <span data-ttu-id="5adc2-251">Так как Visual Basic не может использовать небезопасный код, перегруженный метод, модификатор unsafe и структуры `MyUnsafeStruct` не нужны.</span><span class="sxs-lookup"><span data-stu-id="5adc2-251">Because Visual Basic cannot use unsafe code, the overloaded method, unsafe modifier, and the `MyUnsafeStruct` structure are unnecessary.</span></span>

<span data-ttu-id="5adc2-252">Класс `App` реализует метод `UsingMarshaling`, который выполняет все задачи, необходимые для передачи массива.</span><span class="sxs-lookup"><span data-stu-id="5adc2-252">The `App` class implements the `UsingMarshaling` method, which performs all the tasks necessary to pass the array.</span></span> <span data-ttu-id="5adc2-253">Чтобы указать, что данные передаются от вызываемого объекта к вызывающему, массив помечается зарезервированным словом `out` (`ByRef` в Visual Basic).</span><span class="sxs-lookup"><span data-stu-id="5adc2-253">The array is marked with the `out` (`ByRef` in Visual Basic) keyword to indicate that data passes from callee to caller.</span></span> <span data-ttu-id="5adc2-254">Реализация использует следующие методы класса <xref:System.Runtime.InteropServices.Marshal>:</span><span class="sxs-lookup"><span data-stu-id="5adc2-254">The implementation uses the following <xref:System.Runtime.InteropServices.Marshal> class methods:</span></span>

- <span data-ttu-id="5adc2-255">метод <xref:System.Runtime.InteropServices.Marshal.PtrToStructure%2A> для маршалинга данных из неуправляемого буфера в управляемый объект;</span><span class="sxs-lookup"><span data-stu-id="5adc2-255"><xref:System.Runtime.InteropServices.Marshal.PtrToStructure%2A> to marshal data from the unmanaged buffer to a managed object.</span></span>

- <span data-ttu-id="5adc2-256">метод <xref:System.Runtime.InteropServices.Marshal.DestroyStructure%2A> для освобождения памяти, зарезервированной для строк структуры;</span><span class="sxs-lookup"><span data-stu-id="5adc2-256"><xref:System.Runtime.InteropServices.Marshal.DestroyStructure%2A> to release the memory reserved for strings in the structure.</span></span>

- <span data-ttu-id="5adc2-257">метод <xref:System.Runtime.InteropServices.Marshal.FreeCoTaskMem%2A> для освобождения памяти, зарезервированной для массива.</span><span class="sxs-lookup"><span data-stu-id="5adc2-257"><xref:System.Runtime.InteropServices.Marshal.FreeCoTaskMem%2A> to release the memory reserved for the array.</span></span>

<span data-ttu-id="5adc2-258">Как упоминалось ранее, C# допускает небезопасный код, который Visual Basic не поддерживает.</span><span class="sxs-lookup"><span data-stu-id="5adc2-258">As previously mentioned, C# allows unsafe code and Visual Basic does not.</span></span> <span data-ttu-id="5adc2-259">В примере кода C# `UsingUnsafePointer` является альтернативной реализацией метода, в которой для обратной передачи массива, содержащего структуру `MyUnsafeStruct`, вместо класса <xref:System.Runtime.InteropServices.Marshal> используются указатели.</span><span class="sxs-lookup"><span data-stu-id="5adc2-259">In the C# sample, `UsingUnsafePointer` is an alternative method implementation that uses pointers instead of the <xref:System.Runtime.InteropServices.Marshal> class to pass back the array containing the `MyUnsafeStruct` structure.</span></span>

### <a name="declaring-prototypes"></a><span data-ttu-id="5adc2-260">Объявление прототипов</span><span class="sxs-lookup"><span data-stu-id="5adc2-260">Declaring Prototypes</span></span>

[!code-cpp[Conceptual.Interop.Marshaling#20](~/samples/snippets/cpp/VS_Snippets_CLR/conceptual.interop.marshaling/cpp/outarrayofstructs.cpp#20)]
[!code-csharp[Conceptual.Interop.Marshaling#20](~/samples/snippets/csharp/VS_Snippets_CLR/conceptual.interop.marshaling/cs/outarrayofstructs.cs#20)]
[!code-vb[Conceptual.Interop.Marshaling#20](~/samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.interop.marshaling/vb/outarrayofstructs.vb#20)]

### <a name="calling-functions"></a><span data-ttu-id="5adc2-261">Вызов функций</span><span class="sxs-lookup"><span data-stu-id="5adc2-261">Calling Functions</span></span>

[!code-cpp[Conceptual.Interop.Marshaling#21](~/samples/snippets/cpp/VS_Snippets_CLR/conceptual.interop.marshaling/cpp/outarrayofstructs.cpp#21)]
[!code-csharp[Conceptual.Interop.Marshaling#21](~/samples/snippets/csharp/VS_Snippets_CLR/conceptual.interop.marshaling/cs/outarrayofstructs.cs#21)]
[!code-vb[Conceptual.Interop.Marshaling#21](~/samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.interop.marshaling/vb/outarrayofstructs.vb#21)]

## <a name="see-also"></a><span data-ttu-id="5adc2-262">См. также</span><span class="sxs-lookup"><span data-stu-id="5adc2-262">See also</span></span>

- [<span data-ttu-id="5adc2-263">Маршалинг данных при вызове неуправляемого кода</span><span class="sxs-lookup"><span data-stu-id="5adc2-263">Marshaling Data with Platform Invoke</span></span>](marshaling-data-with-platform-invoke.md)
- [<span data-ttu-id="5adc2-264">Mаршалинг строк</span><span class="sxs-lookup"><span data-stu-id="5adc2-264">Marshaling Strings</span></span>](marshaling-strings.md)
- [<span data-ttu-id="5adc2-265">Маршалинг различных типов массивов</span><span class="sxs-lookup"><span data-stu-id="5adc2-265">Marshaling Different Types of Arrays</span></span>](marshaling-different-types-of-arrays.md)
