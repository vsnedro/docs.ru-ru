---
description: -win32icon (параметры компилятора C#)
title: -win32icon (параметры компилятора C#)
ms.date: 07/20/2015
f1_keywords:
- /win32icon
helpviewer_keywords:
- win32icon compiler option [C#]
- /win32icon compiler option [C#]
- -win32icon compiler option [C#]
ms.assetid: 756d9b6d-ab07-41b7-ba58-5bd88f711138
ms.openlocfilehash: 76a54f9011371492bdc15f15c3e40d51082deed3
ms.sourcegitcommit: d579fb5e4b46745fd0f1f8874c94c6469ce58604
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/30/2020
ms.locfileid: "89138414"
---
# <a name="-win32icon-c-compiler-options"></a><span data-ttu-id="ffa35-103">-win32icon (параметры компилятора C#)</span><span class="sxs-lookup"><span data-stu-id="ffa35-103">-win32icon (C# Compiler Options)</span></span>
<span data-ttu-id="ffa35-104">Параметр **-win32icon** вставляет в выходной файл ICO-файл, который придает выходному файлу необходимый вид в проводнике.</span><span class="sxs-lookup"><span data-stu-id="ffa35-104">The **-win32icon** option inserts an .ico file in the output file, which gives the output file the desired appearance in the File Explorer.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ffa35-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="ffa35-105">Syntax</span></span>  
  
```console  
-win32icon:filename  
```  
  
## <a name="arguments"></a><span data-ttu-id="ffa35-106">Аргументы</span><span class="sxs-lookup"><span data-stu-id="ffa35-106">Arguments</span></span>  
 `filename`  
 <span data-ttu-id="ffa35-107">ICO-файл, который требуется добавить в выходной файл.</span><span class="sxs-lookup"><span data-stu-id="ffa35-107">The .ico file that you want to add to your output file.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="ffa35-108">Remarks</span><span class="sxs-lookup"><span data-stu-id="ffa35-108">Remarks</span></span>  
 <span data-ttu-id="ffa35-109">ICO-файл можно создать с помощью [компилятора ресурсов](/windows/desktop/menurc/resource-compiler).</span><span class="sxs-lookup"><span data-stu-id="ffa35-109">An .ico file can be created with the [Resource Compiler](/windows/desktop/menurc/resource-compiler).</span></span> <span data-ttu-id="ffa35-110">Компилятор ресурсов вызывается при компиляции программы Visual C++; ICO-файл создается из RC-файла.</span><span class="sxs-lookup"><span data-stu-id="ffa35-110">The Resource Compiler is invoked when you compile a Visual C++ program; an .ico file is created from the .rc file.</span></span>  
  
 <span data-ttu-id="ffa35-111">Дополнительные сведения о ссылках на файлы ресурсов .NET Framework и их присоединении см. в разделах [-linkresource](./linkresource-compiler-option.md) и [-resource](./resource-compiler-option.md) соответственно.</span><span class="sxs-lookup"><span data-stu-id="ffa35-111">See [-linkresource](./linkresource-compiler-option.md) (to reference) or [-resource](./resource-compiler-option.md) (to attach) a .NET Framework resource file.</span></span> <span data-ttu-id="ffa35-112">Дополнительные сведения об импорте RES-файла см. в разделе [-win32res](./win32res-compiler-option.md).</span><span class="sxs-lookup"><span data-stu-id="ffa35-112">See [-win32res](./win32res-compiler-option.md) to import a .res file.</span></span>  
  
### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a><span data-ttu-id="ffa35-113">Установка данного параметра компилятора в среде разработки Visual Studio</span><span class="sxs-lookup"><span data-stu-id="ffa35-113">To set this compiler option in the Visual Studio development environment</span></span>  
  
1. <span data-ttu-id="ffa35-114">Откройте страницу **Свойства** проекта.</span><span class="sxs-lookup"><span data-stu-id="ffa35-114">Open the project's **Properties** pages.</span></span>  
  
2. <span data-ttu-id="ffa35-115">Перейдите на страницу свойств **Приложение**.</span><span class="sxs-lookup"><span data-stu-id="ffa35-115">Click the **Application** property page.</span></span>  
  
3. <span data-ttu-id="ffa35-116">Измените свойство **Значок приложения**.</span><span class="sxs-lookup"><span data-stu-id="ffa35-116">Modify the **Application icon** property.</span></span>  
  
 <span data-ttu-id="ffa35-117">Сведения об установке этого параметра компилятора программными средствами см. в статье <xref:VSLangProj80.ProjectProperties3.ApplicationIcon%2A>.</span><span class="sxs-lookup"><span data-stu-id="ffa35-117">For information on how to set this compiler option programmatically, see <xref:VSLangProj80.ProjectProperties3.ApplicationIcon%2A>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="ffa35-118">Пример</span><span class="sxs-lookup"><span data-stu-id="ffa35-118">Example</span></span>  
 <span data-ttu-id="ffa35-119">Скомпилируйте `in.cs` и присоедините ICO-файл `rf.ico`, чтобы получить файл `in.exe`:</span><span class="sxs-lookup"><span data-stu-id="ffa35-119">Compile `in.cs` and attach an .ico file `rf.ico` to produce `in.exe`:</span></span>  
  
```console  
csc -win32icon:rf.ico in.cs  
```  
  
## <a name="see-also"></a><span data-ttu-id="ffa35-120">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="ffa35-120">See also</span></span>

- [<span data-ttu-id="ffa35-121">Параметры компилятора C# </span><span class="sxs-lookup"><span data-stu-id="ffa35-121">C# Compiler Options</span></span>](./index.md)
- [<span data-ttu-id="ffa35-122">Управление свойствами проектов и решений</span><span class="sxs-lookup"><span data-stu-id="ffa35-122">Managing Project and Solution Properties</span></span>](/visualstudio/ide/managing-project-and-solution-properties)
