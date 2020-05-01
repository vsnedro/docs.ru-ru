---
title: -removeintchecks
ms.date: 03/13/2018
f1_keywords:
- removeintchecks
- -removeintchecks
helpviewer_keywords:
- removeintchecks compiler option [Visual Basic]
- /removeintchecks compiler option [Visual Basic]
- -removeintchecks compiler option [Visual Basic]
ms.assetid: c1835bd5-1e38-4fba-bd2f-6984774765d4
ms.openlocfilehash: bea6ca24ea6da9000267e754d52fe0ca152f7d7f
ms.sourcegitcommit: eff6adb61852369ab690f3f047818c90580e7eb1
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/07/2019
ms.locfileid: "72005226"
---
# <a name="-removeintchecks"></a><span data-ttu-id="1ca54-102">-removeintchecks</span><span class="sxs-lookup"><span data-stu-id="1ca54-102">-removeintchecks</span></span>
<span data-ttu-id="1ca54-103">Включает и отключает проверку условий переполнения для целочисленных операций.</span><span class="sxs-lookup"><span data-stu-id="1ca54-103">Turns overflow-error checking for integer operations on or off.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1ca54-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="1ca54-104">Syntax</span></span>  
  
```console  
-removeintchecks[+ | -]  
```  
  
## <a name="arguments"></a><span data-ttu-id="1ca54-105">Аргументы</span><span class="sxs-lookup"><span data-stu-id="1ca54-105">Arguments</span></span>  
  
|<span data-ttu-id="1ca54-106">Термин</span><span class="sxs-lookup"><span data-stu-id="1ca54-106">Term</span></span>|<span data-ttu-id="1ca54-107">Определение</span><span class="sxs-lookup"><span data-stu-id="1ca54-107">Definition</span></span>|  
|---|---|  
|<span data-ttu-id="1ca54-108">`+` &#124; `-`</span><span class="sxs-lookup"><span data-stu-id="1ca54-108">`+` &#124; `-`</span></span>|<span data-ttu-id="1ca54-109">Необязательный элемент.</span><span class="sxs-lookup"><span data-stu-id="1ca54-109">Optional.</span></span> <span data-ttu-id="1ca54-110">Если задан параметр `-removeintchecks-`, компилятор проверяет условия переполнения всех целочисленных операций.</span><span class="sxs-lookup"><span data-stu-id="1ca54-110">The `-removeintchecks-` option causes the compiler to check all integer calculations for overflow errors.</span></span> <span data-ttu-id="1ca54-111">Значение по умолчанию — `-removeintchecks-`.</span><span class="sxs-lookup"><span data-stu-id="1ca54-111">The default is `-removeintchecks-`.</span></span><br /><br /> <span data-ttu-id="1ca54-112">Если задано `-removeintchecks` или `-removeintchecks+`, переполнение не проверяется и целочисленные вычисления выполняются быстрее.</span><span class="sxs-lookup"><span data-stu-id="1ca54-112">Specifying `-removeintchecks` or `-removeintchecks+` prevents error checking and can make integer calculations faster.</span></span> <span data-ttu-id="1ca54-113">Однако в случае переполнения типа данных при отключенной проверке переполнения могут сохраниться неверные результаты без отображения ошибки.</span><span class="sxs-lookup"><span data-stu-id="1ca54-113">However, without error checking, and if data type capacities are overflowed, incorrect results may be stored without raising an error.</span></span>|  
  
|<span data-ttu-id="1ca54-114">Задание параметра -removeintchecks в интегрированной среде разработки Visual Studio</span><span class="sxs-lookup"><span data-stu-id="1ca54-114">To set -removeintchecks in the Visual Studio integrated development environment</span></span>|  
|---|  
|<span data-ttu-id="1ca54-115">1.  Выберите проект в **Обозревателе решений**.</span><span class="sxs-lookup"><span data-stu-id="1ca54-115">1.  Have a project selected in **Solution Explorer**.</span></span> <span data-ttu-id="1ca54-116">В меню **Проект** выберите пункт **Свойства**.</span><span class="sxs-lookup"><span data-stu-id="1ca54-116">On the **Project** menu, click **Properties**.</span></span> <br /><span data-ttu-id="1ca54-117">2.  Откройте вкладку **Компиляция**.</span><span class="sxs-lookup"><span data-stu-id="1ca54-117">2.  Click the **Compile** tab.</span></span><br /><span data-ttu-id="1ca54-118">3.  Нажмите кнопку **Дополнительно** .</span><span class="sxs-lookup"><span data-stu-id="1ca54-118">3.  Click the **Advanced** button.</span></span><br /><span data-ttu-id="1ca54-119">4.  Установите флажок **Отключить проверку переполнения для целочисленных значений**.</span><span class="sxs-lookup"><span data-stu-id="1ca54-119">4.  Modify the value of the **Remove integer overflow checks** box.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="1ca54-120">Пример</span><span class="sxs-lookup"><span data-stu-id="1ca54-120">Example</span></span>  
 <span data-ttu-id="1ca54-121">Следующий код компилирует `Test.vb` и отключает проверку переполнения целочисленных значений.</span><span class="sxs-lookup"><span data-stu-id="1ca54-121">The following code compiles `Test.vb` and turns off integer overflow-error checking.</span></span>  
  
```console
vbc -removeintchecks+ test.vb  
```  
  
## <a name="see-also"></a><span data-ttu-id="1ca54-122">См. также</span><span class="sxs-lookup"><span data-stu-id="1ca54-122">See also</span></span>

- [<span data-ttu-id="1ca54-123">Компилятор Visual Basic с интерфейсом командной строки</span><span class="sxs-lookup"><span data-stu-id="1ca54-123">Visual Basic Command-Line Compiler</span></span>](../../../visual-basic/reference/command-line-compiler/index.md)
- [<span data-ttu-id="1ca54-124">Примеры командных строк компиляции</span><span class="sxs-lookup"><span data-stu-id="1ca54-124">Sample Compilation Command Lines</span></span>](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)
