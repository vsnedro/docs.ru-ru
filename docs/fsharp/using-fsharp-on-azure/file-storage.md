---
title: 'Начало работы с хранилищем файлов Azure с помощью F #'
description: Храните данные файлов в облаке с помощью хранилища файлов Azure и подключите облачный файловый ресурс из виртуальной машины Azure или из локального приложения под управлением Windows.
author: sylvanc
ms.date: 09/20/2016
ms.custom: devx-track-fsharp
ms.openlocfilehash: bcea58b4bf756fc9d696cd5a1010b0feffb127a7
ms.sourcegitcommit: 8299abfbd5c49b596d61f1e4d09bc6b8ba055b36
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/27/2021
ms.locfileid: "98899429"
---
# <a name="get-started-with-azure-file-storage-using-f"></a>Начало работы с хранилищем файлов Azure с помощью F\#

Хранилище файлов Azure — это служба, которая предлагает общие файловые ресурсы в облаке с помощью стандартного [протокола SMB](/windows/win32/fileio/microsoft-smb-protocol-and-cifs-protocol-overview). Поддерживаются версии SMB 2.1 и SMB 3.0. С помощью хранилища файлов Azure можно быстро перенести устаревшие приложения, использующие общие файловые ресурсы, в Azure и без дорогостоящей перезаписи. Приложения, работающие на виртуальных машинах Azure, в облачных службах или на локальных клиентах, могут подключать общую папку в облаке так же, как настольное приложение подключает обычную общую папку SMB. Любое количество компонентов приложений может одновременно подключаться и получать доступ к ресурсам хранилища файлов.

Общие сведения о хранилище файлов см. [в этом](/azure/storage/storage-dotnet-how-to-use-files)разделе.

## <a name="prerequisites"></a>Предварительные требования

Для работы с этим руководством необходимо сначала [создать учетную запись хранения Azure](/azure/storage/storage-create-storage-account).
Вам также потребуется ключ доступа к хранилищу для этой учетной записи.

## <a name="create-an-f-script-and-start-f-interactive"></a>Создание скрипта F # и запуск F# Interactive

Примеры в этой статье можно использовать как в приложении F #, так и в сценарии F #. Чтобы создать скрипт F #, создайте файл с `.fsx` расширением, например `files.fsx` , в среде разработки F #.

