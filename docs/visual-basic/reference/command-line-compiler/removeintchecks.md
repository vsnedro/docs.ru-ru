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
ms.openlocfilehash: ec4722cb7088819dae95ca1b7cbc1469d957a7aa
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/04/2020
ms.locfileid: "84400478"
---
# <a name="-removeintchecks"></a><span data-ttu-id="c4142-102">-removeintchecks</span><span class="sxs-lookup"><span data-stu-id="c4142-102">-removeintchecks</span></span>
<span data-ttu-id="c4142-103">Включает и отключает проверку условий переполнения для целочисленных операций.</span><span class="sxs-lookup"><span data-stu-id="c4142-103">Turns overflow-error checking for integer operations on or off.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c4142-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="c4142-104">Syntax</span></span>  
  
```console  
-removeintchecks[+ | -]  
```  
  
## <a name="arguments"></a><span data-ttu-id="c4142-105">Аргументы</span><span class="sxs-lookup"><span data-stu-id="c4142-105">Arguments</span></span>  
  
|<span data-ttu-id="c4142-106">Термин</span><span class="sxs-lookup"><span data-stu-id="c4142-106">Term</span></span>|<span data-ttu-id="c4142-107">Определение</span><span class="sxs-lookup"><span data-stu-id="c4142-107">Definition</span></span>|  
|---|---|  
|<span data-ttu-id="c4142-108">`+` &#124; `-`</span><span class="sxs-lookup"><span data-stu-id="c4142-108">`+` &#124; `-`</span></span>|<span data-ttu-id="c4142-109">Необязательный элемент.</span><span class="sxs-lookup"><span data-stu-id="c4142-109">Optional.</span></span> <span data-ttu-id="c4142-110">Если задан параметр `-removeintchecks-`, компилятор проверяет условия переполнения всех целочисленных операций.</span><span class="sxs-lookup"><span data-stu-id="c4142-110">The `-removeintchecks-` option causes the compiler to check all integer calculations for overflow errors.</span></span> <span data-ttu-id="c4142-111">Значение по умолчанию — `-removeintchecks-`.</span><span class="sxs-lookup"><span data-stu-id="c4142-111">The default is `-removeintchecks-`.</span></span><br /><br /> <span data-ttu-id="c4142-112">Если задано `-removeintchecks` или `-removeintchecks+`, переполнение не проверяется и целочисленные вычисления выполняются быстрее.</span><span class="sxs-lookup"><span data-stu-id="c4142-112">Specifying `-removeintchecks` or `-removeintchecks+` prevents error checking and can make integer calculations faster.</span></span> <span data-ttu-id="c4142-113">Однако в случае переполнения типа данных при отключенной проверке переполнения могут сохраниться неверные результаты без отображения ошибки.</span><span class="sxs-lookup"><span data-stu-id="c4142-113">However, without error checking, and if data type capacities are overflowed, incorrect results may be stored without raising an error.</span></span>|  
  
|<span data-ttu-id="c4142-114">Задание параметра -removeintchecks в интегрированной среде разработки Visual Studio</span><span class="sxs-lookup"><span data-stu-id="c4142-114">To set -removeintchecks in the Visual Studio integrated development environment</span></span>|  
|---|  
|<span data-ttu-id="c4142-115">1.  Выберите проект в **Обозревателе решений**.</span><span class="sxs-lookup"><span data-stu-id="c4142-115">1.  Have a project selected in **Solution Explorer**.</span></span> <span data-ttu-id="c4142-116">В меню **Проект** выберите пункт **Свойства**.</span><span class="sxs-lookup"><span data-stu-id="c4142-116">On the **Project** menu, click **Properties**.</span></span> <br /><span data-ttu-id="c4142-117">2.  Откройте вкладку **Компиляция**.</span><span class="sxs-lookup"><span data-stu-id="c4142-117">2.  Click the **Compile** tab.</span></span><br /><span data-ttu-id="c4142-118">3.  Нажмите кнопку **Дополнительно** .</span><span class="sxs-lookup"><span data-stu-id="c4142-118">3.  Click the **Advanced** button.</span></span><br /><span data-ttu-id="c4142-119">4.  Установите флажок **Отключить проверку переполнения для целочисленных значений**.</span><span class="sxs-lookup"><span data-stu-id="c4142-119">4.  Modify the value of the **Remove integer overflow checks** box.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="c4142-120">Пример</span><span class="sxs-lookup"><span data-stu-id="c4142-120">Example</span></span>  
 <span data-ttu-id="c4142-121">Следующий код компилирует `Test.vb` и отключает проверку переполнения целочисленных значений.</span><span class="sxs-lookup"><span data-stu-id="c4142-121">The following code compiles `Test.vb` and turns off integer overflow-error checking.</span></span>  
  
```console
vbc -removeintchecks+ test.vb  
```  
  
## <a name="see-also"></a><span data-ttu-id="c4142-122">См. также</span><span class="sxs-lookup"><span data-stu-id="c4142-122">See also</span></span>

- [<span data-ttu-id="c4142-123">Компилятор Visual Basic с интерфейсом командной строки</span><span class="sxs-lookup"><span data-stu-id="c4142-123">Visual Basic Command-Line Compiler</span></span>](index.md)
- [<span data-ttu-id="c4142-124">Примеры командных строк компиляции</span><span class="sxs-lookup"><span data-stu-id="c4142-124">Sample Compilation Command Lines</span></span>](sample-compilation-command-lines.md)
