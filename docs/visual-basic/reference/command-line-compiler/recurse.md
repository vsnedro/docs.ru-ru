---
title: -recurse
ms.date: 03/13/2018
helpviewer_keywords:
- /recurse compiler option [Visual Basic]
- -recurse compiler option [Visual Basic]
- recurse compiler option [Visual Basic]
ms.assetid: 84a0b670-33ae-44c4-a46a-b90388809317
ms.openlocfilehash: 71613af0f1c319801296180d49dbacfedf0ceca4
ms.sourcegitcommit: eff6adb61852369ab690f3f047818c90580e7eb1
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/07/2019
ms.locfileid: "72005259"
---
# <a name="-recurse"></a><span data-ttu-id="62f13-102">-recurse</span><span class="sxs-lookup"><span data-stu-id="62f13-102">-recurse</span></span>
<span data-ttu-id="62f13-103">Компилирует файлы исходного кода во всех дочерних каталогах указанного каталога или каталога проекта.</span><span class="sxs-lookup"><span data-stu-id="62f13-103">Compiles source-code files in all child directories of either the specified directory or the project directory.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="62f13-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="62f13-104">Syntax</span></span>  
  
```console  
-recurse:[dir\]file  
```  
  
## <a name="arguments"></a><span data-ttu-id="62f13-105">Аргументы</span><span class="sxs-lookup"><span data-stu-id="62f13-105">Arguments</span></span>  
 `dir`  
 <span data-ttu-id="62f13-106">Необязательный элемент.</span><span class="sxs-lookup"><span data-stu-id="62f13-106">Optional.</span></span> <span data-ttu-id="62f13-107">Каталог, с которого будет начинаться поиск.</span><span class="sxs-lookup"><span data-stu-id="62f13-107">The directory in which you want the search to begin.</span></span> <span data-ttu-id="62f13-108">Если не указать, поиск начинается в каталоге проекта.</span><span class="sxs-lookup"><span data-stu-id="62f13-108">If not specified, the search begins in the project directory.</span></span>  
  
 `file`  
 <span data-ttu-id="62f13-109">Обязательный.</span><span class="sxs-lookup"><span data-stu-id="62f13-109">Required.</span></span> <span data-ttu-id="62f13-110">Файлы для поиска.</span><span class="sxs-lookup"><span data-stu-id="62f13-110">The file(s) to search for.</span></span> <span data-ttu-id="62f13-111">Поддерживаются подстановочные знаки.</span><span class="sxs-lookup"><span data-stu-id="62f13-111">Wildcard characters are allowed.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="62f13-112">Примечания</span><span class="sxs-lookup"><span data-stu-id="62f13-112">Remarks</span></span>  
 <span data-ttu-id="62f13-113">Чтобы скомпилировать все соответствующие файлы в каталоге проекта, не задавая `-recurse`, можно использовать подстановочные знаки в именах файлов.</span><span class="sxs-lookup"><span data-stu-id="62f13-113">You can use wildcards in a file name to compile all matching files in the project directory without using `-recurse`.</span></span> <span data-ttu-id="62f13-114">Если имя выходного файла не указано, компилятор выводит имя выходного файла для первого обработанного входного файла.</span><span class="sxs-lookup"><span data-stu-id="62f13-114">If no output file name is specified, the compiler bases the output file name on the first input file processed.</span></span> <span data-ttu-id="62f13-115">Обычно это первый файл в списке файлов, скомпилированных при просмотре в алфавитном порядке.</span><span class="sxs-lookup"><span data-stu-id="62f13-115">This is generally the first file in the list of files compiled when viewed alphabetically.</span></span> <span data-ttu-id="62f13-116">По этой причине лучше определять выходной файл с помощью параметра `-out`.</span><span class="sxs-lookup"><span data-stu-id="62f13-116">For this reason, it is best to specify an output file using the `-out` option.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="62f13-117">Параметр `-recurse` недоступен в среде разработки Visual Studio. Он доступен только при компиляции из командной строки.</span><span class="sxs-lookup"><span data-stu-id="62f13-117">The `-recurse` option is not available from within the Visual Studio development environment; it is available only when compiling from the command line.</span></span>  
  
## <a name="example"></a><span data-ttu-id="62f13-118">Пример</span><span class="sxs-lookup"><span data-stu-id="62f13-118">Example</span></span>  
 <span data-ttu-id="62f13-119">Следующая команда компилирует все файлы Visual Basic в текущем каталоге.</span><span class="sxs-lookup"><span data-stu-id="62f13-119">The following command compiles all Visual Basic files in the current directory.</span></span>  
  
```console
vbc *.vb  
```  
  
 <span data-ttu-id="62f13-120">Следующая команда компилирует все файлы Visual Basic в каталоге `Test\ABC` и всех вложенных каталогах, а затем создает `Test.ABC.dll`.</span><span class="sxs-lookup"><span data-stu-id="62f13-120">The following command compiles all Visual Basic files in the `Test\ABC` directory and any directories below it, and then generates `Test.ABC.dll`.</span></span>  
  
```console
vbc -target:library -out:Test.ABC.dll -recurse:Test\ABC\*.vb  
```  
  
## <a name="see-also"></a><span data-ttu-id="62f13-121">См. также</span><span class="sxs-lookup"><span data-stu-id="62f13-121">See also</span></span>

- [<span data-ttu-id="62f13-122">Компилятор Visual Basic с интерфейсом командной строки</span><span class="sxs-lookup"><span data-stu-id="62f13-122">Visual Basic Command-Line Compiler</span></span>](../../../visual-basic/reference/command-line-compiler/index.md)
- [<span data-ttu-id="62f13-123">-out (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="62f13-123">-out (Visual Basic)</span></span>](../../../visual-basic/reference/command-line-compiler/out.md)
- [<span data-ttu-id="62f13-124">Примеры командных строк компиляции</span><span class="sxs-lookup"><span data-stu-id="62f13-124">Sample Compilation Command Lines</span></span>](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)
