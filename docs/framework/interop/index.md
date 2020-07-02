---
title: Взаимодействие с неуправляемым кодом
description: Обзор взаимодействия с неуправляемым кодом. Среда CLR скрывает от клиентов и серверов различия между объектными моделями для компонентов .NET и неуправляемого кода.
ms.date: 01/17/2018
helpviewer_keywords:
- unmanaged code, interoperation
- managed code, interoperation with unmanaged code
- .NET Framework, interoperation with unmanaged code
- unmanaged code
- interoperation with unmanaged code
- interoperation with unmanaged code, about interoperation
- components [.NET Framework], interoperation with unmanaged code
ms.assetid: ccb68ce7-b0e9-4ffb-839d-03b1cd2c1258
ms.openlocfilehash: 1cebd75907fd202715cb337593186d248107bdbb
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/01/2020
ms.locfileid: "85621877"
---
# <a name="interoperating-with-unmanaged-code"></a><span data-ttu-id="46cb3-104">Взаимодействие с неуправляемым кодом</span><span class="sxs-lookup"><span data-stu-id="46cb3-104">Interoperating with unmanaged code</span></span>

<span data-ttu-id="46cb3-105">Платформа .NET Framework обеспечивает взаимодействие с COM-компонентами, службами COM+, внешними библиотеками типов и многими службами операционной системы.</span><span class="sxs-lookup"><span data-stu-id="46cb3-105">The .NET Framework promotes interaction with COM components, COM+ services, external type libraries, and many operating system services.</span></span> <span data-ttu-id="46cb3-106">Типы данных, подписи методов и механизмы обработки ошибок различны в управляемой и неуправляемой моделях объектов.</span><span class="sxs-lookup"><span data-stu-id="46cb3-106">Data types, method signatures, and error-handling mechanisms vary between managed and unmanaged object models.</span></span> <span data-ttu-id="46cb3-107">Для упрощения взаимодействия между компонентами .NET Framework и неуправляемым программным кодом, а также для облегчения перехода от одной модели к другой среда CLR скрывает имеющиеся в этих объектных моделях различия от клиентов и серверов.</span><span class="sxs-lookup"><span data-stu-id="46cb3-107">To simplify interoperation between .NET Framework components and unmanaged code and to ease the migration path, the common language runtime conceals from both clients and servers the differences in these object models.</span></span>

<span data-ttu-id="46cb3-108">Код, выполняющийся под управлением среды выполнения, называется управляемым кодом.</span><span class="sxs-lookup"><span data-stu-id="46cb3-108">Code that executes under the control of the runtime is called managed code.</span></span> <span data-ttu-id="46cb3-109">И наоборот, код, выполняемый вне среды выполнения, называется неуправляемым кодом.</span><span class="sxs-lookup"><span data-stu-id="46cb3-109">Conversely, code that runs outside the runtime is called unmanaged code.</span></span> <span data-ttu-id="46cb3-110">Примерами неуправляемого кода являются компоненты COM, интерфейсы ActiveX и функции Windows API.</span><span class="sxs-lookup"><span data-stu-id="46cb3-110">COM components, ActiveX interfaces, and Windows API functions are examples of unmanaged code.</span></span>

## <a name="in-this-section"></a><span data-ttu-id="46cb3-111">Содержание раздела</span><span class="sxs-lookup"><span data-stu-id="46cb3-111">In this section</span></span>

[<span data-ttu-id="46cb3-112">Предоставление COM-компонентов платформе .NET Framework</span><span class="sxs-lookup"><span data-stu-id="46cb3-112">Exposing COM Components to the .NET Framework</span></span>](exposing-com-components.md)  
<span data-ttu-id="46cb3-113">Описывает способы использования COM-компонентов в приложениях .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="46cb3-113">Describes how to use COM components from .NET Framework applications.</span></span>

[<span data-ttu-id="46cb3-114">Предоставление компонентов .NET Framework клиентам COM</span><span class="sxs-lookup"><span data-stu-id="46cb3-114">Exposing .NET Framework Components to COM</span></span>](exposing-dotnet-components-to-com.md)  
<span data-ttu-id="46cb3-115">Описывает способы использования компонентов .NET Framework в приложениях COM.</span><span class="sxs-lookup"><span data-stu-id="46cb3-115">Describes how to use .NET Framework components from COM applications.</span></span>

[<span data-ttu-id="46cb3-116">Использование неуправляемых функций DLL</span><span class="sxs-lookup"><span data-stu-id="46cb3-116">Consuming Unmanaged DLL Functions</span></span>](consuming-unmanaged-dll-functions.md)  
<span data-ttu-id="46cb3-117">Описывает способ вызова неуправляемых функций DLL с помощью вызова платформы.</span><span class="sxs-lookup"><span data-stu-id="46cb3-117">Describes how to call unmanaged DLL functions using platform invoke.</span></span>

