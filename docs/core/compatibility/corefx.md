---
title: Критические изменения в библиотеке базовых классов
description: В этой статье приведен список критических изменений в основных библиотеках .NET.
ms.date: 07/27/2020
ms.openlocfilehash: 558aa1d76831cd15e2028c17d2b0b2e82f64ef9a
ms.sourcegitcommit: b4f8849c47c1a7145eb26ce68bc9f9976e0dbec3
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/03/2020
ms.locfileid: "87517335"
---
# <a name="core-net-libraries-breaking-changes"></a><span data-ttu-id="e2a22-103">Критические изменения в основных библиотеках .NET</span><span class="sxs-lookup"><span data-stu-id="e2a22-103">Core .NET libraries breaking changes</span></span>

<span data-ttu-id="e2a22-104">Основные библиотеки .NET предоставляет примитивы и другие общие типы, используемые в .NET Core.</span><span class="sxs-lookup"><span data-stu-id="e2a22-104">The core .NET libraries provide the primitives and other general types used by .NET Core.</span></span>

<span data-ttu-id="e2a22-105">На этой странице описаны следующие критические изменения:</span><span class="sxs-lookup"><span data-stu-id="e2a22-105">The following breaking changes are documented on this page:</span></span>

| <span data-ttu-id="e2a22-106">Критическое изменение</span><span class="sxs-lookup"><span data-stu-id="e2a22-106">Breaking change</span></span> | <span data-ttu-id="e2a22-107">Представленная версия</span><span class="sxs-lookup"><span data-stu-id="e2a22-107">Version introduced</span></span> |
| - | :-: |
| [<span data-ttu-id="e2a22-108">Методы сериализации BinaryFormatter устарели и запрещены в приложениях ASP.NET</span><span class="sxs-lookup"><span data-stu-id="e2a22-108">BinaryFormatter serialization methods are obsolete and prohibited in ASP.NET apps</span></span>](#binaryformatter-serialization-methods-are-obsolete-and-prohibited-in-aspnet-apps) | <span data-ttu-id="e2a22-109">5.0</span><span class="sxs-lookup"><span data-stu-id="e2a22-109">5.0</span></span> |
| [<span data-ttu-id="e2a22-110">Пути к коду в кодировке UTF-7 устарели</span><span class="sxs-lookup"><span data-stu-id="e2a22-110">UTF-7 code paths are obsolete</span></span>](#utf-7-code-paths-are-obsolete) | <span data-ttu-id="e2a22-111">5.0</span><span class="sxs-lookup"><span data-stu-id="e2a22-111">5.0</span></span> |
| [<span data-ttu-id="e2a22-112">Vector\<T> всегда вызывает исключение NotSupportedException для неподдерживаемых типов</span><span class="sxs-lookup"><span data-stu-id="e2a22-112">Vector\<T> always throws NotSupportedException for unsupported types</span></span>](#vectort-always-throws-notsupportedexception-for-unsupported-types) | <span data-ttu-id="e2a22-113">5.0</span><span class="sxs-lookup"><span data-stu-id="e2a22-113">5.0</span></span> |
| [<span data-ttu-id="e2a22-114">По умолчанию ActivityIdFormat имеет значение W3C</span><span class="sxs-lookup"><span data-stu-id="e2a22-114">Default ActivityIdFormat is W3C</span></span>](#default-activityidformat-is-w3c) | <span data-ttu-id="e2a22-115">5.0</span><span class="sxs-lookup"><span data-stu-id="e2a22-115">5.0</span></span> |
| [<span data-ttu-id="e2a22-116">Изменение в поведении для Vector2.Lerp и Vector4.Lerp</span><span class="sxs-lookup"><span data-stu-id="e2a22-116">Behavior change for Vector2.Lerp and Vector4.Lerp</span></span>](#behavior-change-for-vector2lerp-and-vector4lerp) | <span data-ttu-id="e2a22-117">5.0</span><span class="sxs-lookup"><span data-stu-id="e2a22-117">5.0</span></span> |
| [<span data-ttu-id="e2a22-118">Методы SSE и SSE2 CompareGreaterThan корректно обрабатывают входные данные, которые не являются числом</span><span class="sxs-lookup"><span data-stu-id="e2a22-118">SSE and SSE2 CompareGreaterThan methods properly handle NaN inputs</span></span>](#sse-and-sse2-comparegreaterthan-methods-properly-handle-nan-inputs) | <span data-ttu-id="e2a22-119">5.0</span><span class="sxs-lookup"><span data-stu-id="e2a22-119">5.0</span></span> |
| [<span data-ttu-id="e2a22-120">Теперь CounterSet.CreateCounterSetInstance создает исключение InvalidOperationException, если экземпляр уже существует</span><span class="sxs-lookup"><span data-stu-id="e2a22-120">CounterSet.CreateCounterSetInstance now throws InvalidOperationException if instance already exist</span></span>](#countersetcreatecountersetinstance-now-throws-invalidoperationexception-if-instance-already-exists) | <span data-ttu-id="e2a22-121">5.0</span><span class="sxs-lookup"><span data-stu-id="e2a22-121">5.0</span></span> |
| [<span data-ttu-id="e2a22-122">Удален пакет Microsoft.DotNet.PlatformAbstractions</span><span class="sxs-lookup"><span data-stu-id="e2a22-122">Microsoft.DotNet.PlatformAbstractions package removed</span></span>](#microsoftdotnetplatformabstractions-package-removed) | <span data-ttu-id="e2a22-123">5.0</span><span class="sxs-lookup"><span data-stu-id="e2a22-123">5.0</span></span> |
| [<span data-ttu-id="e2a22-124">Интерфейсы API, сообщающие версию, теперь сообщают версию продукта, а не файла</span><span class="sxs-lookup"><span data-stu-id="e2a22-124">APIs that report version now report product and not file version</span></span>](#apis-that-report-version-now-report-product-and-not-file-version) | <span data-ttu-id="e2a22-125">3.0</span><span class="sxs-lookup"><span data-stu-id="e2a22-125">3.0</span></span> |
| [<span data-ttu-id="e2a22-126">Пользовательские экземпляры EncoderFallbackBuffer не поддерживают рекурсивный откат</span><span class="sxs-lookup"><span data-stu-id="e2a22-126">Custom EncoderFallbackBuffer instances cannot fall back recursively</span></span>](#custom-encoderfallbackbuffer-instances-cannot-fall-back-recursively) | <span data-ttu-id="e2a22-127">3.0</span><span class="sxs-lookup"><span data-stu-id="e2a22-127">3.0</span></span> |
| [<span data-ttu-id="e2a22-128">Изменено поведение форматирования и анализа при наличии плавающей запятой</span><span class="sxs-lookup"><span data-stu-id="e2a22-128">Floating point formatting and parsing behavior changes</span></span>](#floating-point-formatting-and-parsing-behavior-changed) | <span data-ttu-id="e2a22-129">3.0</span><span class="sxs-lookup"><span data-stu-id="e2a22-129">3.0</span></span> |
| [<span data-ttu-id="e2a22-130">Операции синтаксического анализа с плавающей запятой больше не завершаются ошибкой и не вызывают исключение OverflowException</span><span class="sxs-lookup"><span data-stu-id="e2a22-130">Floating-point parsing operations no longer fail or throw an OverflowException</span></span>](#floating-point-parsing-operations-no-longer-fail-or-throw-an-overflowexception) | <span data-ttu-id="e2a22-131">3.0</span><span class="sxs-lookup"><span data-stu-id="e2a22-131">3.0</span></span> |
| [<span data-ttu-id="e2a22-132">Исключение InvalidAsynchronousStateException перенесено в другую сборку</span><span class="sxs-lookup"><span data-stu-id="e2a22-132">InvalidAsynchronousStateException moved to another assembly</span></span>](#invalidasynchronousstateexception-moved-to-another-assembly) | <span data-ttu-id="e2a22-133">3.0</span><span class="sxs-lookup"><span data-stu-id="e2a22-133">3.0</span></span> |
| [<span data-ttu-id="e2a22-134">Замена неправильно сформированных последовательностей байтов в кодировке UTF-8 в соответствии с правилами Юникода</span><span class="sxs-lookup"><span data-stu-id="e2a22-134">Replacing ill-formed UTF-8 byte sequences follows Unicode guidelines</span></span>](#replacing-ill-formed-utf-8-byte-sequences-follows-unicode-guidelines) | <span data-ttu-id="e2a22-135">3.0</span><span class="sxs-lookup"><span data-stu-id="e2a22-135">3.0</span></span> |
| [<span data-ttu-id="e2a22-136">Класс TypeDescriptionProviderAttribute перенесен в другую сборку</span><span class="sxs-lookup"><span data-stu-id="e2a22-136">TypeDescriptionProviderAttribute moved to another assembly</span></span>](#typedescriptionproviderattribute-moved-to-another-assembly) | <span data-ttu-id="e2a22-137">3.0</span><span class="sxs-lookup"><span data-stu-id="e2a22-137">3.0</span></span> |
| [<span data-ttu-id="e2a22-138">ZipArchiveEntry больше не обрабатывает архивы с несогласованными размерами записей</span><span class="sxs-lookup"><span data-stu-id="e2a22-138">ZipArchiveEntry no longer handles archives with inconsistent entry sizes</span></span>](#ziparchiveentry-no-longer-handles-archives-with-inconsistent-entry-sizes) | <span data-ttu-id="e2a22-139">3.0</span><span class="sxs-lookup"><span data-stu-id="e2a22-139">3.0</span></span> |
| [<span data-ttu-id="e2a22-140">Внесены изменения в семантику (string)null в Utf8JsonWriter</span><span class="sxs-lookup"><span data-stu-id="e2a22-140">Change in semantics of (string)null in Utf8JsonWriter</span></span>](#change-in-semantics-of-stringnull-in-utf8jsonwriter) | <span data-ttu-id="e2a22-141">3.0</span><span class="sxs-lookup"><span data-stu-id="e2a22-141">3.0</span></span> |
| [<span data-ttu-id="e2a22-142">Методы JsonEncodedText.Encode содержат дополнительный аргумент JavaScriptEncoder</span><span class="sxs-lookup"><span data-stu-id="e2a22-142">JsonEncodedText.Encode methods have an additional JavaScriptEncoder argument</span></span>](#jsonencodedtextencode-methods-have-an-additional-javascriptencoder-argument) | <span data-ttu-id="e2a22-143">3.0</span><span class="sxs-lookup"><span data-stu-id="e2a22-143">3.0</span></span> |
| [<span data-ttu-id="e2a22-144">Изменена подпись JsonFactoryConverter.CreateConverter</span><span class="sxs-lookup"><span data-stu-id="e2a22-144">JsonFactoryConverter.CreateConverter signature changed</span></span>](#jsonfactoryconvertercreateconverter-signature-changed) | <span data-ttu-id="e2a22-145">3.0</span><span class="sxs-lookup"><span data-stu-id="e2a22-145">3.0</span></span> |
| [<span data-ttu-id="e2a22-146">Внесены изменения в API JsonElement</span><span class="sxs-lookup"><span data-stu-id="e2a22-146">JsonElement API changes</span></span>](#jsonelement-api-changes) | <span data-ttu-id="e2a22-147">3.0</span><span class="sxs-lookup"><span data-stu-id="e2a22-147">3.0</span></span> |
| [<span data-ttu-id="e2a22-148">FieldInfo.SetValue вызывает исключение для статических полей и полей только для инициализации</span><span class="sxs-lookup"><span data-stu-id="e2a22-148">FieldInfo.SetValue throws exception for static, init-only fields</span></span>](#fieldinfosetvalue-throws-exception-for-static-init-only-fields) | <span data-ttu-id="e2a22-149">3.0</span><span class="sxs-lookup"><span data-stu-id="e2a22-149">3.0</span></span> |
| [<span data-ttu-id="e2a22-150">Во встроенные типы структур добавлены частные поля</span><span class="sxs-lookup"><span data-stu-id="e2a22-150">Private fields added to built-in struct types</span></span>](#private-fields-added-to-built-in-struct-types) | <span data-ttu-id="e2a22-151">2.1</span><span class="sxs-lookup"><span data-stu-id="e2a22-151">2.1</span></span> |
| [<span data-ttu-id="e2a22-152">Изменено значение по умолчанию для UseShellExecute</span><span class="sxs-lookup"><span data-stu-id="e2a22-152">Change in default value of UseShellExecute</span></span>](#change-in-default-value-of-useshellexecute) | <span data-ttu-id="e2a22-153">2.1</span><span class="sxs-lookup"><span data-stu-id="e2a22-153">2.1</span></span> |
| [<span data-ttu-id="e2a22-154">Версии OpenSSL в macOS</span><span class="sxs-lookup"><span data-stu-id="e2a22-154">OpenSSL versions on macOS</span></span>](#openssl-versions-on-macos) | <span data-ttu-id="e2a22-155">2.1</span><span class="sxs-lookup"><span data-stu-id="e2a22-155">2.1</span></span> |
| [<span data-ttu-id="e2a22-156">Исключение UnauthorizedAccessException, вызванное FileSystemInfo.Attributes</span><span class="sxs-lookup"><span data-stu-id="e2a22-156">UnauthorizedAccessException thrown by FileSystemInfo.Attributes</span></span>](#unauthorizedaccessexception-thrown-by-filesysteminfoattributes) | <span data-ttu-id="e2a22-157">1.0</span><span class="sxs-lookup"><span data-stu-id="e2a22-157">1.0</span></span> |
| [<span data-ttu-id="e2a22-158">Обработка исключений с поврежденным состоянием процесса не поддерживается</span><span class="sxs-lookup"><span data-stu-id="e2a22-158">Handling corrupted-process-state exceptions is not supported</span></span>](#handling-corrupted-state-exceptions-is-not-supported) | <span data-ttu-id="e2a22-159">1.0</span><span class="sxs-lookup"><span data-stu-id="e2a22-159">1.0</span></span> |
| [<span data-ttu-id="e2a22-160">Для свойств UriBuilder больше не добавляются начальные символы</span><span class="sxs-lookup"><span data-stu-id="e2a22-160">UriBuilder properties no longer prepend leading characters</span></span>](#uribuilder-properties-no-longer-prepend-leading-characters) | <span data-ttu-id="e2a22-161">1.0</span><span class="sxs-lookup"><span data-stu-id="e2a22-161">1.0</span></span> |
| [<span data-ttu-id="e2a22-162">Process.StartInfo выдает исключение InvalidOperationException для процессов, которые не были запущены</span><span class="sxs-lookup"><span data-stu-id="e2a22-162">Process.StartInfo throws InvalidOperationException for processes you didn't start</span></span>](#processstartinfo-throws-invalidoperationexception-for-processes-you-didnt-start) | <span data-ttu-id="e2a22-163">1.0</span><span class="sxs-lookup"><span data-stu-id="e2a22-163">1.0</span></span> |

## <a name="net-50"></a><span data-ttu-id="e2a22-164">.NET 5.0</span><span class="sxs-lookup"><span data-stu-id="e2a22-164">.NET 5.0</span></span>

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

## <a name="net-core-30"></a><span data-ttu-id="e2a22-165">.NET Core 3.0</span><span class="sxs-lookup"><span data-stu-id="e2a22-165">.NET Core 3.0</span></span>

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

## <a name="net-core-21"></a><span data-ttu-id="e2a22-166">.NET Core 2.1</span><span class="sxs-lookup"><span data-stu-id="e2a22-166">.NET Core 2.1</span></span>

[!INCLUDE[Private fields added to built-in struct types](~/includes/core-changes/corefx/2.1/instantiate-struct.md)]

***

[!INCLUDE[Change in default value of UseShellExecute](~/includes/core-changes/corefx/2.1/process-start-changes.md)]

***

[!INCLUDE [OpenSSL versions on macOS](../../../includes/core-changes/corefx/openssl-dependencies-macos.md)]

***

## <a name="net-core-10"></a><span data-ttu-id="e2a22-167">.NET Core 1.0</span><span class="sxs-lookup"><span data-stu-id="e2a22-167">.NET Core 1.0</span></span>

[!INCLUDE [UnauthorizedAccessException thrown by FileSystemInfo.Attributes](~/includes/core-changes/corefx/1.0/filesysteminfo-attributes-exceptions.md)]

***

[!INCLUDE [corrupted-state-exceptions](~/includes/core-changes/corefx/1.0/corrupted-state-exceptions.md)]

***

[!INCLUDE [uribuilder-behavior-changes](../../../includes/core-changes/corefx/1.0/uribuilder-behavior-changes.md)]

***

[!INCLUDE [startinfo-throws-exception](../../../includes/core-changes/corefx/1.0/startinfo-throws-exception.md)]

***
