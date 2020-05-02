---
title: -libpath
ms.date: 03/10/2018
helpviewer_keywords:
- libpath compiler option [Visual Basic]
- /libpath compiler option [Visual Basic]
- -libpath compiler option [Visual Basic]
ms.assetid: 5f1c26c9-3455-4e89-bdf3-b12d6c2e655b
ms.openlocfilehash: 9a5822a097828f818da020735c3822e86eb3236b
ms.sourcegitcommit: 5f236cd78cf09593c8945a7d753e0850e96a0b80
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/07/2020
ms.locfileid: "75716641"
---
# <a name="-libpath"></a><span data-ttu-id="e6677-102">-libpath</span><span class="sxs-lookup"><span data-stu-id="e6677-102">-libpath</span></span>
<span data-ttu-id="e6677-103">Сообщает расположение указанных сборок.</span><span class="sxs-lookup"><span data-stu-id="e6677-103">Specifies the location of referenced assemblies.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e6677-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="e6677-104">Syntax</span></span>  
  
```console  
-libpath:dirList  
```  
  
## <a name="arguments"></a><span data-ttu-id="e6677-105">Аргументы</span><span class="sxs-lookup"><span data-stu-id="e6677-105">Arguments</span></span>  
  
|<span data-ttu-id="e6677-106">Термин</span><span class="sxs-lookup"><span data-stu-id="e6677-106">Term</span></span>|<span data-ttu-id="e6677-107">Определение</span><span class="sxs-lookup"><span data-stu-id="e6677-107">Definition</span></span>|  
|---|---|  
|`dirList`|<span data-ttu-id="e6677-108">Обязательный.</span><span class="sxs-lookup"><span data-stu-id="e6677-108">Required.</span></span> <span data-ttu-id="e6677-109">Разделенный точками с запятой список каталогов, в котором компилятор должен искать сборку, если она отсутствует как в текущем рабочем каталоге (каталоге, из которого был вызван компилятор), так и в системном каталоге среды CLR.</span><span class="sxs-lookup"><span data-stu-id="e6677-109">Semicolon-delimited list of directories for the compiler to look in if a referenced assembly is not found in either the current working directory (the directory from which you are invoking the compiler) or the common language runtime's system directory.</span></span> <span data-ttu-id="e6677-110">Если имя каталога содержит пробел, заключите имя в кавычки (" ").</span><span class="sxs-lookup"><span data-stu-id="e6677-110">If the directory name contains a space, enclose the name in quotation marks (" ").</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="e6677-111">Примечания</span><span class="sxs-lookup"><span data-stu-id="e6677-111">Remarks</span></span>  
 <span data-ttu-id="e6677-112">Параметр `-libpath` задает расположение сборок, указанных с помощью параметра [-reference](../../../visual-basic/reference/command-line-compiler/reference.md).</span><span class="sxs-lookup"><span data-stu-id="e6677-112">The `-libpath` option specifies the location of assemblies referenced by the [-reference](../../../visual-basic/reference/command-line-compiler/reference.md) option.</span></span>  
  
 <span data-ttu-id="e6677-113">Компилятор выполняет поиск связанных сборок, для которых не указано полное имя, в следующем порядке:</span><span class="sxs-lookup"><span data-stu-id="e6677-113">The compiler searches for assembly references that are not fully qualified in the following order:</span></span>  
  
1. <span data-ttu-id="e6677-114">Текущая рабочая папка.</span><span class="sxs-lookup"><span data-stu-id="e6677-114">Current working directory.</span></span> <span data-ttu-id="e6677-115">Это папка, из которой был вызван компилятор.</span><span class="sxs-lookup"><span data-stu-id="e6677-115">This is the directory from which the compiler is invoked.</span></span>  
  
2. <span data-ttu-id="e6677-116">Системный каталог среды CLR.</span><span class="sxs-lookup"><span data-stu-id="e6677-116">The common language runtime system directory.</span></span>  
  
3. <span data-ttu-id="e6677-117">Каталоги, указанные параметром `-libpath`.</span><span class="sxs-lookup"><span data-stu-id="e6677-117">Directories specified by `-libpath`.</span></span>  
  
