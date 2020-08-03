---
title: Предоставление динамических методов и сборок
description: Предоставляйте динамические методы и сборки с помощью пространства имен System.Reflection.Emit, которое позволяет компилятору или средству порождать метаданные и код MSIL во время выполнения.
ms.date: 08/30/2017
helpviewer_keywords:
- reflection emit
- dynamic assemblies
- metadata, emit interfaces
- reflection emit, overview
- assemblies [.NET Framework], emitting dynamic assemblies
ms.openlocfilehash: 76d2a83943d9df06cc66cf86c6869f18fac2a12c
ms.sourcegitcommit: cf5a800a33de64d0aad6d115ffcc935f32375164
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/20/2020
ms.locfileid: "86475051"
---
# <a name="emitting-dynamic-methods-and-assemblies"></a><span data-ttu-id="415e5-103">Предоставление динамических методов и сборок</span><span class="sxs-lookup"><span data-stu-id="415e5-103">Emitting Dynamic Methods and Assemblies</span></span>

<span data-ttu-id="415e5-104">В этом разделе описывается набор управляемых типов в пространстве имен <xref:System.Reflection.Emit>, позволяющий компилятору или средству порождать метаданные и код MSIL во время выполнения, а также при необходимости создавать переносимый исполняемый (PE) файл на диске.</span><span class="sxs-lookup"><span data-stu-id="415e5-104">This section describes a set of managed types in the <xref:System.Reflection.Emit> namespace that allow a compiler or tool to emit metadata and Microsoft intermediate language (MSIL) at run time and optionally generate a portable executable (PE) file on disk.</span></span> <span data-ttu-id="415e5-105">Основными пользователями этого пространства имен являются обработчики скриптов и компиляторы.</span><span class="sxs-lookup"><span data-stu-id="415e5-105">Script engines and compilers are the primary users of this namespace.</span></span> <span data-ttu-id="415e5-106">В этом разделе функциональные возможности, предоставляемые пространством имен <xref:System.Reflection.Emit>, называются порождением отражения.</span><span class="sxs-lookup"><span data-stu-id="415e5-106">In this section, the functionality provided by the <xref:System.Reflection.Emit> namespace is referred to as reflection emit.</span></span>  
  
<span data-ttu-id="415e5-107">Порождение отражения предоставляет следующие возможности:</span><span class="sxs-lookup"><span data-stu-id="415e5-107">Reflection emit provides the following capabilities:</span></span>  
  
- <span data-ttu-id="415e5-108">определение облегченных глобальных методов во время выполнения с помощью класса <xref:System.Reflection.Emit.DynamicMethod> и их выполнение с помощью делегатов;</span><span class="sxs-lookup"><span data-stu-id="415e5-108">Define lightweight global methods at run time, using the <xref:System.Reflection.Emit.DynamicMethod> class, and execute them using delegates.</span></span>  
  
- <span data-ttu-id="415e5-109">определение сборок во время выполнения и последующий их запуск или сохранение на диск;</span><span class="sxs-lookup"><span data-stu-id="415e5-109">Define assemblies at run time and then run them and/or save them to disk.</span></span>  
  
- <span data-ttu-id="415e5-110">определение сборок во время выполнения с последующим их запуском, выгрузкой и предоставлением сборке мусора разрешения на получение их ресурсов;</span><span class="sxs-lookup"><span data-stu-id="415e5-110">Define assemblies at run time, run them, and then unload them and allow garbage collection to reclaim their resources.</span></span>  
  
- <span data-ttu-id="415e5-111">определение модулей в новых сборках во время выполнения с последующим их запуском или сохранением на диске;</span><span class="sxs-lookup"><span data-stu-id="415e5-111">Define modules in new assemblies at run time and then run and/or save them to disk.</span></span>  
  
- <span data-ttu-id="415e5-112">определение типов в модулях во время выполнения, создание экземпляров этих типов и вызов их методов;</span><span class="sxs-lookup"><span data-stu-id="415e5-112">Define types in modules at run time, create instances of these types, and invoke their methods.</span></span>  
  
