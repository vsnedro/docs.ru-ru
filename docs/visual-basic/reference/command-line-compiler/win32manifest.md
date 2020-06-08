---
title: -win32manifest
ms.date: 03/13/2018
helpviewer_keywords:
- /win32manifest compiler option [Visual Basic]
- win32manifest compiler option [Visual Basic]
- -win32manifest compiler option [Visual Basic]
ms.assetid: 9e3191b4-90db-41c8-966a-28036fd20005
ms.openlocfilehash: 6f77649365f8ca7b163cd55854aa9960d88f2984
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/04/2020
ms.locfileid: "84414263"
---
# <a name="-win32manifest-visual-basic"></a><span data-ttu-id="83d3f-102">-win32manifest (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="83d3f-102">-win32manifest (Visual Basic)</span></span>
<span data-ttu-id="83d3f-103">Определяет пользовательский файл манифеста приложения Win32 для внедрения в переносимый исполняемый файл проекта (PE-файл).</span><span class="sxs-lookup"><span data-stu-id="83d3f-103">Identifies a user-defined Win32 application manifest file to be embedded into a project's portable executable (PE) file.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="83d3f-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="83d3f-104">Syntax</span></span>  
  
```console  
-win32manifest: fileName  
```  
  
## <a name="arguments"></a><span data-ttu-id="83d3f-105">Аргументы</span><span class="sxs-lookup"><span data-stu-id="83d3f-105">Arguments</span></span>  
  
|<span data-ttu-id="83d3f-106">Термин</span><span class="sxs-lookup"><span data-stu-id="83d3f-106">Term</span></span>|<span data-ttu-id="83d3f-107">Определение</span><span class="sxs-lookup"><span data-stu-id="83d3f-107">Definition</span></span>|  
|---|---|  
|`fileName`|<span data-ttu-id="83d3f-108">Путь к пользовательскому файлу манифеста.</span><span class="sxs-lookup"><span data-stu-id="83d3f-108">The path of the custom manifest file.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="83d3f-109">Примечания</span><span class="sxs-lookup"><span data-stu-id="83d3f-109">Remarks</span></span>  
 <span data-ttu-id="83d3f-110">По умолчанию компилятор Visual Basic внедряет манифест приложения, определяющий запрошенный уровень выполнения "asInvoker".</span><span class="sxs-lookup"><span data-stu-id="83d3f-110">By default, the Visual Basic compiler embeds an application manifest that specifies a requested execution level of asInvoker.</span></span> <span data-ttu-id="83d3f-111">Он создает манифест в той же папке, в которой создан исполняемый файл; при использовании Visual Studio обычно это папка bin\Debug или bin\Release.</span><span class="sxs-lookup"><span data-stu-id="83d3f-111">It creates the manifest in the same folder in which the executable file is built, typically the bin\Debug or bin\Release folder when you use Visual Studio.</span></span> <span data-ttu-id="83d3f-112">Если вы хотите предоставить пользовательский манифест, например, чтобы задать запрошенный уровень выполнения highestAvailable или requireAdministrator, используйте этот параметр, чтобы указать имя файла.</span><span class="sxs-lookup"><span data-stu-id="83d3f-112">If you want to supply a custom manifest, for example to specify a requested execution level of highestAvailable or requireAdministrator, use this option to specify the name of the file.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="83d3f-113">Этот параметр и параметр [-win32resource](win32resource.md) являются взаимоисключающими.</span><span class="sxs-lookup"><span data-stu-id="83d3f-113">This option and the [-win32resource](win32resource.md) option are mutually exclusive.</span></span> <span data-ttu-id="83d3f-114">При попытке использовать оба параметра в одной командной строке возникнет ошибка сборки.</span><span class="sxs-lookup"><span data-stu-id="83d3f-114">If you try to use both options in the same command line, you will get a build error.</span></span>  
  
 <span data-ttu-id="83d3f-115">Приложение без манифеста, определяющего запрошенный уровень выполнения, требует виртуализации файлов или реестра с помощью функции "Контроль учетных записей" в Windows Vista.</span><span class="sxs-lookup"><span data-stu-id="83d3f-115">An application that has no application manifest that specifies a requested execution level will be subject to file/registry virtualization under the User Account Control feature in Windows Vista.</span></span> <span data-ttu-id="83d3f-116">Дополнительные сведения о виртуализации см. в статье [ClickOnce Deployment on Windows Vista](/visualstudio/deployment/clickonce-deployment-on-windows-vista) (Развертывание ClickOnce в Windows Vista).</span><span class="sxs-lookup"><span data-stu-id="83d3f-116">For more information about virtualization, see [ClickOnce Deployment on Windows Vista](/visualstudio/deployment/clickonce-deployment-on-windows-vista).</span></span>  
  
 <span data-ttu-id="83d3f-117">Ваше приложение будет виртуализовано, если выполняется одно из следующих условий.</span><span class="sxs-lookup"><span data-stu-id="83d3f-117">Your application will be subject to virtualization if either of the following conditions is true:</span></span>  
  
