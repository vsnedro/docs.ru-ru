---
title: Начало работы с хранилищем файлов Azure с помощью языка F#
description: Хранение данных (файлов) в облаке в хранилище файлов Azure и подключение к общей облачной папке из виртуальной машины Azure или из локального приложения под управлением Windows.
author: sylvanc
ms.date: 09/20/2016
ms.openlocfilehash: 1b38ee53f2f73f7b7f4ee12f712f487cb726d41e
ms.sourcegitcommit: 465547886a1224a5435c3ac349c805e39ce77706
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/21/2020
ms.locfileid: "81739594"
---
# <a name="get-started-with-azure-file-storage-using-f"></a>Начало работы с хранилищем файлов Azure с помощью F\#

Хранение файлов Azure — это служба, которая предлагает файлообменные доли в облаке с помощью стандартного [протокола Server Message Block (SMB).](https://msdn.microsoft.com/library/windows/desktop/aa365233.aspx) Поддерживаются версии SMB 2.1 и SMB 3.0. Хранилище файлов Azure позволяет быстро и без дорогостоящей перезаписи выполнить перенос приложений прежних версий, связанных с общими папками. Приложения, работающие на виртуальных машинах Azure, в облачных службах или на локальных клиентах, могут подключать общую папку в облаке так же, как настольное приложение подключает обычную общую папку SMB. Любое количество компонентов приложений может одновременно подключаться и получать доступ к ресурсам хранилища файлов.

Для концептуального обзора хранения [the .NET guide for file storage](https://docs.microsoft.com/azure/storage/storage-dotnet-how-to-use-files)файлов см.

## <a name="prerequisites"></a>Предварительные требования

Чтобы использовать это руководство, необходимо сначала [создать учетную запись хранения Azure.](https://docs.microsoft.com/azure/storage/storage-create-storage-account)
Для этой учетной записи также понадобится ключ доступа к хранилищу.

## <a name="create-an-f-script-and-start-f-interactive"></a>Создайте сценарий F и начните интерактивный f

Образцы в этой статье могут быть использованы как в приложении F, так и в скрипте F-образного шрифта. Чтобы создать скрипт F,, создайте файл с расширением, `.fsx` например, `files.fsx`в среде разработки F..

Затем используйте [менеджер пакетов,](package-management.md) такой как [Paket](https://fsprojects.github.io/Paket/) или [NuGet,](https://www.nuget.org/) чтобы установить `WindowsAzure.Storage` пакет и ссылку `WindowsAzure.Storage.dll` в свой скрипт с помощью директивы. `#r`

### <a name="add-namespace-declarations"></a>Добавление объявлений пространств имен

Добавьте в начало файла `files.fsx` следующие инструкции `open`:

[!code-fsharp[FileStorage](~/samples/snippets/fsharp/azure/file-storage.fsx#L1-L5)]

### <a name="get-your-connection-string"></a>Получение строки подключения

Для этого учебника вам понадобится строка подключения к системе хранения Azure. Для получения дополнительной информации о строках соединения [см.](https://docs.microsoft.com/azure/storage/storage-configure-connection-string)

Для учебника, вы введете строку соединения в вашем скрипте, как это:

[!code-fsharp[FileStorage](~/samples/snippets/fsharp/azure/file-storage.fsx#L11-L11)]

Однако это **не рекомендуется** для реальных проектов. Ключ учетной записи хранения похож на корневой пароль для вашей учетной записи хранения. Не забудьте защитить ключ учетной записи хранения. Не сообщайте его другим пользователям, не определяйте его в коде и не храните его в текстовом файле, доступном другим пользователям. Вы можете регенерировать ключ с помощью портала Azure, если считаете, что он может быть скомпрометирован.

Для реальных приложений лучший способ сохранить строку подключения к хранилищу — в файле конфигурации. Чтобы получить строку соединения из файла конфигурации, вы можете сделать это:

[!code-fsharp[FileStorage](~/samples/snippets/fsharp/azure/file-storage.fsx#L13-L15)]

Использование диспетчера конфигураций Azure не является обязательным. Можно также использовать API, например `ConfigurationManager` тип рамочного .NET.

### <a name="parse-the-connection-string"></a>Проанализируйте строку подключения

Чтобы разобрать строку соединения, используйте:

[!code-fsharp[FileStorage](~/samples/snippets/fsharp/azure/file-storage.fsx#L21-L22)]

Это вернет `CloudStorageAccount`.

### <a name="create-the-file-service-client"></a>Создание клиента службы файлов

Тип `CloudFileClient` позволяет программно использовать файлы, хранящиеся в хранилище файлов. Вот один из способов создать клиента службы.

[!code-fsharp[FileStorage](~/samples/snippets/fsharp/azure/file-storage.fsx#L28-L28)]

Теперь вы готовы писать код, который считывает данные и записывает данные в хранилище файлов.

## <a name="create-a-file-share"></a>Создание общей папки

В этом примере показано, как создать общий файл, если он еще не существует:

[!code-fsharp[FileStorage](~/samples/snippets/fsharp/azure/file-storage.fsx#L34-L35)]

## <a name="create-a-root-directory-and-a-subdirectory"></a>Создание корневого каталога и субдиректоров

Здесь вы получаете корневой каталог и получаете субдиректорию корня. Вы создаете и то, и другое, если они еще не существуют.

[!code-fsharp[FileStorage](~/samples/snippets/fsharp/azure/file-storage.fsx#L41-L43)]

## <a name="upload-text-as-a-file"></a>Загрузка текста в виде файла

В этом примере показано, как загрузить текст в файл.

[!code-fsharp[FileStorage](~/samples/snippets/fsharp/azure/file-storage.fsx#L49-L50)]

### <a name="download-a-file-to-a-local-copy-of-the-file"></a>Загрузите файл в локальную копию файла

Здесь вы загружаете только что созданный файл, поместив содержимое в локальный файл.

[!code-fsharp[FileStorage](~/samples/snippets/fsharp/azure/file-storage.fsx#L56-L56)]

### <a name="set-the-maximum-size-for-a-file-share"></a>Установка максимального размера для файлового ресурса

В приведенном ниже примере показано, как проверить текущее использование данных в файловом ресурсе, а также задать для него квоту. `FetchAttributes`необходимо призвать к заполнению `Properties`доли `SetProperties` и распространению локальных изменений в хранилище файлов Azure.

[!code-fsharp[FileStorage](~/samples/snippets/fsharp/azure/file-storage.fsx#L62-L72)]

### <a name="generate-a-shared-access-signature-for-a-file-or-file-share"></a>Создание подписи общего доступа для файла или файлового ресурса

Для файлового ресурса или отдельного файла можно создать подписанный URL-адрес (SAS). Также можно создать политики общего доступа на файловом ресурсе, чтобы управлять подписями общего доступа. Создание политики общего доступа рекомендуется, так как она позволяет отменить SAS, если она скомпрометирована.

В данном виде вы создаете общую политику доступа на акции, а затем используете эту политику, чтобы уделить ограничения для SAS в файле в доле.

[!code-fsharp[FileStorage](~/samples/snippets/fsharp/azure/file-storage.fsx#L78-L94)]

Дополнительные сведения см. в статьях [Использование подписанных URL-адресов (SAS)](https://docs.microsoft.com/azure/storage/storage-dotnet-shared-access-signature-part-1) и [Создание и использование подписанного URL-адреса в службе BLOB-объектов](https://docs.microsoft.com/azure/storage/storage-dotnet-shared-access-signature-part-2).

### <a name="copy-files"></a>Копирование файлов

Вы можете скопировать файл в другой файл или в каплю, или капли в файл. Если вы копируете каплю в файл или файл в каплю, *необходимо* использовать общую подпись доступа (SAS) для проверки подлинности исходного объекта, даже если вы копируете в одной учетной записи хранилища.

### <a name="copy-a-file-to-another-file"></a>Копирование файла в другой файл

Здесь вы копируете файл в другой файл в той же акции. Так как эта операция копирования осуществляет копирование между файлами в одной учетной записи хранения, для выполнения копирования можно использовать проверку подлинности Shared Key.

[!code-fsharp[FileStorage](~/samples/snippets/fsharp/azure/file-storage.fsx#L100-L101)]

### <a name="copy-a-file-to-a-blob"></a>Копирование файла в большой двоичный объект

Здесь вы создаете файл и копируете его в blob в одной учетной записи хранилища. Вы создаете SAS для исходного файла, который служба использует для проверки подлинности доступа к исходной файлу во время операции копирования.

[!code-fsharp[FileStorage](~/samples/snippets/fsharp/azure/file-storage.fsx#L107-L120)]

Таким же образом можно скопировать BLOB-объект в файл. Если исходным объектом является BLOB-объект, создайте SAS для проверки подлинности доступа к BLOB-объекту во время операции копирования.

## <a name="troubleshooting-file-storage-using-metrics"></a>Устранение неполадок хранилища файлов с помощью метрик

Аналитика хранения данных Azure поддерживает метрики для хранения файлов. Данные метрик позволяют отслеживать запросы и диагностировать проблемы.

Вы можете включить метрики для хранения файлов с [портала Azure,](https://portal.azure.com)или вы можете сделать это с F- q следующим образом:

[!code-fsharp[FileStorage](~/samples/snippets/fsharp/azure/file-storage.fsx#L126-L140)]

## <a name="next-steps"></a>Следующие шаги

Для получения дополнительной информации о хранилище файлов Azure см.

### <a name="conceptual-articles-and-videos"></a>Тематические статьи и видео

- [Хранилище файлов Azure: удобная облачная файловая система SMB для Windows и Linux](https://azure.microsoft.com/resources/videos/azurecon-2015-azure-files-storage-a-frictionless-cloud-smb-file-system-for-windows-and-linux/)
- [Использование хранилища файлов Azure в Linux](https://docs.microsoft.com/azure/storage/storage-how-to-use-files-linux)

### <a name="tooling-support-for-file-storage"></a>Средства для работы с хранилищем файлов

- [Использование Azure PowerShell со службой хранилища Azure](https://docs.microsoft.com/azure/storage/storage-powershell-guide-full)
- [Использование AzCopy со службой хранилища Microsoft Azure](https://docs.microsoft.com/azure/storage/storage-use-azcopy)
- [Создание, скачивание и составление списка больших двоичных объектов с помощью Azure CLI](https://docs.microsoft.com/azure/storage/blobs/storage-quickstart-blobs-cli#create-and-manage-file-shares)

### <a name="reference"></a>Справочник

- [Справочник по клиентской библиотеке хранилища для .NET](https://msdn.microsoft.com/library/azure/mt347887.aspx)
- [Справочник по REST API службы файлов](/rest/api/storageservices/fileservices/File-Service-REST-API)

### <a name="blog-posts"></a>Записи блога

- [Хранилище файлов Azure стало общедоступным](https://azure.microsoft.com/blog/azure-file-storage-now-generally-available/)
- [Внутри хранения файлов Azure](https://azure.microsoft.com/blog/inside-azure-file-storage/)
- [Введение в службы файлов Microsoft Azure](https://docs.microsoft.com/archive/blogs/windowsazurestorage/introducing-microsoft-azure-file-service)
- [Сохраняемые подключения к файлам Microsoft Azure](https://docs.microsoft.com/archive/blogs/windowsazurestorage/persisting-connections-to-microsoft-azure-files)
