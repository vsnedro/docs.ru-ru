---
description: -pathmap (параметры компилятора C#)
title: -pathmap (параметры компилятора C#)
ms.date: 05/16/2018
f1_keywords:
- /pathmap
helpviewer_keywords:
- -pathmap compiler option [C#]
- pathmap compiler option [C#]
- /pathmap compiler option [C#]
ms.openlocfilehash: 707a37c6946cfcaf429552f0aeece6b87f3ad71d
ms.sourcegitcommit: d579fb5e4b46745fd0f1f8874c94c6469ce58604
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/30/2020
ms.locfileid: "89125011"
---
# <a name="-pathmap-c-compiler-options"></a><span data-ttu-id="31d02-103">-pathmap (параметры компилятора C#)</span><span class="sxs-lookup"><span data-stu-id="31d02-103">-pathmap (C# Compiler Options)</span></span>

<span data-ttu-id="31d02-104">Параметр компилятора **-pathmap** определяет способ сопоставления физических путей и выходных имен исходных путей компилятором.</span><span class="sxs-lookup"><span data-stu-id="31d02-104">The **-pathmap** compiler option specifies how to map physical paths to source path names output by the compiler.</span></span>

## <a name="syntax"></a><span data-ttu-id="31d02-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="31d02-105">Syntax</span></span>

```console
-pathmap:path1=sourcePath1,path2=sourcePath2
```

## <a name="arguments"></a><span data-ttu-id="31d02-106">Аргументы</span><span class="sxs-lookup"><span data-stu-id="31d02-106">Arguments</span></span>

 <span data-ttu-id="31d02-107">`path1` — полный путь к исходным файлам в текущем окружении.</span><span class="sxs-lookup"><span data-stu-id="31d02-107">`path1` The full path to the source files in the current environment</span></span>

 <span data-ttu-id="31d02-108">`sourcePath1` — исходный путь подставляется вместо `path1` в любых выходных файлах.</span><span class="sxs-lookup"><span data-stu-id="31d02-108">`sourcePath1` The source path substituted for `path1` in any output files.</span></span>

<span data-ttu-id="31d02-109">Чтобы указать несколько сопоставленных исходных путей, разделите их запятыми.</span><span class="sxs-lookup"><span data-stu-id="31d02-109">To specify multiple mapped source paths, separate each with a comma.</span></span>

## <a name="remarks"></a><span data-ttu-id="31d02-110">Remarks</span><span class="sxs-lookup"><span data-stu-id="31d02-110">Remarks</span></span>

<span data-ttu-id="31d02-111">Компилятор записывает исходный путь в выходные данные по следующим причинам:</span><span class="sxs-lookup"><span data-stu-id="31d02-111">The compiler writes the source path into its output for the following reasons:</span></span>

1. <span data-ttu-id="31d02-112">Исходный путь подставляется вместо аргумента, когда <xref:System.Runtime.CompilerServices.CallerFilePathAttribute> применяется как необязательный параметр.</span><span class="sxs-lookup"><span data-stu-id="31d02-112">The source path is substituted for an argument when the <xref:System.Runtime.CompilerServices.CallerFilePathAttribute> is applied to an optional parameter.</span></span>
1. <span data-ttu-id="31d02-113">Исходный путь внедряется как PDB-файл.</span><span class="sxs-lookup"><span data-stu-id="31d02-113">The source path is embedded in a PDB file.</span></span>
1. <span data-ttu-id="31d02-114">Путь к PDB-файлу внедряется в PE-файл (переносимый исполняемый файл).</span><span class="sxs-lookup"><span data-stu-id="31d02-114">The path of the PDB file is embedded into a PE (portable executable) file.</span></span>

<span data-ttu-id="31d02-115">Этот параметр сопоставляет каждый физический путь на компьютере, где выполняется компилятор, с соответствующим путем, который должен быть записан в выходные файлы.</span><span class="sxs-lookup"><span data-stu-id="31d02-115">This option maps each physical path on the machine where the compiler runs to a corresponding path that should be written in the output files.</span></span>

## <a name="example"></a><span data-ttu-id="31d02-116">Пример</span><span class="sxs-lookup"><span data-stu-id="31d02-116">Example</span></span>

<span data-ttu-id="31d02-117">Компиляция `t.cs` в каталоге **C:\\work\\tests** и сопоставление этого каталога с каталогом **\publish** в выходных данных:</span><span class="sxs-lookup"><span data-stu-id="31d02-117">Compile `t.cs` in the directory **C:\\work\\tests** and map that directory to **\publish** in the output:</span></span>

```console
csc -pathmap:C:\work\tests=\publish t.cs
```

## <a name="see-also"></a><span data-ttu-id="31d02-118">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="31d02-118">See also</span></span>

- [<span data-ttu-id="31d02-119">Параметры компилятора C# </span><span class="sxs-lookup"><span data-stu-id="31d02-119">C# Compiler Options</span></span>](./index.md)
- [<span data-ttu-id="31d02-120">Управление свойствами проектов и решений</span><span class="sxs-lookup"><span data-stu-id="31d02-120">Managing Project and Solution Properties</span></span>](/visualstudio/ide/managing-project-and-solution-properties)
