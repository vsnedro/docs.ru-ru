---
title: -baseaddress
ms.date: 08/09/2018
f1_keywords:
- /baseaddress
- baseaddress
helpviewer_keywords:
- -baseaddress compiler option [Visual Basic]
- /baseaddress compiler option [Visual Basic]
- baseaddress compiler option [Visual Basic]
ms.assetid: c982bcf2-46e5-47a2-bc8f-a5cc32b7dc47
ms.openlocfilehash: 6ee842dbe65cbd9d147e77ec523a2b031d303738
ms.sourcegitcommit: eff6adb61852369ab690f3f047818c90580e7eb1
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/07/2019
ms.locfileid: "72002385"
---
# <a name="-baseaddress"></a><span data-ttu-id="e04bd-102">-baseaddress</span><span class="sxs-lookup"><span data-stu-id="e04bd-102">-baseaddress</span></span>
<span data-ttu-id="e04bd-103">Определяет базовый адрес по умолчанию при создании библиотеки DLL.</span><span class="sxs-lookup"><span data-stu-id="e04bd-103">Specifies a default base address when creating a DLL.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e04bd-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="e04bd-104">Syntax</span></span>  
  
```console  
-baseaddress:address  
```  
  
## <a name="arguments"></a><span data-ttu-id="e04bd-105">Аргументы</span><span class="sxs-lookup"><span data-stu-id="e04bd-105">Arguments</span></span>  
  
|<span data-ttu-id="e04bd-106">Термин</span><span class="sxs-lookup"><span data-stu-id="e04bd-106">Term</span></span>|<span data-ttu-id="e04bd-107">Определение</span><span class="sxs-lookup"><span data-stu-id="e04bd-107">Definition</span></span>|  
|---|---|  
|`address`|<span data-ttu-id="e04bd-108">Обязательный.</span><span class="sxs-lookup"><span data-stu-id="e04bd-108">Required.</span></span> <span data-ttu-id="e04bd-109">Базовый адрес для библиотеки DLL.</span><span class="sxs-lookup"><span data-stu-id="e04bd-109">The base address for the DLL.</span></span> <span data-ttu-id="e04bd-110">Этот адрес можно определить как десятичное, шестнадцатеричное или восьмеричное число.</span><span class="sxs-lookup"><span data-stu-id="e04bd-110">This address must be specified as a hexadecimal number.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="e04bd-111">Примечания</span><span class="sxs-lookup"><span data-stu-id="e04bd-111">Remarks</span></span>  
 <span data-ttu-id="e04bd-112">Базовый адрес по умолчанию для библиотеки DLL задается платформой .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="e04bd-112">The default base address for a DLL is set by the .NET Framework.</span></span>  
  
 <span data-ttu-id="e04bd-113">Обратите внимание, что младшее слово этого адреса будет округляться.</span><span class="sxs-lookup"><span data-stu-id="e04bd-113">Be aware that the lower-order word in this address is rounded.</span></span> <span data-ttu-id="e04bd-114">Например, значение 0x11110001 округляется до 0x11110000.</span><span class="sxs-lookup"><span data-stu-id="e04bd-114">For example, if you specify 0x11110001, it is rounded to 0x11110000.</span></span>  
  
 <span data-ttu-id="e04bd-115">Чтобы завершить процесс подписи для библиотеки DLL, используйте параметр `–R` средства Strong Name (Sn.exe).</span><span class="sxs-lookup"><span data-stu-id="e04bd-115">To complete the signing process for a DLL, use the `–R` option of the Strong Naming tool (Sn.exe).</span></span>  
  
 <span data-ttu-id="e04bd-116">Этот параметр не учитывается, если целевой объект не является библиотекой DLL.</span><span class="sxs-lookup"><span data-stu-id="e04bd-116">This option is ignored if the target is not a DLL.</span></span>  
  
|<span data-ttu-id="e04bd-117">Чтобы задать параметр -baseaddress в Visual Studio IDE, сделайте следующее:</span><span class="sxs-lookup"><span data-stu-id="e04bd-117">To set -baseaddress in the Visual Studio IDE</span></span>|  
|---|  
|<span data-ttu-id="e04bd-118">1.  Выберите проект в **Обозревателе решений**.</span><span class="sxs-lookup"><span data-stu-id="e04bd-118">1.  Have a project selected in **Solution Explorer**.</span></span> <span data-ttu-id="e04bd-119">В меню **Проект** выберите пункт **Свойства**.</span><span class="sxs-lookup"><span data-stu-id="e04bd-119">On the **Project** menu, click **Properties**.</span></span> <br /><span data-ttu-id="e04bd-120">2.  Откройте вкладку **Компиляция**.</span><span class="sxs-lookup"><span data-stu-id="e04bd-120">2.  Click the **Compile** tab.</span></span><br /><span data-ttu-id="e04bd-121">3.  Нажмите кнопку **Дополнительно**.</span><span class="sxs-lookup"><span data-stu-id="e04bd-121">3.  Click **Advanced**.</span></span><br /><span data-ttu-id="e04bd-122">4.  Измените значение в поле **Базовый адрес DLL**.</span><span class="sxs-lookup"><span data-stu-id="e04bd-122">4.  Modify the value in the **DLL base address:** box.</span></span> <span data-ttu-id="e04bd-123">**Примечание.**      Поле **Базовый адрес DLL** доступно только для чтения, если целевой объект не является библиотекой DLL.</span><span class="sxs-lookup"><span data-stu-id="e04bd-123">**Note:**      The **DLL base address:** box is read-only unless the target is a DLL.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="e04bd-124">См. также</span><span class="sxs-lookup"><span data-stu-id="e04bd-124">See also</span></span>

- [<span data-ttu-id="e04bd-125">Компилятор Visual Basic с интерфейсом командной строки</span><span class="sxs-lookup"><span data-stu-id="e04bd-125">Visual Basic Command-Line Compiler</span></span>](../../../visual-basic/reference/command-line-compiler/index.md)
- [<span data-ttu-id="e04bd-126">-target (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="e04bd-126">-target (Visual Basic)</span></span>](../../../visual-basic/reference/command-line-compiler/target.md)
- [<span data-ttu-id="e04bd-127">Примеры командных строк компиляции</span><span class="sxs-lookup"><span data-stu-id="e04bd-127">Sample Compilation Command Lines</span></span>](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)
- <span data-ttu-id="e04bd-128">[Sn.exe (средство Strong Name)](../../../framework/tools/sn-exe-strong-name-tool.md))</span><span class="sxs-lookup"><span data-stu-id="e04bd-128">[Sn.exe (Strong Name Tool)](../../../framework/tools/sn-exe-strong-name-tool.md))</span></span>
