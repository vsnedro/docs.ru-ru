---
title: '@ (указание файла ответа)'
ms.date: 03/13/2018
helpviewer_keywords:
- '@ (Specify Response File) compiler option [Visual Basic]'
ms.assetid: a6847eaa-e5f9-4303-9421-45b55484b9ca
ms.openlocfilehash: c578495bbba0efee79f02da284c7feffb8c12fab
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/22/2019
ms.locfileid: "74348555"
---
# <a name="-specify-response-file-visual-basic"></a><span data-ttu-id="70a85-102">@ (указание файла ответа) (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="70a85-102">@ (Specify Response File) (Visual Basic)</span></span>

<span data-ttu-id="70a85-103">Указывает файл, содержащий параметры компилятора и файлы исходного кода, которые требуется компилировать.</span><span class="sxs-lookup"><span data-stu-id="70a85-103">Specifies a file that contains compiler options and source-code files to compile.</span></span>

## <a name="syntax"></a><span data-ttu-id="70a85-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="70a85-104">Syntax</span></span>

```console
@response_file
```

## <a name="arguments"></a><span data-ttu-id="70a85-105">Аргументы</span><span class="sxs-lookup"><span data-stu-id="70a85-105">Arguments</span></span>

`response_file`  
<span data-ttu-id="70a85-106">Обязательный.</span><span class="sxs-lookup"><span data-stu-id="70a85-106">Required.</span></span> <span data-ttu-id="70a85-107">Файл, содержащий параметры компилятора и файлы исходного кода, которые требуется компилировать.</span><span class="sxs-lookup"><span data-stu-id="70a85-107">A file that lists compiler options or source-code files to compile.</span></span> <span data-ttu-id="70a85-108">Если имя файла содержит пробел, заключите имя файла в кавычки (" ").</span><span class="sxs-lookup"><span data-stu-id="70a85-108">Enclose the file name in quotation marks (" ") if it contains a space.</span></span>

## <a name="remarks"></a><span data-ttu-id="70a85-109">Примечания</span><span class="sxs-lookup"><span data-stu-id="70a85-109">Remarks</span></span>

<span data-ttu-id="70a85-110">Компилятор обрабатывает параметры компилятора и файлы исходного кода, указанные в файле ответов таким образом, как если бы они были указаны в командной строке.</span><span class="sxs-lookup"><span data-stu-id="70a85-110">The compiler processes the compiler options and source-code files specified in a response file as if they had been specified on the command line.</span></span>

<span data-ttu-id="70a85-111">Чтобы задать несколько файлов ответов для компиляции, используйте соответствующее число параметров файла ответов, таких как следующие.</span><span class="sxs-lookup"><span data-stu-id="70a85-111">To specify more than one response file in a compilation, specify multiple response-file options, such as the following.</span></span>

```console
@file1.rsp @file2.rsp
```

<span data-ttu-id="70a85-112">В одной строке файла ответов может содержаться несколько параметров компилятора и файлов исходного кода.</span><span class="sxs-lookup"><span data-stu-id="70a85-112">In a response file, multiple compiler options and source-code files can appear on one line.</span></span> <span data-ttu-id="70a85-113">Спецификация отдельного параметра компилятора должна размещаться на одной строке и не может разбиваться на несколько строк.</span><span class="sxs-lookup"><span data-stu-id="70a85-113">A single compiler-option specification must appear on one line (cannot span multiple lines).</span></span> <span data-ttu-id="70a85-114">В файл ответов можно добавлять комментарии, которые должны начинаться с символа `#`.</span><span class="sxs-lookup"><span data-stu-id="70a85-114">Response files can have comments that begin with the `#` symbol.</span></span>

