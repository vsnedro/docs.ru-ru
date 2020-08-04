---
title: Руководство по программированию на C#. Взаимодействие
description: Возможность взаимодействия обеспечивает поддержку неуправляемого кода наряду с кодом, который выполняется в общеязыковой среде выполнения. Дополнительные сведения о параметрах взаимодействия можно найти в приведенных ниже ресурсах.
ms.date: 07/20/2015
helpviewer_keywords:
- COM interop
- interoperability
- platform invoke, accessing APIs with C#
- C# language, interoperability
ms.assetid: 238bb95a-e962-4026-bbd5-197055bdb8ee
ms.openlocfilehash: d85eb51107d50e023270fcbe1ef6e08a7788ae78
ms.sourcegitcommit: 6f58a5f75ceeb936f8ee5b786e9adb81a9a3bee9
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/28/2020
ms.locfileid: "87302975"
---
# <a name="interoperability-c-programming-guide"></a><span data-ttu-id="fedb6-104">Взаимодействие (Руководство по программированию в C#)</span><span class="sxs-lookup"><span data-stu-id="fedb6-104">Interoperability (C# Programming Guide)</span></span>

<span data-ttu-id="fedb6-105">Возможность взаимодействия позволяет использовать уже созданный неуправляемый код, экономя средства на разработку.</span><span class="sxs-lookup"><span data-stu-id="fedb6-105">Interoperability enables you to preserve and take advantage of existing investments in unmanaged code.</span></span> <span data-ttu-id="fedb6-106">Код, который выполняется под управлением среды CLR, называется *управляемым кодом*, а код, который выполняется вне среды CLR, называется *неуправляемым кодом*.</span><span class="sxs-lookup"><span data-stu-id="fedb6-106">Code that runs under the control of the common language runtime (CLR) is called *managed code*, and code that runs outside the CLR is called *unmanaged code*.</span></span> <span data-ttu-id="fedb6-107">COM, COM +, компоненты C++, компоненты ActiveX и Microsoft Windows API являются примерами неуправляемого кода.</span><span class="sxs-lookup"><span data-stu-id="fedb6-107">COM, COM+, C++ components, ActiveX components, and Microsoft Windows API are examples of unmanaged code.</span></span>  
  
