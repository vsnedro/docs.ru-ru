---
title: Практическое руководство. Просмотр содержимого сборки
description: Для просмотра атрибутов сборки и ссылок на другие модули и сборки можно использовать дизассемблер IL.
ms.date: 08/20/2019
helpviewer_keywords:
- assembly manifest, viewing information
- Ildasm.exe
- MSIL Disassembler
- assemblies [.NET], viewing contents
- viewing assembly information
- MSIL
- viewing MSIL information
ms.assetid: fb7baaab-4c0d-47ad-8fd3-4591cf834709
dev_langs:
- csharp
- vb
- cpp
ms.openlocfilehash: be2311c601effbebd519e33b7a5e13d49f44bd05
ms.sourcegitcommit: 279fb6e8d515df51676528a7424a1df2f0917116
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/27/2020
ms.locfileid: "92687503"
---
# <a name="how-to-view-assembly-contents"></a><span data-ttu-id="e522a-103">Практическое руководство. Просмотр содержимого сборки</span><span class="sxs-lookup"><span data-stu-id="e522a-103">How to: View assembly contents</span></span>

<span data-ttu-id="e522a-104">Можно использовать [Ildasm.exe (дизассемблер IL)](../../framework/tools/ildasm-exe-il-disassembler.md) для просмотра сведений промежуточного языка MSIL в файле.</span><span class="sxs-lookup"><span data-stu-id="e522a-104">You can use the [Ildasm.exe (IL Disassembler)](../../framework/tools/ildasm-exe-il-disassembler.md) to view Microsoft intermediate language (MSIL) information in a file.</span></span> <span data-ttu-id="e522a-105">Если анализируемый файл является сборкой, то эти данные могут включать в себя атрибуты сборки, а также ссылки на другие модули и сборки.</span><span class="sxs-lookup"><span data-stu-id="e522a-105">If the file being examined is an assembly, this information can include the assembly's attributes and references to other modules and assemblies.</span></span> <span data-ttu-id="e522a-106">Эти данные полезны для определения того, является ли файл сборкой или частью сборки и содержит ли он ссылки на другие модули и сборки.</span><span class="sxs-lookup"><span data-stu-id="e522a-106">This information can be helpful in determining whether a file is an assembly or part of an assembly and whether the file has references to other modules or assemblies.</span></span>

<span data-ttu-id="e522a-107">Чтобы отобразить содержимое сборки с помощью *Ildasm.exe* , введите **ildasm \<assembly name>** в командной строке.</span><span class="sxs-lookup"><span data-stu-id="e522a-107">To display the contents of an assembly using *Ildasm.exe* , enter **ildasm \<assembly name>** at a command prompt.</span></span> <span data-ttu-id="e522a-108">Например, следующая команда дизассемблирует сборку *Hello.exe*.</span><span class="sxs-lookup"><span data-stu-id="e522a-108">For example, the following command disassembles the *Hello.exe* assembly.</span></span>

```cmd
ildasm Hello.exe
```

<span data-ttu-id="e522a-109">Для просмотра сведений о манифесте сборки дважды щелкните значок **Манифест** в окне дизассемблера MSIL.</span><span class="sxs-lookup"><span data-stu-id="e522a-109">To view assembly manifest information, double-click the **Manifest** icon in the MSIL Disassembler window.</span></span>

## <a name="example"></a><span data-ttu-id="e522a-110">Пример</span><span class="sxs-lookup"><span data-stu-id="e522a-110">Example</span></span>

<span data-ttu-id="e522a-111">Следующий пример начинается с простой программы "Hello World".</span><span class="sxs-lookup"><span data-stu-id="e522a-111">The following example starts with a basic "Hello World" program.</span></span> <span data-ttu-id="e522a-112">После компиляции программы используйте *Ildasm.exe* , чтобы декомпилировать сборку *Hello.exe* и просмотреть манифест сборки.</span><span class="sxs-lookup"><span data-stu-id="e522a-112">After compiling the program, use *Ildasm.exe* to disassemble the *Hello.exe* assembly and view the assembly manifest.</span></span>

```cpp
using namespace System;

class MainApp
{
public:
    static void Main()
    {
        Console::WriteLine("Hello World using C++/CLI!");
    }
};

int main()
{
    MainApp::Main();
}
```

```csharp
using System;

class MainApp
{
    public static void Main()
    {
        Console.WriteLine("Hello World using C#!");
    }
}
```

```vb
Class MainApp
    Public Shared Sub Main()
        Console.WriteLine("Hello World using Visual Basic!")
    End Sub
End Class
```

