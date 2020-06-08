---
title: -resource
ms.date: 03/13/2018
helpviewer_keywords:
- /resource compiler option [Visual Basic]
- -resource compiler option [Visual Basic]
- /res compiler option [Visual Basic]
- res compiler option [Visual Basic]
- -res compiler option [Visual Basic]
- resource compiler option [Visual Basic]
ms.assetid: eee2f227-91f2-4f2b-a9d6-1c51c5320858
ms.openlocfilehash: cf9fe8dae0d35df694891633a6e3cf950bfb7376
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/04/2020
ms.locfileid: "84363621"
---
# <a name="-resource-visual-basic"></a><span data-ttu-id="74887-102">-resource (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="74887-102">-resource (Visual Basic)</span></span>
<span data-ttu-id="74887-103">Внедряет управляемый ресурс в сборку.</span><span class="sxs-lookup"><span data-stu-id="74887-103">Embeds a managed resource in an assembly.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="74887-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="74887-104">Syntax</span></span>  
  
```console  
-resource:filename[,identifier[,public|private]]  
```

<span data-ttu-id="74887-105">or</span><span class="sxs-lookup"><span data-stu-id="74887-105">or</span></span>  

```console
-res:filename[,identifier[,public|private]]  
```  
  
## <a name="arguments"></a><span data-ttu-id="74887-106">Аргументы</span><span class="sxs-lookup"><span data-stu-id="74887-106">Arguments</span></span>  
  
|<span data-ttu-id="74887-107">Термин</span><span class="sxs-lookup"><span data-stu-id="74887-107">Term</span></span>|<span data-ttu-id="74887-108">Определение</span><span class="sxs-lookup"><span data-stu-id="74887-108">Definition</span></span>|  
|---|---|  
|`filename`|<span data-ttu-id="74887-109">Обязательный.</span><span class="sxs-lookup"><span data-stu-id="74887-109">Required.</span></span> <span data-ttu-id="74887-110">Имя файла ресурсов, который вам нужно внедрить в выходной файл.</span><span class="sxs-lookup"><span data-stu-id="74887-110">The name of the resource file to embed in the output file.</span></span> <span data-ttu-id="74887-111">По умолчанию `filename` в сборке является общедоступным.</span><span class="sxs-lookup"><span data-stu-id="74887-111">By default, `filename` is public in the assembly.</span></span> <span data-ttu-id="74887-112">Если имя файла содержит пробел, заключите это имя в кавычки (" ").</span><span class="sxs-lookup"><span data-stu-id="74887-112">Enclose the file name in quotation marks (" ") if it contains a space.</span></span>|  
|`identifier`|<span data-ttu-id="74887-113">Необязательный элемент.</span><span class="sxs-lookup"><span data-stu-id="74887-113">Optional.</span></span> <span data-ttu-id="74887-114">Логическое имя ресурса, которое используется для его загрузки.</span><span class="sxs-lookup"><span data-stu-id="74887-114">The logical name for the resource; the name used to load it.</span></span> <span data-ttu-id="74887-115">По умолчанию используется имя файла.</span><span class="sxs-lookup"><span data-stu-id="74887-115">The default is the name of the file.</span></span> <span data-ttu-id="74887-116">При необходимости в манифесте сборки можно указать, является ли ресурс общедоступным или частным, например так: `-res:filename.res, myname.res, public`.</span><span class="sxs-lookup"><span data-stu-id="74887-116">Optionally, you can specify whether the resource is public or private in the assembly manifest, as with the following: `-res:filename.res, myname.res, public`</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="74887-117">Примечания</span><span class="sxs-lookup"><span data-stu-id="74887-117">Remarks</span></span>  
 <span data-ttu-id="74887-118">Используйте `-linkresource`, чтобы связать ресурс со сборкой без размещения файла ресурсов в выходном файле.</span><span class="sxs-lookup"><span data-stu-id="74887-118">Use `-linkresource` to link a resource to an assembly without placing the resource file in the output file.</span></span>  
  
 <span data-ttu-id="74887-119">Если `filename` — файл ресурса .NET Framework, созданный генератором файлов ресурсов ([Resgen.exe](../../../framework/tools/resgen-exe-resource-file-generator.md)) или в среде разработки, то к нему можно обращаться с помощью элементов пространства имен <xref:System.Resources> (дополнительные сведения см. в статье о классе <xref:System.Resources.ResourceManager>).</span><span class="sxs-lookup"><span data-stu-id="74887-119">If `filename` is a .NET Framework resource file created, for example, by the [Resgen.exe (Resource File Generator)](../../../framework/tools/resgen-exe-resource-file-generator.md) or in the development environment, it can be accessed with members in the <xref:System.Resources> namespace (see <xref:System.Resources.ResourceManager> for more information).</span></span> <span data-ttu-id="74887-120">Для доступа ко всем остальным ресурсам во время выполнения используйте следующие методы: <xref:System.Reflection.Assembly.GetManifestResourceInfo%2A>, <xref:System.Reflection.Assembly.GetManifestResourceNames%2A> и <xref:System.Reflection.Assembly.GetManifestResourceStream%2A>.</span><span class="sxs-lookup"><span data-stu-id="74887-120">To access all other resources at run time, use one of the following methods: <xref:System.Reflection.Assembly.GetManifestResourceInfo%2A>, <xref:System.Reflection.Assembly.GetManifestResourceNames%2A>, or <xref:System.Reflection.Assembly.GetManifestResourceStream%2A>.</span></span>  
  
 <span data-ttu-id="74887-121">Краткой формой `-resource` является `-res`.</span><span class="sxs-lookup"><span data-stu-id="74887-121">The short form of `-resource` is `-res`.</span></span>  
  
 <span data-ttu-id="74887-122">Дополнительные сведения о настройке `-resource` в интегрированной среде разработки Visual Studio см. в статье [об управлении ресурсами приложения в .NET](/visualstudio/ide/managing-application-resources-dotnet).</span><span class="sxs-lookup"><span data-stu-id="74887-122">For information about how to set `-resource` in the Visual Studio IDE, see [Managing Application Resources (.NET)](/visualstudio/ide/managing-application-resources-dotnet).</span></span>  
  
