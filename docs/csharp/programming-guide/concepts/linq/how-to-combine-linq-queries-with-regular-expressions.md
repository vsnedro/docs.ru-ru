---
title: Практическое руководство. Объединение запросов LINQ с помощью регулярных выражений (C#)
description: В этом примере показано использование класса Regex в C# для создания регулярного выражения для сопоставлений в текстовых строках.
ms.date: 07/20/2015
ms.assetid: 6b003b65-20a4-4ca2-929e-2ee3f215aecc
ms.openlocfilehash: af63d096e3c2f19ed557180d82d606989a016120
ms.sourcegitcommit: 04022ca5d00b2074e1b1ffdbd76bec4950697c4c
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/23/2020
ms.locfileid: "87105349"
---
# <a name="how-to-combine-linq-queries-with-regular-expressions-c"></a><span data-ttu-id="cf18a-103">Практическое руководство. Объединение запросов LINQ с помощью регулярных выражений (C#)</span><span class="sxs-lookup"><span data-stu-id="cf18a-103">How to combine LINQ queries with regular expressions (C#)</span></span>
<span data-ttu-id="cf18a-104">В этом примере показано, как использовать класс <xref:System.Text.RegularExpressions.Regex> при создании регулярного выражения для более сложных сопоставлений в текстовых строках.</span><span class="sxs-lookup"><span data-stu-id="cf18a-104">This example shows how to use the <xref:System.Text.RegularExpressions.Regex> class to create a regular expression for more complex matching in text strings.</span></span> <span data-ttu-id="cf18a-105">Запрос LINQ упрощает фильтрацию именно тех файлов, которые требуется найти с помощью регулярного выражения, и формирование результатов.</span><span class="sxs-lookup"><span data-stu-id="cf18a-105">The LINQ query makes it easy to filter on exactly the files that you want to search with the regular expression, and to shape the results.</span></span>  
  
## <a name="example"></a><span data-ttu-id="cf18a-106">Пример</span><span class="sxs-lookup"><span data-stu-id="cf18a-106">Example</span></span>  
  
```csharp  
class QueryWithRegEx  
{  
    public static void Main()  
    {  
        // Modify this path as necessary so that it accesses your version of Visual Studio.  
        string startFolder = @"C:\Program Files (x86)\Microsoft Visual Studio 14.0\";  
        // One of the following paths may be more appropriate on your computer.  
        //string startFolder = @"C:\Program Files (x86)\Microsoft Visual Studio\2017\";  
  
        // Take a snapshot of the file system.  
        IEnumerable<System.IO.FileInfo> fileList = GetFiles(startFolder);  
  
        // Create the regular expression to find all things "Visual".  
        System.Text.RegularExpressions.Regex searchTerm =  
            new System.Text.RegularExpressions.Regex(@"Visual (Basic|C#|C\+\+|Studio)");  
  
        // Search the contents of each .htm file.  
        // Remove the where clause to find even more matchedValues!  
        // This query produces a list of files where a match  
        // was found, and a list of the matchedValues in that file.  
        // Note: Explicit typing of "Match" in select clause.  
        // This is required because MatchCollection is not a
        // generic IEnumerable collection.  
        var queryMatchingFiles =  
            from file in fileList  
            where file.Extension == ".htm"  
            let fileText = System.IO.File.ReadAllText(file.FullName)  
            let matches = searchTerm.Matches(fileText)  
            where matches.Count > 0  
            select new  
            {  
                name = file.FullName,  
                matchedValues = from System.Text.RegularExpressions.Match match in matches  
                                select match.Value  
            };  
  
        // Execute the query.  
        Console.WriteLine("The term \"{0}\" was found in:", searchTerm.ToString());  
  
        foreach (var v in queryMatchingFiles)  
        {  
            // Trim the path a bit, then write
            // the file name in which a match was found.  
            string s = v.name.Substring(startFolder.Length - 1);  
            Console.WriteLine(s);  
  
            // For this file, write out all the matching strings  
            foreach (var v2 in v.matchedValues)  
            {  
                Console.WriteLine("  " + v2);  
            }  
        }  
  
        // Keep the console window open in debug mode  
        Console.WriteLine("Press any key to exit");  
        Console.ReadKey();  
    }  
  
    // This method assumes that the application has discovery
    // permissions for all folders under the specified path.  
    static IEnumerable<System.IO.FileInfo> GetFiles(string path)  
    {  
        if (!System.IO.Directory.Exists(path))  
            throw new System.IO.DirectoryNotFoundException();  
  
        string[] fileNames = null;  
        List<System.IO.FileInfo> files = new List<System.IO.FileInfo>();  
  
        fileNames = System.IO.Directory.GetFiles(path, "*.*", System.IO.SearchOption.AllDirectories);  
        foreach (string name in fileNames)  
        {  
            files.Add(new System.IO.FileInfo(name));  
        }  
        return files;  
    }  
}  
```  
  
 <span data-ttu-id="cf18a-107">Обратите внимание, что можно также запросить объект <xref:System.Text.RegularExpressions.MatchCollection>, возвращаемый поиском `RegEx`.</span><span class="sxs-lookup"><span data-stu-id="cf18a-107">Note that you can also query the <xref:System.Text.RegularExpressions.MatchCollection> object that is returned by a `RegEx` search.</span></span> <span data-ttu-id="cf18a-108">В этом примере в результатах создается только значение каждого совпадения.</span><span class="sxs-lookup"><span data-stu-id="cf18a-108">In this example only the value of each match is produced in the results.</span></span> <span data-ttu-id="cf18a-109">Тем не менее вы можете использовать LINQ для выполнения всех видов фильтрации, сортировки и группировки в этой коллекции.</span><span class="sxs-lookup"><span data-stu-id="cf18a-109">However, it is also possible to use LINQ to perform all kinds of filtering, sorting, and grouping on that collection.</span></span> <span data-ttu-id="cf18a-110">Так как <xref:System.Text.RegularExpressions.MatchCollection> является неуниверсальной коллекцией <xref:System.Collections.IEnumerable>, необходимо явно указать тип переменной диапазона в запросе.</span><span class="sxs-lookup"><span data-stu-id="cf18a-110">Because <xref:System.Text.RegularExpressions.MatchCollection> is a non-generic <xref:System.Collections.IEnumerable> collection, you have to explicitly state the type of the range variable in the query.</span></span>  
  
## <a name="compiling-the-code"></a><span data-ttu-id="cf18a-111">Компиляция кода</span><span class="sxs-lookup"><span data-stu-id="cf18a-111">Compiling the Code</span></span>  
 <span data-ttu-id="cf18a-112">Создайте проект консольного приложения C# с директивами `using` для пространств имен System.Linq и System.IO.</span><span class="sxs-lookup"><span data-stu-id="cf18a-112">Create a C# console application project with `using` directives for the System.Linq and System.IO namespaces.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cf18a-113">См. также</span><span class="sxs-lookup"><span data-stu-id="cf18a-113">See also</span></span>

- [<span data-ttu-id="cf18a-114">LINQ и строки (C#)</span><span class="sxs-lookup"><span data-stu-id="cf18a-114">LINQ and Strings (C#)</span></span>](./linq-and-strings.md)
- [<span data-ttu-id="cf18a-115">LINQ и каталоги файлов (C#)</span><span class="sxs-lookup"><span data-stu-id="cf18a-115">LINQ and File Directories (C#)</span></span>](./linq-and-file-directories.md)
