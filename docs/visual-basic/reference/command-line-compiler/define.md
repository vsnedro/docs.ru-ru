---
title: -define
ms.date: 03/10/2018
helpviewer_keywords:
- -d compiler option [Visual Basic]
- /d compiler option [Visual Basic]
- -define compiler option [Visual Basic]
- d compiler option [Visual Basic]
- /define compiler option [Visual Basic]
- define compiler option [Visual Basic]
ms.assetid: f735c57d-1cf9-4f2f-a26f-0de630fd4077
ms.openlocfilehash: 5035466de4aa17c374824e1b0f02ed594731a9d3
ms.sourcegitcommit: 5f236cd78cf09593c8945a7d753e0850e96a0b80
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/07/2020
ms.locfileid: "75716799"
---
# <a name="-define-visual-basic"></a><span data-ttu-id="d4958-102">-define (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="d4958-102">-define (Visual Basic)</span></span>
<span data-ttu-id="d4958-103">Задает константы условной компиляции.</span><span class="sxs-lookup"><span data-stu-id="d4958-103">Defines conditional compiler constants.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d4958-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="d4958-104">Syntax</span></span>  
  
```console  
-define:["]symbol[=value][,symbol[=value]]["]  
```

<span data-ttu-id="d4958-105">or</span><span class="sxs-lookup"><span data-stu-id="d4958-105">or</span></span>

```console  
-d:["]symbol[=value][,symbol[=value]]["]  
```  
  
## <a name="arguments"></a><span data-ttu-id="d4958-106">Аргументы</span><span class="sxs-lookup"><span data-stu-id="d4958-106">Arguments</span></span>  
  
|<span data-ttu-id="d4958-107">Термин</span><span class="sxs-lookup"><span data-stu-id="d4958-107">Term</span></span>|<span data-ttu-id="d4958-108">Определение</span><span class="sxs-lookup"><span data-stu-id="d4958-108">Definition</span></span>|  
|---|---|  
|`symbol`|<span data-ttu-id="d4958-109">Обязательный.</span><span class="sxs-lookup"><span data-stu-id="d4958-109">Required.</span></span> <span data-ttu-id="d4958-110">Определяемый символ.</span><span class="sxs-lookup"><span data-stu-id="d4958-110">The symbol to define.</span></span>|  
|`value`|<span data-ttu-id="d4958-111">Необязательный элемент.</span><span class="sxs-lookup"><span data-stu-id="d4958-111">Optional.</span></span> <span data-ttu-id="d4958-112">Значение, которому назначается `symbol`.</span><span class="sxs-lookup"><span data-stu-id="d4958-112">The value to assign `symbol`.</span></span> <span data-ttu-id="d4958-113">Если `value` является строкой, его необходимо заключить в последовательности из обратной косой черты и кавычки (\\"), а не просто в кавычки.</span><span class="sxs-lookup"><span data-stu-id="d4958-113">If `value` is a string, it must be surrounded by backslash/quotation-mark sequences (\\") instead of quotation marks.</span></span> <span data-ttu-id="d4958-114">Если значение не задано, считается, что используется значение True.</span><span class="sxs-lookup"><span data-stu-id="d4958-114">If no value is specified, then it is taken to be True.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="d4958-115">Примечания</span><span class="sxs-lookup"><span data-stu-id="d4958-115">Remarks</span></span>  
 <span data-ttu-id="d4958-116">Влияние параметра `-define` похоже на использование директивы препроцессора `#Const` в исходном файле, за исключением того, что определенные с помощью `-define` константы являются общими и применяются ко всем файлам в проекте.</span><span class="sxs-lookup"><span data-stu-id="d4958-116">The `-define` option has an effect similar to using a `#Const` preprocessor directive in your source file, except that constants defined with `-define` are public and apply to all files in the project.</span></span>  
  
 <span data-ttu-id="d4958-117">Вы можете использовать символы, созданные этим параметром с помощью директивы `#If`...`Then`...`#Else`, для условной компиляции исходных файлов.</span><span class="sxs-lookup"><span data-stu-id="d4958-117">You can use symbols created by this option with the `#If`...`Then`...`#Else` directive to compile source files conditionally.</span></span>  
  
 <span data-ttu-id="d4958-118">`-d` является краткой формой `-define`.</span><span class="sxs-lookup"><span data-stu-id="d4958-118">`-d` is the short form of `-define`.</span></span>  
  
 <span data-ttu-id="d4958-119">Вы можете определить несколько символов с помощью `-define`, разделяя их определения запятой.</span><span class="sxs-lookup"><span data-stu-id="d4958-119">You can define multiple symbols with `-define` by using a comma to separate symbol definitions.</span></span>  
  
|<span data-ttu-id="d4958-120">Задание параметра -define в интегрированной среде разработки Visual Studio</span><span class="sxs-lookup"><span data-stu-id="d4958-120">To set -define in the Visual Studio integrated development environment</span></span>|  
|---|  
|<span data-ttu-id="d4958-121">1.  Выберите проект в **Обозревателе решений**.</span><span class="sxs-lookup"><span data-stu-id="d4958-121">1.  Have a project selected in **Solution Explorer**.</span></span> <span data-ttu-id="d4958-122">В меню **Проект** выберите пункт **Свойства**.</span><span class="sxs-lookup"><span data-stu-id="d4958-122">On the **Project** menu, click **Properties**.</span></span> <br /><span data-ttu-id="d4958-123">2.  Откройте вкладку **Компиляция**.</span><span class="sxs-lookup"><span data-stu-id="d4958-123">2.  Click the **Compile** tab.</span></span><br /><span data-ttu-id="d4958-124">3.  Нажмите кнопку **Дополнительно**.</span><span class="sxs-lookup"><span data-stu-id="d4958-124">3.  Click **Advanced**.</span></span><br /><span data-ttu-id="d4958-125">4.  Измените значение в поле **Настраиваемые константы**.</span><span class="sxs-lookup"><span data-stu-id="d4958-125">4.  Modify the value in the **Custom Constants** box.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="d4958-126">Пример</span><span class="sxs-lookup"><span data-stu-id="d4958-126">Example</span></span>  
 <span data-ttu-id="d4958-127">В следующем примере кода определяются и используются две константы условной компиляции.</span><span class="sxs-lookup"><span data-stu-id="d4958-127">The following code defines and then uses two conditional compiler constants.</span></span>  
  
 [!code-vb[VbVbalrCompiler#45](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrCompiler/VB/Class1.vb#45)]  
  
## <a name="see-also"></a><span data-ttu-id="d4958-128">См. также</span><span class="sxs-lookup"><span data-stu-id="d4958-128">See also</span></span>

- [<span data-ttu-id="d4958-129">Компилятор Visual Basic с интерфейсом командной строки</span><span class="sxs-lookup"><span data-stu-id="d4958-129">Visual Basic Command-Line Compiler</span></span>](../../../visual-basic/reference/command-line-compiler/index.md)
- [<span data-ttu-id="d4958-130">Директивы #If...Then...#Else</span><span class="sxs-lookup"><span data-stu-id="d4958-130">#If...Then...#Else Directives</span></span>](../../../visual-basic/language-reference/directives/if-then-else-directives.md)
- [<span data-ttu-id="d4958-131">Директива #Const</span><span class="sxs-lookup"><span data-stu-id="d4958-131">#Const Directive</span></span>](../../../visual-basic/language-reference/directives/const-directive.md)
- [<span data-ttu-id="d4958-132">Примеры командных строк компиляции</span><span class="sxs-lookup"><span data-stu-id="d4958-132">Sample Compilation Command Lines</span></span>](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)
