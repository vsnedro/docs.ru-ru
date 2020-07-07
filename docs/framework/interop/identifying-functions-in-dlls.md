---
title: Идентификация функций в библиотеках DLL
description: Идентификация функций в библиотеках DLL. Удостоверение функции в библиотеке DLL состоит из имени функции или порядкового номера, а также имени DLL-файла, в котором реализована функция.
ms.date: 03/30/2017
helpviewer_keywords:
- platform invoke, identifying functions
- COM interop, DLL functions
- unmanaged functions
- COM interop, platform invoke
- interoperation with unmanaged code, DLL functions
- interoperation with unmanaged code, platform invoke
- identifying DLL functions
- DLL functions
ms.assetid: 3e3f6780-6d90-4413-bad7-ba641220364d
ms.openlocfilehash: 054d1351a9ee6adab17117c9f423aa26d0d9ed59
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.contentlocale: ru-RU
ms.lasthandoff: 07/01/2020
ms.locfileid: "85622735"
---
# <a name="identifying-functions-in-dlls"></a><span data-ttu-id="4c2dd-104">Идентификация функций в библиотеках DLL</span><span class="sxs-lookup"><span data-stu-id="4c2dd-104">Identifying Functions in DLLs</span></span>
<span data-ttu-id="4c2dd-105">Идентификатор функции DLL состоит из следующих элементов:</span><span class="sxs-lookup"><span data-stu-id="4c2dd-105">The identity of a DLL function consists of the following elements:</span></span>  
  
- <span data-ttu-id="4c2dd-106">Имя функции или порядковый номер</span><span class="sxs-lookup"><span data-stu-id="4c2dd-106">Function name or ordinal</span></span>  
  
- <span data-ttu-id="4c2dd-107">Имя файла DLL, в котором находится реализация</span><span class="sxs-lookup"><span data-stu-id="4c2dd-107">Name of the DLL file in which the implementation can be found</span></span>  
  
 <span data-ttu-id="4c2dd-108">Например, при указании функции **MessageBox** в библиотеке User32.dll определяется функция (**MessageBox**) и ее расположение (User32.dll, User32 или user32).</span><span class="sxs-lookup"><span data-stu-id="4c2dd-108">For example, specifying the **MessageBox** function in the User32.dll identifies the function (**MessageBox**) and its location (User32.dll, User32, or user32).</span></span> <span data-ttu-id="4c2dd-109">Программный интерфейс Microsoft Windows (API Windows) может содержать две версии для каждой функции, обрабатывающей символы и строки: версию ANSI для однобайтовых символов и версию Юникода для двухбайтовых символов.</span><span class="sxs-lookup"><span data-stu-id="4c2dd-109">The Microsoft Windows application programming interface (Windows API) can contain two versions of each function that handles characters and strings: a 1-byte character ANSI version and a 2-byte character Unicode version.</span></span> <span data-ttu-id="4c2dd-110">Если кодировка не указана, она определяется полем <xref:System.Runtime.InteropServices.DllImportAttribute.CharSet> (по умолчанию ANSI).</span><span class="sxs-lookup"><span data-stu-id="4c2dd-110">When unspecified, the character set, represented by the <xref:System.Runtime.InteropServices.DllImportAttribute.CharSet> field, defaults to ANSI.</span></span> <span data-ttu-id="4c2dd-111">Некоторые функции могут иметь более двух версий.</span><span class="sxs-lookup"><span data-stu-id="4c2dd-111">Some functions can have more than two versions.</span></span>  
  
 <span data-ttu-id="4c2dd-112">**MessageBoxA** — это точка входа ANSI для функции **MessageBox**; **MessageBoxW** — версия для Юникода.</span><span class="sxs-lookup"><span data-stu-id="4c2dd-112">**MessageBoxA** is the ANSI entry point for the **MessageBox** function; **MessageBoxW** is the Unicode version.</span></span> <span data-ttu-id="4c2dd-113">Чтобы получить список имен функций в конкретной библиотеке DLL, например user32.dll, можно воспользоваться различными средствами командной строки.</span><span class="sxs-lookup"><span data-stu-id="4c2dd-113">You can list function names for a specific DLL, such as user32.dll, by running a variety of command-line tools.</span></span> <span data-ttu-id="4c2dd-114">Например, для получения имен функций можно воспользоваться `dumpbin /exports user32.dll` или `link /dump /exports user32.dll`.</span><span class="sxs-lookup"><span data-stu-id="4c2dd-114">For example, you can use `dumpbin /exports user32.dll` or `link /dump /exports user32.dll` to obtain function names.</span></span>  
  
 <span data-ttu-id="4c2dd-115">Неуправляемую функцию в коде можно переименовать, при условии что новое имя функции соответствует исходной точке входа в библиотеке DLL.</span><span class="sxs-lookup"><span data-stu-id="4c2dd-115">You can rename an unmanaged function to whatever you like within your code as long as you map the new name to the original entry point in the DLL.</span></span> <span data-ttu-id="4c2dd-116">Инструкции по переименованию неуправляемой функции DLL в управляемом исходном коде см. в разделе [Указание точки входа](specifying-an-entry-point.md).</span><span class="sxs-lookup"><span data-stu-id="4c2dd-116">For instructions on renaming an unmanaged DLL function in managed source code, see the [Specifying an Entry Point](specifying-an-entry-point.md).</span></span>  
  
 <span data-ttu-id="4c2dd-117">Вызов неуправляемого кода позволяет управлять значительной частью операционной системы с помощью вызова функций в API Windows и других библиотеках DLL.</span><span class="sxs-lookup"><span data-stu-id="4c2dd-117">Platform invoke enables you to control a significant portion of the operating system by calling functions in the Windows API and other DLLs.</span></span> <span data-ttu-id="4c2dd-118">Наряду с API Windows существует несколько других API и библиотек DLL, для которых доступен вызов неуправляемого кода.</span><span class="sxs-lookup"><span data-stu-id="4c2dd-118">In addition to the Windows API, there are numerous other APIs and DLLs available to you through platform invoke.</span></span>  
  
 <span data-ttu-id="4c2dd-119">В следующей таблице описаны несколько распространенных библиотек DLL в API Windows.</span><span class="sxs-lookup"><span data-stu-id="4c2dd-119">The following table describes several commonly used DLLs in the Windows API.</span></span>  
  
