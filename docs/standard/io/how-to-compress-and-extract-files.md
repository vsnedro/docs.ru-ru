---
title: Практическое руководство. Сжатие и извлечение файлов
description: Сжимайте и извлекайте файлы с помощью System.IO.Compression. Ознакомьтесь с примерами использования ZipFile, ZipArchive, ZipArchiveEntry, DeflateStream и GZipStream.
ms.date: 01/14/2019
dev_langs:
- csharp
- vb
helpviewer_keywords:
- I/O [.NET], compression
- compression
- compress files
ms.assetid: e9876165-3c60-4c84-a272-513e47acf579
ms.openlocfilehash: a1077c7277e0aa54e3c8883cfc27d93926485b8e
ms.sourcegitcommit: 965a5af7918acb0a3fd3baf342e15d511ef75188
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/18/2020
ms.locfileid: "94830861"
---
# <a name="how-to-compress-and-extract-files"></a><span data-ttu-id="b831b-104">Практическое руководство. Сжатие и извлечение файлов</span><span class="sxs-lookup"><span data-stu-id="b831b-104">How to: Compress and extract files</span></span>

<span data-ttu-id="b831b-105">Пространство имен <xref:System.IO.Compression> предоставляет следующие типы для сжатия и распаковки файлов и потоков.</span><span class="sxs-lookup"><span data-stu-id="b831b-105">The <xref:System.IO.Compression> namespace contains the following types for compressing and decompressing files and streams.</span></span> <span data-ttu-id="b831b-106">Вы также можете использовать эти типы для чтения и изменения содержимого сжатого файла.</span><span class="sxs-lookup"><span data-stu-id="b831b-106">You can also use these types to read and modify the contents of a compressed file.</span></span>

- <xref:System.IO.Compression.ZipFile>
- <xref:System.IO.Compression.ZipArchive>
- <xref:System.IO.Compression.ZipArchiveEntry>
- <xref:System.IO.Compression.DeflateStream>
- <xref:System.IO.Compression.GZipStream>

<span data-ttu-id="b831b-107">В примерах ниже показано несколько операций для работы со сжатыми файлами.</span><span class="sxs-lookup"><span data-stu-id="b831b-107">The following examples show some of the operations you can perform with compressed files.</span></span> <span data-ttu-id="b831b-108">Для этих примеров требуется добавить в проект следующие пакеты NuGet:</span><span class="sxs-lookup"><span data-stu-id="b831b-108">These examples require the following NuGet packages to be added to your project:</span></span>

