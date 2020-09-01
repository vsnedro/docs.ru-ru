---
description: -target:winexe (параметры компилятора C#)
title: -target:winexe (параметры компилятора C#)
ms.date: 07/20/2015
f1_keywords:
- /target:winexe
helpviewer_keywords:
- /target compiler options [C#], /target:winexe
- -target compiler options [C#], /target:winexe
- target compiler options [C#], /target:winexe
ms.assetid: b5a0619c-8caa-46a5-a743-1cf68408ad7a
ms.openlocfilehash: 8a1be07455b54b375106fef1fb480d7abd2f1ca4
ms.sourcegitcommit: d579fb5e4b46745fd0f1f8874c94c6469ce58604
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/30/2020
ms.locfileid: "89124725"
---
# <a name="-targetwinexe-c-compiler-options"></a><span data-ttu-id="03b51-103">-target:winexe (параметры компилятора C#)</span><span class="sxs-lookup"><span data-stu-id="03b51-103">-target:winexe (C# Compiler Options)</span></span>
<span data-ttu-id="03b51-104">Параметр **-target:winexe** предписывает компилятору создать исполняемый файл (EXE), программу Windows.</span><span class="sxs-lookup"><span data-stu-id="03b51-104">The **-target:winexe** option causes the compiler to create an executable (EXE), Windows program.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="03b51-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="03b51-105">Syntax</span></span>  
  
```console  
-target:winexe  
```  
  
## <a name="remarks"></a><span data-ttu-id="03b51-106">Remarks</span><span class="sxs-lookup"><span data-stu-id="03b51-106">Remarks</span></span>  
 <span data-ttu-id="03b51-107">Исполняемый файл создается с расширением ЕХЕ.</span><span class="sxs-lookup"><span data-stu-id="03b51-107">The executable file will be created with the .exe extension.</span></span> <span data-ttu-id="03b51-108">Программа Windows предоставляет пользовательский интерфейс либо из библиотеки .NET Framework, либо с помощью API Windows.</span><span class="sxs-lookup"><span data-stu-id="03b51-108">A Windows program is one that provides a user interface from either the .NET Framework library or with the Windows APIs.</span></span>  
  
 <span data-ttu-id="03b51-109">Воспользуйтесь параметром [-target:exe](./target-exe-compiler-option.md), чтобы создать консольное приложение.</span><span class="sxs-lookup"><span data-stu-id="03b51-109">Use [-target:exe](./target-exe-compiler-option.md) to create a console application.</span></span>  
  
 <span data-ttu-id="03b51-110">Если не указано иное с помощью параметра [-out](./out-compiler-option.md), имя выходного файла совпадает с именем входного файла, который содержит метод [Main](../../programming-guide/main-and-command-args/index.md).</span><span class="sxs-lookup"><span data-stu-id="03b51-110">Unless otherwise specified with the [-out](./out-compiler-option.md) option, the output file name takes the name of the input file that contains the [Main](../../programming-guide/main-and-command-args/index.md) method.</span></span>  
  
 <span data-ttu-id="03b51-111">Для создания DLL-файла используются все файлы, указанные в командной строке вплоть до следующего параметра **-out** или [-target](./target-compiler-option.md).</span><span class="sxs-lookup"><span data-stu-id="03b51-111">When specified at the command line, all files until the next **-out** or [-target](./target-compiler-option.md) option are used to create the Windows program.</span></span>  
  
 <span data-ttu-id="03b51-112">В файлах исходного кода, который компилируется в EXE-файл, должен содержаться один и только один метод **Main**.</span><span class="sxs-lookup"><span data-stu-id="03b51-112">One and only one **Main** method is required in the source code files that are compiled into an .exe file.</span></span> <span data-ttu-id="03b51-113">Параметр [-main](./main-compiler-option.md) позволяет указывать класс, содержащий метод **Main**, в случаях, когда код содержит несколько классов с методом **Main**.</span><span class="sxs-lookup"><span data-stu-id="03b51-113">The [-main](./main-compiler-option.md) option lets you specify which class contains the **Main** method, in cases where your code has more than one class with a **Main** method.</span></span>  
  
### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a><span data-ttu-id="03b51-114">Установка данного параметра компилятора в среде разработки Visual Studio</span><span class="sxs-lookup"><span data-stu-id="03b51-114">To set this compiler option in the Visual Studio development environment</span></span>  
  
1. <span data-ttu-id="03b51-115">Откройте страницу **Свойства** проекта.</span><span class="sxs-lookup"><span data-stu-id="03b51-115">Open the project's **Properties** page.</span></span>  
  
2. <span data-ttu-id="03b51-116">Перейдите на страницу свойств **Приложение**.</span><span class="sxs-lookup"><span data-stu-id="03b51-116">Click the **Application** property page.</span></span>  
  
3. <span data-ttu-id="03b51-117">Измените значение свойства **Тип выходных данных**.</span><span class="sxs-lookup"><span data-stu-id="03b51-117">Modify the **Output type** property.</span></span>  
  
 <span data-ttu-id="03b51-118">Сведения об установке этого параметра компилятора программными средствами см. в статье <xref:VSLangProj80.ProjectProperties3.OutputType%2A>.</span><span class="sxs-lookup"><span data-stu-id="03b51-118">For information on how to set this compiler option programmatically, see <xref:VSLangProj80.ProjectProperties3.OutputType%2A>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="03b51-119">Пример</span><span class="sxs-lookup"><span data-stu-id="03b51-119">Example</span></span>  
 <span data-ttu-id="03b51-120">Компиляция `in.cs` в программу Windows:</span><span class="sxs-lookup"><span data-stu-id="03b51-120">Compile `in.cs` into a Windows program:</span></span>  
  
```console  
csc -target:winexe in.cs  
```  
  
## <a name="see-also"></a><span data-ttu-id="03b51-121">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="03b51-121">See also</span></span>

- [<span data-ttu-id="03b51-122">-target (параметры компилятора C#)</span><span class="sxs-lookup"><span data-stu-id="03b51-122">-target (C# Compiler Options)</span></span>](./target-compiler-option.md)
- [<span data-ttu-id="03b51-123">Параметры компилятора C# </span><span class="sxs-lookup"><span data-stu-id="03b51-123">C# Compiler Options</span></span>](./index.md)
