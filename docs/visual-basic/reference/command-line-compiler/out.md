---
title: -out
ms.date: 07/20/2015
helpviewer_keywords:
- /out compiler option [Visual Basic]
- -out compiler option [Visual Basic]
- out compiler option [Visual Basic]
ms.assetid: 9f148c15-0909-4cb8-a2db-777f8a8b45ae
ms.openlocfilehash: 67366e13e4dceea4772d0730222413cb25b4e8b7
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/22/2019
ms.locfileid: "74352385"
---
# <a name="-out-visual-basic"></a><span data-ttu-id="33c2e-102">-out (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="33c2e-102">-out (Visual Basic)</span></span>
<span data-ttu-id="33c2e-103">Задает имя выходного файла.</span><span class="sxs-lookup"><span data-stu-id="33c2e-103">Specifies the name of the output file.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="33c2e-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="33c2e-104">Syntax</span></span>  
  
```console  
-out:filename  
```  
  
## <a name="arguments"></a><span data-ttu-id="33c2e-105">Аргументы</span><span class="sxs-lookup"><span data-stu-id="33c2e-105">Arguments</span></span>  
  
|<span data-ttu-id="33c2e-106">Термин</span><span class="sxs-lookup"><span data-stu-id="33c2e-106">Term</span></span>|<span data-ttu-id="33c2e-107">Определение</span><span class="sxs-lookup"><span data-stu-id="33c2e-107">Definition</span></span>|  
|---|---|  
|`filename`|<span data-ttu-id="33c2e-108">Обязательный.</span><span class="sxs-lookup"><span data-stu-id="33c2e-108">Required.</span></span> <span data-ttu-id="33c2e-109">Имя выходного файла, создаваемого компилятором.</span><span class="sxs-lookup"><span data-stu-id="33c2e-109">The name of the output file the compiler creates.</span></span> <span data-ttu-id="33c2e-110">Если имя файла содержит пробел, заключите его в кавычки (" ").</span><span class="sxs-lookup"><span data-stu-id="33c2e-110">If the file name contains a space, enclose the name in quotation marks (" ").</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="33c2e-111">Примечания</span><span class="sxs-lookup"><span data-stu-id="33c2e-111">Remarks</span></span>  
 <span data-ttu-id="33c2e-112">Укажите полное имя и расширение создаваемого файла.</span><span class="sxs-lookup"><span data-stu-id="33c2e-112">Specify the full name and extension of the file to create.</span></span> <span data-ttu-id="33c2e-113">В противном случае этот EXE-файл именуется по файлу исходного кода, содержащему процедуру `Sub Main`, а DLL-файл именуется по первому файлу исходного кода.</span><span class="sxs-lookup"><span data-stu-id="33c2e-113">If you do not, the .exe file takes its name from the source-code file containing the `Sub Main` procedure, and the .dll file takes its name from the first source-code file.</span></span>  
  
 <span data-ttu-id="33c2e-114">Если указать имя файла без расширения EXE или DLL, компилятор автоматически добавляет расширение в зависимости от значения, указанного для параметра компилятора `-target`.</span><span class="sxs-lookup"><span data-stu-id="33c2e-114">If you specify a file name without an .exe or .dll extension, the compiler automatically adds the extension for you, depending on the value specified for the `-target` compiler option.</span></span>  
  
|<span data-ttu-id="33c2e-115">Настройка параметра -out в интегрированной среде разработки Visual Studio</span><span class="sxs-lookup"><span data-stu-id="33c2e-115">To set -out in the Visual Studio integrated development environment</span></span>|  
|---|  
|<span data-ttu-id="33c2e-116">1.  Выберите проект в **Обозревателе решений**.</span><span class="sxs-lookup"><span data-stu-id="33c2e-116">1.  Have a project selected in **Solution Explorer**.</span></span> <span data-ttu-id="33c2e-117">В меню **Проект** выберите пункт **Свойства**.</span><span class="sxs-lookup"><span data-stu-id="33c2e-117">On the **Project** menu, click **Properties**.</span></span> <br /><span data-ttu-id="33c2e-118">2.  Перейдите на вкладку **Приложение** .</span><span class="sxs-lookup"><span data-stu-id="33c2e-118">2.  Click the **Application** tab.</span></span><br /><span data-ttu-id="33c2e-119">3.  Измените значение в поле **Имя сборки**.</span><span class="sxs-lookup"><span data-stu-id="33c2e-119">3.  Modify the value in the **Assembly Name** box.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="33c2e-120">Пример</span><span class="sxs-lookup"><span data-stu-id="33c2e-120">Example</span></span>  
 <span data-ttu-id="33c2e-121">Следующий код компилирует `T2.vb` и создает выходной файл `T2.exe`.</span><span class="sxs-lookup"><span data-stu-id="33c2e-121">The following code compiles `T2.vb` and creates output file `T2.exe`.</span></span>  
  
```console
vbc t2.vb -out:t3.exe  
```  
  
## <a name="see-also"></a><span data-ttu-id="33c2e-122">См. также</span><span class="sxs-lookup"><span data-stu-id="33c2e-122">See also</span></span>

- [<span data-ttu-id="33c2e-123">Компилятор Visual Basic с интерфейсом командной строки</span><span class="sxs-lookup"><span data-stu-id="33c2e-123">Visual Basic Command-Line Compiler</span></span>](../../../visual-basic/reference/command-line-compiler/index.md)
- [<span data-ttu-id="33c2e-124">-target (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="33c2e-124">-target (Visual Basic)</span></span>](../../../visual-basic/reference/command-line-compiler/target.md)
- [<span data-ttu-id="33c2e-125">Примеры командных строк компиляции</span><span class="sxs-lookup"><span data-stu-id="33c2e-125">Sample Compilation Command Lines</span></span>](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)
