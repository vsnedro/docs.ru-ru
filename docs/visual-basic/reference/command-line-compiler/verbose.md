---
title: -verbose
ms.date: 03/13/2018
helpviewer_keywords:
- verbose compiler option [Visual Basic]
- -verbose compiler option [Visual Basic]
- /verbose compiler option [Visual Basic]
ms.assetid: d1aec0c1-0261-421d-9adc-5b13756100be
ms.openlocfilehash: 405b557568a736de3ddc3b51e265261222613131
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/04/2020
ms.locfileid: "84403035"
---
# <a name="-verbose"></a><span data-ttu-id="7d4a0-102">-verbose</span><span class="sxs-lookup"><span data-stu-id="7d4a0-102">-verbose</span></span>
<span data-ttu-id="7d4a0-103">Заставляет компилятор выдавать подробные сообщения о состоянии и ошибках.</span><span class="sxs-lookup"><span data-stu-id="7d4a0-103">Causes the compiler to produce verbose status and error messages.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7d4a0-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="7d4a0-104">Syntax</span></span>  
  
```console  
-verbose[+ | -]  
```  
  
## <a name="arguments"></a><span data-ttu-id="7d4a0-105">Аргументы</span><span class="sxs-lookup"><span data-stu-id="7d4a0-105">Arguments</span></span>  
 <span data-ttu-id="7d4a0-106">`+` &#124; `-`</span><span class="sxs-lookup"><span data-stu-id="7d4a0-106">`+` &#124; `-`</span></span>  
 <span data-ttu-id="7d4a0-107">Необязательный элемент.</span><span class="sxs-lookup"><span data-stu-id="7d4a0-107">Optional.</span></span> <span data-ttu-id="7d4a0-108">Указание `-verbose` аналогично указанию `-verbose+` и приводит к тому, что компилятор выдает подробные сообщения.</span><span class="sxs-lookup"><span data-stu-id="7d4a0-108">Specifying `-verbose` is the same as specifying `-verbose+`, which causes the compiler to emit verbose messages.</span></span> <span data-ttu-id="7d4a0-109">Значение этого параметра по умолчанию равно `-verbose-`.</span><span class="sxs-lookup"><span data-stu-id="7d4a0-109">The default for this option is `-verbose-`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="7d4a0-110">Примечания</span><span class="sxs-lookup"><span data-stu-id="7d4a0-110">Remarks</span></span>  
 <span data-ttu-id="7d4a0-111">Параметр `-verbose` отображает сведения об общем количестве ошибок, выданных компилятором, сообщает о том, какие сборки загружаются модулем, и показывает, какие файлы в данный момент компилируются.</span><span class="sxs-lookup"><span data-stu-id="7d4a0-111">The `-verbose` option displays information about the total number of errors issued by the compiler, reports which assemblies are being loaded by a module, and displays which files are currently being compiled.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="7d4a0-112">Параметр `-verbose` недоступен в среде разработки Visual Studio. Его можно использовать только при компиляции из командной строки.</span><span class="sxs-lookup"><span data-stu-id="7d4a0-112">The `-verbose` option is not available from within the Visual Studio development environment; it is available only when compiling from the command line.</span></span>  
  
## <a name="example"></a><span data-ttu-id="7d4a0-113">Пример</span><span class="sxs-lookup"><span data-stu-id="7d4a0-113">Example</span></span>  
 <span data-ttu-id="7d4a0-114">Следующий код компилирует `In.vb` и предписывает компилятору отображать подробные сведения о состоянии.</span><span class="sxs-lookup"><span data-stu-id="7d4a0-114">The following code compiles `In.vb` and directs the compiler to display verbose status information.</span></span>  
  
```console  
vbc -verbose in.vb  
```  
  
## <a name="see-also"></a><span data-ttu-id="7d4a0-115">См. также</span><span class="sxs-lookup"><span data-stu-id="7d4a0-115">See also</span></span>

- [<span data-ttu-id="7d4a0-116">Компилятор Visual Basic с интерфейсом командной строки</span><span class="sxs-lookup"><span data-stu-id="7d4a0-116">Visual Basic Command-Line Compiler</span></span>](index.md)
- [<span data-ttu-id="7d4a0-117">Примеры командных строк компиляции</span><span class="sxs-lookup"><span data-stu-id="7d4a0-117">Sample Compilation Command Lines</span></span>](sample-compilation-command-lines.md)