<span data-ttu-id="70a85-115">Параметры, указанные в командной строке, можно объединять с параметрами, указанными в одном или нескольких файлах ответов.</span><span class="sxs-lookup"><span data-stu-id="70a85-115">You can combine options specified on the command line with options specified in one or more response files.</span></span> <span data-ttu-id="70a85-116">Компилятор обрабатывает параметры команд в том порядке, в котором встречает их.</span><span class="sxs-lookup"><span data-stu-id="70a85-116">The compiler processes the command options as it encounters them.</span></span> <span data-ttu-id="70a85-117">Таким образом, аргументы командной строки могут переопределять параметры, заданные ранее в файле ответов.</span><span class="sxs-lookup"><span data-stu-id="70a85-117">Therefore, command-line arguments can override previously listed options in response files.</span></span> <span data-ttu-id="70a85-118">Аналогично, параметры в файле ответов будут переопределять параметры, ранее заданные в командной строке или в других файлах ответов.</span><span class="sxs-lookup"><span data-stu-id="70a85-118">Conversely, options in a response file override options listed previously on the command line or in other response files.</span></span>

<span data-ttu-id="70a85-119">В Visual Basic представлен файл Vbc.rsp, который находится в одном каталоге с файлом Vbc.exe.</span><span class="sxs-lookup"><span data-stu-id="70a85-119">Visual Basic provides the Vbc.rsp file, which is located in the same directory as the Vbc.exe file.</span></span> <span data-ttu-id="70a85-120">Файл Vbc.rsp включен по умолчанию, если не используется параметр `-noconfig`.</span><span class="sxs-lookup"><span data-stu-id="70a85-120">The Vbc.rsp file is included by default unless the `-noconfig` option is used.</span></span> <span data-ttu-id="70a85-121">Дополнительные сведения см. в [-noconfig](../../../visual-basic/reference/command-line-compiler/noconfig.md).</span><span class="sxs-lookup"><span data-stu-id="70a85-121">For more information, see [-noconfig](../../../visual-basic/reference/command-line-compiler/noconfig.md).</span></span>

> [!NOTE]
> <span data-ttu-id="70a85-122">Параметр `@` недоступен в среде разработки Visual Studio. Его можно использовать только при компиляции из командной строки.</span><span class="sxs-lookup"><span data-stu-id="70a85-122">The `@` option is not available from within the Visual Studio development environment; it is available only when compiling from the command line.</span></span>

## <a name="example"></a><span data-ttu-id="70a85-123">Пример</span><span class="sxs-lookup"><span data-stu-id="70a85-123">Example</span></span>

<span data-ttu-id="70a85-124">Ниже приведены строки из образца файла ответов.</span><span class="sxs-lookup"><span data-stu-id="70a85-124">The following lines are from a sample response file.</span></span>

```console
# build the first output file
-target:exe
-out:MyExe.exe
source1.vb
source2.vb
```

## <a name="example"></a><span data-ttu-id="70a85-125">Пример</span><span class="sxs-lookup"><span data-stu-id="70a85-125">Example</span></span>

<span data-ttu-id="70a85-126">В следующем примере показано использование класса `@` в сочетании с файлом ответов `File1.rsp`.</span><span class="sxs-lookup"><span data-stu-id="70a85-126">The following example demonstrates how to use the `@` option with the response file named `File1.rsp`.</span></span>

```console
vbc @file1.rsp
```

## <a name="see-also"></a><span data-ttu-id="70a85-127">См. также</span><span class="sxs-lookup"><span data-stu-id="70a85-127">See also</span></span>

- [<span data-ttu-id="70a85-128">Компилятор Visual Basic с интерфейсом командной строки</span><span class="sxs-lookup"><span data-stu-id="70a85-128">Visual Basic Command-Line Compiler</span></span>](../../../visual-basic/reference/command-line-compiler/index.md)
- [<span data-ttu-id="70a85-129">-noconfig</span><span class="sxs-lookup"><span data-stu-id="70a85-129">-noconfig</span></span>](../../../visual-basic/reference/command-line-compiler/noconfig.md)
- [<span data-ttu-id="70a85-130">Примеры командных строк компиляции</span><span class="sxs-lookup"><span data-stu-id="70a85-130">Sample Compilation Command Lines</span></span>](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)
