---
title: "Практическое руководство. Как определить, является ли файл сборкой (C#)"
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
ms.assetid: ea5186bb-5bff-4dcb-bde9-d6ba4e2edd00
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
ms.openlocfilehash: ee402e28374040ab22173788dce421345b2ef3b5
ms.contentlocale: ru-ru
ms.lasthandoff: 07/28/2017

---
# <a name="how-to-determine-if-a-file-is-an-assembly-c"></a><span data-ttu-id="4446b-102">Практическое руководство. Как определить, является ли файл сборкой (C#)</span><span class="sxs-lookup"><span data-stu-id="4446b-102">How to: Determine If a File Is an Assembly (C#)</span></span>
<span data-ttu-id="4446b-103">Файл является сборкой только в том случае, если он является управляемым и содержит запись сборки в своих метаданных.</span><span class="sxs-lookup"><span data-stu-id="4446b-103">A file is an assembly if and only if it is managed, and contains an assembly entry in its metadata.</span></span> <span data-ttu-id="4446b-104">Дополнительные сведения о сборках и метаданных см. в разделе [Манифест сборки](https://msdn.microsoft.com/library/1w45z383).</span><span class="sxs-lookup"><span data-stu-id="4446b-104">For more information on assemblies and metadata, see the topic [Assembly Manifest](https://msdn.microsoft.com/library/1w45z383).</span></span>  
  
### <a name="how-to-manually-determine-if-a-file-is-an-assembly"></a><span data-ttu-id="4446b-105">Как вручную определить, является ли файл сборкой</span><span class="sxs-lookup"><span data-stu-id="4446b-105">How to manually determine if a file is an assembly</span></span>  
  
1.  <span data-ttu-id="4446b-106">Запустите [Ildasm.exe (дизассемблер IL)](https://msdn.microsoft.com/library/f7dy01k1).</span><span class="sxs-lookup"><span data-stu-id="4446b-106">Start the [Ildasm.exe (IL Disassembler)](https://msdn.microsoft.com/library/f7dy01k1).</span></span>  
  
2.  <span data-ttu-id="4446b-107">Загрузите файл, который нужно протестировать.</span><span class="sxs-lookup"><span data-stu-id="4446b-107">Load the file you wish to test.</span></span>  
  
3.  <span data-ttu-id="4446b-108">Если программа **ILDASM** сообщает, что файл не является переносимым исполняемым файлом (PE), то он не является сборкой.</span><span class="sxs-lookup"><span data-stu-id="4446b-108">If **ILDASM** reports that the file is not a portable executable (PE) file, then it is not an assembly.</span></span> <span data-ttu-id="4446b-109">Дополнительные сведения см. в разделе [Практическое руководство. Просмотр содержимого сборок](../../../../framework/app-domains/how-to-view-assembly-contents.md).</span><span class="sxs-lookup"><span data-stu-id="4446b-109">For more information, see the topic [How to: View Assembly Contents](../../../../framework/app-domains/how-to-view-assembly-contents.md).</span></span>  
  
### <a name="how-to-programmatically-determine-if-a-file-is-an-assembly"></a><span data-ttu-id="4446b-110">Как программно определить, является ли файл сборкой</span><span class="sxs-lookup"><span data-stu-id="4446b-110">How to programmatically determine if a file is an assembly</span></span>  
  
1.  <span data-ttu-id="4446b-111">Вызовите метод <xref:System.Reflection.AssemblyName.GetAssemblyName%2A>, указав полный путь к файлу и имя файла, который вы тестируете.</span><span class="sxs-lookup"><span data-stu-id="4446b-111">Call the <xref:System.Reflection.AssemblyName.GetAssemblyName%2A> method, passing the full file path and name of the file you are testing.</span></span>  
  
2.  <span data-ttu-id="4446b-112">Если возникает исключение <xref:System.BadImageFormatException>, значит файл не является сборкой.</span><span class="sxs-lookup"><span data-stu-id="4446b-112">If a <xref:System.BadImageFormatException> exception is thrown, the file is not an assembly.</span></span>  
  
## <a name="example"></a><span data-ttu-id="4446b-113">Пример</span><span class="sxs-lookup"><span data-stu-id="4446b-113">Example</span></span>  
 <span data-ttu-id="4446b-114">Этот пример кода проверяет, является ли библиотека DLL сборкой.</span><span class="sxs-lookup"><span data-stu-id="4446b-114">This example tests a DLL to see if it is an assembly.</span></span>  
  
```  
class TestAssembly  
{  
    static void Main()  
    {  
  
        try  
        {  
            System.Reflection.AssemblyName testAssembly =  
                System.Reflection.AssemblyName.GetAssemblyName(@"C:\Windows\Microsoft.NET\Framework\v3.5\System.Net.dll");  
  
            System.Console.WriteLine("Yes, the file is an assembly.");  
        }  
  
        catch (System.IO.FileNotFoundException)  
        {  
            System.Console.WriteLine("The file cannot be found.");  
        }  
  
        catch (System.BadImageFormatException)  
        {  
            System.Console.WriteLine("The file is not an assembly.");  
        }  
  
        catch (System.IO.FileLoadException)  
        {  
            System.Console.WriteLine("The assembly has already been loaded.");  
        }  
    }  
}  
/* Output (with .NET Framework 3.5 installed):  
    Yes, the file is an assembly.  
*/  
```  
  
 <span data-ttu-id="4446b-115">Метод <xref:System.Reflection.AssemblyName.GetAssemblyName%2A> загружает тестовый файл и освобождает его после того, как информация будет прочитана.</span><span class="sxs-lookup"><span data-stu-id="4446b-115">The <xref:System.Reflection.AssemblyName.GetAssemblyName%2A> method loads the test file, and then releases it once the information is read.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4446b-116">См. также</span><span class="sxs-lookup"><span data-stu-id="4446b-116">See Also</span></span>  
 <span data-ttu-id="4446b-117"><xref:System.Reflection.AssemblyName></span><span class="sxs-lookup"><span data-stu-id="4446b-117"><xref:System.Reflection.AssemblyName></span></span>   
 <span data-ttu-id="4446b-118">[Руководство по программированию на C#](../../../../csharp/programming-guide/index.md) </span><span class="sxs-lookup"><span data-stu-id="4446b-118">[C# Programming Guide](../../../../csharp/programming-guide/index.md) </span></span>  
 [<span data-ttu-id="4446b-119">Сборки и глобальный кэш сборок (C#)</span><span class="sxs-lookup"><span data-stu-id="4446b-119">Assemblies and the Global Assembly Cache (C#)</span></span>](../../../../csharp/programming-guide/concepts/assemblies-gac/index.md)