<span data-ttu-id="e522a-113">Выполните команду *ildasm.exe* над сборкой *Hello.exe* и дважды щелкните значок **Манифест** в окне дизассемблера MSIL, чтобы получить следующие выходные данные:</span><span class="sxs-lookup"><span data-stu-id="e522a-113">Running the command *ildasm.exe* on the *Hello.exe* assembly and double-clicking the **Manifest** icon in the MSIL Disassembler window produces the following output:</span></span>

```output
// Metadata version: v4.0.30319
.assembly extern mscorlib
{
  .publickeytoken = (B7 7A 5C 56 19 34 E0 89 )                         // .z\V.4..
  .ver 4:0:0:0
}
.assembly Hello
{
  .custom instance void [mscorlib]System.Runtime.CompilerServices.CompilationRelaxationsAttribute::.ctor(int32) = ( 01 00 08 00 00 00 00 00 )
  .custom instance void [mscorlib]System.Runtime.CompilerServices.RuntimeCompatibilityAttribute::.ctor() = ( 01 00 01 00 54 02 16 57 72 61 70 4E 6F 6E 45 78   // ....T..WrapNonEx
                                                                                                             63 65 70 74 69 6F 6E 54 68 72 6F 77 73 01 )       // ceptionThrows.
  .hash algorithm 0x00008004
  .ver 0:0:0:0
}
.module Hello.exe
// MVID: {7C2770DB-1594-438D-BAE5-98764C39CCCA}
.imagebase 0x00400000
.file alignment 0x00000200
.stackreserve 0x00100000
.subsystem 0x0003       // WINDOWS_CUI
.corflags 0x00000001    //  ILONLY
// Image base: 0x00600000
```

<span data-ttu-id="e522a-114">В следующей таблице описаны все директивы в манифесте сборки *Hello.exe* , используемой в этом примере.</span><span class="sxs-lookup"><span data-stu-id="e522a-114">The following table describes each directive in the assembly manifest of the *Hello.exe* assembly used in the example:</span></span>

|<span data-ttu-id="e522a-115">Директива</span><span class="sxs-lookup"><span data-stu-id="e522a-115">Directive</span></span>|<span data-ttu-id="e522a-116">Описание</span><span class="sxs-lookup"><span data-stu-id="e522a-116">Description</span></span>|
|---------------|-----------------|
|<span data-ttu-id="e522a-117">**.assembly extern \<assembly name>**</span><span class="sxs-lookup"><span data-stu-id="e522a-117">**.assembly extern \<assembly name>**</span></span>|<span data-ttu-id="e522a-118">Определяет другую сборку, содержащую элементы, на которые имеются ссылки в текущем модуле (в этом примере — `mscorlib`).</span><span class="sxs-lookup"><span data-stu-id="e522a-118">Specifies another assembly that contains items referenced by the current module (in this example, `mscorlib`).</span></span>|
|<span data-ttu-id="e522a-119">**.publickeytoken \<token>**</span><span class="sxs-lookup"><span data-stu-id="e522a-119">**.publickeytoken \<token>**</span></span>|<span data-ttu-id="e522a-120">Определяет маркер действующего ключа сборки, на которую имеется ссылка.</span><span class="sxs-lookup"><span data-stu-id="e522a-120">Specifies the token of the actual key of the referenced assembly.</span></span>|
|<span data-ttu-id="e522a-121">**.ver \<version number>**</span><span class="sxs-lookup"><span data-stu-id="e522a-121">**.ver \<version number>**</span></span>|<span data-ttu-id="e522a-122">Задает номер версии, на которую имеется ссылка.</span><span class="sxs-lookup"><span data-stu-id="e522a-122">Specifies the version number of the referenced assembly.</span></span>|
|<span data-ttu-id="e522a-123">**.assembly \<assembly name>**</span><span class="sxs-lookup"><span data-stu-id="e522a-123">**.assembly \<assembly name>**</span></span>|<span data-ttu-id="e522a-124">Задает имя сборки.</span><span class="sxs-lookup"><span data-stu-id="e522a-124">Specifies the assembly name.</span></span>|
|<span data-ttu-id="e522a-125">**.hash algorithm \<int32 value>**</span><span class="sxs-lookup"><span data-stu-id="e522a-125">**.hash algorithm \<int32 value>**</span></span>|<span data-ttu-id="e522a-126">Задает используемый хэш-алгоритм.</span><span class="sxs-lookup"><span data-stu-id="e522a-126">Specifies the hash algorithm used.</span></span>|
|<span data-ttu-id="e522a-127">**.ver \<version number>**</span><span class="sxs-lookup"><span data-stu-id="e522a-127">**.ver \<version number>**</span></span>|<span data-ttu-id="e522a-128">Задает номер версии сборки.</span><span class="sxs-lookup"><span data-stu-id="e522a-128">Specifies the version number of the assembly.</span></span>|
|<span data-ttu-id="e522a-129">**.module \<file name>**</span><span class="sxs-lookup"><span data-stu-id="e522a-129">**.module \<file name>**</span></span>|<span data-ttu-id="e522a-130">Задает имена модулей, составляющих сборку.</span><span class="sxs-lookup"><span data-stu-id="e522a-130">Specifies the name of the modules that make up the assembly.</span></span> <span data-ttu-id="e522a-131">В этом примере сборка состоит только из одного файла.</span><span class="sxs-lookup"><span data-stu-id="e522a-131">In this example, the assembly consists of only one file.</span></span>|
|<span data-ttu-id="e522a-132">**.subsystem \<value>**</span><span class="sxs-lookup"><span data-stu-id="e522a-132">**.subsystem \<value>**</span></span>|<span data-ttu-id="e522a-133">Указывает требуемую для программы среду приложения.</span><span class="sxs-lookup"><span data-stu-id="e522a-133">Specifies the application environment required for the program.</span></span> <span data-ttu-id="e522a-134">В этом примере значение "3" указывает на то, что выполняемый модуль запускается на консоли.</span><span class="sxs-lookup"><span data-stu-id="e522a-134">In this example, the value 3 indicates that this executable is run from a console.</span></span>|
|<span data-ttu-id="e522a-135">**.corflags**</span><span class="sxs-lookup"><span data-stu-id="e522a-135">**.corflags**</span></span>|<span data-ttu-id="e522a-136">В настоящее время представляет собой зарезервированное поле метаданных.</span><span class="sxs-lookup"><span data-stu-id="e522a-136">Currently a reserved field in the metadata.</span></span>|

