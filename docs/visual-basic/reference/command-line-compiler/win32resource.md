---
title: -win32resource
ms.date: 03/13/2018
f1_keywords:
- -win32resource
- win32resource
helpviewer_keywords:
- /win32resource compiler option [Visual Basic]
- -win32resource compiler option [Visual Basic]
- win32resource compiler option [Visual Basic]
ms.assetid: e226946d-19ce-4cc9-91f5-aed24f77aa2b
ms.openlocfilehash: cee06adec89aac4b3e3f170df3bf932e466f3070
ms.sourcegitcommit: eff6adb61852369ab690f3f047818c90580e7eb1
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/07/2019
ms.locfileid: "72004958"
---
# <a name="-win32resource"></a><span data-ttu-id="69c54-102">-win32resource</span><span class="sxs-lookup"><span data-stu-id="69c54-102">-win32resource</span></span>
<span data-ttu-id="69c54-103">Вставляет файл ресурсов Win32 в выходной файл.</span><span class="sxs-lookup"><span data-stu-id="69c54-103">Inserts a Win32 resource file in the output file.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="69c54-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="69c54-104">Syntax</span></span>  
  
```console  
-win32resource:filename  
```  
  
## <a name="arguments"></a><span data-ttu-id="69c54-105">Аргументы</span><span class="sxs-lookup"><span data-stu-id="69c54-105">Arguments</span></span>  
 `filename`  
 <span data-ttu-id="69c54-106">Имя файла ресурсов, который требуется добавить в выходной файл.</span><span class="sxs-lookup"><span data-stu-id="69c54-106">The name of the resource file to add to your output file.</span></span> <span data-ttu-id="69c54-107">Если имя файла содержит пробел, заключите имя файла в кавычки (" ").</span><span class="sxs-lookup"><span data-stu-id="69c54-107">Enclose the file name in quotation marks (" ") if it contains a space.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="69c54-108">Примечания</span><span class="sxs-lookup"><span data-stu-id="69c54-108">Remarks</span></span>  
 <span data-ttu-id="69c54-109">Вы можете создать файл ресурсов Win32 с помощью компилятора ресурсов Microsoft Windows (RC).</span><span class="sxs-lookup"><span data-stu-id="69c54-109">You can create a Win32 resource file with the Microsoft Windows Resource Compiler (RC).</span></span>  
  
 <span data-ttu-id="69c54-110">Ресурс Win32 может содержать сведения о версии или точечный рисунок (значок), который помогает идентифицировать приложение в **проводнике**.</span><span class="sxs-lookup"><span data-stu-id="69c54-110">A Win32 resource can contain version or bitmap (icon) information that helps identify your application in **File Explorer**.</span></span> <span data-ttu-id="69c54-111">Если параметр `-win32resource` не задан, компилятор создаст сведения о версии на основе версии сборки.</span><span class="sxs-lookup"><span data-stu-id="69c54-111">If you do not specify `-win32resource`, the compiler generates version information based on the assembly version.</span></span> <span data-ttu-id="69c54-112">Параметры `-win32resource` и `-win32icon` являются взаимоисключающими.</span><span class="sxs-lookup"><span data-stu-id="69c54-112">The `-win32resource` and `-win32icon` options are mutually exclusive.</span></span>  
  
 <span data-ttu-id="69c54-113">Чтобы создать ссылку на файл ресурсов .NET Framework, обратитесь к разделу [-linkresource (Visual Basic)](../../../visual-basic/reference/command-line-compiler/linkresource.md). Чтобы присоединить файл ресурсов .NET, обратитесь к разделу [-resource (Visual Basic)](../../../visual-basic/reference/command-line-compiler/resource.md).</span><span class="sxs-lookup"><span data-stu-id="69c54-113">See [-linkresource (Visual Basic)](../../../visual-basic/reference/command-line-compiler/linkresource.md) to reference a .NET Framework resource file, or [-resource (Visual Basic)](../../../visual-basic/reference/command-line-compiler/resource.md) to attach a .NET Framework resource file.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="69c54-114">Параметр `-win32resource` недоступен в среде разработки Visual Studio. Его можно использовать только при компиляции из командной строки.</span><span class="sxs-lookup"><span data-stu-id="69c54-114">The `-win32resource` option is not available from within the Visual Studio development environment; it is available only when compiling from the command line.</span></span>  
  
## <a name="example"></a><span data-ttu-id="69c54-115">Пример</span><span class="sxs-lookup"><span data-stu-id="69c54-115">Example</span></span>  
 <span data-ttu-id="69c54-116">Следующий код компилирует `In.vb` и присоединяет файл ресурсов Win32 `Rf.res`:</span><span class="sxs-lookup"><span data-stu-id="69c54-116">The following code compiles `In.vb` and attaches a Win32 resource file, `Rf.res`:</span></span>  
  
```console  
vbc -win32resource:rf.res in.vb  
```  
  
## <a name="see-also"></a><span data-ttu-id="69c54-117">См. также</span><span class="sxs-lookup"><span data-stu-id="69c54-117">See also</span></span>

- [<span data-ttu-id="69c54-118">Компилятор Visual Basic с интерфейсом командной строки</span><span class="sxs-lookup"><span data-stu-id="69c54-118">Visual Basic Command-Line Compiler</span></span>](../../../visual-basic/reference/command-line-compiler/index.md)
- [<span data-ttu-id="69c54-119">Примеры командных строк компиляции</span><span class="sxs-lookup"><span data-stu-id="69c54-119">Sample Compilation Command Lines</span></span>](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)
