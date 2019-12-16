---
title: "Практическое руководство: Создание подписанных дружественных сборок (Visual Basic) | Документы Microsoft"
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- VB
ms.assetid: f2afd83d-b044-484b-a56d-56d0a8a40647
caps.latest.revision: 4
author: dotnet-bot
ms.author: dotnetcontent
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
ms.translationtype: Machine Translation
ms.sourcegitcommit: 9f5b8ebb69c9206ff90b05e748c64d29d82f7a16
ms.openlocfilehash: a8a7df331c8cd93de45d902cb9b6c67460952c6d
ms.contentlocale: ru-ru
ms.lasthandoff: 04/12/2017

---
# <a name="how-to-create-signed-friend-assemblies-visual-basic"></a><span data-ttu-id="6b20d-102">Практическое руководство: Создание подписанных дружественных сборок (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="6b20d-102">How to: Create Signed Friend Assemblies (Visual Basic)</span></span>
<span data-ttu-id="6b20d-103">В этом примере показано использование дружественных сборок со сборками, имеющими строгие имена.</span><span class="sxs-lookup"><span data-stu-id="6b20d-103">This example shows how to use friend assemblies with assemblies that have strong names.</span></span> <span data-ttu-id="6b20d-104">Обе сборки должны иметь строгое имя.</span><span class="sxs-lookup"><span data-stu-id="6b20d-104">Both assemblies must be strong named.</span></span> <span data-ttu-id="6b20d-105">Хотя обе сборки этого примера используют одинаковые ключи, для двух сборок можно использовать различные ключи.</span><span class="sxs-lookup"><span data-stu-id="6b20d-105">Although both assemblies in this example use the same keys, you could use different keys for two assemblies.</span></span>  
  
### <a name="to-create-a-signed-assembly-and-a-friend-assembly"></a><span data-ttu-id="6b20d-106">Для создания подписанной и дружественной сборки</span><span class="sxs-lookup"><span data-stu-id="6b20d-106">To create a signed assembly and a friend assembly</span></span>  
  
1.  <span data-ttu-id="6b20d-107">Откройте окно командной строки.</span><span class="sxs-lookup"><span data-stu-id="6b20d-107">Open a command prompt.</span></span>  
  
