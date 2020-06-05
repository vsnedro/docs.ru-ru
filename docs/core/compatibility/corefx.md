---
title: Критические изменения в библиотеке базовых классов
description: В этой статье приведен список критических изменений в основных библиотеках .NET.
ms.date: 09/20/2019
ms.openlocfilehash: 45de0f0d418437cf1677c9a8c7cfc9b6c33a24ef
ms.sourcegitcommit: ee5b798427f81237a3c23d1fd81fff7fdc21e8d3
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/28/2020
ms.locfileid: "84144488"
---
# <a name="core-net-libraries-breaking-changes"></a><span data-ttu-id="38f47-103">Критические изменения в основных библиотеках .NET</span><span class="sxs-lookup"><span data-stu-id="38f47-103">Core .NET libraries breaking changes</span></span>

<span data-ttu-id="38f47-104">Основные библиотеки .NET предоставляет примитивы и другие общие типы, используемые в .NET Core.</span><span class="sxs-lookup"><span data-stu-id="38f47-104">The core .NET libraries provide the primitives and other general types used by .NET Core.</span></span>

<span data-ttu-id="38f47-105">На этой странице описаны следующие критические изменения:</span><span class="sxs-lookup"><span data-stu-id="38f47-105">The following breaking changes are documented on this page:</span></span>

