---
title: "Практическое руководство. Создание неподписанных дружественных сборок (C#)"
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-csharp
ms.topic: article
dev_langs:
- CSharp
ms.assetid: 78cbc4f0-b021-4141-a4ff-eb4edbd814ca
caps.latest.revision: 3
author: BillWagner
ms.author: wiwagn
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: 967436204ab0824a510c12dc4c6e288d91d7dfa0
ms.contentlocale: ru-ru
ms.lasthandoff: 07/28/2017

---
# <a name="how-to-create-unsigned-friend-assemblies-c"></a><span data-ttu-id="447c4-102">Практическое руководство. Создание неподписанных дружественных сборок (C#)</span><span class="sxs-lookup"><span data-stu-id="447c4-102">How to: Create Unsigned Friend Assemblies (C#)</span></span>
<span data-ttu-id="447c4-103">В этом примере показано использование дружественных сборок с неподписанными сборками.</span><span class="sxs-lookup"><span data-stu-id="447c4-103">This example shows how to use friend assemblies with assemblies that are unsigned.</span></span>  
  
### <a name="to-create-an-assembly-and-a-friend-assembly"></a><span data-ttu-id="447c4-104">Создание сборки и дружественной сборки</span><span class="sxs-lookup"><span data-stu-id="447c4-104">To create an assembly and a friend assembly</span></span>  
  
1.  <span data-ttu-id="447c4-105">Откройте окно командной строки.</span><span class="sxs-lookup"><span data-stu-id="447c4-105">Open a command prompt.</span></span>  
  
2.  <span data-ttu-id="447c4-106">Создайте файл C# с именем `friend_signed_A.`, содержащий приведенный ниже код.</span><span class="sxs-lookup"><span data-stu-id="447c4-106">Create a C# file named `friend_signed_A.` that contains the following code.</span></span> <span data-ttu-id="447c4-107">Атрибут <xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute> используется в коде для объявления friend_signed_B в качестве дружественной сборки.</span><span class="sxs-lookup"><span data-stu-id="447c4-107">The code uses the <xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute> attribute to declare friend_signed_B as a friend assembly.</span></span>  
  
    ```csharp  
    // friend_unsigned_A.cs  
    // Compile with:   
    // csc /target:library friend_unsigned_A.cs  
    using System.Runtime.CompilerServices;  
    using System;  
  
    [assembly: InternalsVisibleTo("friend_unsigned_B")]  
  
    // Type is internal by default.  
    class Class1  
    {  
        public void Test()  
        {  
            Console.WriteLine("Class1.Test");  
        }  
    }  
  
    // Public type with internal member.  
    public class Class2  
    {  
        internal void Test()  
        {  
            Console.WriteLine("Class2.Test");  
        }  
    }  
    ```  
  
3.  <span data-ttu-id="447c4-108">Скомпилируйте и подпишите сборку friend_signed_A с помощью приведенной ниже команды.</span><span class="sxs-lookup"><span data-stu-id="447c4-108">Compile and sign friend_signed_A by using the following command.</span></span>  
  
    ```csharp  
    csc /target:library friend_unsigned_A.cs  
    ```  
  
4.  <span data-ttu-id="447c4-109">Создайте файл C# с именем `friend_unsigned_B`, содержащий приведенный ниже код.</span><span class="sxs-lookup"><span data-stu-id="447c4-109">Create a C# file named `friend_unsigned_B` that contains the following code.</span></span> <span data-ttu-id="447c4-110">Так как файл friend_unsigned_A задает friend_unsigned_B в качестве дружественной сборки, код friend_unsigned_B может обращаться к типам и членам `internal` из friend_unsigned_A.</span><span class="sxs-lookup"><span data-stu-id="447c4-110">Because friend_unsigned_A specifies friend_unsigned_B as a friend assembly, the code in friend_unsigned_B can access `internal` types and members from friend_unsigned_A.</span></span>  
  
    ```csharp  
    // friend_unsigned_B.cs  
    // Compile with:   
    // csc /r:friend_unsigned_A.dll /out:friend_unsigned_B.exe friend_unsigned_B.cs  
    public class Program  
    {  
        static void Main()  
        {  
            // Access an internal type.  
            Class1 inst1 = new Class1();  
            inst1.Test();  
  
            Class2 inst2 = new Class2();  
            // Access an internal member of a public type.  
            inst2.Test();  
  
            System.Console.ReadLine();  
        }  
    }  
    ```  
  