- <span data-ttu-id="b831b-109">[System.IO.Compression](https://www.nuget.org/packages/System.IO.Compression);</span><span class="sxs-lookup"><span data-stu-id="b831b-109">[System.IO.Compression](https://www.nuget.org/packages/System.IO.Compression)</span></span>
- <span data-ttu-id="b831b-110">[System.IO.Compression.ZipFile](https://www.nuget.org/packages/System.IO.Compression.ZipFile).</span><span class="sxs-lookup"><span data-stu-id="b831b-110">[System.IO.Compression.ZipFile](https://www.nuget.org/packages/System.IO.Compression.ZipFile)</span></span>

<span data-ttu-id="b831b-111">Если вы используете .NET Framework, добавьте в проект ссылки на эти две библиотеки:</span><span class="sxs-lookup"><span data-stu-id="b831b-111">If you're using .NET Framework, add references to these two libraries to your project:</span></span>

- `System.IO.Compression`
- `System.IO.Compression.FileSystem`

## <a name="example-1-create-and-extract-a-zip-file"></a><span data-ttu-id="b831b-112">Пример 1: Создание и извлечение ZIP-файла</span><span class="sxs-lookup"><span data-stu-id="b831b-112">Example 1: Create and extract a .zip file</span></span>

<span data-ttu-id="b831b-113">В следующем примере показано, как создавать и извлекать сжатый файл *.zip* с помощью класса <xref:System.IO.Compression.ZipFile>.</span><span class="sxs-lookup"><span data-stu-id="b831b-113">The following example shows how to create and extract a compressed *.zip* file by using the <xref:System.IO.Compression.ZipFile> class.</span></span> <span data-ttu-id="b831b-114">Он сжимает содержимое папки в новый *ZIP*-файл и затем извлекает его в новую папку.</span><span class="sxs-lookup"><span data-stu-id="b831b-114">The example compresses the contents of a folder into a new *.zip* file, and then extracts the zip to a new folder.</span></span>

<span data-ttu-id="b831b-115">Чтобы запустить пример, создайте папку *start* в папке программы и заполните ее файлами для сжатия.</span><span class="sxs-lookup"><span data-stu-id="b831b-115">To run the sample, create a *start* folder in your program folder and populate it with files to zip.</span></span>

[!code-csharp[System.IO.Compression.ZipFile#1](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.io.compression.zipfile/cs/program1.cs#1)]
[!code-vb[System.IO.Compression.ZipFile#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.io.compression.zipfile/vb/program1.vb#1)]

## <a name="example-2-extract-specific-file-extensions"></a><span data-ttu-id="b831b-116">Пример 2: Извлечение файлов с определенными расширениями</span><span class="sxs-lookup"><span data-stu-id="b831b-116">Example 2: Extract specific file extensions</span></span>

<span data-ttu-id="b831b-117">В этом примере выполняется итерация по содержимому существующего *ZIP*-файла и извлекаются файлы с расширением *.txt*.</span><span class="sxs-lookup"><span data-stu-id="b831b-117">The next example iterates through the contents of an existing *.zip* file and extracts files that have a *.txt* extension.</span></span> <span data-ttu-id="b831b-118">Здесь используется класс <xref:System.IO.Compression.ZipArchive> для доступа к ZIP-файлу и класс <xref:System.IO.Compression.ZipArchiveEntry> для проверки отдельных элементов.</span><span class="sxs-lookup"><span data-stu-id="b831b-118">It uses the <xref:System.IO.Compression.ZipArchive> class to access the zip, and the <xref:System.IO.Compression.ZipArchiveEntry> class to inspect the individual entries.</span></span> <span data-ttu-id="b831b-119">Метод расширения <xref:System.IO.Compression.ZipFileExtensions.ExtractToFile%2A> для объекта <xref:System.IO.Compression.ZipArchiveEntry> доступен в классе <xref:System.IO.Compression.ZipFileExtensions?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="b831b-119">The extension method <xref:System.IO.Compression.ZipFileExtensions.ExtractToFile%2A> for the <xref:System.IO.Compression.ZipArchiveEntry> object is available in the <xref:System.IO.Compression.ZipFileExtensions?displayProperty=nameWithType> class.</span></span>

<span data-ttu-id="b831b-120">Чтобы запустить пример, поместите *ZIP*-файл с именем *result.zip* в папку программы.</span><span class="sxs-lookup"><span data-stu-id="b831b-120">To run the sample, place a *.zip* file called *result.zip* in your program folder.</span></span> <span data-ttu-id="b831b-121">По запросу укажите имя папки для извлечения.</span><span class="sxs-lookup"><span data-stu-id="b831b-121">When prompted, provide a folder name to extract to.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="b831b-122">При распаковке файлов важно убедиться в отсутствии вредоносных путей, которые могут вести за пределы каталога, в который вы извлекаете файлы.</span><span class="sxs-lookup"><span data-stu-id="b831b-122">When unzipping files, you must look for malicious file paths, which can escape out of the directory you unzip into.</span></span> <span data-ttu-id="b831b-123">Такая атака известна как обход путей.</span><span class="sxs-lookup"><span data-stu-id="b831b-123">This is known as a path traversal attack.</span></span> <span data-ttu-id="b831b-124">В следующем примере показано, как правильно проверить наличие вредоносных путей и безопасно извлечь файлы.</span><span class="sxs-lookup"><span data-stu-id="b831b-124">The following example demonstrates how to check for malicious file paths and provides a safe way to unzip.</span></span>

[!code-csharp[System.IO.Compression.ZipArchive#1](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.io.compression.ziparchive/cs/program1.cs#1)]
[!code-vb[System.IO.Compression.ZipArchive#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.io.compression.ziparchive/vb/program1.vb#1)]

## <a name="example-3-add-a-file-to-an-existing-zip"></a><span data-ttu-id="b831b-125">Пример 3. Добавление файла в существующий ZIP-файл</span><span class="sxs-lookup"><span data-stu-id="b831b-125">Example 3: Add a file to an existing zip</span></span>

<span data-ttu-id="b831b-126">В следующем примере используется класс <xref:System.IO.Compression.ZipArchive> для доступа к существующему *ZIP*-файлу и добавления в него файла.</span><span class="sxs-lookup"><span data-stu-id="b831b-126">The following example uses the <xref:System.IO.Compression.ZipArchive> class to access an existing *.zip* file, and adds a file to it.</span></span> <span data-ttu-id="b831b-127">Новый файл сжимается при добавлении в существующий ZIP-файл.</span><span class="sxs-lookup"><span data-stu-id="b831b-127">The new file gets compressed when you add it to the existing zip.</span></span>

[!code-csharp[System.IO.Compression.ZipArchiveMode#1](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.io.compression.ziparchivemode/cs/program1.cs#1)]
[!code-vb[System.IO.Compression.ZipArchiveMode#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.io.compression.ziparchivemode/vb/program1.vb#1)]

## <a name="example-4-compress-and-decompress-gz-files"></a><span data-ttu-id="b831b-128">Пример 4. Сжатие и распаковка GZ-файлов</span><span class="sxs-lookup"><span data-stu-id="b831b-128">Example 4: Compress and decompress .gz files</span></span>

<span data-ttu-id="b831b-129">Также вы можете использовать классы <xref:System.IO.Compression.GZipStream> и <xref:System.IO.Compression.DeflateStream> для сжатия и распаковки данных.</span><span class="sxs-lookup"><span data-stu-id="b831b-129">You can also use the <xref:System.IO.Compression.GZipStream> and <xref:System.IO.Compression.DeflateStream> classes to compress and decompress data.</span></span> <span data-ttu-id="b831b-130">Они применяют тот же алгоритм сжатия.</span><span class="sxs-lookup"><span data-stu-id="b831b-130">They use the same compression algorithm.</span></span> <span data-ttu-id="b831b-131">Вы можете распаковать объекты <xref:System.IO.Compression.GZipStream>, которые записаны в *GZ*-файл, с помощью многих распространенных средств.</span><span class="sxs-lookup"><span data-stu-id="b831b-131">You can decompress <xref:System.IO.Compression.GZipStream> objects that are written to a *.gz* file by using many common tools.</span></span> <span data-ttu-id="b831b-132">В следующем примере показано, как использовать класс <xref:System.IO.Compression.GZipStream> для сжатия и распаковки каталога файлов.</span><span class="sxs-lookup"><span data-stu-id="b831b-132">The following example shows how to compress and decompress a directory of files by using the <xref:System.IO.Compression.GZipStream> class:</span></span>

[!code-csharp[IO.Compression.GZip1#1](../../../samples/snippets/csharp/VS_Snippets_CLR/IO.Compression.GZip1/CS/gziptest.cs#1)]
[!code-vb[IO.Compression.GZip1#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/IO.Compression.GZip1/VB/gziptest.vb#1)]

## <a name="see-also"></a><span data-ttu-id="b831b-133">См. также</span><span class="sxs-lookup"><span data-stu-id="b831b-133">See also</span></span>

- <xref:System.IO.Compression.ZipArchive>  
- <xref:System.IO.Compression.ZipFile>  
- <xref:System.IO.Compression.ZipArchiveEntry>  
- <xref:System.IO.Compression.DeflateStream>  
- <xref:System.IO.Compression.GZipStream>  
- [<span data-ttu-id="b831b-134">Файловый и потоковый ввод-вывод</span><span class="sxs-lookup"><span data-stu-id="b831b-134">File and stream I/O</span></span>](index.md)
