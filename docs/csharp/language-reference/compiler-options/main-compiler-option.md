---
title: -main (параметры компилятора C#)
ms.date: 07/20/2015
f1_keywords:
- /main
helpviewer_keywords:
- -main compiler option [C#]
- main compiler option [C#]
- /main compiler option [C#]
ms.assetid: 975cf4d5-36ac-4530-826c-4aad0c7f2049
ms.openlocfilehash: 7d3cfce474023907eda0bc40b692e4bbb65ffb96
ms.sourcegitcommit: d223616e7e6fe2139079052e6fcbe25413fb9900
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/22/2020
ms.locfileid: "83802832"
---
# <a name="-main-c-compiler-options"></a><span data-ttu-id="96fdb-102">-main (параметры компилятора C#)</span><span class="sxs-lookup"><span data-stu-id="96fdb-102">-main (C# Compiler Options)</span></span>
<span data-ttu-id="96fdb-103">Этот параметр определяет класс, который содержит точку входа в программу, если метод **Main** содержит сразу несколько классов.</span><span class="sxs-lookup"><span data-stu-id="96fdb-103">This option specifies the class that contains the entry point to the program, if more than one class contains a **Main** method.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="96fdb-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="96fdb-104">Syntax</span></span>  
  
```console  
-main:class  
```  
  
## <a name="arguments"></a><span data-ttu-id="96fdb-105">Аргументы</span><span class="sxs-lookup"><span data-stu-id="96fdb-105">Arguments</span></span>  
 `class`  
 <span data-ttu-id="96fdb-106">Тип, содержащий метод **Main**.</span><span class="sxs-lookup"><span data-stu-id="96fdb-106">The type that contains the **Main** method.</span></span>  
 <span data-ttu-id="96fdb-107">Указанное имя класса должно быть полным; оно должно включать полное пространство имен, содержащее ключевое слово class, за которым следует имя класса.</span><span class="sxs-lookup"><span data-stu-id="96fdb-107">The provided class name must be fully qualified; it must include the full namespace containing the class, followed by the class name.</span></span> <span data-ttu-id="96fdb-108">Например, если метод `Main` находится в классе `Program` в пространстве имен `MyApplication.Core`, необходимо указать параметр компилятора `-main:MyApplication.Core.Program`.</span><span class="sxs-lookup"><span data-stu-id="96fdb-108">For example, when the `Main` method is located inside the `Program` class in the `MyApplication.Core` namespace, the compiler option has to be `-main:MyApplication.Core.Program`.</span></span>
  
## <a name="remarks"></a><span data-ttu-id="96fdb-109">Примечания</span><span class="sxs-lookup"><span data-stu-id="96fdb-109">Remarks</span></span>  
 <span data-ttu-id="96fdb-110">Если в компиляцию входят несколько типов с методом [Main](../../programming-guide/main-and-command-args/index.md), можно указать, какой из них содержит метод **Main**, который нужно использовать как точку входа в программу.</span><span class="sxs-lookup"><span data-stu-id="96fdb-110">If your compilation includes more than one type with a [Main](../../programming-guide/main-and-command-args/index.md) method, you can specify which type contains the **Main** method that you want to use as the entry point into the program.</span></span>  
  
 <span data-ttu-id="96fdb-111">Этот параметр предназначен для использования при компиляции файлов EXE.</span><span class="sxs-lookup"><span data-stu-id="96fdb-111">This option is for use when compiling an .exe file.</span></span>  
  
### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a><span data-ttu-id="96fdb-112">Установка данного параметра компилятора в среде разработки Visual Studio</span><span class="sxs-lookup"><span data-stu-id="96fdb-112">To set this compiler option in the Visual Studio development environment</span></span>  
  
1. <span data-ttu-id="96fdb-113">Откройте страницу **Свойства** проекта.</span><span class="sxs-lookup"><span data-stu-id="96fdb-113">Open the project's **Properties** page.</span></span>  
  
2. <span data-ttu-id="96fdb-114">Перейдите на страницу свойств **Приложение**.</span><span class="sxs-lookup"><span data-stu-id="96fdb-114">Click the **Application** property page.</span></span>  
  
3. <span data-ttu-id="96fdb-115">Измените свойство **Автоматически запускаемый объект**.</span><span class="sxs-lookup"><span data-stu-id="96fdb-115">Modify the **Startup object** property.</span></span>  
  
     <span data-ttu-id="96fdb-116">Сведения об установке этого параметра компилятора программными средствами см. в разделе <xref:VSLangProj80.ProjectProperties3.StartupObject%2A>.</span><span class="sxs-lookup"><span data-stu-id="96fdb-116">To set this compiler option programmatically, see <xref:VSLangProj80.ProjectProperties3.StartupObject%2A>.</span></span>  
  
### <a name="to-set-this-compiler-option-by-manually-editing-the-csproj-file"></a><span data-ttu-id="96fdb-117">Настройка параметра компилятора вручную путем редактирования файла. csproj</span><span class="sxs-lookup"><span data-stu-id="96fdb-117">To set this compiler option by manually editing the .csproj file</span></span>
  
<span data-ttu-id="96fdb-118">Этот параметр можно настроить, отредактировав файл .csproj и добавив элемент `StartupObject` в раздел `PropertyGroup`.</span><span class="sxs-lookup"><span data-stu-id="96fdb-118">You can set this option by editing the .csproj file and adding an element `StartupObject` inside the `PropertyGroup` section.</span></span> <span data-ttu-id="96fdb-119">Пример:</span><span class="sxs-lookup"><span data-stu-id="96fdb-119">For example:</span></span>

```
  <PropertyGroup>
    ...
    <StartupObject>MyApplication.Core.Program</StartupObject>
  </PropertyGroup>
```

## <a name="example"></a><span data-ttu-id="96fdb-120">Пример</span><span class="sxs-lookup"><span data-stu-id="96fdb-120">Example</span></span>  
 <span data-ttu-id="96fdb-121">Скомпилируйте `t2.cs` и `t3.cs`, указав, что метод **Main** будет находиться в `Test2`:</span><span class="sxs-lookup"><span data-stu-id="96fdb-121">Compile `t2.cs` and `t3.cs`, specifying that the **Main** method will be found in `Test2`:</span></span>  
  
```console  
csc t2.cs t3.cs -main:Test2  
```  
  
## <a name="see-also"></a><span data-ttu-id="96fdb-122">См. также</span><span class="sxs-lookup"><span data-stu-id="96fdb-122">See also</span></span>

- [<span data-ttu-id="96fdb-123">Параметры компилятора C# </span><span class="sxs-lookup"><span data-stu-id="96fdb-123">C# Compiler Options</span></span>](./index.md)
- [<span data-ttu-id="96fdb-124">Управление свойствами проектов и решений</span><span class="sxs-lookup"><span data-stu-id="96fdb-124">Managing Project and Solution Properties</span></span>](/visualstudio/ide/managing-project-and-solution-properties)
