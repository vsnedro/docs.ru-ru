---
title: Маршалинг с помощью COM- взаимодействия
description: См. статьи, посвященные маршалингу данных с помощью COM-взаимодействия. Инструменты Tlbimp.exe и Tlbexp.exe выполняют преобразование между библиотекой типов COM и сборкой взаимодействия.
ms.date: 09/07/2017
helpviewer_keywords:
- COM interop, data marshaling
- marshaling data, COM interop
ms.openlocfilehash: eedfb60a75e2fe5fafdaa786dbb54adddf28400e
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.contentlocale: ru-RU
ms.lasthandoff: 07/01/2020
ms.locfileid: "85621513"
---
# <a name="marshaling-data-with-com-interop"></a><span data-ttu-id="c5e64-104">Маршалинг с помощью COM- взаимодействия</span><span class="sxs-lookup"><span data-stu-id="c5e64-104">Marshaling Data with COM Interop</span></span>
<span data-ttu-id="c5e64-105">COM-взаимодействие обеспечивает поддержку как для использования COM-объектов из управляемого кода, так и для предоставления доступа к управляемым объектам для COM.</span><span class="sxs-lookup"><span data-stu-id="c5e64-105">COM interop provides support for both using COM objects from managed code and exposing managed objects to COM.</span></span> <span data-ttu-id="c5e64-106">Поддержка маршалинга данных в COM и обратно достаточно полная и почти всегда обеспечивает правильное поведение маршалинга.</span><span class="sxs-lookup"><span data-stu-id="c5e64-106">Support for marshaling data to and from COM is extensive and almost always provides the correct marshaling behavior.</span></span>  
  
 <span data-ttu-id="c5e64-107">Пакет Windows SDK содержит следующие средства COM-взаимодействия:</span><span class="sxs-lookup"><span data-stu-id="c5e64-107">The Windows SDK includes the following COM interop tools:</span></span>  
  
- <span data-ttu-id="c5e64-108">[Средство импорта библиотек типов (Tlbimp.exe)](../tools/tlbimp-exe-type-library-importer.md), которое преобразует библиотеку типов COM в сборку взаимодействия.</span><span class="sxs-lookup"><span data-stu-id="c5e64-108">[Type Library Importer (Tlbimp.exe)](../tools/tlbimp-exe-type-library-importer.md), which converts a COM type library to an interop assembly.</span></span> <span data-ttu-id="c5e64-109">Эта сборка используется службой маршалинга взаимодействия для создания оболочек, маршалирующих данные между управляемой и неуправляемой памятью.</span><span class="sxs-lookup"><span data-stu-id="c5e64-109">From this assembly, the interop marshaling service generates wrappers that perform data marshaling between managed and unmanaged memory.</span></span>  
  
- <span data-ttu-id="c5e64-110">[Средство экспорта библиотек типов (Tlbexp.exe)](../tools/tlbexp-exe-type-library-exporter.md), которое создает библиотеку типов COM из сборки и формирует оболочку, которая выполняет маршалинг при вызовах методов.</span><span class="sxs-lookup"><span data-stu-id="c5e64-110">[Type Library Exporter (Tlbexp.exe)](../tools/tlbexp-exe-type-library-exporter.md), which produces a COM type library from an assembly and generates a wrapper that performs marshaling during method calls.</span></span>  
  
 <span data-ttu-id="c5e64-111">Следующие разделы посвящены процессам настройки оболочек взаимодействий для случаев, когда можно (или необходимо) предоставить упаковщику дополнительную информацию о типах.</span><span class="sxs-lookup"><span data-stu-id="c5e64-111">The following sections link to topics that describe the processes for customizing interop wrappers when you can (or must) supply the marshaler with additional type information.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="c5e64-112">В этом разделе</span><span class="sxs-lookup"><span data-stu-id="c5e64-112">In This Section</span></span>  