- <span data-ttu-id="415e5-113">определение символьной информации для определяемых модулей, которая может использоваться такими средствами, как отладчики и профилировщики кода.</span><span class="sxs-lookup"><span data-stu-id="415e5-113">Define symbolic information for defined modules that can be used by tools such as debuggers and code profilers.</span></span>  
  
<span data-ttu-id="415e5-114">Наряду с управляемыми типами в пространстве имен <xref:System.Reflection.Emit> существуют неуправляемые интерфейсы метаданных, которые описаны в статье [Интерфейсы метаданных](../unmanaged-api/metadata/metadata-interfaces.md) справочной документации.</span><span class="sxs-lookup"><span data-stu-id="415e5-114">In addition to the managed types in the <xref:System.Reflection.Emit> namespace, there are unmanaged metadata interfaces which are described in the [Metadata Interfaces](../unmanaged-api/metadata/metadata-interfaces.md) reference documentation.</span></span> <span data-ttu-id="415e5-115">Управляемое порождение отражения обеспечивает более строгую проверку семантических ошибок и более высокий уровень абстрагирования метаданных, чем неуправляемые интерфейсы метаданных.</span><span class="sxs-lookup"><span data-stu-id="415e5-115">Managed reflection emit provides stronger semantic error checking and a higher level of abstraction of the metadata than the unmanaged metadata interfaces.</span></span>  
  
