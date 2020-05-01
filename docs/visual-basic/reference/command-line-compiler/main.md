---
title: -main
ms.date: 03/13/2018
helpviewer_keywords:
- main compiler option [Visual Basic]
- /main compiler option [Visual Basic]
- -main compiler option [Visual Basic]
ms.assetid: 83fc339d-6652-415d-b205-b5133319b5b0
ms.openlocfilehash: 91f2a27ed9b6fb296dbb9e50fc488fd012311890
ms.sourcegitcommit: eff6adb61852369ab690f3f047818c90580e7eb1
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/07/2019
ms.locfileid: "72005504"
---
# <a name="-main"></a><span data-ttu-id="a0efc-102">-main</span><span class="sxs-lookup"><span data-stu-id="a0efc-102">-main</span></span>
<span data-ttu-id="a0efc-103">Задает класс или модуль, содержащий процедуру `Sub Main`.</span><span class="sxs-lookup"><span data-stu-id="a0efc-103">Specifies the class or module that contains the `Sub Main` procedure.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a0efc-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="a0efc-104">Syntax</span></span>  
  
```console  
-main:location  
```  
  
## <a name="arguments"></a><span data-ttu-id="a0efc-105">Аргументы</span><span class="sxs-lookup"><span data-stu-id="a0efc-105">Arguments</span></span>  
 `location`  
 <span data-ttu-id="a0efc-106">Обязательный.</span><span class="sxs-lookup"><span data-stu-id="a0efc-106">Required.</span></span> <span data-ttu-id="a0efc-107">Имя класса или модуля, который содержит процедуру `Sub Main` для вызова при запуске программы.</span><span class="sxs-lookup"><span data-stu-id="a0efc-107">The name of the class or module that contains the `Sub Main` procedure to be called when the program starts.</span></span> <span data-ttu-id="a0efc-108">Может иметь формат **-main:module** или **-main:namespace.module**.</span><span class="sxs-lookup"><span data-stu-id="a0efc-108">This may be in the form **-main:module** or **-main:namespace.module**.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="a0efc-109">Примечания</span><span class="sxs-lookup"><span data-stu-id="a0efc-109">Remarks</span></span>  
 <span data-ttu-id="a0efc-110">Используйте этот параметр при создании исполняемого файла или исполняемой программы Windows.</span><span class="sxs-lookup"><span data-stu-id="a0efc-110">Use this option when you create an executable file or Windows executable program.</span></span> <span data-ttu-id="a0efc-111">Если параметр **-main** опущен, компилятор ищет допустимый общедоступный объект `Sub Main` во всех открытых классах и модулях.</span><span class="sxs-lookup"><span data-stu-id="a0efc-111">If the **-main** option is omitted, the compiler searches for a valid shared `Sub Main` in all public classes and modules.</span></span>  
  
 <span data-ttu-id="a0efc-112">Описание разных форм процедуры `Main` см. в статье [о процедуре Main в Visual Basic](../../../visual-basic/programming-guide/program-structure/main-procedure.md).</span><span class="sxs-lookup"><span data-stu-id="a0efc-112">See [Main Procedure in Visual Basic](../../../visual-basic/programming-guide/program-structure/main-procedure.md) for a discussion of the various forms of the `Main` procedure.</span></span>  
  
 <span data-ttu-id="a0efc-113">Если класс `location` наследуется от <xref:System.Windows.Forms.Form>, компилятор предоставляет стандартную процедуру `Main`, которая запускает приложение, если в классе нет процедуры `Main`.</span><span class="sxs-lookup"><span data-stu-id="a0efc-113">When `location` is a class that inherits from <xref:System.Windows.Forms.Form>, the compiler provides a default `Main` procedure that starts the application if the class has no `Main` procedure.</span></span> <span data-ttu-id="a0efc-114">Это позволяет компилировать код из командной строки, созданной в среде разработки.</span><span class="sxs-lookup"><span data-stu-id="a0efc-114">This lets you compile code at the command line that was created in the development environment.</span></span>  
  
 [!code-vb[VbVbalrCompiler#16](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrCompiler/VB/Class1.vb#16)]  
  
### <a name="to-set--main-in-the-visual-studio-integrated-development-environment"></a><span data-ttu-id="a0efc-115">Настройка параметра -main в интегрированной среде разработки Visual Studio</span><span class="sxs-lookup"><span data-stu-id="a0efc-115">To set -main in the Visual Studio integrated development environment</span></span>  
  
1. <span data-ttu-id="a0efc-116">Выберите проект в **Обозревателе решений**.</span><span class="sxs-lookup"><span data-stu-id="a0efc-116">Have a project selected in **Solution Explorer**.</span></span> <span data-ttu-id="a0efc-117">В меню **Проект** выберите пункт **Свойства**.</span><span class="sxs-lookup"><span data-stu-id="a0efc-117">On the **Project** menu, click **Properties**.</span></span>  
  
2. <span data-ttu-id="a0efc-118">Перейдите на вкладку **Приложение** .</span><span class="sxs-lookup"><span data-stu-id="a0efc-118">Click the **Application** tab.</span></span>  
  
3. <span data-ttu-id="a0efc-119">Снимите флажок **Включить исполняющую среду**.</span><span class="sxs-lookup"><span data-stu-id="a0efc-119">Make sure the **Enable application framework** check box is not checked.</span></span>  
  
4. <span data-ttu-id="a0efc-120">Измените значение в поле **Автоматически запускаемый объект**.</span><span class="sxs-lookup"><span data-stu-id="a0efc-120">Modify the value in the **Startup object** box.</span></span>  
  
## <a name="example"></a><span data-ttu-id="a0efc-121">Пример</span><span class="sxs-lookup"><span data-stu-id="a0efc-121">Example</span></span>  
 <span data-ttu-id="a0efc-122">В следующем код запускается компиляция `T2.vb` и `T3.vb`, а также указано, что процедура `Sub Main` находится в классе `Test2`.</span><span class="sxs-lookup"><span data-stu-id="a0efc-122">The following code compiles `T2.vb` and `T3.vb`, specifying that the `Sub Main` procedure will be found in the `Test2` class.</span></span>  
  
```console
vbc t2.vb t3.vb -main:Test2  
```  
  
## <a name="see-also"></a><span data-ttu-id="a0efc-123">См. также</span><span class="sxs-lookup"><span data-stu-id="a0efc-123">See also</span></span>

- [<span data-ttu-id="a0efc-124">Компилятор Visual Basic с интерфейсом командной строки</span><span class="sxs-lookup"><span data-stu-id="a0efc-124">Visual Basic Command-Line Compiler</span></span>](../../../visual-basic/reference/command-line-compiler/index.md)
- [<span data-ttu-id="a0efc-125">-target (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="a0efc-125">-target (Visual Basic)</span></span>](../../../visual-basic/reference/command-line-compiler/target.md)
- [<span data-ttu-id="a0efc-126">Примеры командных строк компиляции</span><span class="sxs-lookup"><span data-stu-id="a0efc-126">Sample Compilation Command Lines</span></span>](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)
- [<span data-ttu-id="a0efc-127">Процедура Main в Visual Basic</span><span class="sxs-lookup"><span data-stu-id="a0efc-127">Main Procedure in Visual Basic</span></span>](../../../visual-basic/programming-guide/program-structure/main-procedure.md)
