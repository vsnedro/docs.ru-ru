---
title: Заполнение дерева XML из файловой системы (C#)
description: Узнайте, как заполнить дерево XML из файловой системы в C#. В этом примере показано заполнение дерева XML и выполнение запроса к дереву для вычисления общего размера всех файлов.
ms.date: 07/20/2015
ms.assetid: 2aa2ccac-4a22-47ae-9107-3bb8df232576
ms.openlocfilehash: 676261656be7d306294c9912b75edcb51a31cccc
ms.sourcegitcommit: 04022ca5d00b2074e1b1ffdbd76bec4950697c4c
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/23/2020
ms.locfileid: "87104757"
---
# <a name="how-to-populate-an-xml-tree-from-the-file-system-c"></a><span data-ttu-id="21e4a-104">Заполнение дерева XML из файловой системы (C#)</span><span class="sxs-lookup"><span data-stu-id="21e4a-104">How to populate an XML tree from the file system (C#)</span></span>
<span data-ttu-id="21e4a-105">Распространенным и полезным применением XML-деревьев является использование их в качестве иерархической структуры для хранения данных с именем и значением.</span><span class="sxs-lookup"><span data-stu-id="21e4a-105">A common and useful application of XML trees is as a hierarchical name/value data store.</span></span> <span data-ttu-id="21e4a-106">Можно заполнить дерево XML-данными, распределенными внутри иерархии, после чего выполнять по нему запросы, преобразования и, если необходимо, сериализацию.</span><span class="sxs-lookup"><span data-stu-id="21e4a-106">You can populate an XML tree with hierarchical data, and then query it, transform it, and if necessary, serialize it.</span></span> <span data-ttu-id="21e4a-107">В следующем сценарии многие виды семантических конструкций, присущих XML, например пространства имен и обработка пробельных символов, неважны.</span><span class="sxs-lookup"><span data-stu-id="21e4a-107">In this usage scenario, many of the XML specific semantics, such as namespaces and white space behavior, are not important.</span></span> <span data-ttu-id="21e4a-108">Вместо этого XML-дерево используется как небольшая иерархическая база данных для одного пользователя, которая находится в памяти.</span><span class="sxs-lookup"><span data-stu-id="21e4a-108">Instead, you are using the XML tree as a small, in memory, single user hierarchical database.</span></span>  
  
## <a name="example"></a><span data-ttu-id="21e4a-109">Пример</span><span class="sxs-lookup"><span data-stu-id="21e4a-109">Example</span></span>  
 <span data-ttu-id="21e4a-110">В следующем примере происходит заполнение XML-дерева из локальной файловой системы при помощи рекурсии.</span><span class="sxs-lookup"><span data-stu-id="21e4a-110">The following example populates an XML tree from the local file system using recursion.</span></span> <span data-ttu-id="21e4a-111">Затем выполняется запрос по дереву и вычисляется общий размер всех файлов в дереве.</span><span class="sxs-lookup"><span data-stu-id="21e4a-111">It then queries the tree, calculating the total of the sizes of all files in the tree.</span></span>  
  
```csharp  
class Program  
{  
    static XElement CreateFileSystemXmlTree(string source)  
    {  
        DirectoryInfo di = new DirectoryInfo(source);  
        return new XElement("Dir",  
            new XAttribute("Name", di.Name),  
            from d in Directory.GetDirectories(source)  
            select CreateFileSystemXmlTree(d),  
            from fi in di.GetFiles()  
            select new XElement("File",  
                new XElement("Name", fi.Name),  
                new XElement("Length", fi.Length)  
            )  
        );  
    }  
  
    static void Main(string[] args)  
    {  
        XElement fileSystemTree = CreateFileSystemXmlTree("C:/Tmp");  
        Console.WriteLine(fileSystemTree);  
        Console.WriteLine("------");  
        long totalFileSize =  
            (from f in fileSystemTree.Descendants("File")  
             select (long)f.Element("Length")).Sum();  
        Console.WriteLine("Total File Size:{0}", totalFileSize);  
    }  
}  
```  
  
 <span data-ttu-id="21e4a-112">Этот пример выводит данные примерно так:</span><span class="sxs-lookup"><span data-stu-id="21e4a-112">This example produces output similar to the following:</span></span>  
  
```xml  
<Dir Name="Tmp">  
  <Dir Name="ConsoleApplication1">  
    <Dir Name="bin">  
      <Dir Name="Debug">  
        <File>  
          <Name>ConsoleApplication1.exe</Name>  
          <Length>4608</Length>  
        </File>  
        <File>  
          <Name>ConsoleApplication1.pdb</Name>  
          <Length>11776</Length>  
        </File>  
        <File>  
          <Name>ConsoleApplication1.vshost.exe</Name>  
          <Length>9568</Length>  
        </File>  
        <File>  
          <Name>ConsoleApplication1.vshost.exe.manifest</Name>  
          <Length>473</Length>  
        </File>  
      </Dir>  
    </Dir>  
    <Dir Name="obj">  
      <Dir Name="Debug">  
        <Dir Name="TempPE" />  
        <File>  
          <Name>ConsoleApplication1.csproj.FileListAbsolute.txt</Name>  
          <Length>322</Length>  
        </File>  
        <File>  
          <Name>ConsoleApplication1.exe</Name>  
          <Length>4608</Length>  
        </File>  
        <File>  
          <Name>ConsoleApplication1.pdb</Name>  
          <Length>11776</Length>  
        </File>  
      </Dir>  
    </Dir>  
    <Dir Name="Properties">  
      <File>  
        <Name>AssemblyInfo.cs</Name>  
        <Length>1454</Length>  
      </File>  
    </Dir>  
    <File>  
      <Name>ConsoleApplication1.csproj</Name>  
      <Length>2546</Length>  
    </File>  
    <File>  
      <Name>ConsoleApplication1.sln</Name>  
      <Length>937</Length>  
    </File>  
    <File>  
      <Name>ConsoleApplication1.suo</Name>  
      <Length>10752</Length>  
    </File>  
    <File>  
      <Name>Program.cs</Name>  
      <Length>269</Length>  
    </File>  
  </Dir>  
</Dir>  
------  
Total File Size:59089  
```  
