---
description: '#Справочник по C#. #pragma checksum'
title: '#Справочник по C#. #pragma checksum'
ms.date: 07/20/2015
f1_keywords:
- '#pragma checksum'
helpviewer_keywords:
- '#pragma checksum [C#]'
ms.assetid: 3673e4ca-6098-4ec1-890f-8fceb2a794a2
ms.openlocfilehash: 60c491000337fd50da217e97054e86faccb2e7d7
ms.sourcegitcommit: d579fb5e4b46745fd0f1f8874c94c6469ce58604
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/30/2020
ms.locfileid: "89137985"
---
# <a name="pragma-checksum-c-reference"></a><span data-ttu-id="0f017-103">#pragma checksum (Справочник по C#)</span><span class="sxs-lookup"><span data-stu-id="0f017-103">#pragma checksum (C# Reference)</span></span>
<span data-ttu-id="0f017-104">Создает контрольные суммы для исходных файлов, чтобы помочь с отладкой страниц ASP.NET.</span><span class="sxs-lookup"><span data-stu-id="0f017-104">Generates checksums for source files to aid with debugging ASP.NET pages.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0f017-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="0f017-105">Syntax</span></span>  
  
```csharp
#pragma checksum "filename" "{guid}" "checksum bytes"  
```  
  
## <a name="parameters"></a><span data-ttu-id="0f017-106">Параметры</span><span class="sxs-lookup"><span data-stu-id="0f017-106">Parameters</span></span>  
 `"filename"`  
 <span data-ttu-id="0f017-107">Имя файла, который требует отслеживания изменений или обновлений.</span><span class="sxs-lookup"><span data-stu-id="0f017-107">The name of the file that requires monitoring for changes or updates.</span></span>  
  
 `"{guid}"`  
 <span data-ttu-id="0f017-108">Глобальный уникальный идентификатор (GUID) для хэш-алгоритма.</span><span class="sxs-lookup"><span data-stu-id="0f017-108">The Globally Unique Identifier (GUID) for the hash algorithm.</span></span>  
  
 `"checksum_bytes"`  
 <span data-ttu-id="0f017-109">Строка шестнадцатеричных цифр, представляющая байты контрольной суммы.</span><span class="sxs-lookup"><span data-stu-id="0f017-109">The string of hexadecimal digits representing the bytes of the checksum.</span></span> <span data-ttu-id="0f017-110">Должно быть четным числом шестнадцатеричных цифр.</span><span class="sxs-lookup"><span data-stu-id="0f017-110">Must be an even number of hexadecimal digits.</span></span> <span data-ttu-id="0f017-111">Нечетное число цифр вызовет предупреждение во время компиляции, и директива будет пропущена.</span><span class="sxs-lookup"><span data-stu-id="0f017-111">An odd number of digits results in a compile-time warning, and the directive are ignored.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="0f017-112">Remarks</span><span class="sxs-lookup"><span data-stu-id="0f017-112">Remarks</span></span>  
 <span data-ttu-id="0f017-113">Отладчик Visual Studio использует контрольную сумму, чтобы подтвердить нахождение правильного источника.</span><span class="sxs-lookup"><span data-stu-id="0f017-113">The Visual Studio debugger uses a checksum to make sure  that it always finds the right source.</span></span> <span data-ttu-id="0f017-114">Компилятор вычисляет контрольную сумму для исходного файла, а затем передает результат в файл базы данных (PDB) программы.</span><span class="sxs-lookup"><span data-stu-id="0f017-114">The compiler computes the checksum for a source file, and then emits the output to the program database (PDB) file.</span></span> <span data-ttu-id="0f017-115">Отладчик затем использует PDB-файл для сравнения с контрольной суммой, вычисленной им для исходного файла.</span><span class="sxs-lookup"><span data-stu-id="0f017-115">The debugger then uses the PDB to compare against the checksum that it computes for the source file.</span></span>  
  
 <span data-ttu-id="0f017-116">Это решение не работает для проектов ASP.NET, так как рассчитанная контрольная сумма относится к созданному исходному файлу, а не файлу ASPX.</span><span class="sxs-lookup"><span data-stu-id="0f017-116">This solution does not work for ASP.NET projects, because the computed checksum is for the generated source file, rather than the .aspx file.</span></span> <span data-ttu-id="0f017-117">Чтобы решить эту проблему, `#pragma checksum` предоставляет поддержку контрольных сумм для страниц ASP.NET.</span><span class="sxs-lookup"><span data-stu-id="0f017-117">To address this problem, `#pragma checksum` provides checksum support for ASP.NET pages.</span></span>  
  
 <span data-ttu-id="0f017-118">При создании проекта ASP.NET в Visual C# созданный исходный файл содержит контрольную сумму для ASPX-файла, из которого создается источник.</span><span class="sxs-lookup"><span data-stu-id="0f017-118">When you create an ASP.NET project in Visual C#, the generated source file contains a checksum for the .aspx file, from which the source is generated.</span></span> <span data-ttu-id="0f017-119">Затем компилятор записывает эти данные в PDB-файл.</span><span class="sxs-lookup"><span data-stu-id="0f017-119">The compiler then writes this information into the PDB file.</span></span>  
  
 <span data-ttu-id="0f017-120">Если компилятор не обнаруживает директиву `#pragma checksum` в файле, он вычисляет контрольную сумму и записывает значение в PDB-файл.</span><span class="sxs-lookup"><span data-stu-id="0f017-120">If the compiler encounters no `#pragma checksum` directive in the file, it computes the checksum and writes the value to the PDB file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="0f017-121">Пример</span><span class="sxs-lookup"><span data-stu-id="0f017-121">Example</span></span>  
  
```csharp
class TestClass  
{  
    static int Main()  
    {  
        #pragma checksum "file.cs" "{406EA660-64CF-4C82-B6F0-42D48172A799}" "ab007f1d23d9" // New checksum  
    }  
}  
```  
  
## <a name="see-also"></a><span data-ttu-id="0f017-122">См. также</span><span class="sxs-lookup"><span data-stu-id="0f017-122">See also</span></span>

- [<span data-ttu-id="0f017-123">Справочник по C#</span><span class="sxs-lookup"><span data-stu-id="0f017-123">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="0f017-124">Руководство по программированию на C#</span><span class="sxs-lookup"><span data-stu-id="0f017-124">C# Programming Guide</span></span>](../../programming-guide/index.md)
- [<span data-ttu-id="0f017-125">Директивы препроцессора C#</span><span class="sxs-lookup"><span data-stu-id="0f017-125">C# Preprocessor Directives</span></span>](./index.md)