[<span data-ttu-id="46cb3-118">Маршалинг взаимодействия</span><span class="sxs-lookup"><span data-stu-id="46cb3-118">Interop Marshaling</span></span>](interop-marshaling.md)  
<span data-ttu-id="46cb3-119">Описывается маршалинг для COM-взаимодействия и вызова платформы.</span><span class="sxs-lookup"><span data-stu-id="46cb3-119">Describes marshaling for COM interop and platform invoke.</span></span>

[<span data-ttu-id="46cb3-120">Практическое руководство. Сопоставление значений HRESULT и исключений</span><span class="sxs-lookup"><span data-stu-id="46cb3-120">How to: Map HRESULTs and Exceptions</span></span>](how-to-map-hresults-and-exceptions.md)  
<span data-ttu-id="46cb3-121">Описывает сопоставление исключений и значений HRESULT.</span><span class="sxs-lookup"><span data-stu-id="46cb3-121">Describes the mapping between exceptions and HRESULTs.</span></span>

[<span data-ttu-id="46cb3-122">Эквивалентность типов и внедренные типы взаимодействия</span><span class="sxs-lookup"><span data-stu-id="46cb3-122">Type Equivalence and Embedded Interop Types</span></span>](type-equivalence-and-embedded-interop-types.md)  
<span data-ttu-id="46cb3-123">Описывается способ внедрения сведений о типах COM в сборках и определения общеязыковой средой выполнения эквивалентности встроенных типов COM.</span><span class="sxs-lookup"><span data-stu-id="46cb3-123">Describes how type information for COM types is embedded in assemblies, and how the common language runtime determines the equivalence of embedded COM types.</span></span>

[<span data-ttu-id="46cb3-124">Практическое руководство. Создание основной сборки взаимодействия с помощью программы Tlbimp.exe</span><span class="sxs-lookup"><span data-stu-id="46cb3-124">How to: Generate Primary Interop Assemblies Using Tlbimp.exe</span></span>](how-to-generate-primary-interop-assemblies-using-tlbimp-exe.md)  
<span data-ttu-id="46cb3-125">Описывается способ создания основных сборок взаимодействия с помощью *Tlbimp.exe* (программа импорта библиотек типов).</span><span class="sxs-lookup"><span data-stu-id="46cb3-125">Describes how to produce primary interop assemblies using *Tlbimp.exe* (Type Library Importer).</span></span>

[<span data-ttu-id="46cb3-126">Практическое руководство. Регистрация основных сборок взаимодействия</span><span class="sxs-lookup"><span data-stu-id="46cb3-126">How to: Register Primary Interop Assemblies</span></span>](how-to-register-primary-interop-assemblies.md)  
<span data-ttu-id="46cb3-127">Описывается регистрация основных сборок взаимодействия до того, как на них можно будет создавать ссылки в проектах.</span><span class="sxs-lookup"><span data-stu-id="46cb3-127">Describes how to register the primary interop assemblies before you can reference them in your projects.</span></span>

[<span data-ttu-id="46cb3-128">COM-взаимодействие без регистрации</span><span class="sxs-lookup"><span data-stu-id="46cb3-128">Registration-Free COM Interop</span></span>](registration-free-com-interop.md)  
<span data-ttu-id="46cb3-129">Описывается способ активации COM-взаимодействием компонентов без использования реестра Windows.</span><span class="sxs-lookup"><span data-stu-id="46cb3-129">Describes how COM interop can activate components without using the Windows registry.</span></span>

[<span data-ttu-id="46cb3-130">Практическое руководство. Настройка COM-компонентов на основе платформы .NET Framework для активации без регистрации</span><span class="sxs-lookup"><span data-stu-id="46cb3-130">How to: Configure .NET Framework-Based COM Components for Registration-Free Activation</span></span>](configure-net-framework-based-com-components-for-reg.md)  
<span data-ttu-id="46cb3-131">Описывается способ создания манифеста приложения, а также создания и внедрения манифеста компонента.</span><span class="sxs-lookup"><span data-stu-id="46cb3-131">Describes how to create an application manifest and how to create and embed a component manifest.</span></span>

## <a name="related-sections"></a><span data-ttu-id="46cb3-132">Связанные разделы</span><span class="sxs-lookup"><span data-stu-id="46cb3-132">Related sections</span></span>

[<span data-ttu-id="46cb3-133">Oболочки COM</span><span class="sxs-lookup"><span data-stu-id="46cb3-133">COM Wrappers</span></span>](../../standard/native-interop/com-wrappers.md)  
<span data-ttu-id="46cb3-134">Описываются программы-оболочки, предоставляемые COM-взаимодействием.</span><span class="sxs-lookup"><span data-stu-id="46cb3-134">Describes the wrappers provided by COM interop.</span></span>