## <a name="example"></a><span data-ttu-id="74887-123">Пример</span><span class="sxs-lookup"><span data-stu-id="74887-123">Example</span></span>  
 <span data-ttu-id="74887-124">Следующий код компилирует `In.vb` и присоединяет файл ресурсов `Rf.resource`.</span><span class="sxs-lookup"><span data-stu-id="74887-124">The following code compiles `In.vb` and attaches resource file `Rf.resource`.</span></span>  
  
```console
vbc -res:rf.resource in.vb  
```  
  
## <a name="see-also"></a><span data-ttu-id="74887-125">См. также</span><span class="sxs-lookup"><span data-stu-id="74887-125">See also</span></span>

- [<span data-ttu-id="74887-126">Компилятор Visual Basic с интерфейсом командной строки</span><span class="sxs-lookup"><span data-stu-id="74887-126">Visual Basic Command-Line Compiler</span></span>](index.md)
- [<span data-ttu-id="74887-127">-win32resource</span><span class="sxs-lookup"><span data-stu-id="74887-127">-win32resource</span></span>](win32resource.md)
- [<span data-ttu-id="74887-128">-linkresource (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="74887-128">-linkresource (Visual Basic)</span></span>](linkresource.md)
- [<span data-ttu-id="74887-129">-target (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="74887-129">-target (Visual Basic)</span></span>](target.md)
- [<span data-ttu-id="74887-130">Примеры командных строк компиляции</span><span class="sxs-lookup"><span data-stu-id="74887-130">Sample Compilation Command Lines</span></span>](sample-compilation-command-lines.md)
