---
title: Вызов функции DLL
description: Узнайте о некоторых особенностях вызова функции DLL, который может показаться сложным процессом. Процесс вызова функции зависит от того, является ли тип возвращаемого значения непреобразуемым.
ms.date: 03/30/2017
helpviewer_keywords:
- unmanaged functions, calling
- unmanaged functions
- COM interop, platform invoke
- platform invoke, calling unmanaged functions
- interoperation with unmanaged code, platform invoke
- DLL functions
ms.assetid: 113646de-7ea0-4f0e-8df0-c46dab3e8733
ms.openlocfilehash: 90f8f47148e652a9942a35be1564bed94c155216
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.contentlocale: ru-RU
ms.lasthandoff: 07/01/2020
ms.locfileid: "85620902"
---
# <a name="calling-a-dll-function"></a><span data-ttu-id="b5b45-104">Вызов функции DLL</span><span class="sxs-lookup"><span data-stu-id="b5b45-104">Calling a DLL Function</span></span>
<span data-ttu-id="b5b45-105">Хотя вызов неуправляемых функций DLL почти идентичен вызову другого управляемого кода, все же существуют отличия, которые поначалу могут вызвать некоторые сложности в освоении функций DLL.</span><span class="sxs-lookup"><span data-stu-id="b5b45-105">Although calling unmanaged DLL functions is nearly identical to calling other managed code, there are differences that can make DLL functions seem confusing at first.</span></span> <span data-ttu-id="b5b45-106">В этом разделе представлены статьи, касающиеся некоторых особенностей вызовов.</span><span class="sxs-lookup"><span data-stu-id="b5b45-106">This section introduces topics that describe some of the unusual calling-related issues.</span></span>  
  
 <span data-ttu-id="b5b45-107">Структуры, возвращаемые из вызовов неуправляемого кода, должны быть типами данных, имеющими одинаковые представления в управляемом и неуправляемом коде.</span><span class="sxs-lookup"><span data-stu-id="b5b45-107">Structures that are returned from platform invoke calls must be data types that have the same representation in managed and unmanaged code.</span></span> <span data-ttu-id="b5b45-108">Такие типы называются *непреобразуемыми типами*, так как они не требуют преобразования (см. раздел [Непреобразуемые и преобразуемые типы](blittable-and-non-blittable-types.md)).</span><span class="sxs-lookup"><span data-stu-id="b5b45-108">Such types are called *blittable types* because they do not require conversion (see [Blittable and Non-Blittable Types](blittable-and-non-blittable-types.md)).</span></span> <span data-ttu-id="b5b45-109">Чтобы вызвать функцию с преобразуемой структурой в качестве ее возвращаемого типа, можно определить непреобразуемый вспомогательный тип того же размера, что и преобразуемый тип, и преобразовать данные после возвращения функции.</span><span class="sxs-lookup"><span data-stu-id="b5b45-109">To call a function that has a non-blittable structure as its return type, you can define a blittable helper type of the same size as the non-blittable type and convert the data after the function returns.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="b5b45-110">В этом разделе</span><span class="sxs-lookup"><span data-stu-id="b5b45-110">In This Section</span></span>  
 [<span data-ttu-id="b5b45-111">Передача структур</span><span class="sxs-lookup"><span data-stu-id="b5b45-111">Passing Structures</span></span>](passing-structures.md)  
 <span data-ttu-id="b5b45-112">Описываются вопросы передачи структур данных с предопределенной компоновкой.</span><span class="sxs-lookup"><span data-stu-id="b5b45-112">Identifies the issues of passing data structures with a predefined layout.</span></span>  
  
 [<span data-ttu-id="b5b45-113">Функции обратного вызова</span><span class="sxs-lookup"><span data-stu-id="b5b45-113">Callback Functions</span></span>](callback-functions.md)  
 <span data-ttu-id="b5b45-114">Основные сведения о функциях обратного вызова.</span><span class="sxs-lookup"><span data-stu-id="b5b45-114">Provides basic information about callback functions.</span></span>  
  
 [<span data-ttu-id="b5b45-115">Практическое руководство. Реализация функций обратного вызова</span><span class="sxs-lookup"><span data-stu-id="b5b45-115">How to: Implement Callback Functions</span></span>](how-to-implement-callback-functions.md)  
 <span data-ttu-id="b5b45-116">Описывается реализация функций обратного вызова в управляемом коде.</span><span class="sxs-lookup"><span data-stu-id="b5b45-116">Describes how to implement callback functions in managed code.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="b5b45-117">Связанные разделы</span><span class="sxs-lookup"><span data-stu-id="b5b45-117">Related Sections</span></span>  
 [<span data-ttu-id="b5b45-118">Использование неуправляемых функций DLL</span><span class="sxs-lookup"><span data-stu-id="b5b45-118">Consuming Unmanaged DLL Functions</span></span>](consuming-unmanaged-dll-functions.md)  
 <span data-ttu-id="b5b45-119">Описывает способ вызова неуправляемых функций DLL с помощью вызова платформы.</span><span class="sxs-lookup"><span data-stu-id="b5b45-119">Describes how to call unmanaged DLL functions using platform invoke.</span></span>  
  
 [<span data-ttu-id="b5b45-120">Маршалинг данных при вызове неуправляемого кода</span><span class="sxs-lookup"><span data-stu-id="b5b45-120">Marshaling Data with Platform Invoke</span></span>](marshaling-data-with-platform-invoke.md)  
 <span data-ttu-id="b5b45-121">Описывается способ объявления параметров метода и передачи аргументов в функции, экспортируемые неуправляемыми библиотеками.</span><span class="sxs-lookup"><span data-stu-id="b5b45-121">Describes how to declare method parameters and pass arguments to functions exported by unmanaged libraries.</span></span>
