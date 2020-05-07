---
title: Маршалинг классов, структур и объединений
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
ms.openlocfilehash: 708ed6a232950cb69796f105f6f198749ed53a24
ms.sourcegitcommit: 5988e9a29cedb8757320817deda3c08c6f44a6aa
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/28/2020
ms.locfileid: "82200019"
---
# <a name="marshaling-classes-structures-and-unions"></a><span data-ttu-id="845ac-102">Маршалинг классов, структур и объединений</span><span class="sxs-lookup"><span data-stu-id="845ac-102">Marshaling Classes, Structures, and Unions</span></span>

<span data-ttu-id="845ac-103">Классы и структуры в .NET Framework похожи.</span><span class="sxs-lookup"><span data-stu-id="845ac-103">Classes and structures are similar in the .NET Framework.</span></span> <span data-ttu-id="845ac-104">И те и другие могут иметь поля, свойства и события.</span><span class="sxs-lookup"><span data-stu-id="845ac-104">Both can have fields, properties, and events.</span></span> <span data-ttu-id="845ac-105">Они также могут иметь статические и нестатические методы.</span><span class="sxs-lookup"><span data-stu-id="845ac-105">They can also have static and nonstatic methods.</span></span> <span data-ttu-id="845ac-106">Примечательным отличием является то, что структуры являются типами значений, а классы — ссылочными типами.</span><span class="sxs-lookup"><span data-stu-id="845ac-106">One notable difference is that structures are value types and classes are reference types.</span></span>

<span data-ttu-id="845ac-107">В таблице ниже представлены варианты маршалинга классов, структур и объединений, описывается их применение и приводятся ссылки на соответствующие примеры вызова неуправляемого кода.</span><span class="sxs-lookup"><span data-stu-id="845ac-107">The following table lists marshaling options for classes, structures, and unions; describes their usage; and provides a link to the corresponding platform invoke sample.</span></span>

