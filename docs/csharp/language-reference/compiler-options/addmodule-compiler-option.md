---
description: -addmodule (параметры компилятора C#)
title: -addmodule (параметры компилятора C#)
ms.date: 07/20/2015
f1_keywords:
- /addmodule
helpviewer_keywords:
- /addmodule compiler option [C#]
- -addmodule compiler option [C#]
- addmodule compiler option [C#]
ms.assetid: ed604546-0dc2-4bd4-9a3e-610a8d973e58
ms.openlocfilehash: ec72fc76b3d550029b1286f64b8f86e69e721468
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/24/2020
ms.locfileid: "91150574"
---
# <a name="-addmodule-c-compiler-options"></a><span data-ttu-id="75266-103">-addmodule (параметры компилятора C#)</span><span class="sxs-lookup"><span data-stu-id="75266-103">-addmodule (C# Compiler Options)</span></span>

<span data-ttu-id="75266-104">Установка этого параметра приводит к добавлению модуля, созданного с помощью параметра target:module для текущей компиляции.</span><span class="sxs-lookup"><span data-stu-id="75266-104">This option adds a module that was created with the target:module switch to the current compilation.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="75266-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="75266-105">Syntax</span></span>  
  
```console  
-addmodule:file[;file2]  
```  
  
## <a name="arguments"></a><span data-ttu-id="75266-106">Аргументы</span><span class="sxs-lookup"><span data-stu-id="75266-106">Arguments</span></span>  

 <span data-ttu-id="75266-107">`file`, `file2`</span><span class="sxs-lookup"><span data-stu-id="75266-107">`file`, `file2`</span></span>  
 <span data-ttu-id="75266-108">Выходной файл, содержащий метаданные.</span><span class="sxs-lookup"><span data-stu-id="75266-108">An output file that contains metadata.</span></span> <span data-ttu-id="75266-109">В данный файл не может входить манифест сборки.</span><span class="sxs-lookup"><span data-stu-id="75266-109">The file cannot contain an assembly manifest.</span></span> <span data-ttu-id="75266-110">Чтобы импортировать несколько файлов, разделите их имена запятыми или точками с запятой.</span><span class="sxs-lookup"><span data-stu-id="75266-110">To import more than one file, separate file names with either a comma or a semicolon.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="75266-111">Remarks</span><span class="sxs-lookup"><span data-stu-id="75266-111">Remarks</span></span>  

 <span data-ttu-id="75266-112">Все модули, добавленные с помощью **-addmodule**, во время выполнения должны находиться в том же каталоге, что и выходной файл.</span><span class="sxs-lookup"><span data-stu-id="75266-112">All modules added with **-addmodule** must be in the same directory as the output file at run time.</span></span> <span data-ttu-id="75266-113">То есть во время компиляции можно указать модуль в любом каталоге, но во время выполнения он должен находиться в каталоге приложения.</span><span class="sxs-lookup"><span data-stu-id="75266-113">That is, you can specify a module in any directory at compile time but the module must be in the application directory at run time.</span></span> <span data-ttu-id="75266-114">Если во время выполнения модуль отсутствует в каталоге приложения, возникнет <xref:System.TypeLoadException>.</span><span class="sxs-lookup"><span data-stu-id="75266-114">If the module is not in the application directory at run time, you will get a <xref:System.TypeLoadException>.</span></span>  
  
 <span data-ttu-id="75266-115">`file` не может содержать сборку.</span><span class="sxs-lookup"><span data-stu-id="75266-115">`file` cannot contain an assembly.</span></span> <span data-ttu-id="75266-116">Например, если выходной файл был создан с помощью [-target:module](./target-module-compiler-option.md), для импорта его метаданных можно использовать **-addmodule**.</span><span class="sxs-lookup"><span data-stu-id="75266-116">For example, if the output file was created with [-target:module](./target-module-compiler-option.md), its metadata can be imported with **-addmodule**.</span></span>  
  
 <span data-ttu-id="75266-117">Если выходной файл был создан с помощью параметра **-target**, отличного от **-target:module**, для импорта его метаданных запрещено использовать **-addmodule**, но можно [-reference](./reference-compiler-option.md).</span><span class="sxs-lookup"><span data-stu-id="75266-117">If the output file was created with a **-target** option other than **-target:module**, its metadata cannot be imported with **-addmodule** but can be imported with [-reference](./reference-compiler-option.md).</span></span>  
  
 <span data-ttu-id="75266-118">Этот параметр компилятора недоступен в Visual Studio; проект не может ссылаться на модуль.</span><span class="sxs-lookup"><span data-stu-id="75266-118">This compiler option is unavailable in Visual Studio; a project cannot reference a module.</span></span> <span data-ttu-id="75266-119">Кроме того, этот параметр компилятора нельзя изменить программным способом.</span><span class="sxs-lookup"><span data-stu-id="75266-119">In addition, this compiler option cannot be changed programmatically.</span></span>  
  
## <a name="example"></a><span data-ttu-id="75266-120">Пример</span><span class="sxs-lookup"><span data-stu-id="75266-120">Example</span></span>  

 <span data-ttu-id="75266-121">Скомпилируйте исходный файл `input.cs` и добавьте метаданные из `metad1.netmodule` и `metad2.netmodule`, чтобы создать `out.exe`.</span><span class="sxs-lookup"><span data-stu-id="75266-121">Compile source file `input.cs` and add metadata from `metad1.netmodule` and `metad2.netmodule` to produce `out.exe`:</span></span>  
  
```console  
csc -addmodule:metad1.netmodule;metad2.netmodule -out:out.exe input.cs  
```  
  
## <a name="see-also"></a><span data-ttu-id="75266-122">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="75266-122">See also</span></span>

- [<span data-ttu-id="75266-123">Параметры компилятора C# </span><span class="sxs-lookup"><span data-stu-id="75266-123">C# Compiler Options</span></span>](./index.md)
- [<span data-ttu-id="75266-124">Управление свойствами проектов и решений</span><span class="sxs-lookup"><span data-stu-id="75266-124">Managing Project and Solution Properties</span></span>](/visualstudio/ide/managing-project-and-solution-properties)
- [<span data-ttu-id="75266-125">Многофайловые сборки</span><span class="sxs-lookup"><span data-stu-id="75266-125">Multifile Assemblies</span></span>](../../../framework/app-domains/multifile-assemblies.md)
- [<span data-ttu-id="75266-126">Практическое руководство. Создание многофайловой сборки</span><span class="sxs-lookup"><span data-stu-id="75266-126">How to: Build a Multifile Assembly</span></span>](../../../framework/app-domains/build-multifile-assembly.md)