<span data-ttu-id="e522a-137">Манифест сборки может содержать несколько различных директив, зависящих от содержимого сборки.</span><span class="sxs-lookup"><span data-stu-id="e522a-137">An assembly manifest can contain a number of different directives, depending on the contents of the assembly.</span></span> <span data-ttu-id="e522a-138">Расширенный список директив манифеста сборки содержится в документации ECMA, в том числе в частях "Раздел II. Определение метаданных и семантика" и "Раздел III. Набор инструкций CIL".</span><span class="sxs-lookup"><span data-stu-id="e522a-138">For an extensive list of the directives in the assembly manifest, see the Ecma documentation, especially "Partition II: Metadata Definition and Semantics" and "Partition III: CIL Instruction Set":</span></span>

- [<span data-ttu-id="e522a-139">Стандарты ECMA для C# и Common Language Infrastructure</span><span class="sxs-lookup"><span data-stu-id="e522a-139">ECMA C# and Common Language Infrastructure standards</span></span>](../components.md#applicable-standards)
- [<span data-ttu-id="e522a-140">Стандарт ECMA-335 — Common Language Infrastructure (CLI)</span><span class="sxs-lookup"><span data-stu-id="e522a-140">Standard ECMA-335 - Common Language Infrastructure (CLI)</span></span>](http://www.ecma-international.org/publications/standards/Ecma-335.htm)

## <a name="see-also"></a><span data-ttu-id="e522a-141">См. также</span><span class="sxs-lookup"><span data-stu-id="e522a-141">See also</span></span>

- [<span data-ttu-id="e522a-142">Домены приложений и сборки</span><span class="sxs-lookup"><span data-stu-id="e522a-142">Application domains and assemblies</span></span>](../../framework/app-domains/application-domains.md#application-domains-and-assemblies)
- [<span data-ttu-id="e522a-143">Руководства по работе с доменами приложений и сборками</span><span class="sxs-lookup"><span data-stu-id="e522a-143">Application domains and assemblies how-to topics</span></span>](../../framework/app-domains/application-domains-and-assemblies-how-to-topics.md)
- [<span data-ttu-id="e522a-144">Ildasm.exe (дизассемблер IL)</span><span class="sxs-lookup"><span data-stu-id="e522a-144">Ildasm.exe (IL Disassembler)</span></span>](../../framework/tools/ildasm-exe-il-disassembler.md)