|<span data-ttu-id="4c2dd-120">DLL</span><span class="sxs-lookup"><span data-stu-id="4c2dd-120">DLL</span></span>|<span data-ttu-id="4c2dd-121">Описание содержимого</span><span class="sxs-lookup"><span data-stu-id="4c2dd-121">Description of Contents</span></span>|  
|---------|-----------------------------|  
|<span data-ttu-id="4c2dd-122">GDI32.dll</span><span class="sxs-lookup"><span data-stu-id="4c2dd-122">GDI32.dll</span></span>|<span data-ttu-id="4c2dd-123">Функции интерфейса графических устройств (GDI) для вывода информации на устройство, например функции для рисования и управления шрифтами.</span><span class="sxs-lookup"><span data-stu-id="4c2dd-123">Graphics Device Interface (GDI) functions for device output, such as those for drawing and font management.</span></span>|  
|<span data-ttu-id="4c2dd-124">Kernel32.dll</span><span class="sxs-lookup"><span data-stu-id="4c2dd-124">Kernel32.dll</span></span>|<span data-ttu-id="4c2dd-125">Низкоуровневые функции операционной системы для управления памятью и обработки ресурсов.</span><span class="sxs-lookup"><span data-stu-id="4c2dd-125">Low-level operating system functions for memory management and resource handling.</span></span>|  
|<span data-ttu-id="4c2dd-126">User32.dll</span><span class="sxs-lookup"><span data-stu-id="4c2dd-126">User32.dll</span></span>|<span data-ttu-id="4c2dd-127">Функции управления Windows для обработки сообщений, таймеров, меню и обмена данными.</span><span class="sxs-lookup"><span data-stu-id="4c2dd-127">Windows management functions for message handling, timers, menus, and communications.</span></span>|  
  
 <span data-ttu-id="4c2dd-128">Полную документацию по API Windows см. в разделе "Пакет SDK платформы".</span><span class="sxs-lookup"><span data-stu-id="4c2dd-128">For complete documentation on the Windows API, see the Platform SDK.</span></span> <span data-ttu-id="4c2dd-129">Примеры, демонстрирующие создание объявлений на основе .NET, которые используются с вызовом неуправляемого кода, см. в разделе [Маршалинг данных при вызове неуправляемого кода](marshaling-data-with-platform-invoke.md).</span><span class="sxs-lookup"><span data-stu-id="4c2dd-129">For examples that demonstrate how to construct .NET-based declarations to be used with platform invoke, see [Marshaling Data with Platform Invoke](marshaling-data-with-platform-invoke.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4c2dd-130">См. также</span><span class="sxs-lookup"><span data-stu-id="4c2dd-130">See also</span></span>

- [<span data-ttu-id="4c2dd-131">Использование неуправляемых функций DLL</span><span class="sxs-lookup"><span data-stu-id="4c2dd-131">Consuming Unmanaged DLL Functions</span></span>](consuming-unmanaged-dll-functions.md)
- [<span data-ttu-id="4c2dd-132">Задание точки входа</span><span class="sxs-lookup"><span data-stu-id="4c2dd-132">Specifying an Entry Point</span></span>](specifying-an-entry-point.md)
- [<span data-ttu-id="4c2dd-133">Создание класса, содержащего функции DLL</span><span class="sxs-lookup"><span data-stu-id="4c2dd-133">Creating a Class to Hold DLL Functions</span></span>](creating-a-class-to-hold-dll-functions.md)
- [<span data-ttu-id="4c2dd-134">Создание прототипов в управляемом коде</span><span class="sxs-lookup"><span data-stu-id="4c2dd-134">Creating Prototypes in Managed Code</span></span>](creating-prototypes-in-managed-code.md)
- [<span data-ttu-id="4c2dd-135">Вызов функции DLL</span><span class="sxs-lookup"><span data-stu-id="4c2dd-135">Calling a DLL Function</span></span>](calling-a-dll-function.md)