1. <span data-ttu-id="83d3f-118">Вы используете параметр `-nowin32manifest`, но не предоставляете манифест на более позднем этапе сборки или в файле ресурсов Windows (с расширением RES) с помощью параметра `-win32resource`.</span><span class="sxs-lookup"><span data-stu-id="83d3f-118">You use the `-nowin32manifest` option and you do not provide a manifest in a later build step or as part of a Windows Resource (.res) file by using the `-win32resource` option.</span></span>  
  
2. <span data-ttu-id="83d3f-119">Вы предоставляете пользовательский манифест, не определяющий запрошенный уровень выполнения.</span><span class="sxs-lookup"><span data-stu-id="83d3f-119">You provide a custom manifest that does not specify a requested execution level.</span></span>  
  
 <span data-ttu-id="83d3f-120">Visual Studio создает файл по умолчанию с расширением .manifest и сохраняет его в каталоги отладки и выпуска вместе с исполняемым файлом.</span><span class="sxs-lookup"><span data-stu-id="83d3f-120">Visual Studio creates a default .manifest file and stores it in the debug and release directories alongside the executable file.</span></span> <span data-ttu-id="83d3f-121">Чтобы просмотреть или изменить файл app.manifest по умолчанию, нажмите **Просмотреть параметры контроля учетных записей** на вкладке **Приложение** в конструкторе проектов.</span><span class="sxs-lookup"><span data-stu-id="83d3f-121">You can view or edit the default app.manifest file by clicking **View UAC Settings** on the **Application** tab in the Project Designer.</span></span> <span data-ttu-id="83d3f-122">Дополнительные сведения см. в разделе [Application Page, Project Designer (Visual Basic)](/visualstudio/ide/reference/application-page-project-designer-visual-basic).</span><span class="sxs-lookup"><span data-stu-id="83d3f-122">For more information, see [Application Page, Project Designer (Visual Basic)](/visualstudio/ide/reference/application-page-project-designer-visual-basic).</span></span>  
  
 <span data-ttu-id="83d3f-123">Манифест приложения можно предоставить во время пользовательского этапа после сборки или в составе файла ресурсов Win32 с помощью параметра `-nowin32manifest`.</span><span class="sxs-lookup"><span data-stu-id="83d3f-123">You can provide the application manifest as a custom post-build step or as part of a Win32 resource file by using the `-nowin32manifest` option.</span></span> <span data-ttu-id="83d3f-124">Этот же параметр можно использовать, если вы хотите, чтобы ваше приложение требовало виртуализации файлов или реестров в Windows Vista.</span><span class="sxs-lookup"><span data-stu-id="83d3f-124">Use that same option if you want your application to be subject to file or registry virtualization on Windows Vista.</span></span> <span data-ttu-id="83d3f-125">В этом случае компилятор не будет создавать и внедрять манифест по умолчанию в PE-файл.</span><span class="sxs-lookup"><span data-stu-id="83d3f-125">This will prevent the compiler from creating and embedding a default manifest in the PE file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="83d3f-126">Пример</span><span class="sxs-lookup"><span data-stu-id="83d3f-126">Example</span></span>  
 <span data-ttu-id="83d3f-127">В следующем примере показан манифест по умолчанию, который компилятор Visual C# вставляет в PE.</span><span class="sxs-lookup"><span data-stu-id="83d3f-127">The following example shows the default manifest that the Visual Basic compiler inserts into a PE.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="83d3f-128">Компилятор вставляет в XML-код манифеста стандартное имя приложения, "MyApplication.app".</span><span class="sxs-lookup"><span data-stu-id="83d3f-128">The compiler inserts a standard application name MyApplication.app into the manifest XML.</span></span> <span data-ttu-id="83d3f-129">Это позволяет приложениям работать в Windows Server 2003 с пакетом обновления 3.</span><span class="sxs-lookup"><span data-stu-id="83d3f-129">This is a workaround to enable applications to run on Windows Server 2003 Service Pack 3.</span></span>  
  
```xml  
<?xml version="1.0" encoding="utf-8" standalone="yes"?>  
<assembly xmlns="urn:schemas-microsoft-com:asm.v1" manifestVersion="1.0">  
  <assemblyIdentity version="1.0.0.0" name="MyApplication.app"/>  
  <trustInfo xmlns="urn:schemas-microsoft-com:asm.v2">  
    <security>  
      <requestedPrivileges xmlns="urn:schemas-microsoft-com:asm.v3">  
        <requestedExecutionLevel level="asInvoker"/>  
      </requestedPrivileges>  
    </security>  
  </trustInfo>  
</assembly>  
```  
  
## <a name="see-also"></a><span data-ttu-id="83d3f-130">См. также</span><span class="sxs-lookup"><span data-stu-id="83d3f-130">See also</span></span>

- [<span data-ttu-id="83d3f-131">Компилятор Visual Basic с интерфейсом командной строки</span><span class="sxs-lookup"><span data-stu-id="83d3f-131">Visual Basic Command-Line Compiler</span></span>](index.md)
- [<span data-ttu-id="83d3f-132">-nowin32manifest (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="83d3f-132">-nowin32manifest (Visual Basic)</span></span>](nowin32manifest.md)
