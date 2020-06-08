---
title: -sdkpath
ms.date: 07/20/2015
f1_keywords:
- sdkpath
- -sdkpath
helpviewer_keywords:
- -sdkpath compiler option [Visual Basic]
- /sdkpath compiler option [Visual Basic]
- sdkpath compiler option [Visual Basic]
ms.assetid: fec8a3f1-b791-4a37-8af7-344859f8212d
ms.openlocfilehash: 85aba17b330af1b25b39f462844bc1a4856a448a
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/04/2020
ms.locfileid: "84403113"
---
# <a name="-sdkpath"></a><span data-ttu-id="ec86b-102">-sdkpath</span><span class="sxs-lookup"><span data-stu-id="ec86b-102">-sdkpath</span></span>
<span data-ttu-id="ec86b-103">Задает расположение библиотек mscorlib.dll и Microsoft.VisualBasic.dll.</span><span class="sxs-lookup"><span data-stu-id="ec86b-103">Specifies the location of mscorlib.dll and Microsoft.VisualBasic.dll.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ec86b-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="ec86b-104">Syntax</span></span>  
  
```console  
-sdkpath:path  
```  
  
## <a name="arguments"></a><span data-ttu-id="ec86b-105">Аргументы</span><span class="sxs-lookup"><span data-stu-id="ec86b-105">Arguments</span></span>  
 `path`  
 <span data-ttu-id="ec86b-106">Каталог, содержащий версии библиотек mscorlib.dll и Microsoft.VisualBasic.dll, которые следует использовать для компиляции.</span><span class="sxs-lookup"><span data-stu-id="ec86b-106">The directory containing the versions of mscorlib.dll and Microsoft.VisualBasic.dll to use for compilation.</span></span> <span data-ttu-id="ec86b-107">Этот путь является не проверенным до его загрузки.</span><span class="sxs-lookup"><span data-stu-id="ec86b-107">This path is not verified until it is loaded.</span></span> <span data-ttu-id="ec86b-108">Если имя каталога содержит пробел, заключите это имя в кавычки (" ").</span><span class="sxs-lookup"><span data-stu-id="ec86b-108">Enclose the directory name in quotation marks (" ") if it contains a space.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="ec86b-109">Примечания</span><span class="sxs-lookup"><span data-stu-id="ec86b-109">Remarks</span></span>  
 <span data-ttu-id="ec86b-110">Этот параметр указывает компилятору Visual Basic, что нужно загрузить файлы mscorlib.dll и Microsoft.VisualBasic.dll из нестандартного расположения.</span><span class="sxs-lookup"><span data-stu-id="ec86b-110">This option tells the Visual Basic compiler to load the mscorlib.dll and Microsoft.VisualBasic.dll files from a non-default location.</span></span> <span data-ttu-id="ec86b-111">Параметр `-sdkpath` предназначен для использования с параметром [-netcf](netcf.md).</span><span class="sxs-lookup"><span data-stu-id="ec86b-111">The `-sdkpath` option was designed to be used with [-netcf](netcf.md).</span></span> <span data-ttu-id="ec86b-112">.NET Compact Framework использует разные версии этих библиотек поддержки, чтобы исключить использование типов и языковых компонентов, отсутствующих на устройствах.</span><span class="sxs-lookup"><span data-stu-id="ec86b-112">The .NET Compact Framework uses different versions of these support libraries to avoid the use of types and language features not found on the devices.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="ec86b-113">Параметр `-sdkpath` недоступен в среде разработки Visual Studio. Его можно использовать только при компиляции из командной строки.</span><span class="sxs-lookup"><span data-stu-id="ec86b-113">The `-sdkpath` option is not available from within the Visual Studio development environment; it is available only when compiling from the command line.</span></span> <span data-ttu-id="ec86b-114">Параметр `-sdkpath` задается, когда загружается проект устройства Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="ec86b-114">The `-sdkpath` option is set when a Visual Basic device project is loaded.</span></span>  
  
 <span data-ttu-id="ec86b-115">С помощью параметра `-vbruntime` можно указать, что компилятор должен выполнять компиляцию без обращения к библиотеке времени выполнения Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="ec86b-115">You can specify that the compiler should compile without a reference to the Visual Basic Runtime Library by using the `-vbruntime` compiler option.</span></span> <span data-ttu-id="ec86b-116">Дополнительные сведения см. в описании параметра [-vbruntime](vbruntime.md).</span><span class="sxs-lookup"><span data-stu-id="ec86b-116">For more information, see [-vbruntime](vbruntime.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="ec86b-117">Пример</span><span class="sxs-lookup"><span data-stu-id="ec86b-117">Example</span></span>  
 <span data-ttu-id="ec86b-118">В следующем примере кода выполняется компиляция `Myfile.vb` в .NET Compact Framework с использованием версий библиотек Mscorlib.dll и Microsoft.VisualBasic.dll, которые находятся в каталоге установки .NET Compact Framework по умолчанию на диске C.</span><span class="sxs-lookup"><span data-stu-id="ec86b-118">The following code compiles `Myfile.vb` with the .NET Compact Framework, using the versions of Mscorlib.dll and Microsoft.VisualBasic.dll found in the default installation directory of the .NET Compact Framework on the C drive.</span></span> <span data-ttu-id="ec86b-119">Как правило, следует использовать самую последнюю версию .NET Compact Framework.</span><span class="sxs-lookup"><span data-stu-id="ec86b-119">Typically, you would use the most recent version of the .NET Compact Framework.</span></span>  
  
```console
vbc -netcf -sdkpath:"c:\Program Files\Microsoft Visual Studio .NET 2003\CompactFrameworkSDK\v1.0.5000\Windows CE " myfile.vb  
```  
  
## <a name="see-also"></a><span data-ttu-id="ec86b-120">См. также</span><span class="sxs-lookup"><span data-stu-id="ec86b-120">See also</span></span>

- [<span data-ttu-id="ec86b-121">Компилятор Visual Basic с интерфейсом командной строки</span><span class="sxs-lookup"><span data-stu-id="ec86b-121">Visual Basic Command-Line Compiler</span></span>](index.md)
- [<span data-ttu-id="ec86b-122">Примеры командных строк компиляции</span><span class="sxs-lookup"><span data-stu-id="ec86b-122">Sample Compilation Command Lines</span></span>](sample-compilation-command-lines.md)
- [<span data-ttu-id="ec86b-123">-netcf</span><span class="sxs-lookup"><span data-stu-id="ec86b-123">-netcf</span></span>](netcf.md)
- [<span data-ttu-id="ec86b-124">-vbruntime</span><span class="sxs-lookup"><span data-stu-id="ec86b-124">-vbruntime</span></span>](vbruntime.md)