5.  <span data-ttu-id="447c4-111">Скомпилируйте сборку friend_signed_B с помощью приведенной ниже команды.</span><span class="sxs-lookup"><span data-stu-id="447c4-111">Compile friend_signed_B by using the following command.</span></span>  
  
    ```csharp  
    csc /r:friend_unsigned_A.dll /out:friend_unsigned_B.exe friend_unsigned_B.cs  
    ```  
  
     <span data-ttu-id="447c4-112">Имя сборки, созданной компилятором, должно соответствовать имени дружественной сборки, передаваемой атрибуту <xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute>.</span><span class="sxs-lookup"><span data-stu-id="447c4-112">The name of the assembly that is generated by the compiler must match the friend assembly name that is passed to the <xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute> attribute.</span></span> <span data-ttu-id="447c4-113">Необходимо явно указать имя выходной сборки (EXE или DLL) с помощью параметра компилятора `/out`.</span><span class="sxs-lookup"><span data-stu-id="447c4-113">You must explicitly specify the name of the output assembly (.exe or .dll) by using the `/out` compiler option.</span></span> <span data-ttu-id="447c4-114">Дополнительные сведения см. в разделе [/out (параметры компилятора C#)](../../../../csharp/language-reference/compiler-options/out-compiler-option.md).</span><span class="sxs-lookup"><span data-stu-id="447c4-114">For more information, see [/out (C# Compiler Options)](../../../../csharp/language-reference/compiler-options/out-compiler-option.md).</span></span>  
  
6.  <span data-ttu-id="447c4-115">Запустите файл friend_signed_B.exe.</span><span class="sxs-lookup"><span data-stu-id="447c4-115">Run the friend_signed_B.exe file.</span></span>  
  
     <span data-ttu-id="447c4-116">Программа выведет две строки: "Class1.Test" и "Class2.Test".</span><span class="sxs-lookup"><span data-stu-id="447c4-116">The program prints two strings: "Class1.Test" and "Class2.Test".</span></span>  
  
## <a name="net-framework-security"></a><span data-ttu-id="447c4-117">Безопасность платформы .NET Framework</span><span class="sxs-lookup"><span data-stu-id="447c4-117">.NET Framework Security</span></span>  
 <span data-ttu-id="447c4-118">Между атрибутом <xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute> и классом <xref:System.Security.Permissions.StrongNameIdentityPermission> существует определенное сходство.</span><span class="sxs-lookup"><span data-stu-id="447c4-118">There are similarities between the <xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute> attribute and the <xref:System.Security.Permissions.StrongNameIdentityPermission> class.</span></span> <span data-ttu-id="447c4-119">Основное отличие заключается в том, что для выполнения <xref:System.Security.Permissions.StrongNameIdentityPermission> в определенном разделе кода могут потребоваться разрешения системы безопасности, тогда как атрибут <xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute> определяет видимость членов и типов `internal`.</span><span class="sxs-lookup"><span data-stu-id="447c4-119">The main difference is that <xref:System.Security.Permissions.StrongNameIdentityPermission> can demand security permissions to run a particular section of code, whereas the <xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute> attribute controls the visibility of `internal` types and members.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="447c4-120">См. также</span><span class="sxs-lookup"><span data-stu-id="447c4-120">See Also</span></span>  
 <span data-ttu-id="447c4-121"><xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute></span><span class="sxs-lookup"><span data-stu-id="447c4-121"><xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute></span></span>   
 <span data-ttu-id="447c4-122">[Сборки и глобальный кэш сборок (C#)](../../../../csharp/programming-guide/concepts/assemblies-gac/index.md) </span><span class="sxs-lookup"><span data-stu-id="447c4-122">[Assemblies and the Global Assembly Cache (C#)](../../../../csharp/programming-guide/concepts/assemblies-gac/index.md) </span></span>  
 <span data-ttu-id="447c4-123">[Дружественные сборки (C#)](../../../../csharp/programming-guide/concepts/assemblies-gac/friend-assemblies.md) </span><span class="sxs-lookup"><span data-stu-id="447c4-123">[Friend Assemblies (C#)](../../../../csharp/programming-guide/concepts/assemblies-gac/friend-assemblies.md) </span></span>  
 <span data-ttu-id="447c4-124">[Практическое руководство. Создание подписанных дружественных сборок (C#)](../../../../csharp/programming-guide/concepts/assemblies-gac/how-to-create-signed-friend-assemblies.md) </span><span class="sxs-lookup"><span data-stu-id="447c4-124">[How to: Create Signed Friend Assemblies (C#)](../../../../csharp/programming-guide/concepts/assemblies-gac/how-to-create-signed-friend-assemblies.md) </span></span>  
 [<span data-ttu-id="447c4-125">Руководство по программированию на C#</span><span class="sxs-lookup"><span data-stu-id="447c4-125">C# Programming Guide</span></span>](../../../../csharp/programming-guide/index.md)
