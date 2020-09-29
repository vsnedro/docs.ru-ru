---
description: -resource (параметры компилятора C#)
title: -resource (параметры компилятора C#)
ms.date: 07/20/2015
f1_keywords:
- /resource
helpviewer_keywords:
- -resource compiler option [C#]
- /resource compiler option [C#]
- -res compiler option [C#]
- /res compiler option [C#]
- res compiler option [C#]
- resource compiler option [C#]
ms.assetid: 5212666e-98ab-47e4-a497-b5545ab15c7f
ms.openlocfilehash: 6f90ce6c1590784cefbd5f15ca8a36941aad77ed
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/24/2020
ms.locfileid: "91193781"
---
# <a name="-resource-c-compiler-options"></a><span data-ttu-id="65587-103">-resource (параметры компилятора C#)</span><span class="sxs-lookup"><span data-stu-id="65587-103">-resource (C# Compiler Options)</span></span>

<span data-ttu-id="65587-104">Внедряет указанный ресурс в выходной файл.</span><span class="sxs-lookup"><span data-stu-id="65587-104">Embeds the specified resource into the output file.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="65587-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="65587-105">Syntax</span></span>  
  
```console  
-resource:filename[,identifier[,accessibility-modifier]]  
```  
  
## <a name="arguments"></a><span data-ttu-id="65587-106">Аргументы</span><span class="sxs-lookup"><span data-stu-id="65587-106">Arguments</span></span>  

 `filename`  
 <span data-ttu-id="65587-107">Файл ресурсов .NET, который требуется внедрить в выходной файл.</span><span class="sxs-lookup"><span data-stu-id="65587-107">The .NET resource file that you want to embed in the output file.</span></span>  
  
 <span data-ttu-id="65587-108">Среда `identifier` (необязательно)</span><span class="sxs-lookup"><span data-stu-id="65587-108">`identifier` (optional)</span></span>  
 <span data-ttu-id="65587-109">Логическое имя ресурса, используемое для его загрузки.</span><span class="sxs-lookup"><span data-stu-id="65587-109">The logical name for the resource; the name that is used to load the resource.</span></span> <span data-ttu-id="65587-110">По умолчанию используется имя файла.</span><span class="sxs-lookup"><span data-stu-id="65587-110">The default is the name of the file name.</span></span>  
  
 <span data-ttu-id="65587-111">Среда `accessibility-modifier` (необязательно)</span><span class="sxs-lookup"><span data-stu-id="65587-111">`accessibility-modifier` (optional)</span></span>  
 <span data-ttu-id="65587-112">Доступность ресурса: "public" (открытый) или "private" (закрытый).</span><span class="sxs-lookup"><span data-stu-id="65587-112">The accessibility of the resource: public or private.</span></span> <span data-ttu-id="65587-113">Значение по умолчанию: public.</span><span class="sxs-lookup"><span data-stu-id="65587-113">The default is public.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="65587-114">Remarks</span><span class="sxs-lookup"><span data-stu-id="65587-114">Remarks</span></span>  

 <span data-ttu-id="65587-115">Используйте [-linkresource](./linkresource-compiler-option.md), чтобы связать ресурс со сборкой и не добавлять файл ресурсов в выходной файл.</span><span class="sxs-lookup"><span data-stu-id="65587-115">Use [-linkresource](./linkresource-compiler-option.md) to link a resource to an assembly and not add the resource file to the output file.</span></span>  
  
 <span data-ttu-id="65587-116">По умолчанию ресурсы в сборке открыты, если они создавались с помощью компилятора C#.</span><span class="sxs-lookup"><span data-stu-id="65587-116">By default, resources are public in the assembly when they are created by using the C# compiler.</span></span> <span data-ttu-id="65587-117">Чтобы сделать ресурс закрытым, укажите параметр `private` в качестве модификатора доступа.</span><span class="sxs-lookup"><span data-stu-id="65587-117">To make the resources private, specify `private` as the accessibility modifier.</span></span> <span data-ttu-id="65587-118">Уровни доступности, отличные от `public` или `private`, не допускаются.</span><span class="sxs-lookup"><span data-stu-id="65587-118">No other accessibility other than `public` or `private` is allowed.</span></span>  
  
 <span data-ttu-id="65587-119">Если `filename` является файлом ресурсов .NET, созданным, например, с помощью [Resgen.exe](../../../framework/tools/resgen-exe-resource-file-generator.md) или в среде разработки, то к нему можно обращаться с помощью элементов в пространстве имен <xref:System.Resources>.</span><span class="sxs-lookup"><span data-stu-id="65587-119">If `filename` is a .NET resource file created, for example, by [Resgen.exe](../../../framework/tools/resgen-exe-resource-file-generator.md) or in the development environment, it can be accessed with members in the <xref:System.Resources> namespace.</span></span> <span data-ttu-id="65587-120">Для получения дополнительной информации см. <xref:System.Resources.ResourceManager?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="65587-120">For more information, see <xref:System.Resources.ResourceManager?displayProperty=nameWithType>.</span></span> <span data-ttu-id="65587-121">Чтобы получить доступ ко всем остальным ресурсам во время выполнения, используйте методы `GetManifestResource` в классе <xref:System.Reflection.Assembly>.</span><span class="sxs-lookup"><span data-stu-id="65587-121">For all other resources, use the `GetManifestResource` methods in the <xref:System.Reflection.Assembly> class to access the resource at run time.</span></span>  
  
 <span data-ttu-id="65587-122">**-res** является краткой формой **-resource**.</span><span class="sxs-lookup"><span data-stu-id="65587-122">**-res** is the short form of **-resource**.</span></span>  
  
 <span data-ttu-id="65587-123">Порядок расположения ресурсов в выходном файле будет определяться порядком, указанным в командной строке.</span><span class="sxs-lookup"><span data-stu-id="65587-123">The order of the resources in the output file is determined from the order specified on the command line.</span></span>  
  
### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a><span data-ttu-id="65587-124">Установка данного параметра компилятора в среде разработки Visual Studio</span><span class="sxs-lookup"><span data-stu-id="65587-124">To set this compiler option in the Visual Studio development environment</span></span>  
  
1. <span data-ttu-id="65587-125">Добавьте файл ресурсов в проект.</span><span class="sxs-lookup"><span data-stu-id="65587-125">Add a resource file to your project.</span></span>  
  
2. <span data-ttu-id="65587-126">Выберите файл, который требуется внедрить, в **обозревателе решений**.</span><span class="sxs-lookup"><span data-stu-id="65587-126">Select the file that you want to embed in **Solution Explorer**.</span></span>  
  
3. <span data-ttu-id="65587-127">Выберите **Действие сборки** для файла в окне **Свойства**.</span><span class="sxs-lookup"><span data-stu-id="65587-127">Select **Build Action** for the file in the **Properties** window.</span></span>  
  
4. <span data-ttu-id="65587-128">Присвойте параметру **Действие сборки** значение **Внедренный ресурс**.</span><span class="sxs-lookup"><span data-stu-id="65587-128">Set **Build Action** to **Embedded Resource**.</span></span>  
  
 <span data-ttu-id="65587-129">Дополнительные сведения об установке этого параметра компилятора программным путем см. в разделе <xref:VSLangProj80.FileProperties2.BuildAction%2A>.</span><span class="sxs-lookup"><span data-stu-id="65587-129">For information about how to set this compiler option programmatically, see <xref:VSLangProj80.FileProperties2.BuildAction%2A>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="65587-130">Пример</span><span class="sxs-lookup"><span data-stu-id="65587-130">Example</span></span>  

 <span data-ttu-id="65587-131">Компиляция `in.cs` и привязка файла ресурсов `rf.resource`:</span><span class="sxs-lookup"><span data-stu-id="65587-131">Compile `in.cs` and attach resource file `rf.resource`:</span></span>  
  
```console  
csc -resource:rf.resource in.cs  
```  
  
## <a name="see-also"></a><span data-ttu-id="65587-132">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="65587-132">See also</span></span>

- [<span data-ttu-id="65587-133">Параметры компилятора C# </span><span class="sxs-lookup"><span data-stu-id="65587-133">C# Compiler Options</span></span>](./index.md)
- [<span data-ttu-id="65587-134">Управление свойствами проектов и решений</span><span class="sxs-lookup"><span data-stu-id="65587-134">Managing Project and Solution Properties</span></span>](/visualstudio/ide/managing-project-and-solution-properties)