4. <span data-ttu-id="e6677-118">Каталоги, указанные переменной среды LIB.</span><span class="sxs-lookup"><span data-stu-id="e6677-118">Directories specified by the LIB environment variable.</span></span>  
  
 <span data-ttu-id="e6677-119">Параметры `-libpath` является аддитивным; каждое следующее указание этого параметра присоединяется к предыдущим значениям.</span><span class="sxs-lookup"><span data-stu-id="e6677-119">The `-libpath` option is additive; specifying it more than once appends to any prior values.</span></span>  
  
 <span data-ttu-id="e6677-120">Используйте `-reference` для указания ссылки на сборку.</span><span class="sxs-lookup"><span data-stu-id="e6677-120">Use `-reference` to specify an assembly reference.</span></span>  
  
|<span data-ttu-id="e6677-121">Задание -libpath в интегрированной среде разработки Visual Studio</span><span class="sxs-lookup"><span data-stu-id="e6677-121">To set -libpath in the Visual Studio integrated development environment</span></span>|  
|---|  
|<span data-ttu-id="e6677-122">1.  Выберите проект в **Обозревателе решений**.</span><span class="sxs-lookup"><span data-stu-id="e6677-122">1.  Have a project selected in **Solution Explorer**.</span></span> <span data-ttu-id="e6677-123">В меню **Проект** выберите пункт **Свойства**.</span><span class="sxs-lookup"><span data-stu-id="e6677-123">On the **Project** menu, click **Properties**.</span></span> <br /><span data-ttu-id="e6677-124">2.  Перейдите на вкладку **Ссылки**.</span><span class="sxs-lookup"><span data-stu-id="e6677-124">2.  Click the **References** tab.</span></span><br /><span data-ttu-id="e6677-125">3.  Щелкните кнопку **Пути для ссылок...** .</span><span class="sxs-lookup"><span data-stu-id="e6677-125">3.  Click the **Reference Paths...** button.</span></span><br /><span data-ttu-id="e6677-126">4.  В диалоговом окне **Пути для ссылок** введите имя каталога в поле **Folder:** .</span><span class="sxs-lookup"><span data-stu-id="e6677-126">4.  In the **Reference Paths** dialog box, enter the directory name in the **Folder:** box.</span></span><br /><span data-ttu-id="e6677-127">5.  Щелкните **Добавить папку**.</span><span class="sxs-lookup"><span data-stu-id="e6677-127">5.  Click **Add Folder**.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="e6677-128">Пример</span><span class="sxs-lookup"><span data-stu-id="e6677-128">Example</span></span>  
 <span data-ttu-id="e6677-129">Следующий код компилирует `T2.vb`, чтобы создать файл .exe.</span><span class="sxs-lookup"><span data-stu-id="e6677-129">The following code compiles `T2.vb` to create an .exe file.</span></span> <span data-ttu-id="e6677-130">Компилятор выполнит поиск ссылок на сборку в рабочем каталоге, корневом каталоге диска С и каталоге "Новые сборки" на диске C:.</span><span class="sxs-lookup"><span data-stu-id="e6677-130">The compiler looks in the working directory, in the root directory of the C: drive, and in the New Assemblies directory of the C: drive for assembly references.</span></span>  
  
```console  
vbc -libpath:c:\;"c:\New Assemblies" -reference:t2.dll t2.vb  
```  
  
## <a name="see-also"></a><span data-ttu-id="e6677-131">См. также</span><span class="sxs-lookup"><span data-stu-id="e6677-131">See also</span></span>

- [<span data-ttu-id="e6677-132">Сборки в .NET</span><span class="sxs-lookup"><span data-stu-id="e6677-132">Assemblies in .NET</span></span>](../../../standard/assembly/index.md)
- [<span data-ttu-id="e6677-133">Компилятор Visual Basic с интерфейсом командной строки</span><span class="sxs-lookup"><span data-stu-id="e6677-133">Visual Basic Command-Line Compiler</span></span>](../../../visual-basic/reference/command-line-compiler/index.md)
- [<span data-ttu-id="e6677-134">Примеры командных строк компиляции</span><span class="sxs-lookup"><span data-stu-id="e6677-134">Sample Compilation Command Lines</span></span>](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)
