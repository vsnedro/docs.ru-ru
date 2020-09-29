---
title: -out
ms.date: 07/20/2015
helpviewer_keywords:
- /out compiler option [Visual Basic]
- -out compiler option [Visual Basic]
- out compiler option [Visual Basic]
ms.assetid: 9f148c15-0909-4cb8-a2db-777f8a8b45ae
ms.openlocfilehash: 7c013270c8a6b7c2b28f02766df7437b43075dd2
ms.sourcegitcommit: bf5c5850654187705bc94cc40ebfb62fe346ab02
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/23/2020
ms.locfileid: "91098908"
---
# <a name="-out-visual-basic"></a><span data-ttu-id="1260b-102">-out (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="1260b-102">-out (Visual Basic)</span></span>

<span data-ttu-id="1260b-103">Задает имя выходного файла.</span><span class="sxs-lookup"><span data-stu-id="1260b-103">Specifies the name of the output file.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1260b-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="1260b-104">Syntax</span></span>  
  
```console  
-out:filename  
```  
  
## <a name="arguments"></a><span data-ttu-id="1260b-105">Аргументы</span><span class="sxs-lookup"><span data-stu-id="1260b-105">Arguments</span></span>  
  
|<span data-ttu-id="1260b-106">Термин</span><span class="sxs-lookup"><span data-stu-id="1260b-106">Term</span></span>|<span data-ttu-id="1260b-107">Определение</span><span class="sxs-lookup"><span data-stu-id="1260b-107">Definition</span></span>|  
|---|---|  
|`filename`|<span data-ttu-id="1260b-108">Обязательный.</span><span class="sxs-lookup"><span data-stu-id="1260b-108">Required.</span></span> <span data-ttu-id="1260b-109">Имя выходного файла, создаваемого компилятором.</span><span class="sxs-lookup"><span data-stu-id="1260b-109">The name of the output file the compiler creates.</span></span> <span data-ttu-id="1260b-110">Если имя файла содержит пробел, заключите его в кавычки (" ").</span><span class="sxs-lookup"><span data-stu-id="1260b-110">If the file name contains a space, enclose the name in quotation marks (" ").</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="1260b-111">Примечания</span><span class="sxs-lookup"><span data-stu-id="1260b-111">Remarks</span></span>  

 <span data-ttu-id="1260b-112">Укажите полное имя и расширение создаваемого файла.</span><span class="sxs-lookup"><span data-stu-id="1260b-112">Specify the full name and extension of the file to create.</span></span> <span data-ttu-id="1260b-113">В противном случае этот EXE-файл именуется по файлу исходного кода, содержащему процедуру `Sub Main`, а DLL-файл именуется по первому файлу исходного кода.</span><span class="sxs-lookup"><span data-stu-id="1260b-113">If you do not, the .exe file takes its name from the source-code file containing the `Sub Main` procedure, and the .dll file takes its name from the first source-code file.</span></span>  
  
 <span data-ttu-id="1260b-114">Если указать имя файла без расширения EXE или DLL, компилятор автоматически добавляет расширение в зависимости от значения, указанного для параметра компилятора `-target`.</span><span class="sxs-lookup"><span data-stu-id="1260b-114">If you specify a file name without an .exe or .dll extension, the compiler automatically adds the extension for you, depending on the value specified for the `-target` compiler option.</span></span>  
  
|<span data-ttu-id="1260b-115">Настройка параметра -out в интегрированной среде разработки Visual Studio</span><span class="sxs-lookup"><span data-stu-id="1260b-115">To set -out in the Visual Studio integrated development environment</span></span>|  
|---|  
|<span data-ttu-id="1260b-116">1.  Выберите проект в **Обозревателе решений**.</span><span class="sxs-lookup"><span data-stu-id="1260b-116">1.  Have a project selected in **Solution Explorer**.</span></span> <span data-ttu-id="1260b-117">В меню **Проект** выберите пункт **Свойства**.</span><span class="sxs-lookup"><span data-stu-id="1260b-117">On the **Project** menu, click **Properties**.</span></span> <br /><span data-ttu-id="1260b-118">2.  Перейдите на вкладку **Приложение** .</span><span class="sxs-lookup"><span data-stu-id="1260b-118">2.  Click the **Application** tab.</span></span><br /><span data-ttu-id="1260b-119">3.  Измените значение в поле **Имя сборки**.</span><span class="sxs-lookup"><span data-stu-id="1260b-119">3.  Modify the value in the **Assembly Name** box.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="1260b-120">Пример</span><span class="sxs-lookup"><span data-stu-id="1260b-120">Example</span></span>  

 <span data-ttu-id="1260b-121">Следующий код компилирует `T2.vb` и создает выходной файл `T2.exe`.</span><span class="sxs-lookup"><span data-stu-id="1260b-121">The following code compiles `T2.vb` and creates output file `T2.exe`.</span></span>  
  
```console
vbc t2.vb -out:t3.exe  
```  
  
## <a name="see-also"></a><span data-ttu-id="1260b-122">См. также</span><span class="sxs-lookup"><span data-stu-id="1260b-122">See also</span></span>

- [<span data-ttu-id="1260b-123">Компилятор Visual Basic с интерфейсом командной строки</span><span class="sxs-lookup"><span data-stu-id="1260b-123">Visual Basic Command-Line Compiler</span></span>](index.md)
- [<span data-ttu-id="1260b-124">-target (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="1260b-124">-target (Visual Basic)</span></span>](target.md)
- [<span data-ttu-id="1260b-125">Примеры командных строк компиляции</span><span class="sxs-lookup"><span data-stu-id="1260b-125">Sample Compilation Command Lines</span></span>](sample-compilation-command-lines.md)
