---
title: -optimize
ms.date: 07/20/2015
helpviewer_keywords:
- optimize compiler option [Visual Basic]
- /optimize compiler option [Visual Basic]
- optimization [Visual Basic], enabling
- -optimize compiler option [Visual Basic]
ms.assetid: fcba4a97-3622-4b87-a891-0f77deab4998
ms.openlocfilehash: 337cb794ef9a405a178f1998cbe27b5da7709382
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/04/2020
ms.locfileid: "84397445"
---
# <a name="-optimize"></a><span data-ttu-id="24045-102">-optimize</span><span class="sxs-lookup"><span data-stu-id="24045-102">-optimize</span></span>
<span data-ttu-id="24045-103">Разрешает или запрещает оптимизацию компилятора.</span><span class="sxs-lookup"><span data-stu-id="24045-103">Enables or disables compiler optimizations.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="24045-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="24045-104">Syntax</span></span>  
  
```console  
-optimize[ + | - ]  
```  
  
## <a name="arguments"></a><span data-ttu-id="24045-105">Аргументы</span><span class="sxs-lookup"><span data-stu-id="24045-105">Arguments</span></span>  
  
|<span data-ttu-id="24045-106">Термин</span><span class="sxs-lookup"><span data-stu-id="24045-106">Term</span></span>|<span data-ttu-id="24045-107">Определение</span><span class="sxs-lookup"><span data-stu-id="24045-107">Definition</span></span>|  
|---|---|  
|<span data-ttu-id="24045-108">`+` &#124; `-`</span><span class="sxs-lookup"><span data-stu-id="24045-108">`+` &#124; `-`</span></span>|<span data-ttu-id="24045-109">Необязательный элемент.</span><span class="sxs-lookup"><span data-stu-id="24045-109">Optional.</span></span> <span data-ttu-id="24045-110">Параметр `-optimize-` запрещает оптимизацию компилятора.</span><span class="sxs-lookup"><span data-stu-id="24045-110">The `-optimize-` option disables compiler optimizations.</span></span> <span data-ttu-id="24045-111">Параметр `-optimize+` разрешает оптимизацию компилятора.</span><span class="sxs-lookup"><span data-stu-id="24045-111">The `-optimize+` option enables optimizations.</span></span> <span data-ttu-id="24045-112">По умолчанию оптимизация отключена.</span><span class="sxs-lookup"><span data-stu-id="24045-112">By default, optimizations are disabled.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="24045-113">Примечания</span><span class="sxs-lookup"><span data-stu-id="24045-113">Remarks</span></span>  
 <span data-ttu-id="24045-114">Оптимизации компилятора делают код более быстрым, коротким и эффективным.</span><span class="sxs-lookup"><span data-stu-id="24045-114">Compiler optimizations make your output file smaller, faster, and more efficient.</span></span> <span data-ttu-id="24045-115">Но поскольку оптимизация изменяет порядок строк кода в файле вывода, `-optimize+` может осложнить процесс отладки.</span><span class="sxs-lookup"><span data-stu-id="24045-115">However, because optimizations result in code rearrangement in the output file, `-optimize+` can make debugging difficult.</span></span>  
  
 <span data-ttu-id="24045-116">Все модули, созданные с помощью `-target:module` для сборки, должны использовать те же параметры `-optimize`, что и сборка.</span><span class="sxs-lookup"><span data-stu-id="24045-116">All modules generated with `-target:module` for an assembly must use the same `-optimize` settings as the assembly.</span></span> <span data-ttu-id="24045-117">Дополнительные сведения см. в разделе [-target (Visual Basic)](target.md).</span><span class="sxs-lookup"><span data-stu-id="24045-117">For more information, see [-target (Visual Basic)](target.md).</span></span>  
  
 <span data-ttu-id="24045-118">Параметры `-optimize` и `-debug` можно объединить.</span><span class="sxs-lookup"><span data-stu-id="24045-118">You can combine the `-optimize` and `-debug` options.</span></span>  
  
|<span data-ttu-id="24045-119">Задание параметра -optimize в интегрированной среде разработки Visual Studio</span><span class="sxs-lookup"><span data-stu-id="24045-119">To set -optimize in the Visual Studio integrated development environment</span></span>|  
|---|  
|<span data-ttu-id="24045-120">1.  Выберите проект в **Обозревателе решений**.</span><span class="sxs-lookup"><span data-stu-id="24045-120">1.  Have a project selected in **Solution Explorer**.</span></span> <span data-ttu-id="24045-121">В меню **Проект** выберите пункт **Свойства**.</span><span class="sxs-lookup"><span data-stu-id="24045-121">On the **Project** menu, click **Properties**.</span></span><br />     <br /><span data-ttu-id="24045-122">2.  Откройте вкладку **Компиляция**.</span><span class="sxs-lookup"><span data-stu-id="24045-122">2.  Click the **Compile** tab.</span></span><br /><span data-ttu-id="24045-123">3.  Нажмите кнопку **Дополнительно** .</span><span class="sxs-lookup"><span data-stu-id="24045-123">3.  Click the **Advanced** button.</span></span><br /><span data-ttu-id="24045-124">4.  Установите флажок **Включить оптимизацию**.</span><span class="sxs-lookup"><span data-stu-id="24045-124">4.  Modify the **Enable optimizations** check box.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="24045-125">Пример</span><span class="sxs-lookup"><span data-stu-id="24045-125">Example</span></span>  
 <span data-ttu-id="24045-126">Следующий код компилирует `T2.vb` и включает оптимизацию компилятора.</span><span class="sxs-lookup"><span data-stu-id="24045-126">The following code compiles `T2.vb` and enables compiler optimizations.</span></span>  
  
```console
vbc t2.vb -optimize  
```  
  
## <a name="see-also"></a><span data-ttu-id="24045-127">См. также</span><span class="sxs-lookup"><span data-stu-id="24045-127">See also</span></span>

- [<span data-ttu-id="24045-128">Компилятор Visual Basic с интерфейсом командной строки</span><span class="sxs-lookup"><span data-stu-id="24045-128">Visual Basic Command-Line Compiler</span></span>](index.md)
- [<span data-ttu-id="24045-129">-debug (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="24045-129">-debug (Visual Basic)</span></span>](debug.md)
- [<span data-ttu-id="24045-130">Примеры командных строк компиляции</span><span class="sxs-lookup"><span data-stu-id="24045-130">Sample Compilation Command Lines</span></span>](sample-compilation-command-lines.md)
- [<span data-ttu-id="24045-131">-target (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="24045-131">-target (Visual Basic)</span></span>](target.md)
