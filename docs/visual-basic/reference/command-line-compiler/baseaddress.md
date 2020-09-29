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
ms.openlocfilehash: c794d1fc1c9d20e22ffa747e3175c846341ad8ad
ms.sourcegitcommit: bf5c5850654187705bc94cc40ebfb62fe346ab02
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/23/2020
ms.locfileid: "91097765"
---
# <a name="-baseaddress"></a><span data-ttu-id="ca851-102">-baseaddress</span><span class="sxs-lookup"><span data-stu-id="ca851-102">-baseaddress</span></span>

<span data-ttu-id="ca851-103">Определяет базовый адрес по умолчанию при создании библиотеки DLL.</span><span class="sxs-lookup"><span data-stu-id="ca851-103">Specifies a default base address when creating a DLL.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ca851-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="ca851-104">Syntax</span></span>  
  
```console  
-baseaddress:address  
```  
  
## <a name="arguments"></a><span data-ttu-id="ca851-105">Аргументы</span><span class="sxs-lookup"><span data-stu-id="ca851-105">Arguments</span></span>  
  
|<span data-ttu-id="ca851-106">Термин</span><span class="sxs-lookup"><span data-stu-id="ca851-106">Term</span></span>|<span data-ttu-id="ca851-107">Определение</span><span class="sxs-lookup"><span data-stu-id="ca851-107">Definition</span></span>|  
|---|---|  
|`address`|<span data-ttu-id="ca851-108">Обязательный.</span><span class="sxs-lookup"><span data-stu-id="ca851-108">Required.</span></span> <span data-ttu-id="ca851-109">Базовый адрес для библиотеки DLL.</span><span class="sxs-lookup"><span data-stu-id="ca851-109">The base address for the DLL.</span></span> <span data-ttu-id="ca851-110">Этот адрес можно определить как десятичное, шестнадцатеричное или восьмеричное число.</span><span class="sxs-lookup"><span data-stu-id="ca851-110">This address must be specified as a hexadecimal number.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="ca851-111">Примечания</span><span class="sxs-lookup"><span data-stu-id="ca851-111">Remarks</span></span>  

 <span data-ttu-id="ca851-112">Базовый адрес по умолчанию для библиотеки DLL задается платформой .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="ca851-112">The default base address for a DLL is set by the .NET Framework.</span></span>  
  
 <span data-ttu-id="ca851-113">Обратите внимание, что младшее слово этого адреса будет округляться.</span><span class="sxs-lookup"><span data-stu-id="ca851-113">Be aware that the lower-order word in this address is rounded.</span></span> <span data-ttu-id="ca851-114">Например, значение 0x11110001 округляется до 0x11110000.</span><span class="sxs-lookup"><span data-stu-id="ca851-114">For example, if you specify 0x11110001, it is rounded to 0x11110000.</span></span>  
  
 <span data-ttu-id="ca851-115">Чтобы завершить процесс подписи для библиотеки DLL, используйте параметр `–R` средства Strong Name (Sn.exe).</span><span class="sxs-lookup"><span data-stu-id="ca851-115">To complete the signing process for a DLL, use the `–R` option of the Strong Naming tool (Sn.exe).</span></span>  
  
 <span data-ttu-id="ca851-116">Этот параметр не учитывается, если целевой объект не является библиотекой DLL.</span><span class="sxs-lookup"><span data-stu-id="ca851-116">This option is ignored if the target is not a DLL.</span></span>  
  
|<span data-ttu-id="ca851-117">Чтобы задать параметр -baseaddress в Visual Studio IDE, сделайте следующее:</span><span class="sxs-lookup"><span data-stu-id="ca851-117">To set -baseaddress in the Visual Studio IDE</span></span>|  
|---|  
|<span data-ttu-id="ca851-118">1.  Выберите проект в **Обозревателе решений**.</span><span class="sxs-lookup"><span data-stu-id="ca851-118">1.  Have a project selected in **Solution Explorer**.</span></span> <span data-ttu-id="ca851-119">В меню **Проект** выберите пункт **Свойства**.</span><span class="sxs-lookup"><span data-stu-id="ca851-119">On the **Project** menu, click **Properties**.</span></span> <br /><span data-ttu-id="ca851-120">2.  Откройте вкладку **Компиляция**.</span><span class="sxs-lookup"><span data-stu-id="ca851-120">2.  Click the **Compile** tab.</span></span><br /><span data-ttu-id="ca851-121">3.  Нажмите кнопку **Дополнительно**.</span><span class="sxs-lookup"><span data-stu-id="ca851-121">3.  Click **Advanced**.</span></span><br /><span data-ttu-id="ca851-122">4.  Измените значение в поле **Базовый адрес DLL**.</span><span class="sxs-lookup"><span data-stu-id="ca851-122">4.  Modify the value in the **DLL base address:** box.</span></span> <span data-ttu-id="ca851-123">**Примечание.**      Поле **Базовый адрес DLL** доступно только для чтения, если целевой объект не является библиотекой DLL.</span><span class="sxs-lookup"><span data-stu-id="ca851-123">**Note:**      The **DLL base address:** box is read-only unless the target is a DLL.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="ca851-124">См. также</span><span class="sxs-lookup"><span data-stu-id="ca851-124">See also</span></span>

- [<span data-ttu-id="ca851-125">Компилятор Visual Basic с интерфейсом командной строки</span><span class="sxs-lookup"><span data-stu-id="ca851-125">Visual Basic Command-Line Compiler</span></span>](index.md)
- [<span data-ttu-id="ca851-126">-target (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="ca851-126">-target (Visual Basic)</span></span>](target.md)
- [<span data-ttu-id="ca851-127">Примеры командных строк компиляции</span><span class="sxs-lookup"><span data-stu-id="ca851-127">Sample Compilation Command Lines</span></span>](sample-compilation-command-lines.md)
- <span data-ttu-id="ca851-128">[Sn.exe (средство Strong Name)](../../../framework/tools/sn-exe-strong-name-tool.md))</span><span class="sxs-lookup"><span data-stu-id="ca851-128">[Sn.exe (Strong Name Tool)](../../../framework/tools/sn-exe-strong-name-tool.md))</span></span>