Затем используйте [Диспетчер пакетов](package-management.md) , например [пакет](https://fsprojects.github.io/Paket/) или [NuGet](https://www.nuget.org/) , для установки `WindowsAzure.Storage` пакета и ссылки `WindowsAzure.Storage.dll` в скрипте с помощью `#r` директивы.

### <a name="add-namespace-declarations"></a>Добавление объявлений пространств имен

Добавьте в начало файла `files.fsx` следующие инструкции `open`:

[!code-fsharp[FileStorage](~/samples/snippets/fsharp/azure/file-storage.fsx#L1-L5)]

### <a name="get-your-connection-string"></a>Получение строки подключения

Для работы с этим руководством вам потребуется строка подключения к службе хранилища Azure. Дополнительные сведения о строках подключения см. в разделе [Настройка строк подключения к хранилищу](/azure/storage/storage-configure-connection-string).

В этом руководстве вы введете строку подключения в сценарий следующим образом:

[!code-fsharp[FileStorage](~/samples/snippets/fsharp/azure/file-storage.fsx#L11-L11)]

Однако это **не рекомендуется** для реальных проектов. Ключ учетной записи хранения похож на корневой пароль для вашей учетной записи хранения. Не забудьте защитить ключ учетной записи хранения. Не сообщайте его другим пользователям, не определяйте его в коде и не храните его в текстовом файле, доступном другим пользователям. Вы можете повторно создать ключ, используя портал Azure, если вы считаете, что он был скомпрометирован.

Для реальных приложений лучшим способом поддержания строки подключения к хранилищу является файл конфигурации. Чтобы получить строку подключения из файла конфигурации, можно сделать следующее:

[!code-fsharp[FileStorage](~/samples/snippets/fsharp/azure/file-storage.fsx#L13-L15)]

Использование диспетчера конфигураций Azure не является обязательным. Можно также использовать API, например `ConfigurationManager` тип платформа .NET Framework.

### <a name="parse-the-connection-string"></a>Проанализируйте строку подключения

Чтобы проанализировать строку подключения, используйте:

[!code-fsharp[FileStorage](~/samples/snippets/fsharp/azure/file-storage.fsx#L21-L22)]

Будет возвращен `CloudStorageAccount` .

### <a name="create-the-file-service-client"></a>Создание клиента службы файлов

`CloudFileClient`Тип позволяет программно использовать файлы, хранящиеся в хранилище файлов. Вот один из способов создать клиента службы.

[!code-fsharp[FileStorage](~/samples/snippets/fsharp/azure/file-storage.fsx#L28-L28)]

Теперь все готово для написания кода, считывающего данные из хранилища файлов и записывающего их в хранилище.

## <a name="create-a-file-share"></a>Создание общей папки

В этом примере показано, как создать файловый ресурс, если он еще не существует:

[!code-fsharp[FileStorage](~/samples/snippets/fsharp/azure/file-storage.fsx#L34-L35)]

## <a name="create-a-root-directory-and-a-subdirectory"></a>Создание корневого каталога и подкаталога

Здесь вы получаете корневой каталог и получаете подкаталог корневого каталога. Они создаются, если они еще не существуют.

[!code-fsharp[FileStorage](~/samples/snippets/fsharp/azure/file-storage.fsx#L41-L43)]

## <a name="upload-text-as-a-file"></a>Отправка текста в виде файла

В этом примере показано, как передать текст в виде файла.

[!code-fsharp[FileStorage](~/samples/snippets/fsharp/azure/file-storage.fsx#L49-L50)]

### <a name="download-a-file-to-a-local-copy-of-the-file"></a>Скачать файл в локальную копию файла

Здесь вы скачиваете только что созданный файл, добавляя содержимое в локальный файл.

[!code-fsharp[FileStorage](~/samples/snippets/fsharp/azure/file-storage.fsx#L56-L56)]

### <a name="set-the-maximum-size-for-a-file-share"></a>Установка максимального размера для файлового ресурса

В приведенном ниже примере показано, как проверить текущее использование данных в файловом ресурсе, а также задать для него квоту. `FetchAttributes` должен вызываться для заполнения общей папки `Properties` и `SetProperties` распространения локальных изменений в хранилище файлов Azure.

[!code-fsharp[FileStorage](~/samples/snippets/fsharp/azure/file-storage.fsx#L62-L72)]

### <a name="generate-a-shared-access-signature-for-a-file-or-file-share"></a>Создание подписи общего доступа для файла или файлового ресурса

Для файлового ресурса или отдельного файла можно создать подписанный URL-адрес (SAS). Также можно создать политики общего доступа на файловом ресурсе, чтобы управлять подписями общего доступа. Создание политики общего доступа рекомендуется, так как она позволяет отменить SAS, если она скомпрометирована.

Здесь вы создаете политику общего доступа для общей папки, а затем используете эту политику для предоставления ограничений для SAS для файла в общей папке.

[!code-fsharp[FileStorage](~/samples/snippets/fsharp/azure/file-storage.fsx#L78-L94)]

Дополнительные сведения см. в статьях [Использование подписанных URL-адресов (SAS)](/azure/storage/storage-dotnet-shared-access-signature-part-1) и [Создание и использование подписанного URL-адреса в службе BLOB-объектов](/azure/storage/storage-dotnet-shared-access-signature-part-2).

### <a name="copy-files"></a>Копирование файлов

Файл можно скопировать в другой файл или в большой двоичный объект или в большой двоичный объект в файл. Если вы копируете большой двоичный объект в файл или файл в большой двоичный объект, *необходимо* использовать подписанный URL-адрес (SAS) для проверки подлинности исходного объекта, даже если вы копируете его в ту же учетную запись хранения.

### <a name="copy-a-file-to-another-file"></a>Копирование файла в другой файл

Здесь вы копируете файл в другой файл в той же общей папке. Так как эта операция копирования осуществляет копирование между файлами в одной учетной записи хранения, для выполнения копирования можно использовать проверку подлинности Shared Key.

[!code-fsharp[FileStorage](~/samples/snippets/fsharp/azure/file-storage.fsx#L100-L101)]

### <a name="copy-a-file-to-a-blob"></a>Копирование файла в большой двоичный объект

Здесь вы создаете файл и копируете его в большой двоичный объект в той же учетной записи хранения. Создайте SAS для исходного файла, который служба использует для проверки подлинности доступа к исходному файлу во время операции копирования.

[!code-fsharp[FileStorage](~/samples/snippets/fsharp/azure/file-storage.fsx#L107-L120)]

Таким же образом можно скопировать BLOB-объект в файл. Если исходным объектом является BLOB-объект, создайте SAS для проверки подлинности доступа к BLOB-объекту во время операции копирования.

## <a name="troubleshooting-file-storage-using-metrics"></a>Устранение неполадок хранилища файлов с помощью метрик

Аналитика Службы хранилища Azure поддерживает метрики для хранилища файлов. Данные метрик позволяют отслеживать запросы и диагностировать проблемы.

Вы можете включить метрики для хранилища файлов из [портал Azure](https://portal.azure.com)или можно сделать это в F # следующим образом:

[!code-fsharp[FileStorage](~/samples/snippets/fsharp/azure/file-storage.fsx#L126-L140)]

## <a name="next-steps"></a>Дальнейшие действия

Дополнительные сведения о хранилище файлов Azure см. по этим ссылкам.

### <a name="conceptual-articles-and-videos"></a>Тематические статьи и видео

- [Хранилище файлов Azure: удобная облачная файловая система SMB для Windows и Linux](https://azure.microsoft.com/resources/videos/azurecon-2015-azure-files-storage-a-frictionless-cloud-smb-file-system-for-windows-and-linux/)
- [Использование хранилища файлов Azure в Linux](/azure/storage/storage-how-to-use-files-linux)

### <a name="tooling-support-for-file-storage"></a>Средства для работы с хранилищем файлов

- [Использование Azure PowerShell со службой хранилища Azure](/azure/storage/storage-powershell-guide-full)
- [Использование AzCopy со службой хранилища Microsoft Azure](/azure/storage/storage-use-azcopy)
- [Создание, скачивание и составление списка больших двоичных объектов с помощью Azure CLI](/azure/storage/blobs/storage-quickstart-blobs-cli#create-and-manage-file-shares)

### <a name="reference"></a>Справочник

- [Справочник по клиентской библиотеке хранилища для .NET](/dotnet/api/overview/azure/storage)
- [Справочник по REST API службы файлов](/rest/api/storageservices/fileservices/File-Service-REST-API)

### <a name="blog-posts"></a>Записи блога

- [Хранилище файлов Azure теперь общедоступно](https://azure.microsoft.com/blog/azure-file-storage-now-generally-available/)
- [Внутреннее хранилище файлов Azure](https://azure.microsoft.com/blog/inside-azure-file-storage/)
- [Введение в службы файлов Microsoft Azure](/archive/blogs/windowsazurestorage/introducing-microsoft-azure-file-service)
- [Сохраняемые подключения к файлам Microsoft Azure](/archive/blogs/windowsazurestorage/persisting-connections-to-microsoft-azure-files)