<span data-ttu-id="c5e64-113">[Практическое руководство. Создание оболочек вручную](how-to-create-wrappers-manually.md) Сведения о том, как вручную создать программу-оболочку COM в управляемом исходном коде.</span><span class="sxs-lookup"><span data-stu-id="c5e64-113">[How to: Create Wrappers Manually](how-to-create-wrappers-manually.md) Describes how to create a COM wrapper manually in managed source code.</span></span>

 [<span data-ttu-id="c5e64-114">Практическое руководство. Миграция DCOM с управляемым кодом в WCF</span><span class="sxs-lookup"><span data-stu-id="c5e64-114">How to: Migrate Managed-Code DCOM to WCF</span></span>](how-to-migrate-managed-code-dcom-to-wcf.md)  
 <span data-ttu-id="c5e64-115">Сведения о переносе управляемого кода DCOM в WCF для получения наиболее безопасного решения.</span><span class="sxs-lookup"><span data-stu-id="c5e64-115">Describes how to migrate managed DCOM code to WCF for the most secure solution.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="c5e64-116">Связанные разделы</span><span class="sxs-lookup"><span data-stu-id="c5e64-116">Related Sections</span></span>  
 <span data-ttu-id="c5e64-117">[Типы данных COM](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/sak564ww(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="c5e64-117">[COM Data Types](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/sak564ww(v=vs.100))</span></span>  
 <span data-ttu-id="c5e64-118">Содержит описание соответствующих управляемых и неуправляемых типов данных.</span><span class="sxs-lookup"><span data-stu-id="c5e64-118">Provides corresponding managed and unmanaged data types.</span></span>  
  
 <span data-ttu-id="c5e64-119">[Настройка вызываемых оболочек COM](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/3bwc828w(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="c5e64-119">[Customizing COM Callable Wrappers](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/3bwc828w(v=vs.100))</span></span>  
 <span data-ttu-id="c5e64-120">В этой статье описан способ явного маршалинга типов данных с использованием атрибута <xref:System.Runtime.InteropServices.MarshalAsAttribute> во время разработки.</span><span class="sxs-lookup"><span data-stu-id="c5e64-120">Describes how to explicitly marshal data types using the <xref:System.Runtime.InteropServices.MarshalAsAttribute> attribute at design time.</span></span>  
  
 <span data-ttu-id="c5e64-121">[Настройка вызываемых оболочек времени выполнения](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/e753eftz(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="c5e64-121">[Customizing Runtime Callable Wrappers](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/e753eftz(v=vs.100))</span></span>  
 <span data-ttu-id="c5e64-122">Описаны способы настройки связанного с маршалингом поведения типов в сборке взаимодействия и определения типов COM вручную.</span><span class="sxs-lookup"><span data-stu-id="c5e64-122">Describes how to adjust the marshaling behavior of types in an interop assembly and how to define COM types manually.</span></span>  
  
 <span data-ttu-id="c5e64-123">[Расширенное COM-взаимодействие](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/bd9cdfyx(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="c5e64-123">[Advanced COM Interoperability](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/bd9cdfyx(v=vs.100))</span></span>  
 <span data-ttu-id="c5e64-124">Приводятся ссылки на дополнительные сведения о включении COM-компонентов в разрабатываемое приложение .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="c5e64-124">Provides links to more information about incorporating COM components into your .NET Framework application.</span></span>  
  
 <span data-ttu-id="c5e64-125">[Общие сведения о преобразовании сборки в библиотеку типов](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/xk1120c3(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="c5e64-125">[Assembly to Type Library Conversion Summary](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/xk1120c3(v=vs.100))</span></span>  
 <span data-ttu-id="c5e64-126">Описывается процесс преобразования при экспорте сборки в библиотеку типов.</span><span class="sxs-lookup"><span data-stu-id="c5e64-126">Describes the assembly to type library export conversion process.</span></span>  
  
 <span data-ttu-id="c5e64-127">[Общие сведения о преобразовании библиотеки типов в сборку](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/k83zzh38(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="c5e64-127">[Type Library to Assembly Conversion Summary](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/k83zzh38(v=vs.100))</span></span>  
 <span data-ttu-id="c5e64-128">Описывается процесс преобразования при экспорте библиотеки типов в сборку.</span><span class="sxs-lookup"><span data-stu-id="c5e64-128">Describes the type library to assembly import conversion process.</span></span>  
  
 <span data-ttu-id="c5e64-129">[Взаимодействие с помощью универсальных типов](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/ms229590(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="c5e64-129">[Interoperating Using Generic Types](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/ms229590(v=vs.100))</span></span>  
 <span data-ttu-id="c5e64-130">Описываются действия, поддерживаемые при использовании универсальных типов для взаимодействия COM.</span><span class="sxs-lookup"><span data-stu-id="c5e64-130">Describes which actions are supported when using generic types for COM interoperability.</span></span>
