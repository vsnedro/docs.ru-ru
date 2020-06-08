---
title: -highentropyva
ms.date: 03/10/2018
helpviewer_keywords:
- highentropyva compiler option (Visual Basic)
- /highentropyva compiler option (Visual Basic)
ms.assetid: ff25f20a-6ca2-467b-9e52-5cf439f5028e
ms.openlocfilehash: 9501ea46eb13baa171208e20d0c9645d118c4301
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/04/2020
ms.locfileid: "84408625"
---
# <a name="-highentropyva-visual-basic"></a><span data-ttu-id="1af71-102">-highentropyva (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="1af71-102">-highentropyva (Visual Basic)</span></span>
<span data-ttu-id="1af71-103">Указывает, что 64-разрядный исполняемый файл или исполняемый файл, отмеченный параметром компилятора [-platform:anycpu](platform.md), поддерживает технологию Address Space Layout Randomization (ASLR) с высокой энтропией.</span><span class="sxs-lookup"><span data-stu-id="1af71-103">Indicates whether a 64-bit executable or an executable that's marked by the [-platform:anycpu](platform.md) compiler option supports high entropy Address Space Layout Randomization (ASLR).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1af71-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="1af71-104">Syntax</span></span>  
  
```console  
-highentropyva[+ | -]  
```  
  
## <a name="arguments"></a><span data-ttu-id="1af71-105">Аргументы</span><span class="sxs-lookup"><span data-stu-id="1af71-105">Arguments</span></span>  
 <span data-ttu-id="1af71-106">`+` &#124; `-`</span><span class="sxs-lookup"><span data-stu-id="1af71-106">`+` &#124; `-`</span></span>  
 <span data-ttu-id="1af71-107">Необязательный элемент.</span><span class="sxs-lookup"><span data-stu-id="1af71-107">Optional.</span></span> <span data-ttu-id="1af71-108">Этот параметр выключен по умолчанию или если вы указываете `-highentropyva-`.</span><span class="sxs-lookup"><span data-stu-id="1af71-108">The option is off by default or if you specify `-highentropyva-`.</span></span> <span data-ttu-id="1af71-109">Параметр включен, если вы указываете `-highentropyva` или `-highentropyva+`.</span><span class="sxs-lookup"><span data-stu-id="1af71-109">The option is on if you specify `-highentropyva` or `-highentropyva+`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="1af71-110">Примечания</span><span class="sxs-lookup"><span data-stu-id="1af71-110">Remarks</span></span>  
 <span data-ttu-id="1af71-111">Если этот параметр указан, совместимые версии ядра Windows могут использовать более высокие степени энтропии, когда ядро вносит элемент случайности в структуру адресного пространства процесса в рамках ASLR.</span><span class="sxs-lookup"><span data-stu-id="1af71-111">If you specify this option, compatible versions of the Windows kernel can use higher degrees of entropy when the kernel randomizes the address space layout of a process as part of ASLR.</span></span> <span data-ttu-id="1af71-112">Если ядро использует более высокие степени энтропии, можно выделить больше адресов таким областям памяти, как стеки и кучи.</span><span class="sxs-lookup"><span data-stu-id="1af71-112">If the kernel uses higher degrees of entropy, a larger number of addresses can be allocated to memory regions such as stacks and heaps.</span></span> <span data-ttu-id="1af71-113">Из-за этого сложнее подобрать расположение определенной области памяти.</span><span class="sxs-lookup"><span data-stu-id="1af71-113">As a result, it is more difficult to guess the location of a particular memory region.</span></span>  
  
 <span data-ttu-id="1af71-114">Если этот параметр включен, целевой исполняемый файл и все модули, от которых он зависит, должны быть способны обработать значения указателя, размер которых превышает 4 гигабайта (ГБ), когда они выполняются как 64-разрядный процесс.</span><span class="sxs-lookup"><span data-stu-id="1af71-114">When the option is on, the target executable and any modules on which it depends must be able to handle pointer values that are larger than 4 gigabytes (GB) when those modules are running as 64-bit processes.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1af71-115">См. также</span><span class="sxs-lookup"><span data-stu-id="1af71-115">See also</span></span>

- [<span data-ttu-id="1af71-116">Компилятор Visual Basic с интерфейсом командной строки</span><span class="sxs-lookup"><span data-stu-id="1af71-116">Visual Basic Command-Line Compiler</span></span>](index.md)
- [<span data-ttu-id="1af71-117">Примеры командных строк компиляции</span><span class="sxs-lookup"><span data-stu-id="1af71-117">Sample Compilation Command Lines</span></span>](sample-compilation-command-lines.md)
