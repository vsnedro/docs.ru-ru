---
title: Критические изменения в библиотеке базовых классов
description: В этой статье приведен список критических изменений в основных библиотеках .NET.
ms.date: 09/20/2019
ms.openlocfilehash: 64510809a1cf69ea0e4c4816eb2df54233e8eceb
ms.sourcegitcommit: 97ce5363efa88179dd76e09de0103a500ca9b659
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/13/2020
ms.locfileid: "86281316"
---
# <a name="core-net-libraries-breaking-changes"></a><span data-ttu-id="84b84-103">Критические изменения в основных библиотеках .NET</span><span class="sxs-lookup"><span data-stu-id="84b84-103">Core .NET libraries breaking changes</span></span>

<span data-ttu-id="84b84-104">Основные библиотеки .NET предоставляет примитивы и другие общие типы, используемые в .NET Core.</span><span class="sxs-lookup"><span data-stu-id="84b84-104">The core .NET libraries provide the primitives and other general types used by .NET Core.</span></span>

<span data-ttu-id="84b84-105">На этой странице описаны следующие критические изменения:</span><span class="sxs-lookup"><span data-stu-id="84b84-105">The following breaking changes are documented on this page:</span></span>

| <span data-ttu-id="84b84-106">Критическое изменение</span><span class="sxs-lookup"><span data-stu-id="84b84-106">Breaking change</span></span> | <span data-ttu-id="84b84-107">Представленная версия</span><span class="sxs-lookup"><span data-stu-id="84b84-107">Version introduced</span></span> |
| - | :-: |
| [<span data-ttu-id="84b84-108">По умолчанию ActivityIdFormat имеет значение W3C</span><span class="sxs-lookup"><span data-stu-id="84b84-108">Default ActivityIdFormat is W3C</span></span>](#default-activityidformat-is-w3c) | <span data-ttu-id="84b84-109">5.0</span><span class="sxs-lookup"><span data-stu-id="84b84-109">5.0</span></span> |
| [<span data-ttu-id="84b84-110">Изменение в поведении для Vector2.Lerp и Vector4.Lerp</span><span class="sxs-lookup"><span data-stu-id="84b84-110">Behavior change for Vector2.Lerp and Vector4.Lerp</span></span>](#behavior-change-for-vector2lerp-and-vector4lerp) | <span data-ttu-id="84b84-111">5.0</span><span class="sxs-lookup"><span data-stu-id="84b84-111">5.0</span></span> |
| [<span data-ttu-id="84b84-112">Методы SSE и SSE2 CompareGreaterThan корректно обрабатывают входные данные, которые не являются числом</span><span class="sxs-lookup"><span data-stu-id="84b84-112">SSE and SSE2 CompareGreaterThan methods properly handle NaN inputs</span></span>](#sse-and-sse2-comparegreaterthan-methods-properly-handle-nan-inputs) | <span data-ttu-id="84b84-113">5.0</span><span class="sxs-lookup"><span data-stu-id="84b84-113">5.0</span></span> |
| [<span data-ttu-id="84b84-114">Теперь CounterSet.CreateCounterSetInstance создает исключение InvalidOperationException, если экземпляр уже существует</span><span class="sxs-lookup"><span data-stu-id="84b84-114">CounterSet.CreateCounterSetInstance now throws InvalidOperationException if instance already exist</span></span>](#countersetcreatecountersetinstance-now-throws-invalidoperationexception-if-instance-already-exists) | <span data-ttu-id="84b84-115">5.0</span><span class="sxs-lookup"><span data-stu-id="84b84-115">5.0</span></span> |
| [<span data-ttu-id="84b84-116">Удален пакет Microsoft.DotNet.PlatformAbstractions</span><span class="sxs-lookup"><span data-stu-id="84b84-116">Microsoft.DotNet.PlatformAbstractions package removed</span></span>](#microsoftdotnetplatformabstractions-package-removed) | <span data-ttu-id="84b84-117">5.0</span><span class="sxs-lookup"><span data-stu-id="84b84-117">5.0</span></span> |
| [<span data-ttu-id="84b84-118">Интерфейсы API, сообщающие версию, теперь сообщают версию продукта, а не файла</span><span class="sxs-lookup"><span data-stu-id="84b84-118">APIs that report version now report product and not file version</span></span>](#apis-that-report-version-now-report-product-and-not-file-version) | <span data-ttu-id="84b84-119">3.0</span><span class="sxs-lookup"><span data-stu-id="84b84-119">3.0</span></span> |
| [<span data-ttu-id="84b84-120">Пользовательские экземпляры EncoderFallbackBuffer не поддерживают рекурсивный откат</span><span class="sxs-lookup"><span data-stu-id="84b84-120">Custom EncoderFallbackBuffer instances cannot fall back recursively</span></span>](#custom-encoderfallbackbuffer-instances-cannot-fall-back-recursively) | <span data-ttu-id="84b84-121">3.0</span><span class="sxs-lookup"><span data-stu-id="84b84-121">3.0</span></span> |
| [<span data-ttu-id="84b84-122">Изменено поведение форматирования и анализа при наличии плавающей запятой</span><span class="sxs-lookup"><span data-stu-id="84b84-122">Floating point formatting and parsing behavior changes</span></span>](#floating-point-formatting-and-parsing-behavior-changed) | <span data-ttu-id="84b84-123">3.0</span><span class="sxs-lookup"><span data-stu-id="84b84-123">3.0</span></span> |
| [<span data-ttu-id="84b84-124">Операции синтаксического анализа с плавающей запятой больше не завершаются ошибкой и не вызывают исключение OverflowException</span><span class="sxs-lookup"><span data-stu-id="84b84-124">Floating-point parsing operations no longer fail or throw an OverflowException</span></span>](#floating-point-parsing-operations-no-longer-fail-or-throw-an-overflowexception) | <span data-ttu-id="84b84-125">3.0</span><span class="sxs-lookup"><span data-stu-id="84b84-125">3.0</span></span> |
| [<span data-ttu-id="84b84-126">Исключение InvalidAsynchronousStateException перенесено в другую сборку</span><span class="sxs-lookup"><span data-stu-id="84b84-126">InvalidAsynchronousStateException moved to another assembly</span></span>](#invalidasynchronousstateexception-moved-to-another-assembly) | <span data-ttu-id="84b84-127">3.0</span><span class="sxs-lookup"><span data-stu-id="84b84-127">3.0</span></span> |
| [<span data-ttu-id="84b84-128">Замена неправильно сформированных последовательностей байтов в кодировке UTF-8 в соответствии с правилами Юникода</span><span class="sxs-lookup"><span data-stu-id="84b84-128">Replacing ill-formed UTF-8 byte sequences follows Unicode guidelines</span></span>](#replacing-ill-formed-utf-8-byte-sequences-follows-unicode-guidelines) | <span data-ttu-id="84b84-129">3.0</span><span class="sxs-lookup"><span data-stu-id="84b84-129">3.0</span></span> |
| [<span data-ttu-id="84b84-130">Класс TypeDescriptionProviderAttribute перенесен в другую сборку</span><span class="sxs-lookup"><span data-stu-id="84b84-130">TypeDescriptionProviderAttribute moved to another assembly</span></span>](#typedescriptionproviderattribute-moved-to-another-assembly) | <span data-ttu-id="84b84-131">3.0</span><span class="sxs-lookup"><span data-stu-id="84b84-131">3.0</span></span> |
| [<span data-ttu-id="84b84-132">ZipArchiveEntry больше не обрабатывает архивы с несогласованными размерами записей</span><span class="sxs-lookup"><span data-stu-id="84b84-132">ZipArchiveEntry no longer handles archives with inconsistent entry sizes</span></span>](#ziparchiveentry-no-longer-handles-archives-with-inconsistent-entry-sizes) | <span data-ttu-id="84b84-133">3.0</span><span class="sxs-lookup"><span data-stu-id="84b84-133">3.0</span></span> |
| [<span data-ttu-id="84b84-134">Тип исключения сериализатора JSON изменен с JsonException на NotSupportedException</span><span class="sxs-lookup"><span data-stu-id="84b84-134">JSON serializer exception type changed from JsonException to NotSupportedException</span></span>](#json-serializer-exception-type-changed-from-jsonexception-to-notsupportedexception) | <span data-ttu-id="84b84-135">3.0</span><span class="sxs-lookup"><span data-stu-id="84b84-135">3.0</span></span> |
| [<span data-ttu-id="84b84-136">Внесены изменения в семантику (string)null в Utf8JsonWriter</span><span class="sxs-lookup"><span data-stu-id="84b84-136">Change in semantics of (string)null in Utf8JsonWriter</span></span>](#change-in-semantics-of-stringnull-in-utf8jsonwriter) | <span data-ttu-id="84b84-137">3.0</span><span class="sxs-lookup"><span data-stu-id="84b84-137">3.0</span></span> |
| [<span data-ttu-id="84b84-138">Методы JsonEncodedText.Encode содержат дополнительный аргумент JavaScriptEncoder</span><span class="sxs-lookup"><span data-stu-id="84b84-138">JsonEncodedText.Encode methods have an additional JavaScriptEncoder argument</span></span>](#jsonencodedtextencode-methods-have-an-additional-javascriptencoder-argument) | <span data-ttu-id="84b84-139">3.0</span><span class="sxs-lookup"><span data-stu-id="84b84-139">3.0</span></span> |
| [<span data-ttu-id="84b84-140">Изменена подпись JsonFactoryConverter.CreateConverter</span><span class="sxs-lookup"><span data-stu-id="84b84-140">JsonFactoryConverter.CreateConverter signature changed</span></span>](#jsonfactoryconvertercreateconverter-signature-changed) | <span data-ttu-id="84b84-141">3.0</span><span class="sxs-lookup"><span data-stu-id="84b84-141">3.0</span></span> |
| [<span data-ttu-id="84b84-142">Внесены изменения в API JsonElement</span><span class="sxs-lookup"><span data-stu-id="84b84-142">JsonElement API changes</span></span>](#jsonelement-api-changes) | <span data-ttu-id="84b84-143">3.0</span><span class="sxs-lookup"><span data-stu-id="84b84-143">3.0</span></span> |
| [<span data-ttu-id="84b84-144">FieldInfo.SetValue вызывает исключение для статических полей и полей только для инициализации</span><span class="sxs-lookup"><span data-stu-id="84b84-144">FieldInfo.SetValue throws exception for static, init-only fields</span></span>](#fieldinfosetvalue-throws-exception-for-static-init-only-fields) | <span data-ttu-id="84b84-145">3.0</span><span class="sxs-lookup"><span data-stu-id="84b84-145">3.0</span></span> |
| [<span data-ttu-id="84b84-146">Во встроенные типы структур добавлены частные поля</span><span class="sxs-lookup"><span data-stu-id="84b84-146">Private fields added to built-in struct types</span></span>](#private-fields-added-to-built-in-struct-types) | <span data-ttu-id="84b84-147">2.1</span><span class="sxs-lookup"><span data-stu-id="84b84-147">2.1</span></span> |
| [<span data-ttu-id="84b84-148">Изменено значение по умолчанию для UseShellExecute</span><span class="sxs-lookup"><span data-stu-id="84b84-148">Change in default value of UseShellExecute</span></span>](#change-in-default-value-of-useshellexecute) | <span data-ttu-id="84b84-149">2.1</span><span class="sxs-lookup"><span data-stu-id="84b84-149">2.1</span></span> |
| [<span data-ttu-id="84b84-150">Версии OpenSSL в macOS</span><span class="sxs-lookup"><span data-stu-id="84b84-150">OpenSSL versions on macOS</span></span>](#openssl-versions-on-macos) | <span data-ttu-id="84b84-151">2.1</span><span class="sxs-lookup"><span data-stu-id="84b84-151">2.1</span></span> |
| [<span data-ttu-id="84b84-152">Исключение UnauthorizedAccessException, вызванное FileSystemInfo.Attributes</span><span class="sxs-lookup"><span data-stu-id="84b84-152">UnauthorizedAccessException thrown by FileSystemInfo.Attributes</span></span>](#unauthorizedaccessexception-thrown-by-filesysteminfoattributes) | <span data-ttu-id="84b84-153">1.0</span><span class="sxs-lookup"><span data-stu-id="84b84-153">1.0</span></span> |
| [<span data-ttu-id="84b84-154">Обработка исключений с поврежденным состоянием процесса не поддерживается</span><span class="sxs-lookup"><span data-stu-id="84b84-154">Handling corrupted-process-state exceptions is not supported</span></span>](#handling-corrupted-state-exceptions-is-not-supported) | <span data-ttu-id="84b84-155">1.0</span><span class="sxs-lookup"><span data-stu-id="84b84-155">1.0</span></span> |
| [<span data-ttu-id="84b84-156">Для свойств UriBuilder больше не добавляются начальные символы</span><span class="sxs-lookup"><span data-stu-id="84b84-156">UriBuilder properties no longer prepend leading characters</span></span>](#uribuilder-properties-no-longer-prepend-leading-characters) | <span data-ttu-id="84b84-157">1.0</span><span class="sxs-lookup"><span data-stu-id="84b84-157">1.0</span></span> |
| [<span data-ttu-id="84b84-158">Process.StartInfo выдает исключение InvalidOperationException для процессов, которые не были запущены</span><span class="sxs-lookup"><span data-stu-id="84b84-158">Process.StartInfo throws InvalidOperationException for processes you didn't start</span></span>](#processstartinfo-throws-invalidoperationexception-for-processes-you-didnt-start) | <span data-ttu-id="84b84-159">1.0</span><span class="sxs-lookup"><span data-stu-id="84b84-159">1.0</span></span> |

## <a name="net-50"></a><span data-ttu-id="84b84-160">.NET 5.0</span><span class="sxs-lookup"><span data-stu-id="84b84-160">.NET 5.0</span></span>

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

## <a name="net-core-30"></a><span data-ttu-id="84b84-161">.NET Core 3.0</span><span class="sxs-lookup"><span data-stu-id="84b84-161">.NET Core 3.0</span></span>

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

## <a name="net-core-21"></a><span data-ttu-id="84b84-162">.NET Core 2.1</span><span class="sxs-lookup"><span data-stu-id="84b84-162">.NET Core 2.1</span></span>

[!INCLUDE[Private fields added to built-in struct types](~/includes/core-changes/corefx/2.1/instantiate-struct.md)]

***

[!INCLUDE[Change in default value of UseShellExecute](~/includes/core-changes/corefx/2.1/process-start-changes.md)]

***

[!INCLUDE [OpenSSL versions on macOS](../../../includes/core-changes/corefx/openssl-dependencies-macos.md)]

***

## <a name="net-core-10"></a><span data-ttu-id="84b84-163">.NET Core 1.0</span><span class="sxs-lookup"><span data-stu-id="84b84-163">.NET Core 1.0</span></span>

[!INCLUDE [UnauthorizedAccessException thrown by FileSystemInfo.Attributes](~/includes/core-changes/corefx/1.0/filesysteminfo-attributes-exceptions.md)]

***

[!INCLUDE [corrupted-state-exceptions](~/includes/core-changes/corefx/1.0/corrupted-state-exceptions.md)]

***

[!INCLUDE [uribuilder-behavior-changes](../../../includes/core-changes/corefx/1.0/uribuilder-behavior-changes.md)]

***

[!INCLUDE [startinfo-throws-exception](../../../includes/core-changes/corefx/1.0/startinfo-throws-exception.md)]

***
