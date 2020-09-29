---
description: -main (параметры компилятора C#)
title: -main (параметры компилятора C#)
ms.date: 07/20/2015
f1_keywords:
- /main
helpviewer_keywords:
- -main compiler option [C#]
- main compiler option [C#]
- /main compiler option [C#]
ms.assetid: 975cf4d5-36ac-4530-826c-4aad0c7f2049
ms.openlocfilehash: c27898de2a7cc2f3c01c51f8de1122e81b2233b4
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/24/2020
ms.locfileid: "91194119"
---
# <a name="-main-c-compiler-options"></a><span data-ttu-id="da7b5-103">-main (параметры компилятора C#)</span><span class="sxs-lookup"><span data-stu-id="da7b5-103">-main (C# Compiler Options)</span></span>

<span data-ttu-id="da7b5-104">Этот параметр определяет класс, который содержит точку входа в программу, если метод **Main** содержит сразу несколько классов.</span><span class="sxs-lookup"><span data-stu-id="da7b5-104">This option specifies the class that contains the entry point to the program, if more than one class contains a **Main** method.</span></span>

## <a name="syntax"></a><span data-ttu-id="da7b5-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="da7b5-105">Syntax</span></span>

```console
-main:class
```

## <a name="arguments"></a><span data-ttu-id="da7b5-106">Аргументы</span><span class="sxs-lookup"><span data-stu-id="da7b5-106">Arguments</span></span>

 `class`  
 <span data-ttu-id="da7b5-107">Тип, содержащий метод **Main**.</span><span class="sxs-lookup"><span data-stu-id="da7b5-107">The type that contains the **Main** method.</span></span>  
 <span data-ttu-id="da7b5-108">Указанное имя класса должно быть полным; оно должно включать полное пространство имен, содержащее ключевое слово class, за которым следует имя класса.</span><span class="sxs-lookup"><span data-stu-id="da7b5-108">The provided class name must be fully qualified; it must include the full namespace containing the class, followed by the class name.</span></span> <span data-ttu-id="da7b5-109">Например, если метод `Main` находится в классе `Program` в пространстве имен `MyApplication.Core`, необходимо указать параметр компилятора `-main:MyApplication.Core.Program`.</span><span class="sxs-lookup"><span data-stu-id="da7b5-109">For example, when the `Main` method is located inside the `Program` class in the `MyApplication.Core` namespace, the compiler option has to be `-main:MyApplication.Core.Program`.</span></span>

## <a name="remarks"></a><span data-ttu-id="da7b5-110">Примечания</span><span class="sxs-lookup"><span data-stu-id="da7b5-110">Remarks</span></span>

<span data-ttu-id="da7b5-111">Если в компиляцию входят несколько типов с методом [Main](../../programming-guide/main-and-command-args/index.md), можно указать, какой из них содержит метод **Main**, который нужно использовать как точку входа в программу.</span><span class="sxs-lookup"><span data-stu-id="da7b5-111">If your compilation includes more than one type with a [Main](../../programming-guide/main-and-command-args/index.md) method, you can specify which type contains the **Main** method that you want to use as the entry point into the program.</span></span>

<span data-ttu-id="da7b5-112">Этот параметр предназначен для использования при компиляции файлов *EXE*.</span><span class="sxs-lookup"><span data-stu-id="da7b5-112">This option is for use when compiling an *.exe* file.</span></span>

### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a><span data-ttu-id="da7b5-113">Установка данного параметра компилятора в среде разработки Visual Studio</span><span class="sxs-lookup"><span data-stu-id="da7b5-113">To set this compiler option in the Visual Studio development environment</span></span>

1. <span data-ttu-id="da7b5-114">Откройте страницу **Свойства** проекта.</span><span class="sxs-lookup"><span data-stu-id="da7b5-114">Open the project's **Properties** page.</span></span>

2. <span data-ttu-id="da7b5-115">Перейдите на страницу свойств **Приложение**.</span><span class="sxs-lookup"><span data-stu-id="da7b5-115">Click the **Application** property page.</span></span>

3. <span data-ttu-id="da7b5-116">Измените свойство **Автоматически запускаемый объект**.</span><span class="sxs-lookup"><span data-stu-id="da7b5-116">Modify the **Startup object** property.</span></span>

    <span data-ttu-id="da7b5-117">Сведения об установке этого параметра компилятора программными средствами см. в разделе <xref:VSLangProj80.ProjectProperties3.StartupObject%2A>.</span><span class="sxs-lookup"><span data-stu-id="da7b5-117">To set this compiler option programmatically, see <xref:VSLangProj80.ProjectProperties3.StartupObject%2A>.</span></span>

### <a name="to-set-this-compiler-option-by-manually-editing-the-csproj-file"></a><span data-ttu-id="da7b5-118">Настройка параметра компилятора вручную путем редактирования файла *.csproj*</span><span class="sxs-lookup"><span data-stu-id="da7b5-118">To set this compiler option by manually editing the *.csproj* file</span></span>

<span data-ttu-id="da7b5-119">Этот параметр можно настроить, отредактировав файл .csproj и добавив элемент `StartupObject` в раздел `PropertyGroup`.</span><span class="sxs-lookup"><span data-stu-id="da7b5-119">You can set this option by editing the .csproj file and adding an element `StartupObject` inside the `PropertyGroup` section.</span></span> <span data-ttu-id="da7b5-120">Пример:</span><span class="sxs-lookup"><span data-stu-id="da7b5-120">For example:</span></span>

```xml
  <PropertyGroup>
    ...
    <StartupObject>MyApplication.Core.Program</StartupObject>
  </PropertyGroup>
```

## <a name="example"></a><span data-ttu-id="da7b5-121">Пример</span><span class="sxs-lookup"><span data-stu-id="da7b5-121">Example</span></span>

<span data-ttu-id="da7b5-122">Скомпилируйте `t2.cs` и `t3.cs`, указав, что метод **Main** будет находиться в `Test2`:</span><span class="sxs-lookup"><span data-stu-id="da7b5-122">Compile `t2.cs` and `t3.cs`, specifying that the **Main** method will be found in `Test2`:</span></span>

```console
csc t2.cs t3.cs -main:Test2
```

## <a name="see-also"></a><span data-ttu-id="da7b5-123">См. также</span><span class="sxs-lookup"><span data-stu-id="da7b5-123">See also</span></span>

- [<span data-ttu-id="da7b5-124">Параметры компилятора C# </span><span class="sxs-lookup"><span data-stu-id="da7b5-124">C# Compiler Options</span></span>](./index.md)
- [<span data-ttu-id="da7b5-125">Управление свойствами проектов и решений</span><span class="sxs-lookup"><span data-stu-id="da7b5-125">Managing Project and Solution Properties</span></span>](/visualstudio/ide/managing-project-and-solution-properties)
