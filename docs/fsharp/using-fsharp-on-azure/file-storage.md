---
title: Начало работы с хранилищем файлов Azure с помощью языка F#
description: Хранение данных (файлов) в облаке в хранилище файлов Azure и подключение к общей облачной папке из виртуальной машины Azure или из локального приложения под управлением Windows.
author: sylvanc
ms.date: 09/20/2016
ms.openlocfilehash: 2088442e05ba36b388a3324942ebbf8c7eb263dd
ms.sourcegitcommit: d9470d8b2278b33108332c05224d86049cb9484b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/17/2020
ms.locfileid: "81607471"
---
# <a name="get-started-with-azure-file-storage-using-f"></a><span data-ttu-id="4ca89-103">Начало работы с хранилищем файлов Azure с помощью F\#</span><span class="sxs-lookup"><span data-stu-id="4ca89-103">Get started with Azure File storage using F\#</span></span>

<span data-ttu-id="4ca89-104">Хранение файлов Azure — это служба, которая предлагает файлообменные доли в облаке с помощью стандартного [протокола Server Message Block (SMB).](https://msdn.microsoft.com/library/windows/desktop/aa365233.aspx)</span><span class="sxs-lookup"><span data-stu-id="4ca89-104">Azure File storage is a service that offers file shares in the cloud using the standard [Server Message Block (SMB) Protocol](https://msdn.microsoft.com/library/windows/desktop/aa365233.aspx).</span></span> <span data-ttu-id="4ca89-105">Поддерживаются версии SMB 2.1 и SMB 3.0.</span><span class="sxs-lookup"><span data-stu-id="4ca89-105">Both SMB 2.1 and SMB 3.0 are supported.</span></span> <span data-ttu-id="4ca89-106">Хранилище файлов Azure позволяет быстро и без дорогостоящей перезаписи выполнить перенос приложений прежних версий, связанных с общими папками.</span><span class="sxs-lookup"><span data-stu-id="4ca89-106">With Azure File storage, you can migrate legacy applications that rely on file shares to Azure quickly and without costly rewrites.</span></span> <span data-ttu-id="4ca89-107">Приложения, работающие на виртуальных машинах Azure, в облачных службах или на локальных клиентах, могут подключать общую папку в облаке так же, как настольное приложение подключает обычную общую папку SMB.</span><span class="sxs-lookup"><span data-stu-id="4ca89-107">Applications running in Azure virtual machines or cloud services or from on-premises clients can mount a file share in the cloud, just as a desktop application mounts a typical SMB share.</span></span> <span data-ttu-id="4ca89-108">Любое количество компонентов приложений может одновременно подключаться и получать доступ к ресурсам хранилища файлов.</span><span class="sxs-lookup"><span data-stu-id="4ca89-108">Any number of application components can then mount and access the File storage share simultaneously.</span></span>

<span data-ttu-id="4ca89-109">Для получения концептуального обзора хранения файлов, пожалуйста, ознакомьтесь [с руководством .NET для хранения файлов.](https://docs.microsoft.com/azure/storage/storage-dotnet-how-to-use-files)</span><span class="sxs-lookup"><span data-stu-id="4ca89-109">For a conceptual overview of file storage, please see [the .NET guide for file storage](https://docs.microsoft.com/azure/storage/storage-dotnet-how-to-use-files).</span></span>

## <a name="prerequisites"></a><span data-ttu-id="4ca89-110">Предварительные требования</span><span class="sxs-lookup"><span data-stu-id="4ca89-110">Prerequisites</span></span>

<span data-ttu-id="4ca89-111">Чтобы использовать это руководство, необходимо сначала [создать учетную запись хранения Azure.](https://docs.microsoft.com/azure/storage/storage-create-storage-account)</span><span class="sxs-lookup"><span data-stu-id="4ca89-111">To use this guide, you must first [create an Azure storage account](https://docs.microsoft.com/azure/storage/storage-create-storage-account).</span></span>
<span data-ttu-id="4ca89-112">Для этой учетной записи также понадобится ключ доступа к хранилищу.</span><span class="sxs-lookup"><span data-stu-id="4ca89-112">You'll also need your storage access key for this account.</span></span>

## <a name="create-an-f-script-and-start-f-interactive"></a><span data-ttu-id="4ca89-113">Создайте сценарий F и начните интерактивный f</span><span class="sxs-lookup"><span data-stu-id="4ca89-113">Create an F# Script and Start F# Interactive</span></span>

<span data-ttu-id="4ca89-114">Образцы в этой статье могут быть использованы как в приложении F, так и в скрипте F-образного шрифта.</span><span class="sxs-lookup"><span data-stu-id="4ca89-114">The samples in this article can be used in either an F# application or an F# script.</span></span> <span data-ttu-id="4ca89-115">Чтобы создать скрипт F,, создайте файл с расширением, `.fsx` например, `files.fsx`в среде разработки F..</span><span class="sxs-lookup"><span data-stu-id="4ca89-115">To create an F# script, create a file with the `.fsx` extension, for example `files.fsx`, in your F# development environment.</span></span>

<span data-ttu-id="4ca89-116">Затем используйте [менеджер пакетов,](package-management.md) такой как [Paket](https://fsprojects.github.io/Paket/) или [NuGet,](https://www.nuget.org/) чтобы установить `WindowsAzure.Storage` пакет и ссылку `WindowsAzure.Storage.dll` в свой скрипт с помощью директивы. `#r`</span><span class="sxs-lookup"><span data-stu-id="4ca89-116">Next, use a [package manager](package-management.md) such as [Paket](https://fsprojects.github.io/Paket/) or [NuGet](https://www.nuget.org/) to install the `WindowsAzure.Storage` package and reference `WindowsAzure.Storage.dll` in your script using a `#r` directive.</span></span>

### <a name="add-namespace-declarations"></a><span data-ttu-id="4ca89-117">Добавление объявлений пространств имен</span><span class="sxs-lookup"><span data-stu-id="4ca89-117">Add namespace declarations</span></span>

<span data-ttu-id="4ca89-118">Добавьте в начало файла `files.fsx` следующие инструкции `open`:</span><span class="sxs-lookup"><span data-stu-id="4ca89-118">Add the following `open` statements to the top of the `files.fsx` file:</span></span>

[!code-fsharp[FileStorage](~/samples/snippets/fsharp/azure/file-storage.fsx#L1-L5)]

### <a name="get-your-connection-string"></a><span data-ttu-id="4ca89-119">Получение строки подключения</span><span class="sxs-lookup"><span data-stu-id="4ca89-119">Get your connection string</span></span>

<span data-ttu-id="4ca89-120">Для этого учебника вам понадобится строка подключения к системе хранения Azure.</span><span class="sxs-lookup"><span data-stu-id="4ca89-120">You'll need an Azure Storage connection string for this tutorial.</span></span> <span data-ttu-id="4ca89-121">Для получения дополнительной информации о строках соединения [см.](https://docs.microsoft.com/azure/storage/storage-configure-connection-string)</span><span class="sxs-lookup"><span data-stu-id="4ca89-121">For more information about connection strings, see [Configure Storage Connection Strings](https://docs.microsoft.com/azure/storage/storage-configure-connection-string).</span></span>

<span data-ttu-id="4ca89-122">Для учебника, вы введете строку соединения в вашем скрипте, как это:</span><span class="sxs-lookup"><span data-stu-id="4ca89-122">For the tutorial, you'll enter your connection string in your script, like this:</span></span>

[!code-fsharp[FileStorage](~/samples/snippets/fsharp/azure/file-storage.fsx#L11-L11)]

<span data-ttu-id="4ca89-123">Однако это **не рекомендуется** для реальных проектов.</span><span class="sxs-lookup"><span data-stu-id="4ca89-123">However, this is **not recommended** for real projects.</span></span> <span data-ttu-id="4ca89-124">Ключ учетной записи хранения похож на корневой пароль для вашей учетной записи хранения.</span><span class="sxs-lookup"><span data-stu-id="4ca89-124">Your storage account key is similar to the root password for your storage account.</span></span> <span data-ttu-id="4ca89-125">Не забудьте защитить ключ учетной записи хранения.</span><span class="sxs-lookup"><span data-stu-id="4ca89-125">Always be careful to protect your storage account key.</span></span> <span data-ttu-id="4ca89-126">Не сообщайте его другим пользователям, не определяйте его в коде и не храните его в текстовом файле, доступном другим пользователям.</span><span class="sxs-lookup"><span data-stu-id="4ca89-126">Avoid distributing it to other users, hard-coding it, or saving it in a plain-text file that is accessible to others.</span></span> <span data-ttu-id="4ca89-127">Вы можете регенерировать ключ с помощью портала Azure, если считаете, что он может быть скомпрометирован.</span><span class="sxs-lookup"><span data-stu-id="4ca89-127">You can regenerate your key using the Azure Portal if you believe it may have been compromised.</span></span>

<span data-ttu-id="4ca89-128">Для реальных приложений лучший способ сохранить строку подключения к хранилищу — в файле конфигурации.</span><span class="sxs-lookup"><span data-stu-id="4ca89-128">For real applications, the best way to maintain your storage connection string is in a configuration file.</span></span> <span data-ttu-id="4ca89-129">Чтобы получить строку соединения из файла конфигурации, вы можете сделать это:</span><span class="sxs-lookup"><span data-stu-id="4ca89-129">To fetch the connection string from a configuration file, you can do this:</span></span>

[!code-fsharp[FileStorage](~/samples/snippets/fsharp/azure/file-storage.fsx#L13-L15)]

<span data-ttu-id="4ca89-130">Использование диспетчера конфигураций Azure не является обязательным.</span><span class="sxs-lookup"><span data-stu-id="4ca89-130">Using Azure Configuration Manager is optional.</span></span> <span data-ttu-id="4ca89-131">Можно также использовать API, например `ConfigurationManager` тип рамочного .NET.</span><span class="sxs-lookup"><span data-stu-id="4ca89-131">You can also use an API such as the .NET Framework's `ConfigurationManager` type.</span></span>

### <a name="parse-the-connection-string"></a><span data-ttu-id="4ca89-132">Проанализируйте строку подключения</span><span class="sxs-lookup"><span data-stu-id="4ca89-132">Parse the connection string</span></span>

<span data-ttu-id="4ca89-133">Чтобы разобрать строку соединения, используйте:</span><span class="sxs-lookup"><span data-stu-id="4ca89-133">To parse the connection string, use:</span></span>

[!code-fsharp[FileStorage](~/samples/snippets/fsharp/azure/file-storage.fsx#L21-L22)]

<span data-ttu-id="4ca89-134">Это вернет `CloudStorageAccount`.</span><span class="sxs-lookup"><span data-stu-id="4ca89-134">This will return a `CloudStorageAccount`.</span></span>

### <a name="create-the-file-service-client"></a><span data-ttu-id="4ca89-135">Создание клиента службы файлов</span><span class="sxs-lookup"><span data-stu-id="4ca89-135">Create the File service client</span></span>

<span data-ttu-id="4ca89-136">Тип `CloudFileClient` позволяет программно использовать файлы, хранящиеся в хранилище файлов.</span><span class="sxs-lookup"><span data-stu-id="4ca89-136">The `CloudFileClient` type enables you to programmatically use files stored in File storage.</span></span> <span data-ttu-id="4ca89-137">Вот один из способов создать клиента службы.</span><span class="sxs-lookup"><span data-stu-id="4ca89-137">Here's one way to create the service client:</span></span>

[!code-fsharp[FileStorage](~/samples/snippets/fsharp/azure/file-storage.fsx#L28-L28)]

<span data-ttu-id="4ca89-138">Теперь вы готовы писать код, который считывает данные и записывает данные в хранилище файлов.</span><span class="sxs-lookup"><span data-stu-id="4ca89-138">Now you are ready to write code that reads data from and writes data to File storage.</span></span>

## <a name="create-a-file-share"></a><span data-ttu-id="4ca89-139">Создание общей папки</span><span class="sxs-lookup"><span data-stu-id="4ca89-139">Create a file share</span></span>

<span data-ttu-id="4ca89-140">В этом примере показано, как создать общий файл, если он еще не существует:</span><span class="sxs-lookup"><span data-stu-id="4ca89-140">This example shows how to create a file share if it does not already exist:</span></span>

[!code-fsharp[FileStorage](~/samples/snippets/fsharp/azure/file-storage.fsx#L34-L35)]

## <a name="create-a-root-directory-and-a-subdirectory"></a><span data-ttu-id="4ca89-141">Создание корневого каталога и субдиректоров</span><span class="sxs-lookup"><span data-stu-id="4ca89-141">Create a root directory and a subdirectory</span></span>

<span data-ttu-id="4ca89-142">Здесь вы получите корневой каталог и получите подкаталог корня.</span><span class="sxs-lookup"><span data-stu-id="4ca89-142">Here, you get the root directory and get a sub-directory of the root.</span></span> <span data-ttu-id="4ca89-143">Вы создаете и то, и другое, если они еще не существуют.</span><span class="sxs-lookup"><span data-stu-id="4ca89-143">You create both if they don't already exist.</span></span>

[!code-fsharp[FileStorage](~/samples/snippets/fsharp/azure/file-storage.fsx#L41-L43)]

## <a name="upload-text-as-a-file"></a><span data-ttu-id="4ca89-144">Загрузка текста в виде файла</span><span class="sxs-lookup"><span data-stu-id="4ca89-144">Upload text as a file</span></span>

<span data-ttu-id="4ca89-145">В этом примере показано, как загрузить текст в файл.</span><span class="sxs-lookup"><span data-stu-id="4ca89-145">This example shows how to upload text as a file.</span></span>

[!code-fsharp[FileStorage](~/samples/snippets/fsharp/azure/file-storage.fsx#L49-L50)]

### <a name="download-a-file-to-a-local-copy-of-the-file"></a><span data-ttu-id="4ca89-146">Загрузите файл в локальную копию файла</span><span class="sxs-lookup"><span data-stu-id="4ca89-146">Download a file to a local copy of the file</span></span>

<span data-ttu-id="4ca89-147">Здесь вы загружаете только что созданный файл, поместив содержимое в локальный файл.</span><span class="sxs-lookup"><span data-stu-id="4ca89-147">Here you download the file just created, appending the contents to a local file.</span></span>

[!code-fsharp[FileStorage](~/samples/snippets/fsharp/azure/file-storage.fsx#L56-L56)]

### <a name="set-the-maximum-size-for-a-file-share"></a><span data-ttu-id="4ca89-148">Установка максимального размера для файлового ресурса</span><span class="sxs-lookup"><span data-stu-id="4ca89-148">Set the maximum size for a file share</span></span>

<span data-ttu-id="4ca89-149">В приведенном ниже примере показано, как проверить текущее использование данных в файловом ресурсе, а также задать для него квоту.</span><span class="sxs-lookup"><span data-stu-id="4ca89-149">The example below shows how to check the current usage for a share and how to set the quota for the share.</span></span> <span data-ttu-id="4ca89-150">`FetchAttributes`необходимо призвать к заполнению `Properties`доли `SetProperties` и распространению локальных изменений в хранилище файлов Azure.</span><span class="sxs-lookup"><span data-stu-id="4ca89-150">`FetchAttributes` must be called to populate a share's `Properties`, and `SetProperties` to propagate local changes to Azure File storage.</span></span>

[!code-fsharp[FileStorage](~/samples/snippets/fsharp/azure/file-storage.fsx#L62-L72)]

### <a name="generate-a-shared-access-signature-for-a-file-or-file-share"></a><span data-ttu-id="4ca89-151">Создание подписи общего доступа для файла или файлового ресурса</span><span class="sxs-lookup"><span data-stu-id="4ca89-151">Generate a shared access signature for a file or file share</span></span>

<span data-ttu-id="4ca89-152">Для файлового ресурса или отдельного файла можно создать подписанный URL-адрес (SAS).</span><span class="sxs-lookup"><span data-stu-id="4ca89-152">You can generate a shared access signature (SAS) for a file share or for an individual file.</span></span> <span data-ttu-id="4ca89-153">Также можно создать политики общего доступа на файловом ресурсе, чтобы управлять подписями общего доступа.</span><span class="sxs-lookup"><span data-stu-id="4ca89-153">You can also create a shared access policy on a file share to manage shared access signatures.</span></span> <span data-ttu-id="4ca89-154">Создание политики общего доступа рекомендуется, так как она позволяет отменить SAS, если она скомпрометирована.</span><span class="sxs-lookup"><span data-stu-id="4ca89-154">Creating a shared access policy is recommended, as it provides a means of revoking the SAS if it should be compromised.</span></span>

<span data-ttu-id="4ca89-155">В данном виде вы создаете общую политику доступа на акции, а затем используете эту политику, чтобы уделить ограничения для SAS в файле в доле.</span><span class="sxs-lookup"><span data-stu-id="4ca89-155">Here, you create a shared access policy on a share, and then use that policy to provide the constraints for a SAS on a file in the share.</span></span>

[!code-fsharp[FileStorage](~/samples/snippets/fsharp/azure/file-storage.fsx#L78-L94)]

<span data-ttu-id="4ca89-156">Дополнительные сведения см. в статьях [Использование подписанных URL-адресов (SAS)](https://docs.microsoft.com/azure/storage/storage-dotnet-shared-access-signature-part-1) и [Создание и использование подписанного URL-адреса в службе BLOB-объектов](https://docs.microsoft.com/azure/storage/storage-dotnet-shared-access-signature-part-2).</span><span class="sxs-lookup"><span data-stu-id="4ca89-156">For more information about creating and using shared access signatures, see [Using Shared Access Signatures (SAS)](https://docs.microsoft.com/azure/storage/storage-dotnet-shared-access-signature-part-1) and [Create and use a SAS with Blob storage](https://docs.microsoft.com/azure/storage/storage-dotnet-shared-access-signature-part-2).</span></span>

### <a name="copy-files"></a><span data-ttu-id="4ca89-157">Копирование файлов</span><span class="sxs-lookup"><span data-stu-id="4ca89-157">Copy files</span></span>

<span data-ttu-id="4ca89-158">Вы можете скопировать файл в другой файл или в каплю, или капли в файл.</span><span class="sxs-lookup"><span data-stu-id="4ca89-158">You can copy a file to another file or to a blob, or a blob to a file.</span></span> <span data-ttu-id="4ca89-159">Если вы копируете каплю в файл или файл в каплю, *необходимо* использовать общую подпись доступа (SAS) для проверки подлинности исходного объекта, даже если вы копируете в одной учетной записи хранилища.</span><span class="sxs-lookup"><span data-stu-id="4ca89-159">If you are copying a blob to a file, or a file to a blob, you *must* use a shared access signature (SAS) to authenticate the source object, even if you are copying within the same storage account.</span></span>

### <a name="copy-a-file-to-another-file"></a><span data-ttu-id="4ca89-160">Копирование файла в другой файл</span><span class="sxs-lookup"><span data-stu-id="4ca89-160">Copy a file to another file</span></span>

<span data-ttu-id="4ca89-161">Здесь вы копируете файл в другой файл в той же акции.</span><span class="sxs-lookup"><span data-stu-id="4ca89-161">Here, you copy a file to another file in the same share.</span></span> <span data-ttu-id="4ca89-162">Так как эта операция копирования осуществляет копирование между файлами в одной учетной записи хранения, для выполнения копирования можно использовать проверку подлинности Shared Key.</span><span class="sxs-lookup"><span data-stu-id="4ca89-162">Because this copy operation copies between files in the same storage account, you can use Shared Key authentication to perform the copy.</span></span>

[!code-fsharp[FileStorage](~/samples/snippets/fsharp/azure/file-storage.fsx#L100-L101)]

### <a name="copy-a-file-to-a-blob"></a><span data-ttu-id="4ca89-163">Копирование файла в большой двоичный объект</span><span class="sxs-lookup"><span data-stu-id="4ca89-163">Copy a file to a blob</span></span>

<span data-ttu-id="4ca89-164">Здесь вы создаете файл и копируете его в blob в одной учетной записи хранилища.</span><span class="sxs-lookup"><span data-stu-id="4ca89-164">Here, you create a file and copy it to a blob within the same storage account.</span></span> <span data-ttu-id="4ca89-165">Вы создаете SAS для исходного файла, который служба использует для проверки подлинности доступа к исходной файлу во время операции копирования.</span><span class="sxs-lookup"><span data-stu-id="4ca89-165">You create a SAS for the source file, which the service uses to authenticate access to the source file during the copy operation.</span></span>

[!code-fsharp[FileStorage](~/samples/snippets/fsharp/azure/file-storage.fsx#L107-L120)]

<span data-ttu-id="4ca89-166">Таким же образом можно скопировать BLOB-объект в файл.</span><span class="sxs-lookup"><span data-stu-id="4ca89-166">You can copy a blob to a file in the same way.</span></span> <span data-ttu-id="4ca89-167">Если исходным объектом является BLOB-объект, создайте SAS для проверки подлинности доступа к BLOB-объекту во время операции копирования.</span><span class="sxs-lookup"><span data-stu-id="4ca89-167">If the source object is a blob, then create a SAS to authenticate access to that blob during the copy operation.</span></span>

## <a name="troubleshooting-file-storage-using-metrics"></a><span data-ttu-id="4ca89-168">Устранение неполадок хранилища файлов с помощью метрик</span><span class="sxs-lookup"><span data-stu-id="4ca89-168">Troubleshooting File storage using metrics</span></span>

<span data-ttu-id="4ca89-169">Аналитика хранения данных Azure поддерживает метрики для хранения файлов.</span><span class="sxs-lookup"><span data-stu-id="4ca89-169">Azure Storage Analytics supports metrics for File storage.</span></span> <span data-ttu-id="4ca89-170">Данные метрик позволяют отслеживать запросы и диагностировать проблемы.</span><span class="sxs-lookup"><span data-stu-id="4ca89-170">With metrics data, you can trace requests and diagnose issues.</span></span>

<span data-ttu-id="4ca89-171">Вы можете включить метрики для хранения файлов с [портала Azure](https://portal.azure.com), или вы можете сделать это с F- q следующим образом:</span><span class="sxs-lookup"><span data-stu-id="4ca89-171">You can enable metrics for File storage from the [Azure Portal](https://portal.azure.com), or you can do it from F# like this:</span></span>

[!code-fsharp[FileStorage](~/samples/snippets/fsharp/azure/file-storage.fsx#L126-L140)]

## <a name="next-steps"></a><span data-ttu-id="4ca89-172">Следующие шаги</span><span class="sxs-lookup"><span data-stu-id="4ca89-172">Next steps</span></span>

<span data-ttu-id="4ca89-173">Дополнительную информацию о хранилище файлов Azure см. по этим ссылкам.</span><span class="sxs-lookup"><span data-stu-id="4ca89-173">See these links for more information about Azure File storage.</span></span>

### <a name="conceptual-articles-and-videos"></a><span data-ttu-id="4ca89-174">Тематические статьи и видео</span><span class="sxs-lookup"><span data-stu-id="4ca89-174">Conceptual articles and videos</span></span>

- [<span data-ttu-id="4ca89-175">Хранилище файлов Azure: удобная облачная файловая система SMB для Windows и Linux</span><span class="sxs-lookup"><span data-stu-id="4ca89-175">Azure Files Storage: a frictionless cloud SMB file system for Windows and Linux</span></span>](https://azure.microsoft.com/resources/videos/azurecon-2015-azure-files-storage-a-frictionless-cloud-smb-file-system-for-windows-and-linux/)
- [<span data-ttu-id="4ca89-176">Использование хранилища файлов Azure в Linux</span><span class="sxs-lookup"><span data-stu-id="4ca89-176">How to use Azure File Storage with Linux</span></span>](https://docs.microsoft.com/azure/storage/storage-how-to-use-files-linux)

### <a name="tooling-support-for-file-storage"></a><span data-ttu-id="4ca89-177">Средства для работы с хранилищем файлов</span><span class="sxs-lookup"><span data-stu-id="4ca89-177">Tooling support for File storage</span></span>

- [<span data-ttu-id="4ca89-178">Использование Azure PowerShell со службой хранилища Azure</span><span class="sxs-lookup"><span data-stu-id="4ca89-178">Using Azure PowerShell with Azure Storage</span></span>](https://docs.microsoft.com/azure/storage/storage-powershell-guide-full)
- [<span data-ttu-id="4ca89-179">Использование AzCopy со службой хранилища Microsoft Azure</span><span class="sxs-lookup"><span data-stu-id="4ca89-179">How to use AzCopy with Microsoft Azure Storage</span></span>](https://docs.microsoft.com/azure/storage/storage-use-azcopy)
- [<span data-ttu-id="4ca89-180">Создание, скачивание и составление списка больших двоичных объектов с помощью Azure CLI</span><span class="sxs-lookup"><span data-stu-id="4ca89-180">Create, download, and list blobs with Azure CLI</span></span>](https://docs.microsoft.com/azure/storage/blobs/storage-quickstart-blobs-cli#create-and-manage-file-shares)

### <a name="reference"></a><span data-ttu-id="4ca89-181">Справочник</span><span class="sxs-lookup"><span data-stu-id="4ca89-181">Reference</span></span>

- [<span data-ttu-id="4ca89-182">Справочник по клиентской библиотеке хранилища для .NET</span><span class="sxs-lookup"><span data-stu-id="4ca89-182">Storage Client Library for .NET reference</span></span>](https://msdn.microsoft.com/library/azure/mt347887.aspx)
- [<span data-ttu-id="4ca89-183">Справочник по REST API службы файлов</span><span class="sxs-lookup"><span data-stu-id="4ca89-183">File Service REST API reference</span></span>](/rest/api/storageservices/fileservices/File-Service-REST-API)

### <a name="blog-posts"></a><span data-ttu-id="4ca89-184">Записи блога</span><span class="sxs-lookup"><span data-stu-id="4ca89-184">Blog posts</span></span>

- [<span data-ttu-id="4ca89-185">Хранилище файлов Azure стало общедоступным</span><span class="sxs-lookup"><span data-stu-id="4ca89-185">Azure File storage is now generally available</span></span>](https://azure.microsoft.com/blog/azure-file-storage-now-generally-available/)
- [<span data-ttu-id="4ca89-186">Внутри хранения файлов Azure</span><span class="sxs-lookup"><span data-stu-id="4ca89-186">Inside Azure File Storage</span></span>](https://azure.microsoft.com/blog/inside-azure-file-storage/)
- [<span data-ttu-id="4ca89-187">Введение в службы файлов Microsoft Azure</span><span class="sxs-lookup"><span data-stu-id="4ca89-187">Introducing Microsoft Azure File Service</span></span>](https://docs.microsoft.com/archive/blogs/windowsazurestorage/introducing-microsoft-azure-file-service)
- [<span data-ttu-id="4ca89-188">Сохраняемые подключения к файлам Microsoft Azure</span><span class="sxs-lookup"><span data-stu-id="4ca89-188">Persisting connections to Microsoft Azure Files</span></span>](https://docs.microsoft.com/archive/blogs/windowsazurestorage/persisting-connections-to-microsoft-azure-files)
