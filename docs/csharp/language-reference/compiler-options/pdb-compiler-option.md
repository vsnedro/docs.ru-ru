---
description: -pdb (параметры компилятора C#)
title: -pdb (параметры компилятора C#)
ms.date: 07/20/2015
f1_keywords:
- /pdb
helpviewer_keywords:
- -pdb compiler option [C#]
- pdb compiler option [C#]
- /pdb compiler option [C#]
ms.assetid: e9d0f96a-5b75-45d6-9765-92538dd5f823
ms.openlocfilehash: ced1ee1f4f079830a032a628da96a389ba27da90
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/24/2020
ms.locfileid: "91193859"
---
# <a name="-pdb-c-compiler-options"></a><span data-ttu-id="9d827-103">-pdb (параметры компилятора C#)</span><span class="sxs-lookup"><span data-stu-id="9d827-103">-pdb (C# Compiler Options)</span></span>

<span data-ttu-id="9d827-104">Параметр компилятора **-pdb** задает имя и расположение файла отладочных символов.</span><span class="sxs-lookup"><span data-stu-id="9d827-104">The **-pdb** compiler option specifies the name and location of the debug symbols file.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9d827-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="9d827-105">Syntax</span></span>  
  
```console  
-pdb:filename  
```  
  
## <a name="arguments"></a><span data-ttu-id="9d827-106">Аргументы</span><span class="sxs-lookup"><span data-stu-id="9d827-106">Arguments</span></span>  

 `filename`  
 <span data-ttu-id="9d827-107">Имя и расположение файла отладочных символов.</span><span class="sxs-lookup"><span data-stu-id="9d827-107">The name and location of the debug symbols file.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="9d827-108">Remarks</span><span class="sxs-lookup"><span data-stu-id="9d827-108">Remarks</span></span>  

 <span data-ttu-id="9d827-109">Если указан параметр [-debug (параметры компилятора C#)](./debug-compiler-option.md), компилятор создаст в каталоге с выходным файлом (EXE или DLL) PDB-файл с тем же именем.</span><span class="sxs-lookup"><span data-stu-id="9d827-109">When you specify [-debug (C# Compiler Options)](./debug-compiler-option.md), the compiler will create a .pdb file in the same directory where the compiler will create the output file (.exe or .dll) with a file name that is the same as the name of the output file.</span></span>  
  
 <span data-ttu-id="9d827-110">С помощью параметра **-pdb** можно задать имя PDB-файла, отличающееся от используемого по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="9d827-110">**-pdb** allows you to specify a non-default file name and location for the .pdb file.</span></span>  
  
 <span data-ttu-id="9d827-111">Этот параметр компилятора нельзя задать в среде разработки Visual Studio или изменить программными средствами.</span><span class="sxs-lookup"><span data-stu-id="9d827-111">This compiler option cannot be set in the Visual Studio development environment, nor can it be changed programmatically.</span></span>  
  
## <a name="example"></a><span data-ttu-id="9d827-112">Пример</span><span class="sxs-lookup"><span data-stu-id="9d827-112">Example</span></span>  

 <span data-ttu-id="9d827-113">Компиляция файла `t.cs` и создание файла tt.pdb:</span><span class="sxs-lookup"><span data-stu-id="9d827-113">Compile `t.cs` and create a .pdb file called tt.pdb:</span></span>  
  
```console  
csc -debug -pdb:tt t.cs  
```  
  
## <a name="see-also"></a><span data-ttu-id="9d827-114">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="9d827-114">See also</span></span>

- [<span data-ttu-id="9d827-115">Параметры компилятора C# </span><span class="sxs-lookup"><span data-stu-id="9d827-115">C# Compiler Options</span></span>](./index.md)
- [<span data-ttu-id="9d827-116">Управление свойствами проектов и решений</span><span class="sxs-lookup"><span data-stu-id="9d827-116">Managing Project and Solution Properties</span></span>](/visualstudio/ide/managing-project-and-solution-properties)
