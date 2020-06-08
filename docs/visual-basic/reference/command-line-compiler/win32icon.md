---
title: -win32icon
ms.date: 03/13/2018
helpviewer_keywords:
- win32icon compiler option [Visual Basic]
- -win32icon compiler option [Visual Basic]
- /win32icon compiler option [Visual Basic]
ms.assetid: aecaab01-9353-46c5-941c-6edabd4eff92
ms.openlocfilehash: 52ef0b991554c800dba4320b0c64c81ddd1b0ff4
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/04/2020
ms.locfileid: "84414289"
---
# <a name="-win32icon"></a><span data-ttu-id="3f3c2-102">-win32icon</span><span class="sxs-lookup"><span data-stu-id="3f3c2-102">-win32icon</span></span>
<span data-ttu-id="3f3c2-103">Внедряет ICO-файл в выходной файл.</span><span class="sxs-lookup"><span data-stu-id="3f3c2-103">Inserts an .ico file in the output file.</span></span> <span data-ttu-id="3f3c2-104">Этот ICO-файл представляет выходной файл в **проводнике**.</span><span class="sxs-lookup"><span data-stu-id="3f3c2-104">This .ico file represents the output file in **File Explorer**.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3f3c2-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="3f3c2-105">Syntax</span></span>  
  
```console  
-win32icon:filename  
```  
  
## <a name="arguments"></a><span data-ttu-id="3f3c2-106">Аргументы</span><span class="sxs-lookup"><span data-stu-id="3f3c2-106">Arguments</span></span>  
  
|<span data-ttu-id="3f3c2-107">Термин</span><span class="sxs-lookup"><span data-stu-id="3f3c2-107">Term</span></span>|<span data-ttu-id="3f3c2-108">Определение</span><span class="sxs-lookup"><span data-stu-id="3f3c2-108">Definition</span></span>|  
|---|---|  
|`filename`|<span data-ttu-id="3f3c2-109">ICO-файл, который требуется добавить в выходной файл.</span><span class="sxs-lookup"><span data-stu-id="3f3c2-109">The .ico file to add to your output file.</span></span> <span data-ttu-id="3f3c2-110">Если имя файла содержит пробел, заключите это имя в кавычки (" ").</span><span class="sxs-lookup"><span data-stu-id="3f3c2-110">Enclose the file name in quotation marks (" ") if it contains a space.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="3f3c2-111">Примечания</span><span class="sxs-lookup"><span data-stu-id="3f3c2-111">Remarks</span></span>  
 <span data-ttu-id="3f3c2-112">Вы можете создать ICO-файл с помощью компилятора ресурсов Microsoft Windows (RC).</span><span class="sxs-lookup"><span data-stu-id="3f3c2-112">You can create an .ico file with the Microsoft Windows Resource Compiler (RC).</span></span> <span data-ttu-id="3f3c2-113">Компилятор ресурсов вызывается при компиляции программы Visual C++. При этом ICO-файл создается из RC-файла.</span><span class="sxs-lookup"><span data-stu-id="3f3c2-113">The resource compiler is invoked when you compile a Visual C++ program; an .ico file is created from the .rc file.</span></span> <span data-ttu-id="3f3c2-114">Параметры `-win32icon` и `-win32resource` являются взаимоисключающими.</span><span class="sxs-lookup"><span data-stu-id="3f3c2-114">The `-win32icon` and `-win32resource` options are mutually exclusive.</span></span>  
  
 <span data-ttu-id="3f3c2-115">Чтобы создать ссылку на файл ресурсов .NET Framework, см. раздел [-linkresource (Visual Basic)](linkresource.md). Чтобы присоединить файл ресурсов .NET, см. раздел [-resource (Visual Basic)](resource.md).</span><span class="sxs-lookup"><span data-stu-id="3f3c2-115">See [-linkresource (Visual Basic)](linkresource.md) to reference a .NET Framework resource file, or [-resource (Visual Basic)](resource.md) to attach a .NET Framework resource file.</span></span> <span data-ttu-id="3f3c2-116">См. сведения об импорте RES-файла в разделе [-win32resource](win32resource.md).</span><span class="sxs-lookup"><span data-stu-id="3f3c2-116">See [-win32resource](win32resource.md) to import a .res file.</span></span>  
  
|<span data-ttu-id="3f3c2-117">Чтобы задать параметр -win32icon в Visual Studio IDE, сделайте следующее:</span><span class="sxs-lookup"><span data-stu-id="3f3c2-117">To set -win32icon in the Visual Studio IDE</span></span>|  
|---|  
|<span data-ttu-id="3f3c2-118">1.  Выберите проект в **Обозревателе решений**.</span><span class="sxs-lookup"><span data-stu-id="3f3c2-118">1.  Have a project selected in **Solution Explorer**.</span></span> <span data-ttu-id="3f3c2-119">В меню **Проект** выберите пункт **Свойства**.</span><span class="sxs-lookup"><span data-stu-id="3f3c2-119">On the **Project** menu, click **Properties**.</span></span> <br /><span data-ttu-id="3f3c2-120">2.  Перейдите на вкладку **Приложение** .</span><span class="sxs-lookup"><span data-stu-id="3f3c2-120">2.  Click the **Application** tab.</span></span><br /><span data-ttu-id="3f3c2-121">3.  Измените значение в поле **Значок**.</span><span class="sxs-lookup"><span data-stu-id="3f3c2-121">3.  Modify the value in the **Icon** box.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="3f3c2-122">Пример</span><span class="sxs-lookup"><span data-stu-id="3f3c2-122">Example</span></span>  
 <span data-ttu-id="3f3c2-123">Следующий код компилирует `In.vb` и присоединяет ICO-файл `Rf.ico`.</span><span class="sxs-lookup"><span data-stu-id="3f3c2-123">The following code compiles `In.vb` and attaches an .ico file, `Rf.ico`.</span></span>  
  
```console
vbc -win32icon:rf.ico in.vb  
```  
  
## <a name="see-also"></a><span data-ttu-id="3f3c2-124">См. также</span><span class="sxs-lookup"><span data-stu-id="3f3c2-124">See also</span></span>

- [<span data-ttu-id="3f3c2-125">Компилятор Visual Basic с интерфейсом командной строки</span><span class="sxs-lookup"><span data-stu-id="3f3c2-125">Visual Basic Command-Line Compiler</span></span>](index.md)
- [<span data-ttu-id="3f3c2-126">Примеры командных строк компиляции</span><span class="sxs-lookup"><span data-stu-id="3f3c2-126">Sample Compilation Command Lines</span></span>](sample-compilation-command-lines.md)
