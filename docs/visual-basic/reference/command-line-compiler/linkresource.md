---
title: -linkresource
ms.date: 03/10/2018
helpviewer_keywords:
- /linkresource compiler option [Visual Basic]
- -linkresource compiler option [Visual Basic]
- linkresource compiler option [Visual Basic]
- /linkres compiler option [Visual Basic]
- linkres compiler option [Visual Basic]
- -linkres compiler option [Visual Basic]
ms.assetid: cf4dcad8-17b7-404c-9184-29358aa05b15
ms.openlocfilehash: 43ebb61efa26ed11af573e2c4e73a6fd71ac0902
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/04/2020
ms.locfileid: "84403204"
---
# <a name="-linkresource-visual-basic"></a><span data-ttu-id="2ba24-102">-linkresource (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="2ba24-102">-linkresource (Visual Basic)</span></span>
<span data-ttu-id="2ba24-103">Создает ссылку на управляемый ресурс.</span><span class="sxs-lookup"><span data-stu-id="2ba24-103">Creates a link to a managed resource.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2ba24-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="2ba24-104">Syntax</span></span>  
  
```console  
-linkresource:filename[,identifier[,public|private]]  
```

<span data-ttu-id="2ba24-105">or</span><span class="sxs-lookup"><span data-stu-id="2ba24-105">or</span></span>  

```console
-linkres:filename[,identifier[,public|private]]  
```  
  
## <a name="arguments"></a><span data-ttu-id="2ba24-106">Аргументы</span><span class="sxs-lookup"><span data-stu-id="2ba24-106">Arguments</span></span>  
 `filename`  
 <span data-ttu-id="2ba24-107">Обязательный.</span><span class="sxs-lookup"><span data-stu-id="2ba24-107">Required.</span></span> <span data-ttu-id="2ba24-108">Файл ресурсов, связываемый со сборкой.</span><span class="sxs-lookup"><span data-stu-id="2ba24-108">The resource file to link to the assembly.</span></span> <span data-ttu-id="2ba24-109">Если имя файла содержит пробел, заключите его в кавычки (" ").</span><span class="sxs-lookup"><span data-stu-id="2ba24-109">If the file name contains a space, enclose the name in quotation marks (" ").</span></span>  
  
 `identifier`  
 <span data-ttu-id="2ba24-110">Необязательный элемент.</span><span class="sxs-lookup"><span data-stu-id="2ba24-110">Optional.</span></span> <span data-ttu-id="2ba24-111">Логическое имя ресурса.</span><span class="sxs-lookup"><span data-stu-id="2ba24-111">The logical name for the resource.</span></span> <span data-ttu-id="2ba24-112">Имя, которое используется для загрузки ресурса.</span><span class="sxs-lookup"><span data-stu-id="2ba24-112">The name that is used to load the resource.</span></span> <span data-ttu-id="2ba24-113">По умолчанию используется имя файла.</span><span class="sxs-lookup"><span data-stu-id="2ba24-113">The default is the name of the file.</span></span> <span data-ttu-id="2ba24-114">При необходимости в манифесте сборки можно указать, является ли файл общедоступным или частным, например: `-linkres:filename.res,myname.res,public`.</span><span class="sxs-lookup"><span data-stu-id="2ba24-114">Optionally, you can specify whether the file is public or private in the assembly manifest, for example: `-linkres:filename.res,myname.res,public`.</span></span> <span data-ttu-id="2ba24-115">По умолчанию `filename` в сборке является общедоступным.</span><span class="sxs-lookup"><span data-stu-id="2ba24-115">By default, `filename` is public in the assembly.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="2ba24-116">Примечания</span><span class="sxs-lookup"><span data-stu-id="2ba24-116">Remarks</span></span>  
 <span data-ttu-id="2ba24-117">Параметр `-linkresource` не подразумевает внедрение файла ресурсов в выходной файл; для этого используйте параметр `-resource`.</span><span class="sxs-lookup"><span data-stu-id="2ba24-117">The `-linkresource` option does not embed the resource file in the output file; use the `-resource` option to do this.</span></span>  
  
 <span data-ttu-id="2ba24-118">Для параметра `-linkresource` требуется один из параметров `-target`, кроме `-target:module`.</span><span class="sxs-lookup"><span data-stu-id="2ba24-118">The `-linkresource` option requires one of the `-target` options other than `-target:module`.</span></span>  
  
 <span data-ttu-id="2ba24-119">Если `filename` является файлом ресурсов .NET Framework, созданным, например, генератором файлов ресурсов ([Resgen.exe](../../../framework/tools/resgen-exe-resource-file-generator.md)) или в среде разработки, то к нему можно обращаться с помощью элементов пространства имен <xref:System.Resources>.</span><span class="sxs-lookup"><span data-stu-id="2ba24-119">If `filename` is a .NET Framework resource file created, for example, by the [Resgen.exe (Resource File Generator)](../../../framework/tools/resgen-exe-resource-file-generator.md) or in the development environment, it can be accessed with members in the <xref:System.Resources> namespace.</span></span> <span data-ttu-id="2ba24-120">(Дополнительные сведения см. в разделе <xref:System.Resources.ResourceManager>.) Для доступа ко всем остальным ресурсам во время выполнения используйте методы, начинающиеся с `GetManifestResource`, из класса <xref:System.Reflection.Assembly>.</span><span class="sxs-lookup"><span data-stu-id="2ba24-120">(For more information, see <xref:System.Resources.ResourceManager>.) To access all other resources at run time, use the methods that begin with `GetManifestResource` in the <xref:System.Reflection.Assembly> class.</span></span>  
  
 <span data-ttu-id="2ba24-121">Имя файла может быть в любом формате файла.</span><span class="sxs-lookup"><span data-stu-id="2ba24-121">The file name can be any file format.</span></span> <span data-ttu-id="2ba24-122">Например, может потребоваться сделать имеющуюся на компьютере библиотеку DLL частью сборки, поэтому ее можно разместить в глобальном кэше сборок и обеспечить к ней доступ из управляемого кода сборки.</span><span class="sxs-lookup"><span data-stu-id="2ba24-122">For example, you may want to make a native DLL part of the assembly, so that it can be installed into the global assembly cache and accessed from managed code in the assembly.</span></span>  
  
 <span data-ttu-id="2ba24-123">Краткой формой `-linkresource` является `-linkres`.</span><span class="sxs-lookup"><span data-stu-id="2ba24-123">The short form of `-linkresource` is `-linkres`.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="2ba24-124">Параметр `-linkresource` недоступен в среде разработки Visual Studio. Его можно использовать только при компиляции из командной строки.</span><span class="sxs-lookup"><span data-stu-id="2ba24-124">The `-linkresource` option is not available from the Visual Studio development environment; it is available only when you compile from the command line.</span></span>  
  
