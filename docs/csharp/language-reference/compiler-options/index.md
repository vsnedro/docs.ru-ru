---
description: Параметры компилятора C#
title: Параметры компилятора C#
ms.date: 07/20/2015
f1_keywords:
- cs.build.options
helpviewer_keywords:
- compiler options [C#]
- csc.exe
- cl.exe compiler, C# options
- Visual C# compiler
- Visual C#, compiler options
ms.assetid: d3403556-1816-4546-a782-e8223a772e44
ms.openlocfilehash: bcb246055ecb553bbefad2a0d5c95bf6a083ee6f
ms.sourcegitcommit: d579fb5e4b46745fd0f1f8874c94c6469ce58604
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/30/2020
ms.locfileid: "89125531"
---
# <a name="c-compiler-options"></a><span data-ttu-id="f555b-103">Параметры компилятора C#</span><span class="sxs-lookup"><span data-stu-id="f555b-103">C# Compiler Options</span></span>

<span data-ttu-id="f555b-104">Компилятор создает исполняемые файлы (EXE-файлы), библиотеки динамической компоновки (DLL-файлы) или модули кода (.netmodule).</span><span class="sxs-lookup"><span data-stu-id="f555b-104">The compiler produces executable (.exe) files, dynamic-link libraries (.dll), or code modules (.netmodule).</span></span>

<span data-ttu-id="f555b-105">Каждый параметр компилятора можно использовать в двух формах записи: **-параметр** или **/параметр**.</span><span class="sxs-lookup"><span data-stu-id="f555b-105">Every compiler option is available in two forms: **-option** and **/option**.</span></span> <span data-ttu-id="f555b-106">В документации показана только форма **-<параметр>** .</span><span class="sxs-lookup"><span data-stu-id="f555b-106">The documentation only shows the **-option** form.</span></span>

<span data-ttu-id="f555b-107">В Visual Studio параметры компилятора задаются в файле *web.config*.</span><span class="sxs-lookup"><span data-stu-id="f555b-107">In Visual Studio, you set compiler options in the *web.config* file.</span></span> <span data-ttu-id="f555b-108">Дополнительные сведения см. в разделе [\<compiler>Element](../../../framework/configure-apps/file-schema/compiler/compiler-element.md).</span><span class="sxs-lookup"><span data-stu-id="f555b-108">For more information, see [\<compiler> Element](../../../framework/configure-apps/file-schema/compiler/compiler-element.md).</span></span>

## <a name="in-this-section"></a><span data-ttu-id="f555b-109">Содержание раздела</span><span class="sxs-lookup"><span data-stu-id="f555b-109">In this section</span></span>

- <span data-ttu-id="f555b-110">[Создание из командной строки с помощью csc.exe](command-line-building-with-csc-exe.md) — сведения о создании приложений Visual C# из командной строки.</span><span class="sxs-lookup"><span data-stu-id="f555b-110">[Command-line Building With csc.exe](command-line-building-with-csc-exe.md) Information about building a Visual C# application from the command line.</span></span>

- <span data-ttu-id="f555b-111">[Настройка переменных среды для командной строки Visual Studio](how-to-set-environment-variables-for-the-visual-studio-command-line.md) — пошаговые инструкции по запуску файла *vsvars32.bat* для сборки из командной строки.</span><span class="sxs-lookup"><span data-stu-id="f555b-111">[How to set environment variables for the Visual Studio Command Line](how-to-set-environment-variables-for-the-visual-studio-command-line.md) Provides steps for running *vsvars32.bat* to enable command-line builds.</span></span>

- <span data-ttu-id="f555b-112">[Параметры компилятора C#, перечисленные по категории](listed-by-category.md) — список параметров компилятора по категориям.</span><span class="sxs-lookup"><span data-stu-id="f555b-112">[C# Compiler Options Listed by Category](listed-by-category.md) A categorical listing of the compiler options.</span></span>

- <span data-ttu-id="f555b-113">[Параметры компилятора C#, перечисленные по алфавиту](listed-alphabetically.md) — список параметров компилятора по алфавиту.</span><span class="sxs-lookup"><span data-stu-id="f555b-113">[C# Compiler Options Listed Alphabetically](listed-alphabetically.md) An alphabetical listing of the compiler options.</span></span>

## <a name="related-sections"></a><span data-ttu-id="f555b-114">Связанные разделы</span><span class="sxs-lookup"><span data-stu-id="f555b-114">Related sections</span></span>

- <span data-ttu-id="f555b-115">[Страница сборки, конструктор проектов](/visualstudio/ide/reference/build-page-project-designer-csharp) — настройка свойств, управляющих компиляцией, сборкой и отладкой проекта.</span><span class="sxs-lookup"><span data-stu-id="f555b-115">[Build Page, Project Designer](/visualstudio/ide/reference/build-page-project-designer-csharp) Setting properties that govern how your project is compiled, built, and debugged.</span></span> <span data-ttu-id="f555b-116">Содержит сведения о настраиваемых этапах сборки для проектов Visual C#.</span><span class="sxs-lookup"><span data-stu-id="f555b-116">Includes information about custom build steps in Visual C# projects.</span></span>

- <span data-ttu-id="f555b-117">[Сборки по умолчанию и пользовательские сборки](/visualstudio/ide/compiling-and-building-in-visual-studio) — сведения о конфигурациях и типах сборок.</span><span class="sxs-lookup"><span data-stu-id="f555b-117">[Default and Custom Builds](/visualstudio/ide/compiling-and-building-in-visual-studio) Information on build types and configurations.</span></span>

- <span data-ttu-id="f555b-118">[Подготовка и администрирование сборок](/visualstudio/ide/building-and-cleaning-projects-and-solutions-in-visual-studio) — создание приложений в среде разработки Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="f555b-118">[Preparing and Managing Builds](/visualstudio/ide/building-and-cleaning-projects-and-solutions-in-visual-studio) Procedures for building within the Visual Studio development environment.</span></span>