<span data-ttu-id="415e5-116">Другим полезным ресурсом для работы с метаданными и кодом MSIL является документация Common Language Infrastructure (CLI), особенно "Раздел II. Определение метаданных и семантика" и "Раздел III. Набор инструкций CIL".</span><span class="sxs-lookup"><span data-stu-id="415e5-116">Another useful resource for working with metadata and MSIL is the Common Language Infrastructure (CLI) documentation, especially "Partition II: Metadata Definition and Semantics" and "Partition III: CIL Instruction Set".</span></span> <span data-ttu-id="415e5-117">Документация доступна в Интернете на [веб-сайте Ecma](https://www.ecma-international.org/publications/standards/Ecma-335.htm).</span><span class="sxs-lookup"><span data-stu-id="415e5-117">The documentation is available online at the [Ecma Web site](https://www.ecma-international.org/publications/standards/Ecma-335.htm).</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="415e5-118">В этом разделе</span><span class="sxs-lookup"><span data-stu-id="415e5-118">In This Section</span></span>
  
[<span data-ttu-id="415e5-119">Вопросы безопасности в порождении отражения</span><span class="sxs-lookup"><span data-stu-id="415e5-119">Security issues in reflection emit</span></span>](security-issues-in-reflection-emit.md)  
<span data-ttu-id="415e5-120">Описываются проблемы безопасности, связанные с созданием динамических сборок с помощью порождения отражения.</span><span class="sxs-lookup"><span data-stu-id="415e5-120">Describes security issues related to creating dynamic assemblies using reflection emit.</span></span>  

<span data-ttu-id="415e5-121">[Практическое руководство. Определение и выполнение динамических методов](how-to-define-and-execute-dynamic-methods.md). Показывается, как выполнить простой динамический метод и динамический метод, привязанный к экземпляру класса.</span><span class="sxs-lookup"><span data-stu-id="415e5-121">[How to: Define and execute dynamic methods](how-to-define-and-execute-dynamic-methods.md) Shows how to execute a simple dynamic method and a dynamic method bound to an instance of a class.</span></span>

<span data-ttu-id="415e5-122">[Практическое руководство. Определение универсального типа с порождением отражения](how-to-define-a-generic-type-with-reflection-emit.md). Показывается, как создать простой универсальный тип с двумя параметрами типа, как применять класс, интерфейс и специальные ограничения для параметров типа и как создать элементы, использующие параметры типа класса в качестве типов параметров и типов возвращаемых значений.</span><span class="sxs-lookup"><span data-stu-id="415e5-122">[How to: Define a generic type with reflection emit](how-to-define-a-generic-type-with-reflection-emit.md) Shows how to create a simple generic type with two type parameters, how to apply class, interface, and special constraints to the type parameters, and how to create members that use the type parameters of the class as parameter types and return types.</span></span>

<span data-ttu-id="415e5-123">[Практическое руководство. Определение универсального метода с порождением отражения](how-to-define-a-generic-method-with-reflection-emit.md). Показывается, как создать, породить и вызвать простой универсальный метод.</span><span class="sxs-lookup"><span data-stu-id="415e5-123">[How to: Define a generic method with reflection emit](how-to-define-a-generic-method-with-reflection-emit.md) Shows how to create, emit, and invoke a simple generic method.</span></span>

<span data-ttu-id="415e5-124">[Сборки с возможностью сбора для динамической генерации типов](collectible-assemblies.md). Общие сведения о сборках с возможностью сбора, то есть динамических сборках, которые можно выгружать без выгрузки домена приложения, в котором они были созданы.</span><span class="sxs-lookup"><span data-stu-id="415e5-124">[Collectible assemblies for dynamic type generation](collectible-assemblies.md) Introduces collectible assemblies, which are dynamic assemblies that can be unloaded without unloading the application domain in which they were created.</span></span>
  
## <a name="reference"></a><span data-ttu-id="415e5-125">Справочник</span><span class="sxs-lookup"><span data-stu-id="415e5-125">Reference</span></span>  

<xref:System.Reflection.Emit.OpCodes>  
<span data-ttu-id="415e5-126">Каталог кодов инструкций MSIL, которые можно использовать для построения тел методов.</span><span class="sxs-lookup"><span data-stu-id="415e5-126">Catalogs the MSIL instruction codes you can use to build method bodies.</span></span>  
  
<xref:System.Reflection.Emit>  
<span data-ttu-id="415e5-127">Содержит управляемые классы, используемые для порождения динамических методов, сборок и типов.</span><span class="sxs-lookup"><span data-stu-id="415e5-127">Contains managed classes used to emit dynamic methods, assemblies, and types.</span></span>  
  
<xref:System.Type>  
<span data-ttu-id="415e5-128">Описывается класс <xref:System.Type>, который представляет типы в управляемом отражении и порождении отражения и является ключевым элементом при использовании этих технологий.</span><span class="sxs-lookup"><span data-stu-id="415e5-128">Describes the <xref:System.Type> class, which represents types in managed reflection and reflection emit, and which is key to the use of these technologies.</span></span>  
  
<xref:System.Reflection>  
<span data-ttu-id="415e5-129">Содержит управляемые классы, используемые для просмотра метаданных и управляемого кода.</span><span class="sxs-lookup"><span data-stu-id="415e5-129">Contains managed classes used to explore metadata and managed code.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="415e5-130">Связанные разделы</span><span class="sxs-lookup"><span data-stu-id="415e5-130">Related Sections</span></span>  

[<span data-ttu-id="415e5-131">Отражение</span><span class="sxs-lookup"><span data-stu-id="415e5-131">Reflection</span></span>](reflection.md)  
<span data-ttu-id="415e5-132">Описываются способы просмотра метаданных и управляемого кода.</span><span class="sxs-lookup"><span data-stu-id="415e5-132">Explains how to explore metadata and managed code.</span></span>  
  
[<span data-ttu-id="415e5-133">Сборки в .NET</span><span class="sxs-lookup"><span data-stu-id="415e5-133">Assemblies in .NET</span></span>](../../standard/assembly/index.md)  
<span data-ttu-id="415e5-134">Предоставляет обзор сборок в реализациях .NET.</span><span class="sxs-lookup"><span data-stu-id="415e5-134">Provides an overview of assemblies in .NET implementations.</span></span>