## <a name="example"></a><span data-ttu-id="2ba24-125">Пример</span><span class="sxs-lookup"><span data-stu-id="2ba24-125">Example</span></span>  
 <span data-ttu-id="2ba24-126">Следующий код компилирует `in.vb` и обращается к файлу ресурсов `rf.resource`.</span><span class="sxs-lookup"><span data-stu-id="2ba24-126">The following code compiles `in.vb` and links to resource file `rf.resource`.</span></span>  
  
```console  
vbc -linkresource:rf.resource in.vb  
```  
  
## <a name="see-also"></a><span data-ttu-id="2ba24-127">См. также</span><span class="sxs-lookup"><span data-stu-id="2ba24-127">See also</span></span>

- [<span data-ttu-id="2ba24-128">Компилятор Visual Basic с интерфейсом командной строки</span><span class="sxs-lookup"><span data-stu-id="2ba24-128">Visual Basic Command-Line Compiler</span></span>](index.md)
- [<span data-ttu-id="2ba24-129">-target (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="2ba24-129">-target (Visual Basic)</span></span>](target.md)
- [<span data-ttu-id="2ba24-130">-resource (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="2ba24-130">-resource (Visual Basic)</span></span>](resource.md)
- [<span data-ttu-id="2ba24-131">Примеры командных строк компиляции</span><span class="sxs-lookup"><span data-stu-id="2ba24-131">Sample Compilation Command Lines</span></span>](sample-compilation-command-lines.md)
