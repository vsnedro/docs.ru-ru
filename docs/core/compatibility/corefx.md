---
title: Критические изменения в библиотеке базовых классов
description: В этой статье приведен список критических изменений в основных библиотеках .NET.
ms.date: 09/20/2019
ms.openlocfilehash: 1c56358e69d0dd6e8572a41229c1b9edbcdad795
ms.sourcegitcommit: 63bb83322814f5e5e5c5b69939b14a3139a6ca7e
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/25/2020
ms.locfileid: "85365624"
---
# <a name="core-net-libraries-breaking-changes"></a><span data-ttu-id="cacc8-103">Критические изменения в основных библиотеках .NET</span><span class="sxs-lookup"><span data-stu-id="cacc8-103">Core .NET libraries breaking changes</span></span>

<span data-ttu-id="cacc8-104">Основные библиотеки .NET предоставляет примитивы и другие общие типы, используемые в .NET Core.</span><span class="sxs-lookup"><span data-stu-id="cacc8-104">The core .NET libraries provide the primitives and other general types used by .NET Core.</span></span>

<span data-ttu-id="cacc8-105">На этой странице описаны следующие критические изменения:</span><span class="sxs-lookup"><span data-stu-id="cacc8-105">The following breaking changes are documented on this page:</span></span>

| <span data-ttu-id="cacc8-106">Критическое изменение</span><span class="sxs-lookup"><span data-stu-id="cacc8-106">Breaking change</span></span> | <span data-ttu-id="cacc8-107">Представленная версия</span><span class="sxs-lookup"><span data-stu-id="cacc8-107">Version introduced</span></span> |
| - | :-: |
| [<span data-ttu-id="cacc8-108">Методы SSE и SSE2 CompareGreaterThan корректно обрабатывают входные данные, которые не являются числом</span><span class="sxs-lookup"><span data-stu-id="cacc8-108">SSE and SSE2 CompareGreaterThan methods properly handle NaN inputs</span></span>](#sse-and-sse2-comparegreaterthan-methods-properly-handle-nan-inputs) | <span data-ttu-id="cacc8-109">5.0</span><span class="sxs-lookup"><span data-stu-id="cacc8-109">5.0</span></span> |
| [<span data-ttu-id="cacc8-110">Теперь CounterSet.CreateCounterSetInstance создает исключение InvalidOperationException, если экземпляр уже существует</span><span class="sxs-lookup"><span data-stu-id="cacc8-110">CounterSet.CreateCounterSetInstance now throws InvalidOperationException if instance already exist</span></span>](#countersetcreatecountersetinstance-now-throws-invalidoperationexception-if-instance-already-exists) | <span data-ttu-id="cacc8-111">5.0</span><span class="sxs-lookup"><span data-stu-id="cacc8-111">5.0</span></span> |
| [<span data-ttu-id="cacc8-112">Удален пакет Microsoft.DotNet.PlatformAbstractions</span><span class="sxs-lookup"><span data-stu-id="cacc8-112">Microsoft.DotNet.PlatformAbstractions package removed</span></span>](#microsoftdotnetplatformabstractions-package-removed) | <span data-ttu-id="cacc8-113">5.0</span><span class="sxs-lookup"><span data-stu-id="cacc8-113">5.0</span></span> |
| [<span data-ttu-id="cacc8-114">Интерфейсы API, сообщающие версию, теперь сообщают версию продукта, а не файла</span><span class="sxs-lookup"><span data-stu-id="cacc8-114">APIs that report version now report product and not file version</span></span>](#apis-that-report-version-now-report-product-and-not-file-version) | <span data-ttu-id="cacc8-115">3.0</span><span class="sxs-lookup"><span data-stu-id="cacc8-115">3.0</span></span> |
| [<span data-ttu-id="cacc8-116">Пользовательские экземпляры EncoderFallbackBuffer не поддерживают рекурсивный откат</span><span class="sxs-lookup"><span data-stu-id="cacc8-116">Custom EncoderFallbackBuffer instances cannot fall back recursively</span></span>](#custom-encoderfallbackbuffer-instances-cannot-fall-back-recursively) | <span data-ttu-id="cacc8-117">3.0</span><span class="sxs-lookup"><span data-stu-id="cacc8-117">3.0</span></span> |
| [<span data-ttu-id="cacc8-118">Изменено поведение форматирования и анализа при наличии плавающей запятой</span><span class="sxs-lookup"><span data-stu-id="cacc8-118">Floating point formatting and parsing behavior changes</span></span>](#floating-point-formatting-and-parsing-behavior-changed) | <span data-ttu-id="cacc8-119">3.0</span><span class="sxs-lookup"><span data-stu-id="cacc8-119">3.0</span></span> |
| [<span data-ttu-id="cacc8-120">Операции синтаксического анализа с плавающей запятой больше не завершаются ошибкой и не вызывают исключение OverflowException</span><span class="sxs-lookup"><span data-stu-id="cacc8-120">Floating-point parsing operations no longer fail or throw an OverflowException</span></span>](#floating-point-parsing-operations-no-longer-fail-or-throw-an-overflowexception) | <span data-ttu-id="cacc8-121">3.0</span><span class="sxs-lookup"><span data-stu-id="cacc8-121">3.0</span></span> |
| [<span data-ttu-id="cacc8-122">Исключение InvalidAsynchronousStateException перенесено в другую сборку</span><span class="sxs-lookup"><span data-stu-id="cacc8-122">InvalidAsynchronousStateException moved to another assembly</span></span>](#invalidasynchronousstateexception-moved-to-another-assembly) | <span data-ttu-id="cacc8-123">3.0</span><span class="sxs-lookup"><span data-stu-id="cacc8-123">3.0</span></span> |
| [<span data-ttu-id="cacc8-124">Замена неправильно сформированных последовательностей байтов в кодировке UTF-8 в соответствии с правилами Юникода</span><span class="sxs-lookup"><span data-stu-id="cacc8-124">Replacing ill-formed UTF-8 byte sequences follows Unicode guidelines</span></span>](#replacing-ill-formed-utf-8-byte-sequences-follows-unicode-guidelines) | <span data-ttu-id="cacc8-125">3.0</span><span class="sxs-lookup"><span data-stu-id="cacc8-125">3.0</span></span> |
| [<span data-ttu-id="cacc8-126">Класс TypeDescriptionProviderAttribute перенесен в другую сборку</span><span class="sxs-lookup"><span data-stu-id="cacc8-126">TypeDescriptionProviderAttribute moved to another assembly</span></span>](#typedescriptionproviderattribute-moved-to-another-assembly) | <span data-ttu-id="cacc8-127">3.0</span><span class="sxs-lookup"><span data-stu-id="cacc8-127">3.0</span></span> |
| [<span data-ttu-id="cacc8-128">ZipArchiveEntry больше не обрабатывает архивы с несогласованными размерами записей</span><span class="sxs-lookup"><span data-stu-id="cacc8-128">ZipArchiveEntry no longer handles archives with inconsistent entry sizes</span></span>](#ziparchiveentry-no-longer-handles-archives-with-inconsistent-entry-sizes) | <span data-ttu-id="cacc8-129">3.0</span><span class="sxs-lookup"><span data-stu-id="cacc8-129">3.0</span></span> |
| [<span data-ttu-id="cacc8-130">Тип исключения сериализатора JSON изменен с JsonException на NotSupportedException</span><span class="sxs-lookup"><span data-stu-id="cacc8-130">JSON serializer exception type changed from JsonException to NotSupportedException</span></span>](#json-serializer-exception-type-changed-from-jsonexception-to-notsupportedexception) | <span data-ttu-id="cacc8-131">3.0</span><span class="sxs-lookup"><span data-stu-id="cacc8-131">3.0</span></span> |
| [<span data-ttu-id="cacc8-132">Внесены изменения в семантику (string)null в Utf8JsonWriter</span><span class="sxs-lookup"><span data-stu-id="cacc8-132">Change in semantics of (string)null in Utf8JsonWriter</span></span>](#change-in-semantics-of-stringnull-in-utf8jsonwriter) | <span data-ttu-id="cacc8-133">3.0</span><span class="sxs-lookup"><span data-stu-id="cacc8-133">3.0</span></span> |
| [<span data-ttu-id="cacc8-134">Методы JsonEncodedText.Encode содержат дополнительный аргумент JavaScriptEncoder</span><span class="sxs-lookup"><span data-stu-id="cacc8-134">JsonEncodedText.Encode methods have an additional JavaScriptEncoder argument</span></span>](#jsonencodedtextencode-methods-have-an-additional-javascriptencoder-argument) | <span data-ttu-id="cacc8-135">3.0</span><span class="sxs-lookup"><span data-stu-id="cacc8-135">3.0</span></span> |
| [<span data-ttu-id="cacc8-136">Изменена подпись JsonFactoryConverter.CreateConverter</span><span class="sxs-lookup"><span data-stu-id="cacc8-136">JsonFactoryConverter.CreateConverter signature changed</span></span>](#jsonfactoryconvertercreateconverter-signature-changed) | <span data-ttu-id="cacc8-137">3.0</span><span class="sxs-lookup"><span data-stu-id="cacc8-137">3.0</span></span> |
| [<span data-ttu-id="cacc8-138">Внесены изменения в API JsonElement</span><span class="sxs-lookup"><span data-stu-id="cacc8-138">JsonElement API changes</span></span>](#jsonelement-api-changes) | <span data-ttu-id="cacc8-139">3.0</span><span class="sxs-lookup"><span data-stu-id="cacc8-139">3.0</span></span> |
| [<span data-ttu-id="cacc8-140">FieldInfo.SetValue вызывает исключение для статических полей и полей только для инициализации</span><span class="sxs-lookup"><span data-stu-id="cacc8-140">FieldInfo.SetValue throws exception for static, init-only fields</span></span>](#fieldinfosetvalue-throws-exception-for-static-init-only-fields) | <span data-ttu-id="cacc8-141">3.0</span><span class="sxs-lookup"><span data-stu-id="cacc8-141">3.0</span></span> |
| [<span data-ttu-id="cacc8-142">Во встроенные типы структур добавлены частные поля</span><span class="sxs-lookup"><span data-stu-id="cacc8-142">Private fields added to built-in struct types</span></span>](#private-fields-added-to-built-in-struct-types) | <span data-ttu-id="cacc8-143">2.1</span><span class="sxs-lookup"><span data-stu-id="cacc8-143">2.1</span></span> |
| [<span data-ttu-id="cacc8-144">Изменено значение по умолчанию для UseShellExecute</span><span class="sxs-lookup"><span data-stu-id="cacc8-144">Change in default value of UseShellExecute</span></span>](#change-in-default-value-of-useshellexecute) | <span data-ttu-id="cacc8-145">2.1</span><span class="sxs-lookup"><span data-stu-id="cacc8-145">2.1</span></span> |
| [<span data-ttu-id="cacc8-146">Версии OpenSSL в macOS</span><span class="sxs-lookup"><span data-stu-id="cacc8-146">OpenSSL versions on macOS</span></span>](#openssl-versions-on-macos) | <span data-ttu-id="cacc8-147">2.1</span><span class="sxs-lookup"><span data-stu-id="cacc8-147">2.1</span></span> |
| [<span data-ttu-id="cacc8-148">Исключение UnauthorizedAccessException, вызванное FileSystemInfo.Attributes</span><span class="sxs-lookup"><span data-stu-id="cacc8-148">UnauthorizedAccessException thrown by FileSystemInfo.Attributes</span></span>](#unauthorizedaccessexception-thrown-by-filesysteminfoattributes) | <span data-ttu-id="cacc8-149">1.0</span><span class="sxs-lookup"><span data-stu-id="cacc8-149">1.0</span></span> |
| [<span data-ttu-id="cacc8-150">Обработка исключений с поврежденным состоянием процесса не поддерживается</span><span class="sxs-lookup"><span data-stu-id="cacc8-150">Handling corrupted-process-state exceptions is not supported</span></span>](#handling-corrupted-state-exceptions-is-not-supported) | <span data-ttu-id="cacc8-151">1.0</span><span class="sxs-lookup"><span data-stu-id="cacc8-151">1.0</span></span> |
| [<span data-ttu-id="cacc8-152">Для свойств UriBuilder больше не добавляются начальные символы</span><span class="sxs-lookup"><span data-stu-id="cacc8-152">UriBuilder properties no longer prepend leading characters</span></span>](#uribuilder-properties-no-longer-prepend-leading-characters) | <span data-ttu-id="cacc8-153">1.0</span><span class="sxs-lookup"><span data-stu-id="cacc8-153">1.0</span></span> |
| [<span data-ttu-id="cacc8-154">Process.StartInfo выдает исключение InvalidOperationException для процессов, которые не были запущены</span><span class="sxs-lookup"><span data-stu-id="cacc8-154">Process.StartInfo throws InvalidOperationException for processes you didn't start</span></span>](#processstartinfo-throws-invalidoperationexception-for-processes-you-didnt-start) | <span data-ttu-id="cacc8-155">1.0</span><span class="sxs-lookup"><span data-stu-id="cacc8-155">1.0</span></span> |

## <a name="net-50"></a><span data-ttu-id="cacc8-156">.NET 5.0</span><span class="sxs-lookup"><span data-stu-id="cacc8-156">.NET 5.0</span></span>

[!INCLUDE [sse-comparegreaterthan-intrinsics](../../../includes/core-changes/corefx/5.0/sse-comparegreaterthan-intrinsics.md)]

***

[!INCLUDE [createcountersetinstance-throws-invalidoperation](../../../includes/core-changes/corefx/5.0/createcountersetinstance-throws-invalidoperation.md)]

***

[!INCLUDE [platformabstractions-package-removed](../../../includes/core-changes/corefx/5.0/platformabstractions-package-removed.md)]

***

## <a name="net-core-30"></a><span data-ttu-id="cacc8-157">.NET Core 3.0</span><span class="sxs-lookup"><span data-stu-id="cacc8-157">.NET Core 3.0</span></span>

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

## <a name="net-core-21"></a><span data-ttu-id="cacc8-158">.NET Core 2.1</span><span class="sxs-lookup"><span data-stu-id="cacc8-158">.NET Core 2.1</span></span>

[!INCLUDE[Private fields added to built-in struct types](~/includes/core-changes/corefx/2.1/instantiate-struct.md)]

***

[!INCLUDE[Change in default value of UseShellExecute](~/includes/core-changes/corefx/2.1/process-start-changes.md)]

***

[!INCLUDE [OpenSSL versions on macOS](../../../includes/core-changes/corefx/openssl-dependencies-macos.md)]

***

## <a name="net-core-10"></a><span data-ttu-id="cacc8-159">.NET Core 1.0</span><span class="sxs-lookup"><span data-stu-id="cacc8-159">.NET Core 1.0</span></span>

[!INCLUDE [UnauthorizedAccessException thrown by FileSystemInfo.Attributes](~/includes/core-changes/corefx/1.0/filesysteminfo-attributes-exceptions.md)]

***

[!INCLUDE [corrupted-state-exceptions](~/includes/core-changes/corefx/1.0/corrupted-state-exceptions.md)]

***

[!INCLUDE [uribuilder-behavior-changes](../../../includes/core-changes/corefx/1.0/uribuilder-behavior-changes.md)]

***

[!INCLUDE [startinfo-throws-exception](../../../includes/core-changes/corefx/1.0/startinfo-throws-exception.md)]

***