<span data-ttu-id="fedb6-108">.NET обеспечивает взаимодействие с неуправляемым кодом посредством служб вызова неуправляемого кода (PInvoke), пространства имен <xref:System.Runtime.InteropServices>, COM-взаимодействия и взаимодействия с C++.</span><span class="sxs-lookup"><span data-stu-id="fedb6-108">.NET enables interoperability with unmanaged code through platform invoke services, the <xref:System.Runtime.InteropServices> namespace, C++ interoperability, and COM interoperability (COM interop).</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="fedb6-109">В этом разделе</span><span class="sxs-lookup"><span data-stu-id="fedb6-109">In This Section</span></span>  
 [<span data-ttu-id="fedb6-110">Общие сведения о взаимодействии</span><span class="sxs-lookup"><span data-stu-id="fedb6-110">Interoperability Overview</span></span>](./interoperability-overview.md)  
 <span data-ttu-id="fedb6-111">Описывает способы взаимодействия между управляемым кодом C# и неуправляемым кодом.</span><span class="sxs-lookup"><span data-stu-id="fedb6-111">Describes methods to interoperate between C# managed code and unmanaged code.</span></span>  
  
 [<span data-ttu-id="fedb6-112">Практическое руководство. Доступ к объектам взаимодействия Office с помощью функций языка C#</span><span class="sxs-lookup"><span data-stu-id="fedb6-112">How to access Office interop objects by using C# features</span></span>](./how-to-access-office-onterop-objects.md)  
 <span data-ttu-id="fedb6-113">Описывает возможности, представленные в Visual C#, которые упрощают программирование для Office.</span><span class="sxs-lookup"><span data-stu-id="fedb6-113">Describes features that are introduced in Visual C# to facilitate Office programming.</span></span>  
  
 [<span data-ttu-id="fedb6-114">Практическое руководство. Использование индексированных свойств в программировании COM-взаимодействия</span><span class="sxs-lookup"><span data-stu-id="fedb6-114">How to use indexed properties in COM interop programming</span></span>](./how-to-use-indexed-properties-in-com-interop-rogramming.md)  
 <span data-ttu-id="fedb6-115">Описывает использование индексированных свойств для доступа к свойствам COM, которые имеют параметры.</span><span class="sxs-lookup"><span data-stu-id="fedb6-115">Describes how to use indexed properties to access COM properties that have parameters.</span></span>  
  
 [<span data-ttu-id="fedb6-116">Практическое руководство. Использование вызова неуправляемого кода для воспроизведения WAV-файла</span><span class="sxs-lookup"><span data-stu-id="fedb6-116">How to use platform invoke to play a WAV file</span></span>](./how-to-use-platform-invoke-to-play-a-wave-file.md)  
 <span data-ttu-id="fedb6-117">Описывает, как использовать платформу вызова служб, чтобы воспроизвести звуковой WAV-файл в операционной системе Windows.</span><span class="sxs-lookup"><span data-stu-id="fedb6-117">Describes how to use platform invoke services to play a .wav sound file on the Windows operating system.</span></span>  
  
 [<span data-ttu-id="fedb6-118">Пошаговое руководство. Программирование для Office</span><span class="sxs-lookup"><span data-stu-id="fedb6-118">Walkthrough: Office Programming</span></span>](./walkthrough-office-programming.md)  
 <span data-ttu-id="fedb6-119">Описывает процесс создания книги Excel и документа Word со ссылкой на эту книгу.</span><span class="sxs-lookup"><span data-stu-id="fedb6-119">Shows how to create an Excel workbook and a Word document that contains a link to the workbook.</span></span>  
  
 [<span data-ttu-id="fedb6-120">Пример COM-класса</span><span class="sxs-lookup"><span data-stu-id="fedb6-120">Example COM Class</span></span>](./example-com-class.md)  
 <span data-ttu-id="fedb6-121">Предлагает пример предоставления класса C# в качестве COM-объекта.</span><span class="sxs-lookup"><span data-stu-id="fedb6-121">Demonstrates how to expose a C# class as a COM object.</span></span>  
  
## <a name="c-language-specification"></a><span data-ttu-id="fedb6-122">Спецификация языка C#</span><span class="sxs-lookup"><span data-stu-id="fedb6-122">C# Language Specification</span></span>  

<span data-ttu-id="fedb6-123">Дополнительные сведения см. в разделе [Основные понятия](~/_csharplang/spec/unsafe-code.md) в [Спецификации языка C#](/dotnet/csharp/language-reference/language-specification/introduction).</span><span class="sxs-lookup"><span data-stu-id="fedb6-123">For more information, see [Basic concepts](~/_csharplang/spec/unsafe-code.md) in the [C# Language Specification](/dotnet/csharp/language-reference/language-specification/introduction).</span></span> <span data-ttu-id="fedb6-124">Спецификация языка является предписывающим источником информации о синтаксисе и использовании языка C#.</span><span class="sxs-lookup"><span data-stu-id="fedb6-124">The language specification is the definitive source for C# syntax and usage.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="fedb6-125">См. также</span><span class="sxs-lookup"><span data-stu-id="fedb6-125">See also</span></span>

- <xref:System.Runtime.InteropServices.Marshal.ReleaseComObject%2A?displayProperty=nameWithType>
- [<span data-ttu-id="fedb6-126">Руководство по программированию на C#</span><span class="sxs-lookup"><span data-stu-id="fedb6-126">C# Programming Guide</span></span>](../index.md)
- [<span data-ttu-id="fedb6-127">Взаимодействие с неуправляемым кодом</span><span class="sxs-lookup"><span data-stu-id="fedb6-127">Interoperating with Unmanaged Code</span></span>](../../../framework/interop/index.md)
- [<span data-ttu-id="fedb6-128">Пошаговое руководство: Программирование для Office</span><span class="sxs-lookup"><span data-stu-id="fedb6-128">Walkthrough: Office Programming</span></span>](./walkthrough-office-programming.md)
