---
description: -recurse (параметры компилятора C#)
title: -recurse (параметры компилятора C#)
ms.date: 07/20/2015
f1_keywords:
- /recurse
helpviewer_keywords:
- /recurse compiler option [C#]
- recurse compiler option [C#]
- -recurse compiler option [C#]
ms.assetid: 4e8212e5-04e3-45b1-8a42-41bc50e683b0
ms.openlocfilehash: 9e84ff95f7f0addac1c2c2d79af0ab53572da27f
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/24/2020
ms.locfileid: "91193807"
---
# <a name="-recurse-c-compiler-options"></a><span data-ttu-id="3f5ea-103">-recurse (параметры компилятора C#)</span><span class="sxs-lookup"><span data-stu-id="3f5ea-103">-recurse (C# Compiler Options)</span></span>

<span data-ttu-id="3f5ea-104">Параметр -recurse позволяет компилировать файлы исходного кода во всех вложенных каталогах заданного каталога (dir) или каталога проекта.</span><span class="sxs-lookup"><span data-stu-id="3f5ea-104">The -recurse option enables you to compile source code files in all child directories of either the specified directory (dir) or of the project directory.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3f5ea-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="3f5ea-105">Syntax</span></span>  
  
```console  
-recurse:[dir\]file  
```  
  
## <a name="arguments"></a><span data-ttu-id="3f5ea-106">Аргументы</span><span class="sxs-lookup"><span data-stu-id="3f5ea-106">Arguments</span></span>  

 <span data-ttu-id="3f5ea-107">Среда `dir` (необязательно)</span><span class="sxs-lookup"><span data-stu-id="3f5ea-107">`dir` (optional)</span></span>  
 <span data-ttu-id="3f5ea-108">Каталог, с которого будет начинаться поиск.</span><span class="sxs-lookup"><span data-stu-id="3f5ea-108">The directory in which you want the search to begin.</span></span> <span data-ttu-id="3f5ea-109">Если этот параметр не задан, поиск начинается с каталога проекта.</span><span class="sxs-lookup"><span data-stu-id="3f5ea-109">If this is not specified, the search begins in the project directory.</span></span>  
  
 `file`  
 <span data-ttu-id="3f5ea-110">Файлы для поиска.</span><span class="sxs-lookup"><span data-stu-id="3f5ea-110">The file(s) to search for.</span></span> <span data-ttu-id="3f5ea-111">Поддерживаются подстановочные знаки.</span><span class="sxs-lookup"><span data-stu-id="3f5ea-111">Wildcard characters are allowed.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="3f5ea-112">Примечания</span><span class="sxs-lookup"><span data-stu-id="3f5ea-112">Remarks</span></span>  

 <span data-ttu-id="3f5ea-113">Параметр **-recurse** позволяет компилировать файлы исходного кода во всех вложенных каталогах заданного каталога (`dir`) или каталога проекта.</span><span class="sxs-lookup"><span data-stu-id="3f5ea-113">The **-recurse** option lets you compile source code files in all child directories of either the specified directory (`dir`) or of the project directory.</span></span>  
  
 <span data-ttu-id="3f5ea-114">Чтобы скомпилировать все соответствующие файлы в каталоге проекта, не задавая параметр **-recurse**, можно использовать подстановочные знаки в именах файлов.</span><span class="sxs-lookup"><span data-stu-id="3f5ea-114">You can use wildcards in a file name to compile all matching files in the project directory without using **-recurse**.</span></span>  
  
 <span data-ttu-id="3f5ea-115">Этот параметр компилятора недоступен в Visual Studio и не может быть изменен программным способом.</span><span class="sxs-lookup"><span data-stu-id="3f5ea-115">This compiler option is unavailable in Visual Studio and cannot be changed programmatically.</span></span>  
  
## <a name="example"></a><span data-ttu-id="3f5ea-116">Пример</span><span class="sxs-lookup"><span data-stu-id="3f5ea-116">Example</span></span>  

 <span data-ttu-id="3f5ea-117">Компиляция всех файлов C# в текущем каталоге:</span><span class="sxs-lookup"><span data-stu-id="3f5ea-117">Compiles all C# files in the current directory:</span></span>  
  
```console  
csc *.cs  
```  
  
 <span data-ttu-id="3f5ea-118">Компиляция всех файлов C# в каталоге dir1\dir2 и всех вложенных в него каталогах, а также создание файла dir2.dll:</span><span class="sxs-lookup"><span data-stu-id="3f5ea-118">Compiles all of the C# files in the dir1\dir2 directory and any directories below it and generates dir2.dll:</span></span>  
  
```console  
csc -target:library -out:dir2.dll -recurse:dir1\dir2\*.cs  
```  
  
## <a name="see-also"></a><span data-ttu-id="3f5ea-119">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="3f5ea-119">See also</span></span>

- [<span data-ttu-id="3f5ea-120">Параметры компилятора C# </span><span class="sxs-lookup"><span data-stu-id="3f5ea-120">C# Compiler Options</span></span>](./index.md)
- [<span data-ttu-id="3f5ea-121">Управление свойствами проектов и решений</span><span class="sxs-lookup"><span data-stu-id="3f5ea-121">Managing Project and Solution Properties</span></span>](/visualstudio/ide/managing-project-and-solution-properties)
