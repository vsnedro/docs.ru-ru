---
title: -noconfig
ms.date: 03/13/2018
helpviewer_keywords:
- noconfig compiler option [Visual Basic]
- -noconfig compiler option [Visual Basic]
- /noconfig compiler option [Visual Basic]
ms.assetid: a7405067-bd21-4171-adf4-a126fa3ad6c3
ms.openlocfilehash: c57ed1699d110959e9faf3dc3d43bcc200851c1c
ms.sourcegitcommit: eff6adb61852369ab690f3f047818c90580e7eb1
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/07/2019
ms.locfileid: "72005432"
---
# <a name="-noconfig"></a><span data-ttu-id="81596-102">-noconfig</span><span class="sxs-lookup"><span data-stu-id="81596-102">-noconfig</span></span>
<span data-ttu-id="81596-103">Указывает, что компилятор не должен автоматически ссылаться на часто используемые сборки .NET Framework и импортировать пространства имен `System` и `Microsoft.VisualBasic`.</span><span class="sxs-lookup"><span data-stu-id="81596-103">Specifies that the compiler should not automatically reference the commonly used .NET Framework assemblies or import the `System` and `Microsoft.VisualBasic` namespaces.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="81596-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="81596-104">Syntax</span></span>  
  
```console  
-noconfig  
```  
  
## <a name="remarks"></a><span data-ttu-id="81596-105">Примечания</span><span class="sxs-lookup"><span data-stu-id="81596-105">Remarks</span></span>  
 <span data-ttu-id="81596-106">Параметр `-noconfig` указывает компилятору не выполнять сборку с использованием файла Vbc.rsp, который располагается в том же каталоге, что и файл Vbc.exe.</span><span class="sxs-lookup"><span data-stu-id="81596-106">The `-noconfig` option tells the compiler not to compile with the Vbc.rsp file, which is located in the same directory as the Vbc.exe file.</span></span> <span data-ttu-id="81596-107">Файл Vbc.rsp ссылается на часто используемые сборки .NET Framework и импортирует пространства имен `System` и `Microsoft.VisualBasic`.</span><span class="sxs-lookup"><span data-stu-id="81596-107">The Vbc.rsp file references the commonly used .NET Framework assemblies and imports the `System` and `Microsoft.VisualBasic` namespaces.</span></span> <span data-ttu-id="81596-108">Компилятор неявно ссылается на сборку System.dll, если не указан параметр `-nostdlib`.</span><span class="sxs-lookup"><span data-stu-id="81596-108">The compiler implicitly references the System.dll assembly unless the `-nostdlib` option is specified.</span></span> <span data-ttu-id="81596-109">Параметр `-nostdlib` указывает компилятору не выполнять сборку с использованием файла Vbc.rsp и не ссылаться на сборку System.dll автоматически.</span><span class="sxs-lookup"><span data-stu-id="81596-109">The `-nostdlib` option tells the compiler not to compile with Vbc.rsp or automatically reference the System.dll assembly.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="81596-110">При этом компилятор всегда ссылается на сборки Mscorlib.dll и Microsoft.VisualBasic.dll.</span><span class="sxs-lookup"><span data-stu-id="81596-110">The Mscorlib.dll and Microsoft.VisualBasic.dll assemblies are always referenced.</span></span>  
  
 <span data-ttu-id="81596-111">Можно изменить файл Vbc.rsp, указав дополнительные параметры компилятора, которые должны включаться в каждую компиляцию Vbc.exe (за исключением случаев, когда указан параметр `-noconfig`).</span><span class="sxs-lookup"><span data-stu-id="81596-111">You can modify the Vbc.rsp file to specify additional compiler options that should be included in every Vbc.exe compilation (except when specifying the `-noconfig` option).</span></span> <span data-ttu-id="81596-112">Дополнительные сведения см. в документации синтаксиса [@ (указание файла ответа)](../../../visual-basic/reference/command-line-compiler/specify-response-file.md).</span><span class="sxs-lookup"><span data-stu-id="81596-112">For more information, see [@ (Specify Response File)](../../../visual-basic/reference/command-line-compiler/specify-response-file.md).</span></span>  
  
 <span data-ttu-id="81596-113">Компилятор обрабатывает параметры, передаваемые в команду `vbc`, последними.</span><span class="sxs-lookup"><span data-stu-id="81596-113">The compiler processes the options passed to the `vbc` command last.</span></span> <span data-ttu-id="81596-114">Таким образом, любой параметр командной строки переопределяет значение аналогичного параметра в файле Vbc.rsp.</span><span class="sxs-lookup"><span data-stu-id="81596-114">Therefore, any option on the command line overrides the setting of the same option in the Vbc.rsp file.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="81596-115">Параметр `-noconfig` недоступен в среде разработки Visual Studio. Его можно использовать только при компиляции из командной строки.</span><span class="sxs-lookup"><span data-stu-id="81596-115">The `-noconfig` option is not available from within the Visual Studio development environment; it is available only when compiling from the command line.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="81596-116">См. также</span><span class="sxs-lookup"><span data-stu-id="81596-116">See also</span></span>

- [<span data-ttu-id="81596-117">-nostdlib (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="81596-117">-nostdlib (Visual Basic)</span></span>](../../../visual-basic/reference/command-line-compiler/nostdlib.md)
- [<span data-ttu-id="81596-118">Компилятор Visual Basic с интерфейсом командной строки</span><span class="sxs-lookup"><span data-stu-id="81596-118">Visual Basic Command-Line Compiler</span></span>](../../../visual-basic/reference/command-line-compiler/index.md)
- [<span data-ttu-id="81596-119">@ (указание файла ответов)</span><span class="sxs-lookup"><span data-stu-id="81596-119">@ (Specify Response File)</span></span>](../../../visual-basic/reference/command-line-compiler/specify-response-file.md)
- [<span data-ttu-id="81596-120">-reference (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="81596-120">-reference (Visual Basic)</span></span>](../../../visual-basic/reference/command-line-compiler/reference.md)