|<span data-ttu-id="845ac-108">Type</span><span class="sxs-lookup"><span data-stu-id="845ac-108">Type</span></span>|<span data-ttu-id="845ac-109">Описание</span><span class="sxs-lookup"><span data-stu-id="845ac-109">Description</span></span>|<span data-ttu-id="845ac-110">Пример</span><span class="sxs-lookup"><span data-stu-id="845ac-110">Sample</span></span>|
|----------|-----------------|------------|
|<span data-ttu-id="845ac-111">Класс по значению.</span><span class="sxs-lookup"><span data-stu-id="845ac-111">Class by value.</span></span>|<span data-ttu-id="845ac-112">Передает класс с целочисленными членами в качестве параметра In или Out (как и в случае управляемого класса).</span><span class="sxs-lookup"><span data-stu-id="845ac-112">Passes a class with integer members as an In/Out parameter, like the managed case.</span></span>|[<span data-ttu-id="845ac-113">Пример SysTime</span><span class="sxs-lookup"><span data-stu-id="845ac-113">SysTime sample</span></span>](#systime-sample)|
|<span data-ttu-id="845ac-114">Структура по значению.</span><span class="sxs-lookup"><span data-stu-id="845ac-114">Structure by value.</span></span>|<span data-ttu-id="845ac-115">Передает структуры в качестве параметров In.</span><span class="sxs-lookup"><span data-stu-id="845ac-115">Passes structures as In parameters.</span></span>|[<span data-ttu-id="845ac-116">Пример структур</span><span class="sxs-lookup"><span data-stu-id="845ac-116">Structures sample</span></span>](#structures-sample)|
|<span data-ttu-id="845ac-117">Структура по ссылке.</span><span class="sxs-lookup"><span data-stu-id="845ac-117">Structure by reference.</span></span>|<span data-ttu-id="845ac-118">Передает структуры в качестве параметров In и Out.</span><span class="sxs-lookup"><span data-stu-id="845ac-118">Passes structures as In/Out parameters.</span></span>|<span data-ttu-id="845ac-119">[Пример OSInfo](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/795sy883(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="845ac-119">[OSInfo sample](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/795sy883(v=vs.100))</span></span>|
|<span data-ttu-id="845ac-120">Структура с вложенными структурами (выровненная).</span><span class="sxs-lookup"><span data-stu-id="845ac-120">Structure with nested structures (flattened).</span></span>|<span data-ttu-id="845ac-121">Передает класс, представляющий структуру с вложенными структурами, в неуправляемую функцию.</span><span class="sxs-lookup"><span data-stu-id="845ac-121">Passes a class that represents a structure with nested structures in the unmanaged function.</span></span> <span data-ttu-id="845ac-122">Структура выравнивается в одну большую структуру в управляемом прототипе.</span><span class="sxs-lookup"><span data-stu-id="845ac-122">The structure is flattened to one big structure in the managed prototype.</span></span>|[<span data-ttu-id="845ac-123">Пример FindFile</span><span class="sxs-lookup"><span data-stu-id="845ac-123">FindFile sample</span></span>](#findfile-sample)|
|<span data-ttu-id="845ac-124">Структура с указателем на другую структуру.</span><span class="sxs-lookup"><span data-stu-id="845ac-124">Structure with a pointer to another structure.</span></span>|<span data-ttu-id="845ac-125">Передает структуру, содержащую указатель на другую структуру в качестве члена.</span><span class="sxs-lookup"><span data-stu-id="845ac-125">Passes a structure that contains a pointer to a second structure as a member.</span></span>|[<span data-ttu-id="845ac-126">Пример структур</span><span class="sxs-lookup"><span data-stu-id="845ac-126">Structures Sample</span></span>](#structures-sample)|
|<span data-ttu-id="845ac-127">Массив структур с целочисленными значениями по значению.</span><span class="sxs-lookup"><span data-stu-id="845ac-127">Array of structures with integers by value.</span></span>|<span data-ttu-id="845ac-128">Передает массив структур, содержащих только целые числа, в виде параметра In или Out.</span><span class="sxs-lookup"><span data-stu-id="845ac-128">Passes an array of structures that contain only integers as an In/Out parameter.</span></span> <span data-ttu-id="845ac-129">Элементы массива можно изменять.</span><span class="sxs-lookup"><span data-stu-id="845ac-129">Members of the array can be changed.</span></span>|[<span data-ttu-id="845ac-130">Пример массивов</span><span class="sxs-lookup"><span data-stu-id="845ac-130">Arrays Sample</span></span>](marshaling-different-types-of-arrays.md)|
|<span data-ttu-id="845ac-131">Массив структур с целочисленными значениями и строками по ссылке.</span><span class="sxs-lookup"><span data-stu-id="845ac-131">Array of structures with integers and strings by reference.</span></span>|<span data-ttu-id="845ac-132">Передает массив структур, содержащих целые числа и строки, в качестве параметра Out.</span><span class="sxs-lookup"><span data-stu-id="845ac-132">Passes an array of structures that contain integers and strings as an Out parameter.</span></span> <span data-ttu-id="845ac-133">Вызываемая функция выделяет память под массив.</span><span class="sxs-lookup"><span data-stu-id="845ac-133">The called function allocates memory for the array.</span></span>|[<span data-ttu-id="845ac-134">Пример OutArrayOfStructs</span><span class="sxs-lookup"><span data-stu-id="845ac-134">OutArrayOfStructs Sample</span></span>](#outarrayofstructs-sample)|
|<span data-ttu-id="845ac-135">Объединения с типами значений.</span><span class="sxs-lookup"><span data-stu-id="845ac-135">Unions with value types.</span></span>|<span data-ttu-id="845ac-136">Передает объединения с типами значений (целочисленными и двойной точности).</span><span class="sxs-lookup"><span data-stu-id="845ac-136">Passes unions with value types (integer and double).</span></span>|[<span data-ttu-id="845ac-137">Пример объединений</span><span class="sxs-lookup"><span data-stu-id="845ac-137">Unions sample</span></span>](#unions-sample)|
|<span data-ttu-id="845ac-138">Объединения со смешанными типами.</span><span class="sxs-lookup"><span data-stu-id="845ac-138">Unions with mixed types.</span></span>|<span data-ttu-id="845ac-139">Передает объединения со смешанными типами (целое число и строка).</span><span class="sxs-lookup"><span data-stu-id="845ac-139">Passes unions with mixed types (integer and string).</span></span>|[<span data-ttu-id="845ac-140">Пример объединений</span><span class="sxs-lookup"><span data-stu-id="845ac-140">Unions sample</span></span>](#unions-sample)|
|<span data-ttu-id="845ac-141">Структура с макетом, зависящим от платформы.</span><span class="sxs-lookup"><span data-stu-id="845ac-141">Struct with platform-specific layout.</span></span>|<span data-ttu-id="845ac-142">Передает тип с определениями собственной упаковки.</span><span class="sxs-lookup"><span data-stu-id="845ac-142">Passes a type with native-packing definitions.</span></span>|[<span data-ttu-id="845ac-143">Пример платформы</span><span class="sxs-lookup"><span data-stu-id="845ac-143">Platform sample</span></span>](#platform-sample)|
|<span data-ttu-id="845ac-144">Значения Null в структуре.</span><span class="sxs-lookup"><span data-stu-id="845ac-144">Null values in structure.</span></span>|<span data-ttu-id="845ac-145">Передает пустую ссылку (**Nothing** в Visual Basic) вместо ссылки на тип значения.</span><span class="sxs-lookup"><span data-stu-id="845ac-145">Passes a null reference (**Nothing** in Visual Basic) instead of a reference to a value type.</span></span>|<span data-ttu-id="845ac-146">[Пример HandleRef](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.0/hc662t8k(v=vs.85))</span><span class="sxs-lookup"><span data-stu-id="845ac-146">[HandleRef sample](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.0/hc662t8k(v=vs.85))</span></span>|

## <a name="structures-sample"></a><span data-ttu-id="845ac-147">Пример структур</span><span class="sxs-lookup"><span data-stu-id="845ac-147">Structures sample</span></span>

<span data-ttu-id="845ac-148">В этом примере показан способ передачи структуры, указывающей на вторую структуру, передачи структуры с внедренной структурой и передачи структуры с внедренным массивом.</span><span class="sxs-lookup"><span data-stu-id="845ac-148">This sample demonstrates how to pass a structure that points to a second structure, pass a structure with an embedded structure, and pass a structure with an embedded array.</span></span>  
  
<span data-ttu-id="845ac-149">В примере используются следующие неуправляемые функции, показанные с исходными объявлениями:</span><span class="sxs-lookup"><span data-stu-id="845ac-149">The Structs sample uses the following unmanaged functions, shown with their original function declaration:</span></span>

- <span data-ttu-id="845ac-150">функция **TestStructInStruct**, экспортированная из PinvokeLib.dll;</span><span class="sxs-lookup"><span data-stu-id="845ac-150">**TestStructInStruct** exported from PinvokeLib.dll.</span></span>

    ```cpp
    int TestStructInStruct(MYPERSON2* pPerson2);
    ```

- <span data-ttu-id="845ac-151">функция **TestStructInStruct3**, экспортированная из PinvokeLib.dll;</span><span class="sxs-lookup"><span data-stu-id="845ac-151">**TestStructInStruct3** exported from PinvokeLib.dll.</span></span>

    ```cpp
    void TestStructInStruct3(MYPERSON3 person3);
    ```

- <span data-ttu-id="845ac-152">функция **TestArrayInStruct**, экспортированная из PinvokeLib.dll.</span><span class="sxs-lookup"><span data-stu-id="845ac-152">**TestArrayInStruct** exported from PinvokeLib.dll.</span></span>

    ```cpp
    void TestArrayInStruct(MYARRAYSTRUCT* pStruct);
    ```

<span data-ttu-id="845ac-153">[PinvokeLib.dll](marshaling-data-with-platform-invoke.md#pinvokelibdll) — это пользовательская неуправляемая библиотека, содержащая реализацию вышеуказанных функций и четырех структур: **MYPERSON**, **MYPERSON2**, **MYPERSON3** и **MYARRAYSTRUCT**.</span><span class="sxs-lookup"><span data-stu-id="845ac-153">[PinvokeLib.dll](marshaling-data-with-platform-invoke.md#pinvokelibdll) is a custom unmanaged library that contains implementations for the previously listed functions and four structures: **MYPERSON**, **MYPERSON2**, **MYPERSON3**, and **MYARRAYSTRUCT**.</span></span> <span data-ttu-id="845ac-154">Эти структуры содержат следующие элементы:</span><span class="sxs-lookup"><span data-stu-id="845ac-154">These structures contain the following elements:</span></span>

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

<span data-ttu-id="845ac-155">Управляемые структуры `MyPerson`, `MyPerson2`, `MyPerson3` и `MyArrayStruct` обладают следующими характеристиками:</span><span class="sxs-lookup"><span data-stu-id="845ac-155">The managed `MyPerson`, `MyPerson2`, `MyPerson3`, and `MyArrayStruct` structures have the following characteristic:</span></span>

- <span data-ttu-id="845ac-156">Структура `MyPerson` содержит только члены-строки.</span><span class="sxs-lookup"><span data-stu-id="845ac-156">`MyPerson` contains only string members.</span></span> <span data-ttu-id="845ac-157">Поле [CharSet](specifying-a-character-set.md) задает формат строк ANSI при передаче строки в неуправляемую функцию.</span><span class="sxs-lookup"><span data-stu-id="845ac-157">The [CharSet](specifying-a-character-set.md) field sets the strings to ANSI format when passed to the unmanaged function.</span></span>

- <span data-ttu-id="845ac-158">`MyPerson2` содержит указатель **IntPtr** на структуру `MyPerson`.</span><span class="sxs-lookup"><span data-stu-id="845ac-158">`MyPerson2` contains an **IntPtr** to the `MyPerson` structure.</span></span> <span data-ttu-id="845ac-159">Тип **IntPtr** заменяет исходный указатель на неуправляемую структуру, так как приложения .NET Framework не используют указатели, если код не помечен как **небезопасный**.</span><span class="sxs-lookup"><span data-stu-id="845ac-159">The **IntPtr** type replaces the original pointer to the unmanaged structure because .NET Framework applications do not use pointers unless the code is marked **unsafe**.</span></span>

- <span data-ttu-id="845ac-160">Структура `MyPerson3` содержит структуру `MyPerson` в качестве внедренной.</span><span class="sxs-lookup"><span data-stu-id="845ac-160">`MyPerson3` contains `MyPerson` as an embedded structure.</span></span> <span data-ttu-id="845ac-161">Внедренную структуру можно выровнять путем помещения ее элементов прямо в основную структуру, или ее можно оставить внедренной, как показано в примере.</span><span class="sxs-lookup"><span data-stu-id="845ac-161">A structure embedded within another structure can be flattened by placing the elements of the embedded structure directly into the main structure, or it can be left as an embedded structure, as is done in this sample.</span></span>

- <span data-ttu-id="845ac-162">Структура `MyArrayStruct` содержит массив целочисленных значений.</span><span class="sxs-lookup"><span data-stu-id="845ac-162">`MyArrayStruct` contains an array of integers.</span></span> <span data-ttu-id="845ac-163">Атрибут <xref:System.Runtime.InteropServices.MarshalAsAttribute> задает для перечисления <xref:System.Runtime.InteropServices.UnmanagedType> значение **ByValArray**, которое используется для указания количества элементов в массиве.</span><span class="sxs-lookup"><span data-stu-id="845ac-163">The <xref:System.Runtime.InteropServices.MarshalAsAttribute> attribute sets the <xref:System.Runtime.InteropServices.UnmanagedType> enumeration value to **ByValArray**, which is used to indicate the number of elements in the array.</span></span>

<span data-ttu-id="845ac-164">Для всех структур в этом примере применяется атрибут <xref:System.Runtime.InteropServices.StructLayoutAttribute>, гарантирующий последовательное размещение элементов в памяти в порядке их появления.</span><span class="sxs-lookup"><span data-stu-id="845ac-164">For all structures in this sample, the <xref:System.Runtime.InteropServices.StructLayoutAttribute> attribute is applied to ensure that the members are arranged in memory sequentially, in the order in which they appear.</span></span>

<span data-ttu-id="845ac-165">Класс `NativeMethods` содержит управляемые прототипы методов `TestStructInStruct`, `TestStructInStruct3` и `TestArrayInStruct`, вызываемые классом `App`.</span><span class="sxs-lookup"><span data-stu-id="845ac-165">The `NativeMethods` class contains managed prototypes for the `TestStructInStruct`, `TestStructInStruct3`, and `TestArrayInStruct` methods called by the `App` class.</span></span> <span data-ttu-id="845ac-166">Каждый прототип объявляет один параметр указанным ниже способом.</span><span class="sxs-lookup"><span data-stu-id="845ac-166">Each prototype declares a single parameter, as follows:</span></span>

- <span data-ttu-id="845ac-167">`TestStructInStruct` объявляет в качестве своего параметра ссылку на тип `MyPerson2`.</span><span class="sxs-lookup"><span data-stu-id="845ac-167">`TestStructInStruct` declares a reference to type `MyPerson2` as its parameter.</span></span>

- <span data-ttu-id="845ac-168">`TestStructInStruct3` в качестве своего параметра объявляет тип `MyPerson3` и передает параметр по значению.</span><span class="sxs-lookup"><span data-stu-id="845ac-168">`TestStructInStruct3` declares type `MyPerson3` as its parameter and passes the parameter by value.</span></span>

- <span data-ttu-id="845ac-169">`TestArrayInStruct` объявляет в качестве своего параметра ссылку на тип `MyArrayStruct`.</span><span class="sxs-lookup"><span data-stu-id="845ac-169">`TestArrayInStruct` declares a reference to type `MyArrayStruct` as its parameter.</span></span>

<span data-ttu-id="845ac-170">Структуры, выступающие в роли аргументов методов, передаются по значению, если параметр не содержит ключевого слова **ref** (**ByRef** в Visual Basic).</span><span class="sxs-lookup"><span data-stu-id="845ac-170">Structures as arguments to methods are passed by value unless the parameter contains the **ref** (**ByRef** in Visual Basic) keyword.</span></span> <span data-ttu-id="845ac-171">Например, метод `TestStructInStruct` передает в неуправляемый код ссылку (значение адреса) на объект типа `MyPerson2`.</span><span class="sxs-lookup"><span data-stu-id="845ac-171">For example, the `TestStructInStruct` method passes a reference (the value of an address) to an object of type `MyPerson2` to unmanaged code.</span></span> <span data-ttu-id="845ac-172">Для работы со структурой, на которую указывает `MyPerson2`, в примере с помощью методов <xref:System.Runtime.InteropServices.Marshal.AllocCoTaskMem%2A?displayProperty=nameWithType> и <xref:System.Runtime.InteropServices.Marshal.SizeOf%2A?displayProperty=nameWithType> создается буфер заданного размера и возвращается его адрес.</span><span class="sxs-lookup"><span data-stu-id="845ac-172">To manipulate the structure that `MyPerson2` points to, the sample creates a buffer of a specified size and returns its address by combining the <xref:System.Runtime.InteropServices.Marshal.AllocCoTaskMem%2A?displayProperty=nameWithType> and <xref:System.Runtime.InteropServices.Marshal.SizeOf%2A?displayProperty=nameWithType> methods.</span></span> <span data-ttu-id="845ac-173">Далее в неуправляемый буфер копируется содержимое управляемой структуры.</span><span class="sxs-lookup"><span data-stu-id="845ac-173">Next, the sample copies the content of the managed structure to the unmanaged buffer.</span></span> <span data-ttu-id="845ac-174">Наконец, используются метод <xref:System.Runtime.InteropServices.Marshal.PtrToStructure%2A?displayProperty=nameWithType> для маршалинга данных из неуправляемого буфера в управляемый объект и метод <xref:System.Runtime.InteropServices.Marshal.FreeCoTaskMem%2A?displayProperty=nameWithType> для освобождения неуправляемого блока памяти.</span><span class="sxs-lookup"><span data-stu-id="845ac-174">Finally, the sample uses the <xref:System.Runtime.InteropServices.Marshal.PtrToStructure%2A?displayProperty=nameWithType> method to marshal data from the unmanaged buffer to a managed object and the <xref:System.Runtime.InteropServices.Marshal.FreeCoTaskMem%2A?displayProperty=nameWithType> method to free the unmanaged block of memory.</span></span>

### <a name="declaring-prototypes"></a><span data-ttu-id="845ac-175">Объявление прототипов</span><span class="sxs-lookup"><span data-stu-id="845ac-175">Declaring Prototypes</span></span>

[!code-cpp[Conceptual.Interop.Marshaling#23](~/samples/snippets/cpp/VS_Snippets_CLR/conceptual.interop.marshaling/cpp/structures.cpp#23)]
[!code-csharp[Conceptual.Interop.Marshaling#23](~/samples/snippets/csharp/VS_Snippets_CLR/conceptual.interop.marshaling/cs/structures.cs#23)]
[!code-vb[Conceptual.Interop.Marshaling#23](~/samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.interop.marshaling/vb/structures.vb#23)]

### <a name="calling-functions"></a><span data-ttu-id="845ac-176">Вызов функций</span><span class="sxs-lookup"><span data-stu-id="845ac-176">Calling Functions</span></span>

[!code-cpp[Conceptual.Interop.Marshaling#24](~/samples/snippets/cpp/VS_Snippets_CLR/conceptual.interop.marshaling/cpp/structures.cpp#24)]
[!code-csharp[Conceptual.Interop.Marshaling#24](~/samples/snippets/csharp/VS_Snippets_CLR/conceptual.interop.marshaling/cs/structures.cs#24)]
[!code-vb[Conceptual.Interop.Marshaling#24](~/samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.interop.marshaling/vb/structures.vb#24)]

## <a name="findfile-sample"></a><span data-ttu-id="845ac-177">пример FindFile</span><span class="sxs-lookup"><span data-stu-id="845ac-177">FindFile sample</span></span>

<span data-ttu-id="845ac-178">В этом примере показан способ передачи структуры, содержащей другую, внедренную структуру, в неуправляемую функцию.</span><span class="sxs-lookup"><span data-stu-id="845ac-178">This sample demonstrates how to pass a structure that contains a second, embedded structure to an unmanaged function.</span></span> <span data-ttu-id="845ac-179">Также показано, как с помощью атрибута <xref:System.Runtime.InteropServices.MarshalAsAttribute> объявить массив фиксированной длины внутри структуры.</span><span class="sxs-lookup"><span data-stu-id="845ac-179">It also demonstrates how to use the <xref:System.Runtime.InteropServices.MarshalAsAttribute> attribute to declare a fixed-length array within the structure.</span></span> <span data-ttu-id="845ac-180">В этом примере элементы внедренной структуры добавляются в родительскую структуру.</span><span class="sxs-lookup"><span data-stu-id="845ac-180">In this sample, the embedded structure elements are added to the parent structure.</span></span> <span data-ttu-id="845ac-181">Пример внедренной структуры (не преобразованной в плоскую структуру) см. в разделе [Пример структур](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/eadtsekz(v=vs.100)).</span><span class="sxs-lookup"><span data-stu-id="845ac-181">For a sample of an embedded structure that is not flattened, see [Structures Sample](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/eadtsekz(v=vs.100)).</span></span>

<span data-ttu-id="845ac-182">В примере FindFile используются следующие неуправляемые функции, показанные с исходными объявлениями:</span><span class="sxs-lookup"><span data-stu-id="845ac-182">The FindFile sample uses the following unmanaged function, shown with its original function declaration:</span></span>

- <span data-ttu-id="845ac-183">функция **FindFirstFile**, экспортированная из Kernel32.dll.</span><span class="sxs-lookup"><span data-stu-id="845ac-183">**FindFirstFile** exported from Kernel32.dll.</span></span>

    ```cpp
    HANDLE FindFirstFile(LPCTSTR lpFileName, LPWIN32_FIND_DATA lpFindFileData);
    ```

<span data-ttu-id="845ac-184">Исходная структура, переданная в функцию, содержит следующие элементы:</span><span class="sxs-lookup"><span data-stu-id="845ac-184">The original structure passed to the function contains the following elements:</span></span>

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

<span data-ttu-id="845ac-185">В этом примере класс `FindData` содержит члены данных, соответствующие каждому элементу исходной и внедренной структур.</span><span class="sxs-lookup"><span data-stu-id="845ac-185">In this sample, the `FindData` class contains a corresponding data member for each element of the original structure and the embedded structure.</span></span> <span data-ttu-id="845ac-186">Вместо двух исходных символьных буферов класс подставляет строки.</span><span class="sxs-lookup"><span data-stu-id="845ac-186">In place of two original character buffers, the class substitutes strings.</span></span> <span data-ttu-id="845ac-187">Атрибут **MarshalAsAttribute** задает для перечисления <xref:System.Runtime.InteropServices.UnmanagedType> значение **ByValTStr**, которое используется для идентификации встроенных символьных массивов фиксированной длины в неуправляемых структурах.</span><span class="sxs-lookup"><span data-stu-id="845ac-187">**MarshalAsAttribute** sets the <xref:System.Runtime.InteropServices.UnmanagedType> enumeration to **ByValTStr**, which is used to identify the inline, fixed-length character arrays that appear within the unmanaged structures.</span></span>

<span data-ttu-id="845ac-188">Класс `NativeMethods` содержит управляемый прототип метода `FindFirstFile`, передающий класс `FindData` в качестве параметра.</span><span class="sxs-lookup"><span data-stu-id="845ac-188">The `NativeMethods` class contains a managed prototype of the `FindFirstFile` method, which passes the `FindData` class as a parameter.</span></span> <span data-ttu-id="845ac-189">Этот параметр должен быть объявлен с атрибутами <xref:System.Runtime.InteropServices.InAttribute> и <xref:System.Runtime.InteropServices.OutAttribute>, так как классы, являющиеся ссылочными типами, по умолчанию передаются как параметры In.</span><span class="sxs-lookup"><span data-stu-id="845ac-189">The parameter must be declared with the <xref:System.Runtime.InteropServices.InAttribute> and <xref:System.Runtime.InteropServices.OutAttribute> attributes because classes, which are reference types, are passed as In parameters by default.</span></span>

### <a name="declaring-prototypes"></a><span data-ttu-id="845ac-190">Объявление прототипов</span><span class="sxs-lookup"><span data-stu-id="845ac-190">Declaring Prototypes</span></span>

[!code-cpp[Conceptual.Interop.Marshaling#17](~/samples/snippets/cpp/VS_Snippets_CLR/conceptual.interop.marshaling/cpp/findfile.cpp#17)]
[!code-csharp[Conceptual.Interop.Marshaling#17](~/samples/snippets/csharp/VS_Snippets_CLR/conceptual.interop.marshaling/cs/findfile.cs#17)]
[!code-vb[Conceptual.Interop.Marshaling#17](~/samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.interop.marshaling/vb/findfile.vb#17)]

### <a name="calling-functions"></a><span data-ttu-id="845ac-191">Вызов функций</span><span class="sxs-lookup"><span data-stu-id="845ac-191">Calling Functions</span></span>

[!code-cpp[Conceptual.Interop.Marshaling#18](~/samples/snippets/cpp/VS_Snippets_CLR/conceptual.interop.marshaling/cpp/findfile.cpp#18)]
[!code-csharp[Conceptual.Interop.Marshaling#18](~/samples/snippets/csharp/VS_Snippets_CLR/conceptual.interop.marshaling/cs/findfile.cs#18)]
 [!code-vb[Conceptual.Interop.Marshaling#18](~/samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.interop.marshaling/vb/findfile.vb#18)]

## <a name="unions-sample"></a><span data-ttu-id="845ac-192">пример Unions</span><span class="sxs-lookup"><span data-stu-id="845ac-192">Unions sample</span></span>

<span data-ttu-id="845ac-193">В этом примере показан способ передачи структур, содержащих только типы значений, а также структур, содержащих тип значения и строку, в качестве параметров в неуправляемую функцию, ожидающую объединения.</span><span class="sxs-lookup"><span data-stu-id="845ac-193">This sample demonstrates how to pass structures containing only value types, and structures containing a value type and a string as parameters to an unmanaged function expecting a union.</span></span> <span data-ttu-id="845ac-194">Объединение представляет собой ячейку памяти, которая может совместно использоваться двумя и более переменными.</span><span class="sxs-lookup"><span data-stu-id="845ac-194">A union represents a memory location that can be shared by two or more variables.</span></span>

<span data-ttu-id="845ac-195">В примере используются следующие неуправляемые функции, показанные с исходными объявлениями:</span><span class="sxs-lookup"><span data-stu-id="845ac-195">The Unions sample uses the following unmanaged function, shown with its original function declaration:</span></span>

- <span data-ttu-id="845ac-196">функция **TestUnion**, экспортированная из PinvokeLib.dll.</span><span class="sxs-lookup"><span data-stu-id="845ac-196">**TestUnion** exported from PinvokeLib.dll.</span></span>

    ```cpp
    void TestUnion(MYUNION u, int type);
    ```

<span data-ttu-id="845ac-197">[PinvokeLib.dll](marshaling-data-with-platform-invoke.md#pinvokelibdll) — это пользовательская неуправляемая библиотека, содержащая реализацию указанной выше функции и два объединения: **MYUNION** и **MYUNION2**.</span><span class="sxs-lookup"><span data-stu-id="845ac-197">[PinvokeLib.dll](marshaling-data-with-platform-invoke.md#pinvokelibdll) is a custom unmanaged library that contains an implementation for the previously listed function and two unions, **MYUNION** and **MYUNION2**.</span></span> <span data-ttu-id="845ac-198">Объединение содержит следующие элементы:</span><span class="sxs-lookup"><span data-stu-id="845ac-198">The unions contain the following elements:</span></span>

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

<span data-ttu-id="845ac-199">В управляемом коде объединения определяются как структуры.</span><span class="sxs-lookup"><span data-stu-id="845ac-199">In managed code, unions are defined as structures.</span></span> <span data-ttu-id="845ac-200">Структура `MyUnion` в качестве своих членов содержит два типа значений: целочисленный и число двойной точности.</span><span class="sxs-lookup"><span data-stu-id="845ac-200">The `MyUnion` structure contains two value types as its members: an integer and a double.</span></span> <span data-ttu-id="845ac-201">Для управления точным положением каждого члена данных задается атрибут <xref:System.Runtime.InteropServices.StructLayoutAttribute>.</span><span class="sxs-lookup"><span data-stu-id="845ac-201">The <xref:System.Runtime.InteropServices.StructLayoutAttribute> attribute is set to control the precise position of each data member.</span></span> <span data-ttu-id="845ac-202">Атрибут <xref:System.Runtime.InteropServices.FieldOffsetAttribute> предоставляет физическое положение полей внутри неуправляемого представления объединения.</span><span class="sxs-lookup"><span data-stu-id="845ac-202">The <xref:System.Runtime.InteropServices.FieldOffsetAttribute> attribute provides the physical position of fields within the unmanaged representation of a union.</span></span> <span data-ttu-id="845ac-203">Обратите внимание, что значения смещения у обоих членов одинаковы, что позволяет членам определять один и тот же участок памяти.</span><span class="sxs-lookup"><span data-stu-id="845ac-203">Notice that both members have the same offset values, so the members can define the same piece of memory.</span></span>

<span data-ttu-id="845ac-204">Объединения `MyUnion2_1` и `MyUnion2_2` содержат тип значения (целое число) и строку соответственно.</span><span class="sxs-lookup"><span data-stu-id="845ac-204">`MyUnion2_1` and `MyUnion2_2` contain a value type (integer) and a string, respectively.</span></span> <span data-ttu-id="845ac-205">В управляемом коде типы значений и ссылочные типы не могут перекрываться.</span><span class="sxs-lookup"><span data-stu-id="845ac-205">In managed code, value types and reference types are not permitted to overlap.</span></span> <span data-ttu-id="845ac-206">Чтобы при вызове одной и той же неуправляемой функции вызывающий объект мог использовать оба типа, в этом примере применяется перегрузка метода.</span><span class="sxs-lookup"><span data-stu-id="845ac-206">This sample uses method overloading to enable the caller to use both types when calling the same unmanaged function.</span></span> <span data-ttu-id="845ac-207">Структура `MyUnion2_1` задана явным образом и имеет точное значение смещения.</span><span class="sxs-lookup"><span data-stu-id="845ac-207">The layout of `MyUnion2_1` is explicit and has a precise offset value.</span></span> <span data-ttu-id="845ac-208">Напротив, `MyUnion2_2` имеет последовательную структуру, так как структуры, заданные явным образом, нельзя использовать со ссылочными типами.</span><span class="sxs-lookup"><span data-stu-id="845ac-208">In contrast, `MyUnion2_2` has a sequential layout, because explicit layouts are not permitted with reference types.</span></span> <span data-ttu-id="845ac-209">Атрибут <xref:System.Runtime.InteropServices.MarshalAsAttribute> задает для перечисления <xref:System.Runtime.InteropServices.UnmanagedType> значение **ByValTStr**, которое используется для идентификации встроенных символьных массивов фиксированной длины в неуправляемом представлении объединения.</span><span class="sxs-lookup"><span data-stu-id="845ac-209">The <xref:System.Runtime.InteropServices.MarshalAsAttribute> attribute sets the <xref:System.Runtime.InteropServices.UnmanagedType> enumeration to **ByValTStr**, which is used to identify the inline, fixed-length character arrays that appear within the unmanaged representation of the union.</span></span>

<span data-ttu-id="845ac-210">Класс `NativeMethods` содержит прототипы для методов `TestUnion` и `TestUnion2`.</span><span class="sxs-lookup"><span data-stu-id="845ac-210">The `NativeMethods` class contains the prototypes for the `TestUnion` and `TestUnion2` methods.</span></span> <span data-ttu-id="845ac-211">`TestUnion2` перегружается для объявления `MyUnion2_1` или `MyUnion2_2` в качестве параметров.</span><span class="sxs-lookup"><span data-stu-id="845ac-211">`TestUnion2` is overloaded to declare `MyUnion2_1` or `MyUnion2_2` as parameters.</span></span>

### <a name="declaring-prototypes"></a><span data-ttu-id="845ac-212">Объявление прототипов</span><span class="sxs-lookup"><span data-stu-id="845ac-212">Declaring Prototypes</span></span>

[!code-cpp[Conceptual.Interop.Marshaling#28](~/samples/snippets/cpp/VS_Snippets_CLR/conceptual.interop.marshaling/cpp/unions.cpp#28)]
[!code-csharp[Conceptual.Interop.Marshaling#28](~/samples/snippets/csharp/VS_Snippets_CLR/conceptual.interop.marshaling/cs/unions.cs#28)]
[!code-vb[Conceptual.Interop.Marshaling#28](~/samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.interop.marshaling/vb/unions.vb#28)]

### <a name="calling-functions"></a><span data-ttu-id="845ac-213">Вызов функций</span><span class="sxs-lookup"><span data-stu-id="845ac-213">Calling Functions</span></span>

[!code-cpp[Conceptual.Interop.Marshaling#29](~/samples/snippets/cpp/VS_Snippets_CLR/conceptual.interop.marshaling/cpp/unions.cpp#29)]
[!code-csharp[Conceptual.Interop.Marshaling#29](~/samples/snippets/csharp/VS_Snippets_CLR/conceptual.interop.marshaling/cs/unions.cs#29)]
[!code-vb[Conceptual.Interop.Marshaling#29](~/samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.interop.marshaling/vb/unions.vb#29)]

## <a name="platform-sample"></a><span data-ttu-id="845ac-214">Пример платформы</span><span class="sxs-lookup"><span data-stu-id="845ac-214">Platform sample</span></span>

<span data-ttu-id="845ac-215">В некоторых сценариях макеты `struct` и `union` могут различаться в зависимости от целевой платформы.</span><span class="sxs-lookup"><span data-stu-id="845ac-215">In some scenarios, `struct` and `union` layouts can differ depending on the targeted platform.</span></span> <span data-ttu-id="845ac-216">Например, рассмотрим тип [`STRRET`](/windows/win32/api/shtypes/ns-shtypes-strret) при определении в сценарии COM:</span><span class="sxs-lookup"><span data-stu-id="845ac-216">For example, consider the [`STRRET`](/windows/win32/api/shtypes/ns-shtypes-strret) type when defined in a COM scenario:</span></span>

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

<span data-ttu-id="845ac-217">Приведенный выше `struct` объявляется с заголовками Windows, которые влияют на макет памяти типа.</span><span class="sxs-lookup"><span data-stu-id="845ac-217">The above `struct` is declared with Windows' headers that influence the memory layout of the type.</span></span> <span data-ttu-id="845ac-218">При определении в управляемой среде эти сведения о макете необходимы для правильного взаимодействия с машинным кодом.</span><span class="sxs-lookup"><span data-stu-id="845ac-218">When defined in a managed environment, these layout details are needed to properly interoperate with native code.</span></span>

<span data-ttu-id="845ac-219">Правильное управляемое определение этого типа в 32-разрядном процессе имеет следующий вид:</span><span class="sxs-lookup"><span data-stu-id="845ac-219">The correct managed definition of this type in a 32-bit process is:</span></span>

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

<span data-ttu-id="845ac-220">В 64-разрядном процессе размеры смещений полей *и* различаются.</span><span class="sxs-lookup"><span data-stu-id="845ac-220">On a 64-bit process, the size *and* field offsets are different.</span></span> <span data-ttu-id="845ac-221">Правильный макет:</span><span class="sxs-lookup"><span data-stu-id="845ac-221">The correct layout is:</span></span>

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

<span data-ttu-id="845ac-222">Неправильный выбор собственного макета в сценарии взаимодействия может привести к возникновению случайных сбоев или, что еще хуже, к неправильным вычислениям.</span><span class="sxs-lookup"><span data-stu-id="845ac-222">Failure to properly consider the native layout in an interop scenario can result in random crashes or worse, incorrect computations.</span></span>

<span data-ttu-id="845ac-223">По умолчанию сборки .NET могут работать как в 32-разрядной, так и в 64-разрядной версии среды выполнения .NET.</span><span class="sxs-lookup"><span data-stu-id="845ac-223">By default, .NET assemblies can run in both a 32-bit and 64-bit version of the .NET runtime.</span></span> <span data-ttu-id="845ac-224">Приложение должно ожидать от среды выполнения решения о том, какое из предыдущих определений использовать.</span><span class="sxs-lookup"><span data-stu-id="845ac-224">The app must wait until run time to decide which of the previous definitions to use.</span></span>

<span data-ttu-id="845ac-225">В следующем фрагменте кода показан пример выбора между 32-разрядным и 64-разрядным определением в среде выполнения.</span><span class="sxs-lookup"><span data-stu-id="845ac-225">The following code snippet shows an example of how to choose between the 32-bit and 64-bit definition at run time.</span></span>

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

## <a name="systime-sample"></a><span data-ttu-id="845ac-226">Пример SysTime</span><span class="sxs-lookup"><span data-stu-id="845ac-226">SysTime sample</span></span>

<span data-ttu-id="845ac-227">В этом примере показано, как передать указатель на класс в неуправляемую функцию, ожидающую указатель на структуру.</span><span class="sxs-lookup"><span data-stu-id="845ac-227">This sample demonstrates how to pass a pointer to a class to an unmanaged function that expects a pointer to a structure.</span></span>

<span data-ttu-id="845ac-228">В примере используется следующая неуправляемая функция, показанная с исходным объявлением:</span><span class="sxs-lookup"><span data-stu-id="845ac-228">The SysTime sample uses the following unmanaged function, shown with its original function declaration:</span></span>

- <span data-ttu-id="845ac-229">функция **GetSystemTime**, экспортированная из Kernel32.dll.</span><span class="sxs-lookup"><span data-stu-id="845ac-229">**GetSystemTime** exported from Kernel32.dll.</span></span>

    ```cpp
    VOID GetSystemTime(LPSYSTEMTIME lpSystemTime);
    ```

<span data-ttu-id="845ac-230">Исходная структура, переданная в функцию, содержит следующие элементы:</span><span class="sxs-lookup"><span data-stu-id="845ac-230">The original structure passed to the function contains the following elements:</span></span>

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

<span data-ttu-id="845ac-231">В этом примере класс `SystemTime` содержит элементы исходной структуры, представленные в виде членов класса.</span><span class="sxs-lookup"><span data-stu-id="845ac-231">In this sample, the `SystemTime` class contains the elements of the original structure represented as class members.</span></span> <span data-ttu-id="845ac-232">Чтобы гарантировать последовательное размещение членов в памяти в порядке их появления, применяется атрибут <xref:System.Runtime.InteropServices.StructLayoutAttribute> .</span><span class="sxs-lookup"><span data-stu-id="845ac-232">The <xref:System.Runtime.InteropServices.StructLayoutAttribute> attribute is set to ensure that the members are arranged in memory sequentially, in the order in which they appear.</span></span>

<span data-ttu-id="845ac-233">Класс `NativeMethods` содержит управляемый прототип метода `GetSystemTime`, который по умолчанию передает класс `SystemTime` в качестве параметра In или Out.</span><span class="sxs-lookup"><span data-stu-id="845ac-233">The `NativeMethods` class contains a managed prototype of the `GetSystemTime` method, which passes the `SystemTime` class as an In/Out parameter by default.</span></span> <span data-ttu-id="845ac-234">Этот параметр должен быть объявлен с атрибутами <xref:System.Runtime.InteropServices.InAttribute> и <xref:System.Runtime.InteropServices.OutAttribute>, так как классы, являющиеся ссылочными типами, по умолчанию передаются как параметры In.</span><span class="sxs-lookup"><span data-stu-id="845ac-234">The parameter must be declared with the <xref:System.Runtime.InteropServices.InAttribute> and <xref:System.Runtime.InteropServices.OutAttribute> attributes because classes, which are reference types, are passed as In parameters by default.</span></span> <span data-ttu-id="845ac-235">Чтобы вызывающий объект получал результаты, необходимо явным образом применить [атрибуты направления](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/77e6taeh(v=vs.100)).</span><span class="sxs-lookup"><span data-stu-id="845ac-235">For the caller to receive the results, these [directional attributes](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/77e6taeh(v=vs.100)) must be applied explicitly.</span></span> <span data-ttu-id="845ac-236">Класс `App` создает экземпляр класса `SystemTime` и осуществляет доступ к его полям данных.</span><span class="sxs-lookup"><span data-stu-id="845ac-236">The `App` class creates a new instance of the `SystemTime` class and accesses its data fields.</span></span>

### <a name="code-samples"></a><span data-ttu-id="845ac-237">Примеры кода</span><span class="sxs-lookup"><span data-stu-id="845ac-237">Code Samples</span></span>

[!code-cpp[Conceptual.Interop.Marshaling#25](~/samples/snippets/cpp/VS_Snippets_CLR/conceptual.interop.marshaling/cpp/systime.cpp#25)]
[!code-csharp[Conceptual.Interop.Marshaling#25](~/samples/snippets/csharp/VS_Snippets_CLR/conceptual.interop.marshaling/cs/systime.cs#25)]
[!code-vb[Conceptual.Interop.Marshaling#25](~/samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.interop.marshaling/vb/systime.vb#25)]

## <a name="outarrayofstructs-sample"></a><span data-ttu-id="845ac-238">Пример OutArrayOfStructs </span><span class="sxs-lookup"><span data-stu-id="845ac-238">OutArrayOfStructs sample</span></span>

<span data-ttu-id="845ac-239">В этом примере показано, как передать в неуправляемую функцию массив структур, содержащий целочисленные значения и строки, в виде параметров Out.</span><span class="sxs-lookup"><span data-stu-id="845ac-239">This sample shows how to pass an array of structures that contains integers and strings as Out parameters to an unmanaged function.</span></span>

<span data-ttu-id="845ac-240">В этом примере демонстрируется, как вызывать собственную функцию с помощью класса <xref:System.Runtime.InteropServices.Marshal> и небезопасного кода.</span><span class="sxs-lookup"><span data-stu-id="845ac-240">This sample demonstrates how to call a native function by using the <xref:System.Runtime.InteropServices.Marshal> class and by using unsafe code.</span></span>

<span data-ttu-id="845ac-241">В примере используются функции-оболочки и вызовы неуправляемого кода, определенные в библиотеке [PinvokeLib.dll](marshaling-data-with-platform-invoke.md#pinvokelibdll) и содержащиеся в исходных файлах.</span><span class="sxs-lookup"><span data-stu-id="845ac-241">This sample uses a wrapper functions and platform invokes defined in [PinvokeLib.dll](marshaling-data-with-platform-invoke.md#pinvokelibdll), also provided in the source files.</span></span> <span data-ttu-id="845ac-242">В нем используется функция `TestOutArrayOfStructs` и структура `MYSTRSTRUCT2`.</span><span class="sxs-lookup"><span data-stu-id="845ac-242">It uses the `TestOutArrayOfStructs` function and the `MYSTRSTRUCT2` structure.</span></span> <span data-ttu-id="845ac-243">Структура содержит следующие элементы:</span><span class="sxs-lookup"><span data-stu-id="845ac-243">The structure contains the following elements:</span></span>

```cpp
typedef struct _MYSTRSTRUCT2
{
   char* buffer;
   UINT size;
} MYSTRSTRUCT2;
```

<span data-ttu-id="845ac-244">Класс `MyStruct` содержит строковый объект из символов ANSI.</span><span class="sxs-lookup"><span data-stu-id="845ac-244">The `MyStruct` class contains a string object of ANSI characters.</span></span> <span data-ttu-id="845ac-245">Поле <xref:System.Runtime.InteropServices.DllImportAttribute.CharSet> определяет формат ANSI.</span><span class="sxs-lookup"><span data-stu-id="845ac-245">The <xref:System.Runtime.InteropServices.DllImportAttribute.CharSet> field specifies ANSI format.</span></span> <span data-ttu-id="845ac-246">`MyUnsafeStruct` — это структура, содержащая тип <xref:System.IntPtr> вместо строки.</span><span class="sxs-lookup"><span data-stu-id="845ac-246">`MyUnsafeStruct`, is a structure containing an <xref:System.IntPtr> type instead of a string.</span></span>

<span data-ttu-id="845ac-247">Класс `NativeMethods` содержит перегруженный метод прототипа `TestOutArrayOfStructs`.</span><span class="sxs-lookup"><span data-stu-id="845ac-247">The `NativeMethods` class contains the overloaded `TestOutArrayOfStructs` prototype method.</span></span> <span data-ttu-id="845ac-248">Если в качестве параметра метод объявляет указатель, класс должен быть помечен зарезервированным словом `unsafe`.</span><span class="sxs-lookup"><span data-stu-id="845ac-248">If a method declares a pointer as a parameter, the class should be marked with the `unsafe` keyword.</span></span> <span data-ttu-id="845ac-249">Так как Visual Basic не может использовать небезопасный код, перегруженный метод, модификатор unsafe и структуры `MyUnsafeStruct` не нужны.</span><span class="sxs-lookup"><span data-stu-id="845ac-249">Because Visual Basic cannot use unsafe code, the overloaded method, unsafe modifier, and the `MyUnsafeStruct` structure are unnecessary.</span></span>

<span data-ttu-id="845ac-250">Класс `App` реализует метод `UsingMarshaling`, который выполняет все задачи, необходимые для передачи массива.</span><span class="sxs-lookup"><span data-stu-id="845ac-250">The `App` class implements the `UsingMarshaling` method, which performs all the tasks necessary to pass the array.</span></span> <span data-ttu-id="845ac-251">Чтобы указать, что данные передаются от вызываемого объекта к вызывающему, массив помечается зарезервированным словом `out` (`ByRef` в Visual Basic).</span><span class="sxs-lookup"><span data-stu-id="845ac-251">The array is marked with the `out` (`ByRef` in Visual Basic) keyword to indicate that data passes from callee to caller.</span></span> <span data-ttu-id="845ac-252">Реализация использует следующие методы класса <xref:System.Runtime.InteropServices.Marshal>:</span><span class="sxs-lookup"><span data-stu-id="845ac-252">The implementation uses the following <xref:System.Runtime.InteropServices.Marshal> class methods:</span></span>

- <span data-ttu-id="845ac-253">метод <xref:System.Runtime.InteropServices.Marshal.PtrToStructure%2A> для маршалинга данных из неуправляемого буфера в управляемый объект;</span><span class="sxs-lookup"><span data-stu-id="845ac-253"><xref:System.Runtime.InteropServices.Marshal.PtrToStructure%2A> to marshal data from the unmanaged buffer to a managed object.</span></span>

- <span data-ttu-id="845ac-254">метод <xref:System.Runtime.InteropServices.Marshal.DestroyStructure%2A> для освобождения памяти, зарезервированной для строк структуры;</span><span class="sxs-lookup"><span data-stu-id="845ac-254"><xref:System.Runtime.InteropServices.Marshal.DestroyStructure%2A> to release the memory reserved for strings in the structure.</span></span>

- <span data-ttu-id="845ac-255">метод <xref:System.Runtime.InteropServices.Marshal.FreeCoTaskMem%2A> для освобождения памяти, зарезервированной для массива.</span><span class="sxs-lookup"><span data-stu-id="845ac-255"><xref:System.Runtime.InteropServices.Marshal.FreeCoTaskMem%2A> to release the memory reserved for the array.</span></span>

<span data-ttu-id="845ac-256">Как упоминалось ранее, C# допускает небезопасный код, который Visual Basic не поддерживает.</span><span class="sxs-lookup"><span data-stu-id="845ac-256">As previously mentioned, C# allows unsafe code and Visual Basic does not.</span></span> <span data-ttu-id="845ac-257">В примере кода C# `UsingUnsafePointer` является альтернативной реализацией метода, в которой для обратной передачи массива, содержащего структуру `MyUnsafeStruct`, вместо класса <xref:System.Runtime.InteropServices.Marshal> используются указатели.</span><span class="sxs-lookup"><span data-stu-id="845ac-257">In the C# sample, `UsingUnsafePointer` is an alternative method implementation that uses pointers instead of the <xref:System.Runtime.InteropServices.Marshal> class to pass back the array containing the `MyUnsafeStruct` structure.</span></span>

### <a name="declaring-prototypes"></a><span data-ttu-id="845ac-258">Объявление прототипов</span><span class="sxs-lookup"><span data-stu-id="845ac-258">Declaring Prototypes</span></span>

[!code-cpp[Conceptual.Interop.Marshaling#20](~/samples/snippets/cpp/VS_Snippets_CLR/conceptual.interop.marshaling/cpp/outarrayofstructs.cpp#20)]
[!code-csharp[Conceptual.Interop.Marshaling#20](~/samples/snippets/csharp/VS_Snippets_CLR/conceptual.interop.marshaling/cs/outarrayofstructs.cs#20)]
[!code-vb[Conceptual.Interop.Marshaling#20](~/samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.interop.marshaling/vb/outarrayofstructs.vb#20)]

### <a name="calling-functions"></a><span data-ttu-id="845ac-259">Вызов функций</span><span class="sxs-lookup"><span data-stu-id="845ac-259">Calling Functions</span></span>

[!code-cpp[Conceptual.Interop.Marshaling#21](~/samples/snippets/cpp/VS_Snippets_CLR/conceptual.interop.marshaling/cpp/outarrayofstructs.cpp#21)]
[!code-csharp[Conceptual.Interop.Marshaling#21](~/samples/snippets/csharp/VS_Snippets_CLR/conceptual.interop.marshaling/cs/outarrayofstructs.cs#21)]
[!code-vb[Conceptual.Interop.Marshaling#21](~/samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.interop.marshaling/vb/outarrayofstructs.vb#21)]

## <a name="see-also"></a><span data-ttu-id="845ac-260">См. также</span><span class="sxs-lookup"><span data-stu-id="845ac-260">See also</span></span>

- [<span data-ttu-id="845ac-261">Маршалинг данных при вызове неуправляемого кода</span><span class="sxs-lookup"><span data-stu-id="845ac-261">Marshaling Data with Platform Invoke</span></span>](marshaling-data-with-platform-invoke.md)
- [<span data-ttu-id="845ac-262">Mаршалинг строк</span><span class="sxs-lookup"><span data-stu-id="845ac-262">Marshaling Strings</span></span>](marshaling-strings.md)
- [<span data-ttu-id="845ac-263">Маршалинг различных типов массивов</span><span class="sxs-lookup"><span data-stu-id="845ac-263">Marshaling Different Types of Arrays</span></span>](marshaling-different-types-of-arrays.md)
