---
title: Критические изменения в библиотеке .NET
description: Список критических изменений в основных библиотеках .NET для .NET Core версий 1.0–3.0.
ms.date: 07/27/2020
ms.openlocfilehash: 092ff36a5e07c9e226fe2a67d5e7cfd391e9d16b
ms.sourcegitcommit: fcbe432482464b1639decad78cc4dc8387c6269e
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/12/2020
ms.locfileid: "97366886"
---
# <a name="core-net-libraries-breaking-changes-in-net-core-10-30"></a>Критические изменения в основных библиотеках .NET Core версий 1.0–3.0.

Основные библиотеки .NET предоставляет примитивы и другие общие типы, используемые в .NET Core.

На этой странице описаны следующие критические изменения:

| Критическое изменение | Представленная версия |
| - | :-: |
| [Передача GroupCollection в методы расширения, принимающие IEnumerable\<T>, требует устранения неоднозначности](#passing-groupcollection-to-extension-methods-taking-ienumerablet-requires-disambiguation) | 3.0 |
| [Интерфейсы API, сообщающие версию, теперь сообщают версию продукта, а не файла](#apis-that-report-version-now-report-product-and-not-file-version) | 3.0 |
| [Пользовательские экземпляры EncoderFallbackBuffer не поддерживают рекурсивный откат](#custom-encoderfallbackbuffer-instances-cannot-fall-back-recursively) | 3.0 |
| [Изменено поведение форматирования и анализа при наличии плавающей запятой](#floating-point-formatting-and-parsing-behavior-changed) | 3.0 |
| [Операции синтаксического анализа с плавающей запятой больше не завершаются ошибкой и не вызывают исключение OverflowException](#floating-point-parsing-operations-no-longer-fail-or-throw-an-overflowexception) | 3.0 |
| [Исключение InvalidAsynchronousStateException перенесено в другую сборку](#invalidasynchronousstateexception-moved-to-another-assembly) | 3.0 |
| [Замена неправильно сформированных последовательностей байтов в кодировке UTF-8 в соответствии с правилами Юникода](#replacing-ill-formed-utf-8-byte-sequences-follows-unicode-guidelines) | 3.0 |
| [Класс TypeDescriptionProviderAttribute перенесен в другую сборку](#typedescriptionproviderattribute-moved-to-another-assembly) | 3.0 |
| [ZipArchiveEntry больше не обрабатывает архивы с несогласованными размерами записей](#ziparchiveentry-no-longer-handles-archives-with-inconsistent-entry-sizes) | 3.0 |
| [FieldInfo.SetValue вызывает исключение для статических полей и полей только для инициализации](#fieldinfosetvalue-throws-exception-for-static-init-only-fields) | 3.0 |
| [Во встроенные типы структур добавлены частные поля](#private-fields-added-to-built-in-struct-types) | 2.1 |
| [Изменено значение по умолчанию для UseShellExecute](#change-in-default-value-of-useshellexecute) | 2.1 |
| [Версии OpenSSL в macOS](#openssl-versions-on-macos) | 2.1 |
| [Исключение UnauthorizedAccessException, вызванное FileSystemInfo.Attributes](#unauthorizedaccessexception-thrown-by-filesysteminfoattributes) | 1.0 |
| [Обработка исключений с поврежденным состоянием процесса не поддерживается](#handling-corrupted-state-exceptions-is-not-supported) | 1.0 |
| [Для свойств UriBuilder больше не добавляются начальные символы](#uribuilder-properties-no-longer-prepend-leading-characters) | 1.0 |
| [Process.StartInfo выдает исключение InvalidOperationException для процессов, которые не были запущены](#processstartinfo-throws-invalidoperationexception-for-processes-you-didnt-start) | 1.0 |

## <a name="net-core-30"></a>.NET Core 3.0

[!INCLUDE [disambiguate-generic-type-for-groupcollection](../../../includes/core-changes/corefx/3.0/disambiguate-generic-type-for-groupcollection.md)]

***

[!INCLUDE[APIs that report version now report product and not file version](~/includes/core-changes/corefx/3.0/version-information-changes.md)]

**_

[!INCLUDE[Custom EncoderFallbackBuffer instances cannot fall back recursively](~/includes/core-changes/corefx/3.0/custom-encoderfallbackbuffer-cannot-be-recursive.md)]

_*_

[!INCLUDE[Floating point formatting and parsing behavior changes](~/includes/core-changes/corefx/3.0/floating-point-changes.md)]

_*_

[!INCLUDE[Floating-point parsing operations no longer fail or throw an OverflowException](~/includes/core-changes/corefx/3.0/floating-point-parsing-does-not-overflow.md)]

_*_

[!INCLUDE[InvalidAsynchronousStateException moved to another assembly](~/includes/core-changes/corefx/3.0/move-invalidasynchronousstateexception.md)]

_*_

[!INCLUDE[NET Core 3.0 follows Unicode best practices when replacing ill-formed UTF-8 byte sequences](~/includes/core-changes/corefx/3.0/net-core-3-0-follows-unicode-utf8-best-practices.md)]

_*_

[!INCLUDE[TypeDescriptionProviderAttribute moved to another assembly](~/includes/core-changes/corefx/3.0/move-typedescriptionproviderattribute.md)]

_*_

[!INCLUDE[ZipArchiveEntry no longer handles archives with inconsistent entry sizes](~/includes/core-changes/corefx/3.0/ziparchiveentry-and-inconsistent-entry-sizes.md)]

_*_

[!INCLUDE [FieldInfo.SetValue throws exception for static, init-only fields](~/includes/core-changes/corefx/3.0/fieldinfo-setvalue-exception.md)]

_*_

## <a name="net-core-21"></a>.NET Core 2.1

[!INCLUDE[Private fields added to built-in struct types](~/includes/core-changes/corefx/2.1/instantiate-struct.md)]

_*_

[!INCLUDE[Change in default value of UseShellExecute](~/includes/core-changes/corefx/2.1/process-start-changes.md)]

_*_

[!INCLUDE [OpenSSL versions on macOS](../../../includes/core-changes/corefx/openssl-dependencies-macos.md)]

_*_

## <a name="net-core-10"></a>.NET Core 1.0

[!INCLUDE [UnauthorizedAccessException thrown by FileSystemInfo.Attributes](~/includes/core-changes/corefx/1.0/filesysteminfo-attributes-exceptions.md)]

_*_

[!INCLUDE [corrupted-state-exceptions](~/includes/core-changes/corefx/1.0/corrupted-state-exceptions.md)]

_*_

[!INCLUDE [uribuilder-behavior-changes](../../../includes/core-changes/corefx/1.0/uribuilder-behavior-changes.md)]

_*_

[!INCLUDE [startinfo-throws-exception](../../../includes/core-changes/corefx/1.0/startinfo-throws-exception.md)]

_**
