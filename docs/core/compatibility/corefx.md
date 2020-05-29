---
title: Критические изменения в библиотеке базовых классов
description: В этой статье приведен список критических изменений в основных библиотеках .NET.
ms.date: 09/20/2019
ms.openlocfilehash: ca50123b842c256607d47010dbef9b216ece4661
ms.sourcegitcommit: 9a4488a3625866335e83a20da5e9c5286b1f034c
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/15/2020
ms.locfileid: "83420437"
---
# <a name="core-net-libraries-breaking-changes"></a><span data-ttu-id="dfd50-103">Критические изменения в основных библиотеках .NET</span><span class="sxs-lookup"><span data-stu-id="dfd50-103">Core .NET libraries breaking changes</span></span>

<span data-ttu-id="dfd50-104">Основные библиотеки .NET предоставляет примитивы и другие общие типы, используемые в .NET Core.</span><span class="sxs-lookup"><span data-stu-id="dfd50-104">The core .NET libraries provide the primitives and other general types used by .NET Core.</span></span>

<span data-ttu-id="dfd50-105">На этой странице описаны следующие критические изменения:</span><span class="sxs-lookup"><span data-stu-id="dfd50-105">The following breaking changes are documented on this page:</span></span>

| <span data-ttu-id="dfd50-106">Критическое изменение</span><span class="sxs-lookup"><span data-stu-id="dfd50-106">Breaking change</span></span> | <span data-ttu-id="dfd50-107">Представленная версия</span><span class="sxs-lookup"><span data-stu-id="dfd50-107">Version introduced</span></span> |
| - | :-: |
| [<span data-ttu-id="dfd50-108">Методы SSE и SSE2 CompareGreaterThan корректно обрабатывают входные данные, которые не являются числом</span><span class="sxs-lookup"><span data-stu-id="dfd50-108">SSE and SSE2 CompareGreaterThan methods properly handle NaN inputs</span></span>](#sse-and-sse2-comparegreaterthan-methods-properly-handle-nan-inputs) | <span data-ttu-id="dfd50-109">5.0</span><span class="sxs-lookup"><span data-stu-id="dfd50-109">5.0</span></span> |
| [<span data-ttu-id="dfd50-110">Интерфейсы API, сообщающие версию, теперь сообщают версию продукта, а не файла</span><span class="sxs-lookup"><span data-stu-id="dfd50-110">APIs that report version now report product and not file version</span></span>](#apis-that-report-version-now-report-product-and-not-file-version) | <span data-ttu-id="dfd50-111">3.0</span><span class="sxs-lookup"><span data-stu-id="dfd50-111">3.0</span></span> |
| [<span data-ttu-id="dfd50-112">Пользовательские экземпляры EncoderFallbackBuffer не поддерживают рекурсивный откат</span><span class="sxs-lookup"><span data-stu-id="dfd50-112">Custom EncoderFallbackBuffer instances cannot fall back recursively</span></span>](#custom-encoderfallbackbuffer-instances-cannot-fall-back-recursively) | <span data-ttu-id="dfd50-113">3.0</span><span class="sxs-lookup"><span data-stu-id="dfd50-113">3.0</span></span> |
| [<span data-ttu-id="dfd50-114">Изменено поведение форматирования и анализа при наличии плавающей запятой</span><span class="sxs-lookup"><span data-stu-id="dfd50-114">Floating point formatting and parsing behavior changes</span></span>](#floating-point-formatting-and-parsing-behavior-changed) | <span data-ttu-id="dfd50-115">3.0</span><span class="sxs-lookup"><span data-stu-id="dfd50-115">3.0</span></span> |
| [<span data-ttu-id="dfd50-116">Операции синтаксического анализа с плавающей запятой больше не завершаются ошибкой и не вызывают исключение OverflowException</span><span class="sxs-lookup"><span data-stu-id="dfd50-116">Floating-point parsing operations no longer fail or throw an OverflowException</span></span>](#floating-point-parsing-operations-no-longer-fail-or-throw-an-overflowexception) | <span data-ttu-id="dfd50-117">3.0</span><span class="sxs-lookup"><span data-stu-id="dfd50-117">3.0</span></span> |
| [<span data-ttu-id="dfd50-118">Исключение InvalidAsynchronousStateException перенесено в другую сборку</span><span class="sxs-lookup"><span data-stu-id="dfd50-118">InvalidAsynchronousStateException moved to another assembly</span></span>](#invalidasynchronousstateexception-moved-to-another-assembly) | <span data-ttu-id="dfd50-119">3.0</span><span class="sxs-lookup"><span data-stu-id="dfd50-119">3.0</span></span> |
| [<span data-ttu-id="dfd50-120">Замена неправильно сформированных последовательностей байтов в кодировке UTF-8 в соответствии с правилами Юникода</span><span class="sxs-lookup"><span data-stu-id="dfd50-120">Replacing ill-formed UTF-8 byte sequences follows Unicode guidelines</span></span>](#replacing-ill-formed-utf-8-byte-sequences-follows-unicode-guidelines) | <span data-ttu-id="dfd50-121">3.0</span><span class="sxs-lookup"><span data-stu-id="dfd50-121">3.0</span></span> |
| [<span data-ttu-id="dfd50-122">Класс TypeDescriptionProviderAttribute перенесен в другую сборку</span><span class="sxs-lookup"><span data-stu-id="dfd50-122">TypeDescriptionProviderAttribute moved to another assembly</span></span>](#typedescriptionproviderattribute-moved-to-another-assembly) | <span data-ttu-id="dfd50-123">3.0</span><span class="sxs-lookup"><span data-stu-id="dfd50-123">3.0</span></span> |
| [<span data-ttu-id="dfd50-124">ZipArchiveEntry больше не обрабатывает архивы с несогласованными размерами записей</span><span class="sxs-lookup"><span data-stu-id="dfd50-124">ZipArchiveEntry no longer handles archives with inconsistent entry sizes</span></span>](#ziparchiveentry-no-longer-handles-archives-with-inconsistent-entry-sizes) | <span data-ttu-id="dfd50-125">3.0</span><span class="sxs-lookup"><span data-stu-id="dfd50-125">3.0</span></span> |
| [<span data-ttu-id="dfd50-126">Тип исключения сериализатора JSON изменен с JsonException на NotSupportedException</span><span class="sxs-lookup"><span data-stu-id="dfd50-126">JSON serializer exception type changed from JsonException to NotSupportedException</span></span>](#json-serializer-exception-type-changed-from-jsonexception-to-notsupportedexception) | <span data-ttu-id="dfd50-127">3.0</span><span class="sxs-lookup"><span data-stu-id="dfd50-127">3.0</span></span> |
| [<span data-ttu-id="dfd50-128">Внесены изменения в семантику (string)null в Utf8JsonWriter</span><span class="sxs-lookup"><span data-stu-id="dfd50-128">Change in semantics of (string)null in Utf8JsonWriter</span></span>](#change-in-semantics-of-stringnull-in-utf8jsonwriter) | <span data-ttu-id="dfd50-129">3.0</span><span class="sxs-lookup"><span data-stu-id="dfd50-129">3.0</span></span> |
| [<span data-ttu-id="dfd50-130">Методы JsonEncodedText.Encode содержат дополнительный аргумент JavaScriptEncoder</span><span class="sxs-lookup"><span data-stu-id="dfd50-130">JsonEncodedText.Encode methods have an additional JavaScriptEncoder argument</span></span>](#jsonencodedtextencode-methods-have-an-additional-javascriptencoder-argument) | <span data-ttu-id="dfd50-131">3.0</span><span class="sxs-lookup"><span data-stu-id="dfd50-131">3.0</span></span> |
| [<span data-ttu-id="dfd50-132">Изменена подпись JsonFactoryConverter.CreateConverter</span><span class="sxs-lookup"><span data-stu-id="dfd50-132">JsonFactoryConverter.CreateConverter signature changed</span></span>](#jsonfactoryconvertercreateconverter-signature-changed) | <span data-ttu-id="dfd50-133">3.0</span><span class="sxs-lookup"><span data-stu-id="dfd50-133">3.0</span></span> |
| [<span data-ttu-id="dfd50-134">Внесены изменения в API JsonElement</span><span class="sxs-lookup"><span data-stu-id="dfd50-134">JsonElement API changes</span></span>](#jsonelement-api-changes) | <span data-ttu-id="dfd50-135">3.0</span><span class="sxs-lookup"><span data-stu-id="dfd50-135">3.0</span></span> |
| [<span data-ttu-id="dfd50-136">FieldInfo.SetValue вызывает исключение для статических полей и полей только для инициализации</span><span class="sxs-lookup"><span data-stu-id="dfd50-136">FieldInfo.SetValue throws exception for static, init-only fields</span></span>](#fieldinfosetvalue-throws-exception-for-static-init-only-fields) | <span data-ttu-id="dfd50-137">3.0</span><span class="sxs-lookup"><span data-stu-id="dfd50-137">3.0</span></span> |
| [<span data-ttu-id="dfd50-138">Во встроенные типы структур добавлены частные поля</span><span class="sxs-lookup"><span data-stu-id="dfd50-138">Private fields added to built-in struct types</span></span>](#private-fields-added-to-built-in-struct-types) | <span data-ttu-id="dfd50-139">2.1</span><span class="sxs-lookup"><span data-stu-id="dfd50-139">2.1</span></span> |
| [<span data-ttu-id="dfd50-140">Изменено значение по умолчанию для UseShellExecute</span><span class="sxs-lookup"><span data-stu-id="dfd50-140">Change in default value of UseShellExecute</span></span>](#change-in-default-value-of-useshellexecute) | <span data-ttu-id="dfd50-141">2.1</span><span class="sxs-lookup"><span data-stu-id="dfd50-141">2.1</span></span> |
| [<span data-ttu-id="dfd50-142">Версии OpenSSL в macOS</span><span class="sxs-lookup"><span data-stu-id="dfd50-142">OpenSSL versions on macOS</span></span>](#openssl-versions-on-macos) | <span data-ttu-id="dfd50-143">2.1</span><span class="sxs-lookup"><span data-stu-id="dfd50-143">2.1</span></span> |
| [<span data-ttu-id="dfd50-144">Исключение UnauthorizedAccessException, вызванное FileSystemInfo.Attributes</span><span class="sxs-lookup"><span data-stu-id="dfd50-144">UnauthorizedAccessException thrown by FileSystemInfo.Attributes</span></span>](#unauthorizedaccessexception-thrown-by-filesysteminfoattributes) | <span data-ttu-id="dfd50-145">1.0</span><span class="sxs-lookup"><span data-stu-id="dfd50-145">1.0</span></span> |
| [<span data-ttu-id="dfd50-146">Обработка исключений с поврежденным состоянием процесса не поддерживается</span><span class="sxs-lookup"><span data-stu-id="dfd50-146">Handling corrupted-process-state exceptions is not supported</span></span>](#handling-corrupted-state-exceptions-is-not-supported) | <span data-ttu-id="dfd50-147">1.0</span><span class="sxs-lookup"><span data-stu-id="dfd50-147">1.0</span></span> |
| [<span data-ttu-id="dfd50-148">Для свойств UriBuilder больше не добавляются начальные символы</span><span class="sxs-lookup"><span data-stu-id="dfd50-148">UriBuilder properties no longer prepend leading characters</span></span>](#uribuilder-properties-no-longer-prepend-leading-characters) | <span data-ttu-id="dfd50-149">1.0</span><span class="sxs-lookup"><span data-stu-id="dfd50-149">1.0</span></span> |
| [<span data-ttu-id="dfd50-150">Process.StartInfo выдает исключение InvalidOperationException для процессов, которые не были запущены</span><span class="sxs-lookup"><span data-stu-id="dfd50-150">Process.StartInfo throws InvalidOperationException for processes you didn't start</span></span>](#processstartinfo-throws-invalidoperationexception-for-processes-you-didnt-start) | <span data-ttu-id="dfd50-151">1.0</span><span class="sxs-lookup"><span data-stu-id="dfd50-151">1.0</span></span> |

## <a name="net-50"></a><span data-ttu-id="dfd50-152">.NET 5.0</span><span class="sxs-lookup"><span data-stu-id="dfd50-152">.NET 5.0</span></span>

[!INCLUDE [sse-comparegreaterthan-intrinsics](../../../includes/core-changes/corefx/5.0/sse-comparegreaterthan-intrinsics.md)]

***

## <a name="net-core-30"></a><span data-ttu-id="dfd50-153">.NET Core 3.0</span><span class="sxs-lookup"><span data-stu-id="dfd50-153">.NET Core 3.0</span></span>

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

## <a name="net-core-21"></a><span data-ttu-id="dfd50-154">.NET Core 2.1</span><span class="sxs-lookup"><span data-stu-id="dfd50-154">.NET Core 2.1</span></span>

[!INCLUDE[Private fields added to built-in struct types](~/includes/core-changes/corefx/2.1/instantiate-struct.md)]

***

[!INCLUDE[Change in default value of UseShellExecute](~/includes/core-changes/corefx/2.1/process-start-changes.md)]

***

[!INCLUDE [OpenSSL versions on macOS](../../../includes/core-changes/corefx/openssl-dependencies-macos.md)]

***

## <a name="net-core-10"></a><span data-ttu-id="dfd50-155">.NET Core 1.0</span><span class="sxs-lookup"><span data-stu-id="dfd50-155">.NET Core 1.0</span></span>

[!INCLUDE [UnauthorizedAccessException thrown by FileSystemInfo.Attributes](~/includes/core-changes/corefx/1.0/filesysteminfo-attributes-exceptions.md)]

***

[!INCLUDE [corrupted-state-exceptions](~/includes/core-changes/corefx/1.0/corrupted-state-exceptions.md)]

***

[!INCLUDE [uribuilder-behavior-changes](../../../includes/core-changes/corefx/1.0/uribuilder-behavior-changes.md)]

***

[!INCLUDE [startinfo-throws-exception](../../../includes/core-changes/corefx/1.0/startinfo-throws-exception.md)]

***