2.  <span data-ttu-id="6b20d-108">Используйте следующую последовательность команд с помощью программы строгих имен для формирования файла ключа и отображения его открытого ключа.</span><span class="sxs-lookup"><span data-stu-id="6b20d-108">Use the following sequence of commands with the Strong Name tool to generate a keyfile and to display its public key.</span></span> <span data-ttu-id="6b20d-109">Дополнительные сведения см. на странице [Sn.exe (Strong Name Tool)](https://msdn.microsoft.com/library/k5b5tt23) (Sn.exe: средство строгих имен).</span><span class="sxs-lookup"><span data-stu-id="6b20d-109">For more information, see [Sn.exe (Strong Name Tool)](https://msdn.microsoft.com/library/k5b5tt23).</span></span>  
  
    1.  <span data-ttu-id="6b20d-110">Создание ключа строгого имени для этого примера и сохранить его в файл FriendAssemblies.snk:</span><span class="sxs-lookup"><span data-stu-id="6b20d-110">Generate a strong-name key for this example and store it in the file FriendAssemblies.snk:</span></span>  
  
         `sn -k FriendAssemblies.snk`  
  
    2.  <span data-ttu-id="6b20d-111">Извлечь открытый ключ из FriendAssemblies.snk и перевести ее в FriendAssemblies.publickey:</span><span class="sxs-lookup"><span data-stu-id="6b20d-111">Extract the public key from FriendAssemblies.snk and put it into FriendAssemblies.publickey:</span></span>  
  
         `sn -p FriendAssemblies.snk FriendAssemblies.publickey`  
  
    3.  <span data-ttu-id="6b20d-112">Для отображения открытого ключа, хранящегося в файле FriendAssemblies.publickey:</span><span class="sxs-lookup"><span data-stu-id="6b20d-112">Display the public key stored in the file FriendAssemblies.publickey:</span></span>  
  
         `sn -tp FriendAssemblies.publickey`  
  
3.  <span data-ttu-id="6b20d-113">Создайте файл Visual Basic с именем `friend_signed_A` , содержащий следующий код.</span><span class="sxs-lookup"><span data-stu-id="6b20d-113">Create a Visual Basic file named `friend_signed_A` that contains the following code.</span></span> <span data-ttu-id="6b20d-114">Код использует <xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute>атрибут для объявления friend_signed_B в качестве дружественной сборки.</xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute></span><span class="sxs-lookup"><span data-stu-id="6b20d-114">The code uses the <xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute> attribute to declare friend_signed_B as a friend assembly.</span></span>  
  
     <span data-ttu-id="6b20d-115">Программа строгих имен создает новый открытый ключ, каждый раз при его запуске.</span><span class="sxs-lookup"><span data-stu-id="6b20d-115">The Strong Name tool generates a new public key every time it runs.</span></span> <span data-ttu-id="6b20d-116">Таким образом необходимо заменить открытый ключ в следующем коде с помощью открытого ключа, который только что созданную, как показано в следующем примере.</span><span class="sxs-lookup"><span data-stu-id="6b20d-116">Therefore, you must replace the public key in the following code with the public key you just generated, as shown in the following example.</span></span>  
  
    ```vb  
    ' friend_signed_A.vb  
    ' Compile with:   
    ' Vbc /target:library /keyfile:FriendAssemblies.snk friend_signed_A.vb  
    Imports System.Runtime.CompilerServices  
  
    <Assembly: InternalsVisibleTo("friend_signed_B, PublicKey=0024000004800000940000000602000000240000525341310004000001000100e3aedce99b7e10823920206f8e46cd5558b4ec7345bd1a5b201ffe71660625dcb8f9a08687d881c8f65a0dcf042f81475d2e88f3e3e273c8311ee40f952db306c02fbfc5d8bc6ee1e924e6ec8fe8c01932e0648a0d3e5695134af3bb7fab370d3012d083fa6b83179dd3d031053f72fc1f7da8459140b0af5afc4d2804deccb6")>   
    Public Class Class1  
        Public Sub Test()  
            System.Console.WriteLine("Class1.Test")  
            System.Console.ReadLine()  
        End Sub  
    End Class  
    ```  
  
4.  <span data-ttu-id="6b20d-117">Откомпилируйте и подпишите сборку friend_signed_A с помощью следующей команды.</span><span class="sxs-lookup"><span data-stu-id="6b20d-117">Compile and sign friend_signed_A by using the following command.</span></span>  
  
    ```vb  
    Vbc /target:library /keyfile:FriendAssemblies.snk friend_signed_A.vb  
    ```  
  
5.  <span data-ttu-id="6b20d-118">Создайте файл Visual Basic с именем `friend_signed_B` и содержит следующий код.</span><span class="sxs-lookup"><span data-stu-id="6b20d-118">Create a Visual Basic file that is named `friend_signed_B` and contains the following code.</span></span> <span data-ttu-id="6b20d-119">Поскольку сборку friend_signed_A указывает сборку friend_signed_B в качестве дружественной сборки, могут обращаться к кода в сборку friend_signed_B `Friend` типы и члены в сборку friend_signed_A.</span><span class="sxs-lookup"><span data-stu-id="6b20d-119">Because friend_signed_A specifies friend_signed_B as a friend assembly, the code in friend_signed_B can access `Friend` types and members from friend_signed_A.</span></span> <span data-ttu-id="6b20d-120">Файл содержит следующий код.</span><span class="sxs-lookup"><span data-stu-id="6b20d-120">The file contains the following code.</span></span>  
  
    ```vb  
    ' friend_signed_B.vb  
    ' Compile with:   
    ' Vbc /keyfile:FriendAssemblies.snk /r:friend_signed_A.dll friend_signed_B.vb  
    Module Sample  
        Public Sub Main()  
            Dim inst As New Class1  
            inst.Test()  
        End Sub  
    End Module  
    ```  
  
6.  <span data-ttu-id="6b20d-121">Откомпилируйте и подпишите сборку friend_signed_B с помощью следующей команды.</span><span class="sxs-lookup"><span data-stu-id="6b20d-121">Compile and sign friend_signed_B by using the following command.</span></span>  
  
    ```vb  
    Vbc /keyfile:FriendAssemblies.snk /r:friend_signed_A.dll friend_signed_B.vb  
    ```  
  
     <span data-ttu-id="6b20d-122">Имя сборки, созданный компилятором, должно соответствовать имя дружественной сборки, передаваемый <xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute>атрибут.</xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute></span><span class="sxs-lookup"><span data-stu-id="6b20d-122">The name of the assembly generated by the compiler must match the friend assembly name passed to the <xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute> attribute.</span></span> <span data-ttu-id="6b20d-123">Можно явно задать сборку, используя `/out` параметр компилятора.</span><span class="sxs-lookup"><span data-stu-id="6b20d-123">You can explicitly set the assembly by using the `/out` compiler option.</span></span> <span data-ttu-id="6b20d-124">Дополнительные сведения см. в разделе [/out (Visual Basic)](../../../../visual-basic/reference/command-line-compiler/out.md).</span><span class="sxs-lookup"><span data-stu-id="6b20d-124">For more information, see [/out (Visual Basic)](../../../../visual-basic/reference/command-line-compiler/out.md).</span></span>  
  
7.  <span data-ttu-id="6b20d-125">Запустите файл friend_signed_B.exe.</span><span class="sxs-lookup"><span data-stu-id="6b20d-125">Run the friend_signed_B.exe file.</span></span>  
  
     <span data-ttu-id="6b20d-126">Программа выводит строку «Class1.Test».</span><span class="sxs-lookup"><span data-stu-id="6b20d-126">The program prints the string "Class1.Test".</span></span>  
  
## <a name="net-framework-security"></a><span data-ttu-id="6b20d-127">Безопасность платформы .NET Framework</span><span class="sxs-lookup"><span data-stu-id="6b20d-127">.NET Framework Security</span></span>  
 <span data-ttu-id="6b20d-128">Существует сходство между <xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute>атрибутом и <xref:System.Security.Permissions.StrongNameIdentityPermission>класса.</xref:System.Security.Permissions.StrongNameIdentityPermission> </xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute></span><span class="sxs-lookup"><span data-stu-id="6b20d-128">There are similarities between the <xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute> attribute and the <xref:System.Security.Permissions.StrongNameIdentityPermission> class.</span></span> <span data-ttu-id="6b20d-129">Основное различие заключается в, <xref:System.Security.Permissions.StrongNameIdentityPermission>может потребовать разрешения безопасности для выполнения определенного раздела кода, тогда как <xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute>атрибут управляет видимостью `Friend` типы и члены.</xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute> </xref:System.Security.Permissions.StrongNameIdentityPermission></span><span class="sxs-lookup"><span data-stu-id="6b20d-129">The main difference is that <xref:System.Security.Permissions.StrongNameIdentityPermission> can demand security permissions to run a particular section of code, whereas the <xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute> attribute controls the visibility of `Friend` types and members.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6b20d-130">См. также</span><span class="sxs-lookup"><span data-stu-id="6b20d-130">See Also</span></span>  
 <span data-ttu-id="6b20d-131"><xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute></xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute></span><span class="sxs-lookup"><span data-stu-id="6b20d-131"><xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute></span></span>   
<span data-ttu-id="6b20d-132"> [Сборки и глобальный кэш сборок (Visual Basic)](../../../../visual-basic/programming-guide/concepts/assemblies-gac/index.md) </span><span class="sxs-lookup"><span data-stu-id="6b20d-132"> [Assemblies and the Global Assembly Cache (Visual Basic)](../../../../visual-basic/programming-guide/concepts/assemblies-gac/index.md) </span></span>  
<span data-ttu-id="6b20d-133"> [Дружественные сборки (Visual Basic)](../../../../visual-basic/programming-guide/concepts/assemblies-gac/friend-assemblies.md) </span><span class="sxs-lookup"><span data-stu-id="6b20d-133"> [Friend Assemblies (Visual Basic)](../../../../visual-basic/programming-guide/concepts/assemblies-gac/friend-assemblies.md) </span></span>  
<span data-ttu-id="6b20d-134"> [Практическое руководство: создание неподписанных дружественных сборок (Visual Basic)](../../../../visual-basic/programming-guide/concepts/assemblies-gac/how-to-create-unsigned-friend-assemblies.md) </span><span class="sxs-lookup"><span data-stu-id="6b20d-134"> [How to: Create Unsigned Friend Assemblies (Visual Basic)](../../../../visual-basic/programming-guide/concepts/assemblies-gac/how-to-create-unsigned-friend-assemblies.md) </span></span>  
<span data-ttu-id="6b20d-135"> [/ keyfile](../../../../visual-basic/reference/command-line-compiler/keyfile.md) </span><span class="sxs-lookup"><span data-stu-id="6b20d-135"> [/keyfile](../../../../visual-basic/reference/command-line-compiler/keyfile.md) </span></span>  
<span data-ttu-id="6b20d-136"> [Sn.exe (средство строгих имен)](https://msdn.microsoft.com/library/k5b5tt23) </span><span class="sxs-lookup"><span data-stu-id="6b20d-136"> [Sn.exe (Strong Name Tool)](https://msdn.microsoft.com/library/k5b5tt23) </span></span>  
<span data-ttu-id="6b20d-137"> [Создание и использование сборок со строгими именами](https://msdn.microsoft.com/library/xwb8f617) </span><span class="sxs-lookup"><span data-stu-id="6b20d-137"> [Creating and Using Strong-Named Assemblies](https://msdn.microsoft.com/library/xwb8f617) </span></span>  
<span data-ttu-id="6b20d-138"> [Основные понятия программирования](../../../../visual-basic/programming-guide/concepts/index.md)</span><span class="sxs-lookup"><span data-stu-id="6b20d-138"> [Programming Concepts](../../../../visual-basic/programming-guide/concepts/index.md)</span></span>