---
title: Критические изменения в библиотеке базовых классов
description: В этой статье приведен список критических изменений в основных библиотеках .NET.
ms.date: 07/27/2020
ms.openlocfilehash: 0667d975ce5bba5692fe5d179341235bd3c61790
ms.sourcegitcommit: 1e6439ec4d5889fc08cf3bfb4dac2b91931eb827
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/08/2020
ms.locfileid: "88024708"
---
# <a name="core-net-libraries-breaking-changes"></a>Критические изменения в основных библиотеках .NET

Основные библиотеки .NET предоставляет примитивы и другие общие типы, используемые в .NET Core.

На этой странице описаны следующие критические изменения:

| Критическое изменение | Представленная версия |
| - | :-: |
| [IntPtr и UIntPtr реализуют IFormattable](#intptr-and-uintptr-implement-iformattable) | 5.0 |
| [PrincipalPermissionAttribute устарел и является ошибочным](#principalpermissionattribute-is-obsolete-as-error) | 5.0 |
| [Методы сериализации BinaryFormatter устарели и запрещены в приложениях ASP.NET](#binaryformatter-serialization-methods-are-obsolete-and-prohibited-in-aspnet-apps) | 5.0 |
| [Пути к коду в кодировке UTF-7 устарели](#utf-7-code-paths-are-obsolete) | 5.0 |
| [Vector\<T> всегда вызывает исключение NotSupportedException для неподдерживаемых типов](#vectort-always-throws-notsupportedexception-for-unsupported-types) | 5.0 |
| [По умолчанию ActivityIdFormat имеет значение W3C](#default-activityidformat-is-w3c) | 5.0 |
| [Изменение в поведении для Vector2.Lerp и Vector4.Lerp](#behavior-change-for-vector2lerp-and-vector4lerp) | 5.0 |
| [Методы SSE и SSE2 CompareGreaterThan корректно обрабатывают входные данные, которые не являются числом](#sse-and-sse2-comparegreaterthan-methods-properly-handle-nan-inputs) | 5.0 |
| [Теперь CounterSet.CreateCounterSetInstance создает исключение InvalidOperationException, если экземпляр уже существует](#countersetcreatecountersetinstance-now-throws-invalidoperationexception-if-instance-already-exists) | 5.0 |
| [Удален пакет Microsoft.DotNet.PlatformAbstractions](#microsoftdotnetplatformabstractions-package-removed) | 5.0 |
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

## <a name="net-50"></a>.NET 5.0

[!INCLUDE [intptr-uintptr-implement-iformattable](../../../includes/core-changes/corefx/5.0/intptr-uintptr-implement-iformattable.md)]

***

[!INCLUDE [principalpermissionattribute-obsolete](../../../includes/core-changes/corefx/5.0/principalpermissionattribute-obsolete.md)]

***

[!INCLUDE [binaryformatter-serialization-obsolete](../../../includes/core-changes/corefx/5.0/binaryformatter-serialization-obsolete.md)]

***

[!INCLUDE [utf-7-code-paths-obsolete](../../../includes/core-changes/corefx/5.0/utf-7-code-paths-obsolete.md)]

***

[!INCLUDE [vectort-throws-notsupportedexception](../../../includes/core-changes/corefx/5.0/vectort-throws-notsupportedexception.md)]

***

[!INCLUDE [default-activityidformat-changed](../../../includes/core-changes/corefx/5.0/default-activityidformat-changed.md)]

***

[!INCLUDE [vector-lerp-behavior-change](../../../includes/core-changes/corefx/5.0/vector-lerp-behavior-change.md)]

***

[!INCLUDE [sse-comparegreaterthan-intrinsics](../../../includes/core-changes/corefx/5.0/sse-comparegreaterthan-intrinsics.md)]

***

[!INCLUDE [createcountersetinstance-throws-invalidoperation](../../../includes/core-changes/corefx/5.0/createcountersetinstance-throws-invalidoperation.md)]

***

[!INCLUDE [platformabstractions-package-removed](../../../includes/core-changes/corefx/5.0/platformabstractions-package-removed.md)]

***

## <a name="net-core-30"></a>.NET Core 3.0

[!INCLUDE[APIs that report version now report product and not file version](~/includes/core-changes/corefx/3.0/version-information-changes.md)]

***

[!INCLUDE[Custom EncoderFallbackBuffer instances cannot fall back recursively](~/includes/core-changes/corefx/3.0/custom-encoderfallbackbuffer-cannot-be-recursive.md)]

***

[!INCLUDE[Floating point formatting and parsing behavior changes](~/includes/core-changes/corefx/3.0/floating-point-changes.md)]

***

[!INCLUDE[Floating-point parsing operations no longer fail or throw an OverflowException](~/includes/core-changes/corefx/3.0/floating-point-parsing-does-not-overflow.md)]

***

[!INCLUDE[InvalidAsynchronousStateException moved to another assembly](~/includes/core-changes/corefx/3.0/move-invalidasynchronousstateexception.md)]

***

[!INCLUDE[NET Core 3.0 follows Unicode best practices when replacing ill-formed UTF-8 byte sequences](~/includes/core-changes/corefx/3.0/net-core-3-0-follows-unicode-utf8-best-practices.md)]

***

[!INCLUDE[TypeDescriptionProviderAttribute moved to another assembly](~/includes/core-changes/corefx/3.0/move-typedescriptionproviderattribute.md)]

***

[!INCLUDE[ZipArchiveEntry no longer handles archives with inconsistent entry sizes](~/includes/core-changes/corefx/3.0/ziparchiveentry-and-inconsistent-entry-sizes.md)]

***

[!INCLUDE [FieldInfo.SetValue throws exception for static, init-only fields](~/includes/core-changes/corefx/3.0/fieldinfo-setvalue-exception.md)]

***

## <a name="net-core-21"></a>.NET Core 2.1

[!INCLUDE[Private fields added to built-in struct types](~/includes/core-changes/corefx/2.1/instantiate-struct.md)]

***

[!INCLUDE[Change in default value of UseShellExecute](~/includes/core-changes/corefx/2.1/process-start-changes.md)]

***

[!INCLUDE [OpenSSL versions on macOS](../../../includes/core-changes/corefx/openssl-dependencies-macos.md)]

***

## <a name="net-core-10"></a>.NET Core 1.0

[!INCLUDE [UnauthorizedAccessException thrown by FileSystemInfo.Attributes](~/includes/core-changes/corefx/1.0/filesysteminfo-attributes-exceptions.md)]

***

[!INCLUDE [corrupted-state-exceptions](~/includes/core-changes/corefx/1.0/corrupted-state-exceptions.md)]

***

[!INCLUDE [uribuilder-behavior-changes](../../../includes/core-changes/corefx/1.0/uribuilder-behavior-changes.md)]

***

[!INCLUDE [startinfo-throws-exception](../../../includes/core-changes/corefx/1.0/startinfo-throws-exception.md)]

***
