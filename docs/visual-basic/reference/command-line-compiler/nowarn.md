---
title: -nowarn
ms.date: 07/20/2015
helpviewer_keywords:
- nowarn compiler option [Visual Basic]
- /nowarn compiler option [Visual Basic]
- -nowarn compiler option [Visual Basic]
ms.assetid: 7ebf2106-0652-4fdc-bf60-70fc86465d83
ms.openlocfilehash: cde96fff975a65d6303ee62e6a811bfd83d5ff97
ms.sourcegitcommit: bf5c5850654187705bc94cc40ebfb62fe346ab02
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/23/2020
ms.locfileid: "91097687"
---
# <a name="-nowarn"></a><span data-ttu-id="6c052-102">-nowarn</span><span class="sxs-lookup"><span data-stu-id="6c052-102">-nowarn</span></span>

<span data-ttu-id="6c052-103">Отключает возможность компилятора создавать предупреждения.</span><span class="sxs-lookup"><span data-stu-id="6c052-103">Suppresses the compiler's ability to generate warnings.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6c052-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="6c052-104">Syntax</span></span>  
  
```console  
-nowarn[:numberList]  
```  
  
## <a name="arguments"></a><span data-ttu-id="6c052-105">Аргументы</span><span class="sxs-lookup"><span data-stu-id="6c052-105">Arguments</span></span>  
  
|<span data-ttu-id="6c052-106">Термин</span><span class="sxs-lookup"><span data-stu-id="6c052-106">Term</span></span>|<span data-ttu-id="6c052-107">Определение</span><span class="sxs-lookup"><span data-stu-id="6c052-107">Definition</span></span>|  
|---|---|  
|`numberList`|<span data-ttu-id="6c052-108">Необязательный элемент.</span><span class="sxs-lookup"><span data-stu-id="6c052-108">Optional.</span></span> <span data-ttu-id="6c052-109">Разделенный запятыми список с идентификаторами предупреждений, которые должен подавлять компилятор.</span><span class="sxs-lookup"><span data-stu-id="6c052-109">Comma-delimited list of the warning ID numbers that the compiler should suppress.</span></span> <span data-ttu-id="6c052-110">Если идентификаторы предупреждений не указаны, подавляются все предупреждения.</span><span class="sxs-lookup"><span data-stu-id="6c052-110">If the warning IDs are not specified, all warnings are suppressed.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="6c052-111">Примечания</span><span class="sxs-lookup"><span data-stu-id="6c052-111">Remarks</span></span>  

 <span data-ttu-id="6c052-112">Параметр `-nowarn` указывает компилятору не генерировать предупреждения.</span><span class="sxs-lookup"><span data-stu-id="6c052-112">The `-nowarn` option causes the compiler to not generate warnings.</span></span> <span data-ttu-id="6c052-113">Чтобы подавить отдельное предупреждение, укажите идентификатор предупреждения в параметре `-nowarn` после двоеточия.</span><span class="sxs-lookup"><span data-stu-id="6c052-113">To suppress an individual warning, supply the warning ID to the `-nowarn` option following the colon.</span></span> <span data-ttu-id="6c052-114">Можно указать несколько кодов предупреждений, разделяя их запятыми.</span><span class="sxs-lookup"><span data-stu-id="6c052-114">Separate multiple warning numbers with commas.</span></span>  
  
 <span data-ttu-id="6c052-115">Указывайте только числовую часть идентификатора предупреждения.</span><span class="sxs-lookup"><span data-stu-id="6c052-115">You need to specify only the numeric part of the warning identifier.</span></span> <span data-ttu-id="6c052-116">Например, если вы хотите подавить предупреждение BC42024, которое создается для неиспользуемых локальных переменных, укажите `-nowarn:42024`.</span><span class="sxs-lookup"><span data-stu-id="6c052-116">For example, if you want to suppress BC42024, the warning for unused local variables, specify `-nowarn:42024`.</span></span>  
  
 <span data-ttu-id="6c052-117">Дополнительные сведения о идентификаторах предупреждений см. в статье [Настройка предупреждений в Visual Basic](/visualstudio/ide/configuring-warnings-in-visual-basic).</span><span class="sxs-lookup"><span data-stu-id="6c052-117">For more information on the warning ID numbers, see [Configuring Warnings in Visual Basic](/visualstudio/ide/configuring-warnings-in-visual-basic).</span></span>  
  
