---
title: Служебная программа клиента служб данных WCF (DataSvcUtil.exe)
ms.date: 03/30/2017
helpviewer_keywords:
- WCF Data Services, generating client data classes
- WCF Data Services, client library
- WCF Data Services, consuming
ms.assetid: 9d0af606-929b-4c03-b307-3ef5f705afce
ms.openlocfilehash: 600cb9a4f91ff2051f60ee86d4cb80cc5b404c61
ms.sourcegitcommit: 27a15a55019f6b5f2733961738babe94aec0def3
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/15/2020
ms.locfileid: "90544301"
---
# <a name="wcf-data-service-client-utility-datasvcutilexe"></a>Служебная программа клиента служб данных WCF (DataSvcUtil.exe)

DataSvcUtil.exe — это средство командной строки, предоставляемое WCF Data Services, которое использует канал Open Data Protocol (OData) и создает классы клиентских служб данных, необходимые для доступа к службе данных из клиентского приложения .NET Framework. Эта программа формирует классы данных с использованием следующих источников метаданных.

- Корневой URI службы данных. Эта программа запрашивает документ метаданных службы, в котором описывается модель данных, предоставленная службой данных. Дополнительные сведения см. в разделе [AtomPub (RFC5023)](https://tools.ietf.org/html/rfc5023#section-8).

- Файл модели данных (CSDL), определяемый на языке CSDL, как определено в спецификации [ \[ файла MC-CSDL \] : определение концептуальной схемы](/openspecs/windows_protocols/mc-csdl/c03ad8c3-e8b7-4306-af96-a9e52bb3df12) .

- Файл EDMX, созданный при помощи программ для работы с моделью EDM, входящих в комплект Entity Framework. Дополнительные сведения см. в описании [ \[ пакета MC-EDMX \] : EDM for Data Services](/openspecs/windows_protocols/mc-edmx/5dff5e25-56a1-408b-9d44-bff6634c7d16) .

Дополнительные сведения см. [в разделе как вручную создавать классы службы данных клиента](how-to-manually-generate-client-data-service-classes-wcf-data-services.md).

Средство DataSvcUtil.exe устанавливается в каталог .NET Framework. Во многих случаях это находится в *C:\Windows\Microsoft.NET\Framework\v4.0*. Для 64-разрядных систем это расположение находится в *C:\Windows\Microsoft.NET\Framework64\v4.0*. Вы также можете получить доступ к средству DataSvcUtil.exe из Командная строка разработчика для Visual Studio.

## <a name="syntax"></a>Синтаксис

```console
datasvcutil /out:file [/in:file | /uri:serviceuri] [/dataservicecollection] [/language:devlang] [/nologo] [/version:ver] [/help]
```

## <a name="parameters"></a>Параметры

|Параметр|Описание|
|------------|-----------------|
|`/dataservicecollection`|Указывает, что будет также сформирован код, необходимый для привязки объектов к элементам управления.|
|`/help`<br /><br /> -или-<br /><br /> `/?`|Отображает синтаксис команд и параметров программы.|
|`/in:` *\<file>*|Указывает файл CSDL или EDMX либо каталог, в котором находится этот файл.|
|`/language:`[VB&#124;CSharp]|Задает язык для сформированных файлов с исходным кодом. Язык по умолчанию — C#.|
|`/nologo`|Отключает вывод сообщения об авторских правах.|
|`/out:` *\<file>*|Задает имя файла с исходным кодом, в котором содержатся сформированные клиентские классы службы данных.|
|`/uri:` *\<string>*|URI веб-канала OData.|
|`/version:`[1,0&#124;2,0]|Указывает максимально допустимую версию OData. Версия определяется на основе `DataServiceVersion` атрибута элемента данных в возвращенных метаданных службы данных. Дополнительные сведения см. в разделе [Управление версиями службы данных](data-service-versioning-wcf-data-services.md). При указании `/dataservicecollection` параметра необходимо также указать, `/version:2.0` чтобы включить привязку данных.|

## <a name="see-also"></a>См. также

- [Создание библиотеки клиентов службы данных](generating-the-data-service-client-library-wcf-data-services.md)
- [Практическое руководство. Добавление ссылки на службу данных](how-to-add-a-data-service-reference-wcf-data-services.md)
