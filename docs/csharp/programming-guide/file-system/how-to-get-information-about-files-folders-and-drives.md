---
title: Руководство по программированию на C#. Получение сведений о файлах, папках и дисках
description: Сведения о получении данных о файлах, папках и дисках. Изучите пример кода и ознакомьтесь с дополнительными ресурсами.
ms.date: 07/20/2015
helpviewer_keywords:
- files [C#], getting information about
ms.assetid: 22fc2da6-5494-405b-995e-c0b99142a93e
ms.openlocfilehash: f696cd90f197bede1a64949d211a563ce9a18376
ms.sourcegitcommit: 6f58a5f75ceeb936f8ee5b786e9adb81a9a3bee9
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/28/2020
ms.locfileid: "87299933"
---
# <a name="how-to-get-information-about-files-folders-and-drives--c-programming-guide"></a><span data-ttu-id="c2866-104">Руководство по программированию на C#. Получение сведений о файлах, папках и дисках</span><span class="sxs-lookup"><span data-stu-id="c2866-104">How to get information about files, folders, and drives  (C# Programming Guide)</span></span>
<span data-ttu-id="c2866-105">На платформе .NET доступ к сведениям о файловой системе можно получить, используя следующие классы.</span><span class="sxs-lookup"><span data-stu-id="c2866-105">In .NET, you can access file system information by using the following classes:</span></span>  
  
- <xref:System.IO.FileInfo?displayProperty=nameWithType>  
  
- <xref:System.IO.DirectoryInfo?displayProperty=nameWithType>  
  
- <xref:System.IO.DriveInfo?displayProperty=nameWithType>  
  
- <xref:System.IO.Directory?displayProperty=nameWithType>  
  
- <xref:System.IO.File?displayProperty=nameWithType>  
  
 <span data-ttu-id="c2866-106">Классы <xref:System.IO.FileInfo> и <xref:System.IO.DirectoryInfo> представляют файл или каталог и содержат свойства, представляющие многие атрибуты файла, поддерживаемые файловой системой NTFS.</span><span class="sxs-lookup"><span data-stu-id="c2866-106">The <xref:System.IO.FileInfo> and <xref:System.IO.DirectoryInfo> classes represent a file or directory and contain properties that expose many of the file attributes that are supported by the NTFS file system.</span></span> <span data-ttu-id="c2866-107">Они также содержат методы для открытия, закрытия, перемещения и удаления файлов и папок.</span><span class="sxs-lookup"><span data-stu-id="c2866-107">They also contain methods for opening, closing, moving, and deleting files and folders.</span></span> <span data-ttu-id="c2866-108">Экземпляры этих классов можно создать, передав в конструктор строку, представляющую имя файла, папки или диска.</span><span class="sxs-lookup"><span data-stu-id="c2866-108">You can create instances of these classes by passing a string that represents the name of the file, folder, or drive in to the constructor:</span></span>  
  
```csharp  
System.IO.DriveInfo di = new System.IO.DriveInfo(@"C:\");  
```  
  
 <span data-ttu-id="c2866-109">Имена файлов, папок или дисков можно также получить с помощью вызова <xref:System.IO.DirectoryInfo.GetDirectories%2A?displayProperty=nameWithType>, <xref:System.IO.DirectoryInfo.GetFiles%2A?displayProperty=nameWithType> и <xref:System.IO.DriveInfo.RootDirectory%2A?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="c2866-109">You can also obtain the names of files, folders, or drives by using calls to <xref:System.IO.DirectoryInfo.GetDirectories%2A?displayProperty=nameWithType>, <xref:System.IO.DirectoryInfo.GetFiles%2A?displayProperty=nameWithType>, and <xref:System.IO.DriveInfo.RootDirectory%2A?displayProperty=nameWithType>.</span></span>  
  
 <span data-ttu-id="c2866-110">Классы <xref:System.IO.Directory?displayProperty=nameWithType> и <xref:System.IO.File?displayProperty=nameWithType> предоставляют статические методы для получения сведений о каталогах и файлах.</span><span class="sxs-lookup"><span data-stu-id="c2866-110">The <xref:System.IO.Directory?displayProperty=nameWithType> and <xref:System.IO.File?displayProperty=nameWithType> classes provide static methods for retrieving information about directories and files.</span></span>  
  
## <a name="example"></a><span data-ttu-id="c2866-111">Пример</span><span class="sxs-lookup"><span data-stu-id="c2866-111">Example</span></span>  
 <span data-ttu-id="c2866-112">В следующем примере показаны различные способы доступа к сведениям о файлах и папках.</span><span class="sxs-lookup"><span data-stu-id="c2866-112">The following example shows various ways to access information about files and folders.</span></span>  
  
 [!code-csharp[csFilesandFolders#6](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csFilesAndFolders/CS/FileIteration.cs#6)]  
  
## <a name="robust-programming"></a><span data-ttu-id="c2866-113">Отказоустойчивость</span><span class="sxs-lookup"><span data-stu-id="c2866-113">Robust Programming</span></span>  
 <span data-ttu-id="c2866-114">При обработке заданных пользователем строк, определяющих пути, необходимо также обрабатывать исключения для следующих условий:</span><span class="sxs-lookup"><span data-stu-id="c2866-114">When you process user-specified path strings, you should also handle exceptions for the following conditions:</span></span>  
  
- <span data-ttu-id="c2866-115">Неверное имя файла.</span><span class="sxs-lookup"><span data-stu-id="c2866-115">The file name is malformed.</span></span> <span data-ttu-id="c2866-116">Например, оно содержит недопустимые символы или состоит из одних пробелов.</span><span class="sxs-lookup"><span data-stu-id="c2866-116">For example, it contains invalid characters or only white space.</span></span>  
  
- <span data-ttu-id="c2866-117">Имя файла имеет значение NULL.</span><span class="sxs-lookup"><span data-stu-id="c2866-117">The file name is null.</span></span>  
  
- <span data-ttu-id="c2866-118">Имя файла больше максимальной длины, определенной системой.</span><span class="sxs-lookup"><span data-stu-id="c2866-118">The file name is longer than the system-defined maximum length.</span></span>  
  
- <span data-ttu-id="c2866-119">Имя файла содержит двоеточие (:).</span><span class="sxs-lookup"><span data-stu-id="c2866-119">The file name contains a colon (:).</span></span>  
  
 <span data-ttu-id="c2866-120">Если у приложения недостаточно прав для чтения указанного файла, метод `Exists` возвратит значение `false` независимо от существования указанного пути. Исключений этот метод не вызывает.</span><span class="sxs-lookup"><span data-stu-id="c2866-120">If the application does not have sufficient permissions to read the specified file, the `Exists` method returns `false` regardless of whether a path exists; the method does not throw an exception.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c2866-121">См. также</span><span class="sxs-lookup"><span data-stu-id="c2866-121">See also</span></span>

- <xref:System.IO?displayProperty=nameWithType>
- [<span data-ttu-id="c2866-122">Руководство по программированию на C#</span><span class="sxs-lookup"><span data-stu-id="c2866-122">C# Programming Guide</span></span>](../index.md)
- [<span data-ttu-id="c2866-123">Файловая система и реестр (руководство по программированию на C#)</span><span class="sxs-lookup"><span data-stu-id="c2866-123">File System and the Registry (C# Programming Guide)</span></span>](./index.md)