|<span data-ttu-id="6c052-118">Задание параметра -nowarn в интегрированной среде разработки Visual Studio</span><span class="sxs-lookup"><span data-stu-id="6c052-118">To set -nowarn in the Visual Studio integrated development environment</span></span>|  
|---|  
|<span data-ttu-id="6c052-119">1.  Выберите проект в **Обозревателе решений**.</span><span class="sxs-lookup"><span data-stu-id="6c052-119">1.  Have a project selected in **Solution Explorer**.</span></span> <span data-ttu-id="6c052-120">В меню **Проект** выберите пункт **Свойства**.</span><span class="sxs-lookup"><span data-stu-id="6c052-120">On the **Project** menu, click **Properties**.</span></span> <br /><span data-ttu-id="6c052-121">2.  Откройте вкладку **Компиляция**.</span><span class="sxs-lookup"><span data-stu-id="6c052-121">2.  Click the **Compile** tab.</span></span><br /><span data-ttu-id="6c052-122">3.  Установите флажок **Выключить все предупреждения**, чтобы полностью отключить предупреждения.</span><span class="sxs-lookup"><span data-stu-id="6c052-122">3.  Select the **Disable all warnings** check box to disable all warnings.</span></span><br />     <span data-ttu-id="6c052-123">-или-</span><span class="sxs-lookup"><span data-stu-id="6c052-123">- or -</span></span><br />     <span data-ttu-id="6c052-124">Чтобы отключить конкретное предупреждение, выберите **Нет** из раскрывающегося списка рядом с предупреждением.</span><span class="sxs-lookup"><span data-stu-id="6c052-124">To disable a particular warning, click **None** from the drop-down list adjacent to the warning.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="6c052-125">Пример</span><span class="sxs-lookup"><span data-stu-id="6c052-125">Example</span></span>  

 <span data-ttu-id="6c052-126">Следующий код компилирует `T2.vb` и не отображает никаких предупреждений.</span><span class="sxs-lookup"><span data-stu-id="6c052-126">The following code compiles `T2.vb` and does not display any warnings.</span></span>  
  
```console
vbc -nowarn t2.vb  
```  
  
## <a name="example"></a><span data-ttu-id="6c052-127">Пример</span><span class="sxs-lookup"><span data-stu-id="6c052-127">Example</span></span>  

 <span data-ttu-id="6c052-128">Следующий код компилирует `T2.vb` и не отображает предупреждений о неиспользуемых локальных переменных (42024).</span><span class="sxs-lookup"><span data-stu-id="6c052-128">The following code compiles `T2.vb` and does not display the warnings for unused local variables (42024).</span></span>  
  
```console
vbc -nowarn:42024 t2.vb  
```  
  
## <a name="see-also"></a><span data-ttu-id="6c052-129">См. также</span><span class="sxs-lookup"><span data-stu-id="6c052-129">See also</span></span>

- [<span data-ttu-id="6c052-130">Компилятор Visual Basic с интерфейсом командной строки</span><span class="sxs-lookup"><span data-stu-id="6c052-130">Visual Basic Command-Line Compiler</span></span>](index.md)
- [<span data-ttu-id="6c052-131">Примеры командных строк компиляции</span><span class="sxs-lookup"><span data-stu-id="6c052-131">Sample Compilation Command Lines</span></span>](sample-compilation-command-lines.md)
- [<span data-ttu-id="6c052-132">Configuring Warnings in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="6c052-132">Configuring Warnings in Visual Basic</span></span>](/visualstudio/ide/configuring-warnings-in-visual-basic)