| <span data-ttu-id="38f47-106">Критическое изменение</span><span class="sxs-lookup"><span data-stu-id="38f47-106">Breaking change</span></span> | <span data-ttu-id="38f47-107">Представленная версия</span><span class="sxs-lookup"><span data-stu-id="38f47-107">Version introduced</span></span> |
| - | :-: |
| [<span data-ttu-id="38f47-108">Методы SSE и SSE2 CompareGreaterThan корректно обрабатывают входные данные, которые не являются числом</span><span class="sxs-lookup"><span data-stu-id="38f47-108">SSE and SSE2 CompareGreaterThan methods properly handle NaN inputs</span></span>](#sse-and-sse2-comparegreaterthan-methods-properly-handle-nan-inputs) | <span data-ttu-id="38f47-109">5.0</span><span class="sxs-lookup"><span data-stu-id="38f47-109">5.0</span></span> |
| [<span data-ttu-id="38f47-110">Теперь CounterSet.CreateCounterSetInstance создает исключение InvalidOperationException, если экземпляр уже существует</span><span class="sxs-lookup"><span data-stu-id="38f47-110">CounterSet.CreateCounterSetInstance now throws InvalidOperationException if instance already exist</span></span>](#countersetcreatecountersetinstance-now-throws-invalidoperationexception-if-instance-already-exists) | <span data-ttu-id="38f47-111">5.0</span><span class="sxs-lookup"><span data-stu-id="38f47-111">5.0</span></span> |
| [<span data-ttu-id="38f47-112">Интерфейсы API, сообщающие версию, теперь сообщают версию продукта, а не файла</span><span class="sxs-lookup"><span data-stu-id="38f47-112">APIs that report version now report product and not file version</span></span>](#apis-that-report-version-now-report-product-and-not-file-version) | <span data-ttu-id="38f47-113">3.0</span><span class="sxs-lookup"><span data-stu-id="38f47-113">3.0</span></span> |
| [<span data-ttu-id="38f47-114">Пользовательские экземпляры EncoderFallbackBuffer не поддерживают рекурсивный откат</span><span class="sxs-lookup"><span data-stu-id="38f47-114">Custom EncoderFallbackBuffer instances cannot fall back recursively</span></span>](#custom-encoderfallbackbuffer-instances-cannot-fall-back-recursively) | <span data-ttu-id="38f47-115">3.0</span><span class="sxs-lookup"><span data-stu-id="38f47-115">3.0</span></span> |
| [<span data-ttu-id="38f47-116">Изменено поведение форматирования и анализа при наличии плавающей запятой</span><span class="sxs-lookup"><span data-stu-id="38f47-116">Floating point formatting and parsing behavior changes</span></span>](#floating-point-formatting-and-parsing-behavior-changed) | <span data-ttu-id="38f47-117">3.0</span><span class="sxs-lookup"><span data-stu-id="38f47-117">3.0</span></span> |
| [<span data-ttu-id="38f47-118">Операции синтаксического анализа с плавающей запятой больше не завершаются ошибкой и не вызывают исключение OverflowException</span><span class="sxs-lookup"><span data-stu-id="38f47-118">Floating-point parsing operations no longer fail or throw an OverflowException</span></span>](#floating-point-parsing-operations-no-longer-fail-or-throw-an-overflowexception) | <span data-ttu-id="38f47-119">3.0</span><span class="sxs-lookup"><span data-stu-id="38f47-119">3.0</span></span> |
| [<span data-ttu-id="38f47-120">Исключение InvalidAsynchronousStateException перенесено в другую сборку</span><span class="sxs-lookup"><span data-stu-id="38f47-120">InvalidAsynchronousStateException moved to another assembly</span></span>](#invalidasynchronousstateexception-moved-to-another-assembly) | <span data-ttu-id="38f47-121">3.0</span><span class="sxs-lookup"><span data-stu-id="38f47-121">3.0</span></span> |
| [<span data-ttu-id="38f47-122">Замена неправильно сформированных последовательностей байтов в кодировке UTF-8 в соответствии с правилами Юникода</span><span class="sxs-lookup"><span data-stu-id="38f47-122">Replacing ill-formed UTF-8 byte sequences follows Unicode guidelines</span></span>](#replacing-ill-formed-utf-8-byte-sequences-follows-unicode-guidelines) | <span data-ttu-id="38f47-123">3.0</span><span class="sxs-lookup"><span data-stu-id="38f47-123">3.0</span></span> |
| [<span data-ttu-id="38f47-124">Класс TypeDescriptionProviderAttribute перенесен в другую сборку</span><span class="sxs-lookup"><span data-stu-id="38f47-124">TypeDescriptionProviderAttribute moved to another assembly</span></span>](#typedescriptionproviderattribute-moved-to-another-assembly) | <span data-ttu-id="38f47-125">3.0</span><span class="sxs-lookup"><span data-stu-id="38f47-125">3.0</span></span> |
| [<span data-ttu-id="38f47-126">ZipArchiveEntry больше не обрабатывает архивы с несогласованными размерами записей</span><span class="sxs-lookup"><span data-stu-id="38f47-126">ZipArchiveEntry no longer handles archives with inconsistent entry sizes</span></span>](#ziparchiveentry-no-longer-handles-archives-with-inconsistent-entry-sizes) | <span data-ttu-id="38f47-127">3.0</span><span class="sxs-lookup"><span data-stu-id="38f47-127">3.0</span></span> |
| [<span data-ttu-id="38f47-128">Тип исключения сериализатора JSON изменен с JsonException на NotSupportedException</span><span class="sxs-lookup"><span data-stu-id="38f47-128">JSON serializer exception type changed from JsonException to NotSupportedException</span></span>](#json-serializer-exception-type-changed-from-jsonexception-to-notsupportedexception) | <span data-ttu-id="38f47-129">3.0</span><span class="sxs-lookup"><span data-stu-id="38f47-129">3.0</span></span> |
| [<span data-ttu-id="38f47-130">Внесены изменения в семантику (string)null в Utf8JsonWriter</span><span class="sxs-lookup"><span data-stu-id="38f47-130">Change in semantics of (string)null in Utf8JsonWriter</span></span>](#change-in-semantics-of-stringnull-in-utf8jsonwriter) | <span data-ttu-id="38f47-131">3.0</span><span class="sxs-lookup"><span data-stu-id="38f47-131">3.0</span></span> |
| [<span data-ttu-id="38f47-132">Методы JsonEncodedText.Encode содержат дополнительный аргумент JavaScriptEncoder</span><span class="sxs-lookup"><span data-stu-id="38f47-132">JsonEncodedText.Encode methods have an additional JavaScriptEncoder argument</span></span>](#jsonencodedtextencode-methods-have-an-additional-javascriptencoder-argument) | <span data-ttu-id="38f47-133">3.0</span><span class="sxs-lookup"><span data-stu-id="38f47-133">3.0</span></span> |
| [<span data-ttu-id="38f47-134">Изменена подпись JsonFactoryConverter.CreateConverter</span><span class="sxs-lookup"><span data-stu-id="38f47-134">JsonFactoryConverter.CreateConverter signature changed</span></span>](#jsonfactoryconvertercreateconverter-signature-changed) | <span data-ttu-id="38f47-135">3.0</span><span class="sxs-lookup"><span data-stu-id="38f47-135">3.0</span></span> |
| [<span data-ttu-id="38f47-136">Внесены изменения в API JsonElement</span><span class="sxs-lookup"><span data-stu-id="38f47-136">JsonElement API changes</span></span>](#jsonelement-api-changes) | <span data-ttu-id="38f47-137">3.0</span><span class="sxs-lookup"><span data-stu-id="38f47-137">3.0</span></span> |
| [<span data-ttu-id="38f47-138">FieldInfo.SetValue вызывает исключение для статических полей и полей только для инициализации</span><span class="sxs-lookup"><span data-stu-id="38f47-138">FieldInfo.SetValue throws exception for static, init-only fields</span></span>](#fieldinfosetvalue-throws-exception-for-static-init-only-fields) | <span data-ttu-id="38f47-139">3.0</span><span class="sxs-lookup"><span data-stu-id="38f47-139">3.0</span></span> |
| [<span data-ttu-id="38f47-140">Во встроенные типы структур добавлены частные поля</span><span class="sxs-lookup"><span data-stu-id="38f47-140">Private fields added to built-in struct types</span></span>](#private-fields-added-to-built-in-struct-types) | <span data-ttu-id="38f47-141">2.1</span><span class="sxs-lookup"><span data-stu-id="38f47-141">2.1</span></span> |
| [<span data-ttu-id="38f47-142">Изменено значение по умолчанию для UseShellExecute</span><span class="sxs-lookup"><span data-stu-id="38f47-142">Change in default value of UseShellExecute</span></span>](#change-in-default-value-of-useshellexecute) | <span data-ttu-id="38f47-143">2.1</span><span class="sxs-lookup"><span data-stu-id="38f47-143">2.1</span></span> |
| [<span data-ttu-id="38f47-144">Версии OpenSSL в macOS</span><span class="sxs-lookup"><span data-stu-id="38f47-144">OpenSSL versions on macOS</span></span>](#openssl-versions-on-macos) | <span data-ttu-id="38f47-145">2.1</span><span class="sxs-lookup"><span data-stu-id="38f47-145">2.1</span></span> |
| [<span data-ttu-id="38f47-146">Исключение UnauthorizedAccessException, вызванное FileSystemInfo.Attributes</span><span class="sxs-lookup"><span data-stu-id="38f47-146">UnauthorizedAccessException thrown by FileSystemInfo.Attributes</span></span>](#unauthorizedaccessexception-thrown-by-filesysteminfoattributes) | <span data-ttu-id="38f47-147">1.0</span><span class="sxs-lookup"><span data-stu-id="38f47-147">1.0</span></span> |
| [<span data-ttu-id="38f47-148">Обработка исключений с поврежденным состоянием процесса не поддерживается</span><span class="sxs-lookup"><span data-stu-id="38f47-148">Handling corrupted-process-state exceptions is not supported</span></span>](#handling-corrupted-state-exceptions-is-not-supported) | <span data-ttu-id="38f47-149">1.0</span><span class="sxs-lookup"><span data-stu-id="38f47-149">1.0</span></span> |
| [<span data-ttu-id="38f47-150">Для свойств UriBuilder больше не добавляются начальные символы</span><span class="sxs-lookup"><span data-stu-id="38f47-150">UriBuilder properties no longer prepend leading characters</span></span>](#uribuilder-properties-no-longer-prepend-leading-characters) | <span data-ttu-id="38f47-151">1.0</span><span class="sxs-lookup"><span data-stu-id="38f47-151">1.0</span></span> |
| [<span data-ttu-id="38f47-152">Process.StartInfo выдает исключение InvalidOperationException для процессов, которые не были запущены</span><span class="sxs-lookup"><span data-stu-id="38f47-152">Process.StartInfo throws InvalidOperationException for processes you didn't start</span></span>](#processstartinfo-throws-invalidoperationexception-for-processes-you-didnt-start) | <span data-ttu-id="38f47-153">1.0</span><span class="sxs-lookup"><span data-stu-id="38f47-153">1.0</span></span> |

## <a name="net-50"></a><span data-ttu-id="38f47-154">.NET 5.0</span><span class="sxs-lookup"><span data-stu-id="38f47-154">.NET 5.0</span></span>

[!INCLUDE [sse-comparegreaterthan-intrinsics](../../../includes/core-changes/corefx/5.0/sse-comparegreaterthan-intrinsics.md)]

***

[!INCLUDE [createcountersetinstance-throws-invalidoperation](../../../includes/core-changes/corefx/5.0/createcountersetinstance-throws-invalidoperation.md)]

***

## <a name="net-core-30"></a><span data-ttu-id="38f47-155">.NET Core 3.0</span><span class="sxs-lookup"><span data-stu-id="38f47-155">.NET Core 3.0</span></span>

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

[!INCLUDE[JSON serializer exception type changed from JsonException to NotSupportedException](~/includes/core-changes/corefx/3.0/serializer-throws-notsupportedexception.md)]

***

[!INCLUDE[Change in semantics of (string)null in Utf8JsonWriter](~/includes/core-changes/corefx/3.0/change-in-null-in-utf8jsonwriter.md)]

***

[!INCLUDE[JsonEncodedText.Encode methods have an additional JavaScriptEncoder argument](~/includes/core-changes/corefx/3.0/jsonencodedtext-encode-has-additional-argument.md)]

***

[!INCLUDE[JsonFactoryConverter.CreateConverter signature changed](~/includes/core-changes/corefx/3.0/jsonfactoryconverter-createconverter.md)]

***

[!INCLUDE[JsonElement API changes](~/includes/core-changes/corefx/3.0/jsonelement-api-changes.md)]

***

[!INCLUDE [FieldInfo.SetValue throws exception for static, init-only fields](~/includes/core-changes/corefx/3.0/fieldinfo-setvalue-exception.md)]

***

## <a name="net-core-21"></a><span data-ttu-id="38f47-156">.NET Core 2.1</span><span class="sxs-lookup"><span data-stu-id="38f47-156">.NET Core 2.1</span></span>

[!INCLUDE[Private fields added to built-in struct types](~/includes/core-changes/corefx/2.1/instantiate-struct.md)]

***

[!INCLUDE[Change in default value of UseShellExecute](~/includes/core-changes/corefx/2.1/process-start-changes.md)]

***

[!INCLUDE [OpenSSL versions on macOS](../../../includes/core-changes/corefx/openssl-dependencies-macos.md)]

***

## <a name="net-core-10"></a><span data-ttu-id="38f47-157">.NET Core 1.0</span><span class="sxs-lookup"><span data-stu-id="38f47-157">.NET Core 1.0</span></span>

[!INCLUDE [UnauthorizedAccessException thrown by FileSystemInfo.Attributes](~/includes/core-changes/corefx/1.0/filesysteminfo-attributes-exceptions.md)]

***

[!INCLUDE [corrupted-state-exceptions](~/includes/core-changes/corefx/1.0/corrupted-state-exceptions.md)]

***

[!INCLUDE [uribuilder-behavior-changes](../../../includes/core-changes/corefx/1.0/uribuilder-behavior-changes.md)]

***

[!INCLUDE [startinfo-throws-exception](../../../includes/core-changes/corefx/1.0/startinfo-throws-exception.md)]

***
