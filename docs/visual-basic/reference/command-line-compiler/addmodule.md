---
title: -addmodule
ms.date: 03/09/2018
helpviewer_keywords:
- /addmodule compiler option [Visual Basic]
- addmodule compiler option [Visual Basic]
- -addmodule compiler option [Visual Basic]
ms.assetid: fb4b89d4-4926-4f20-868d-427fa28497b2
ms.openlocfilehash: dd98b45d75ff421dc81666ed47695132a49bfa3a
ms.sourcegitcommit: 4f4a32a5c16a75724920fa9627c59985c41e173c
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/17/2019
ms.locfileid: "72524476"
---
# <a name="-addmodule"></a><span data-ttu-id="2caf6-102">-addmodule</span><span class="sxs-lookup"><span data-stu-id="2caf6-102">-addmodule</span></span>
<span data-ttu-id="2caf6-103">Дает компилятору указание сделать всю информацию о типах из указанных файлов доступной компилируемому проекту.</span><span class="sxs-lookup"><span data-stu-id="2caf6-103">Causes the compiler to make all type information from the specified file(s) available to the project you are currently compiling.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2caf6-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="2caf6-104">Syntax</span></span>  
  
```console  
-addmodule:fileList  
```  
  
## <a name="arguments"></a><span data-ttu-id="2caf6-105">Аргументы</span><span class="sxs-lookup"><span data-stu-id="2caf6-105">Arguments</span></span>  
 `fileList`  
 <span data-ttu-id="2caf6-106">Обязательный.</span><span class="sxs-lookup"><span data-stu-id="2caf6-106">Required.</span></span> <span data-ttu-id="2caf6-107">Разделенный запятыми список файлов, содержащих метаданные, но не содержащих манифесты сборки.</span><span class="sxs-lookup"><span data-stu-id="2caf6-107">Comma-delimited list of files that contain metadata but do not contain assembly manifests.</span></span> <span data-ttu-id="2caf6-108">Имена файлов, содержащие пробелы, должны быть заключены в кавычки (" ").</span><span class="sxs-lookup"><span data-stu-id="2caf6-108">File names containing spaces should be surrounded by quotation marks (" ").</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="2caf6-109">Примечания</span><span class="sxs-lookup"><span data-stu-id="2caf6-109">Remarks</span></span>  
 <span data-ttu-id="2caf6-110">Файлы, перечисленные в параметре `fileList`, должны быть созданы с использованием параметра `-target:module` или параметра, эквивалентного `-target:module`, в другом компиляторе.</span><span class="sxs-lookup"><span data-stu-id="2caf6-110">The files listed by the `fileList` parameter must be created with the `-target:module` option, or with another compiler's equivalent to `-target:module`.</span></span>  
  
 <span data-ttu-id="2caf6-111">Все модули, добавленные с помощью `-addmodule`, во время выполнения должны находиться в том же каталоге, что и выходной файл.</span><span class="sxs-lookup"><span data-stu-id="2caf6-111">All modules added with `-addmodule` must be in the same directory as the output file at run time.</span></span> <span data-ttu-id="2caf6-112">То есть во время компиляции можно указать модуль в любом каталоге, но во время выполнения он должен находиться в каталоге приложения.</span><span class="sxs-lookup"><span data-stu-id="2caf6-112">That is, you can specify a module in any directory at compile time, but the module must be in the application directory at run time.</span></span> <span data-ttu-id="2caf6-113">В противном случае возникает ошибка <xref:System.TypeLoadException>.</span><span class="sxs-lookup"><span data-stu-id="2caf6-113">If it is not, you get a <xref:System.TypeLoadException> error.</span></span>  
  
 <span data-ttu-id="2caf6-114">При указании (неявно или явно) любого параметра [-target (Visual Basic)](../../../visual-basic/reference/command-line-compiler/target.md), кроме `-target:module` с `-addmodule`, файлы, передаваемые в `-addmodule`, становятся частью сборки проекта.</span><span class="sxs-lookup"><span data-stu-id="2caf6-114">If you specify (implicitly or explicitly) any[-target (Visual Basic)](../../../visual-basic/reference/command-line-compiler/target.md) option other than `-target:module` with `-addmodule`, the files you pass to `-addmodule` become part of the project's assembly.</span></span> <span data-ttu-id="2caf6-115">Сборка необходима для запуска выходного файла, который содержит один или несколько файлов, добавленных с помощью `-addmodule`.</span><span class="sxs-lookup"><span data-stu-id="2caf6-115">An assembly is required to run an output file that has one or more files added with `-addmodule`.</span></span>  
  
 <span data-ttu-id="2caf6-116">Используйте параметр [-reference (Visual Basic)](../../../visual-basic/reference/command-line-compiler/reference.md) для импорта метаданных из файла, содержащего сборку.</span><span class="sxs-lookup"><span data-stu-id="2caf6-116">Use [-reference (Visual Basic)](../../../visual-basic/reference/command-line-compiler/reference.md) to import metadata from a file that contains an assembly.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="2caf6-117">Параметр `-addmodule` недоступен в среде разработки Visual Studio. Его можно использовать только при компиляции из командной строки.</span><span class="sxs-lookup"><span data-stu-id="2caf6-117">The `-addmodule` option is not available from within the Visual Studio development environment; it is available only when compiling from the command line.</span></span>  
  
## <a name="example"></a><span data-ttu-id="2caf6-118">Пример</span><span class="sxs-lookup"><span data-stu-id="2caf6-118">Example</span></span>  
 <span data-ttu-id="2caf6-119">Следующий код создает модуль.</span><span class="sxs-lookup"><span data-stu-id="2caf6-119">The following code creates a module.</span></span>  
  
 [!code-vb[VbVbalrCompiler#47](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrCompiler/VB/OptionStrictOff.vb#47)]  
  
 <span data-ttu-id="2caf6-120">Следующий код импортирует типы модуля.</span><span class="sxs-lookup"><span data-stu-id="2caf6-120">The following code imports the module's types.</span></span>  
  
 [!code-vb[VbVbalrCompiler#48](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrCompiler/VB/OptionStrictOff.vb#48)]  
  
 <span data-ttu-id="2caf6-121">При запуске `t1` он выводит `802`.</span><span class="sxs-lookup"><span data-stu-id="2caf6-121">When you run `t1`, it outputs `802`.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2caf6-122">См. также</span><span class="sxs-lookup"><span data-stu-id="2caf6-122">See also</span></span>

- [<span data-ttu-id="2caf6-123">Компилятор Visual Basic с интерфейсом командной строки</span><span class="sxs-lookup"><span data-stu-id="2caf6-123">Visual Basic Command-Line Compiler</span></span>](../../../visual-basic/reference/command-line-compiler/index.md)
- [<span data-ttu-id="2caf6-124">-target (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="2caf6-124">-target (Visual Basic)</span></span>](../../../visual-basic/reference/command-line-compiler/target.md)
- [<span data-ttu-id="2caf6-125">-reference (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="2caf6-125">-reference (Visual Basic)</span></span>](../../../visual-basic/reference/command-line-compiler/reference.md)
- [<span data-ttu-id="2caf6-126">Примеры командных строк компиляции</span><span class="sxs-lookup"><span data-stu-id="2caf6-126">Sample Compilation Command Lines</span></span>](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)
