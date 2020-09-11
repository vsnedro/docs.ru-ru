---
title: Критические изменения в библиотеке базовых классов
description: В этой статье приведен список критических изменений в основных библиотеках .NET.
ms.date: 07/27/2020
ms.openlocfilehash: d8d886785ff71f22a3b2da65e973d899cf0371f6
ms.sourcegitcommit: e7acba36517134238065e4d50bb4a1cfe47ebd06
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/04/2020
ms.locfileid: "89465895"
---
# <a name="core-net-libraries-breaking-changes"></a><span data-ttu-id="c413a-103">Критические изменения в основных библиотеках .NET</span><span class="sxs-lookup"><span data-stu-id="c413a-103">Core .NET libraries breaking changes</span></span>

<span data-ttu-id="c413a-104">Основные библиотеки .NET предоставляет примитивы и другие общие типы, используемые в .NET Core.</span><span class="sxs-lookup"><span data-stu-id="c413a-104">The core .NET libraries provide the primitives and other general types used by .NET Core.</span></span>

<span data-ttu-id="c413a-105">На этой странице описаны следующие критические изменения:</span><span class="sxs-lookup"><span data-stu-id="c413a-105">The following breaking changes are documented on this page:</span></span>

| <span data-ttu-id="c413a-106">Критическое изменение</span><span class="sxs-lookup"><span data-stu-id="c413a-106">Breaking change</span></span> | <span data-ttu-id="c413a-107">Представленная версия</span><span class="sxs-lookup"><span data-stu-id="c413a-107">Version introduced</span></span> |
| - | :-: |
| [<span data-ttu-id="c413a-108">Устаревшие свойства ConsoleLoggerOptions</span><span class="sxs-lookup"><span data-stu-id="c413a-108">Obsolete properties on ConsoleLoggerOptions</span></span>](#obsolete-properties-on-consoleloggeroptions) | <span data-ttu-id="c413a-109">5.0</span><span class="sxs-lookup"><span data-stu-id="c413a-109">5.0</span></span> |
| [<span data-ttu-id="c413a-110">Встроенные проверки IsSupported, поддерживаемые оборудованием, могут отличаться для вложенных типов</span><span class="sxs-lookup"><span data-stu-id="c413a-110">Hardware intrinsic IsSupported checks may differ for nested types</span></span>](#hardware-intrinsic-issupported-checks-may-differ-for-nested-types) | <span data-ttu-id="c413a-111">5.0</span><span class="sxs-lookup"><span data-stu-id="c413a-111">5.0</span></span> |
| [<span data-ttu-id="c413a-112">В ссылочных сборках изменились имена параметров</span><span class="sxs-lookup"><span data-stu-id="c413a-112">Parameter names changed in reference assemblies</span></span>](#parameter-names-changed-in-reference-assemblies) | <span data-ttu-id="c413a-113">5.0</span><span class="sxs-lookup"><span data-stu-id="c413a-113">5.0</span></span> |
| [<span data-ttu-id="c413a-114">В UNIX правильно анализируются пути URI с символами, отличными от ASCII</span><span class="sxs-lookup"><span data-stu-id="c413a-114">URI paths with non-ASCII characters parse correctly on Unix</span></span>](#uri-paths-with-non-ascii-characters-parse-correctly-on-unix) | <span data-ttu-id="c413a-115">5.0</span><span class="sxs-lookup"><span data-stu-id="c413a-115">5.0</span></span> |
| [<span data-ttu-id="c413a-116">Распознавание URI UNC-путей в UNIX</span><span class="sxs-lookup"><span data-stu-id="c413a-116">Uri recognition of UNC paths on Unix</span></span>](#uri-recognition-of-unc-paths-on-unix) | <span data-ttu-id="c413a-117">5.0</span><span class="sxs-lookup"><span data-stu-id="c413a-117">5.0</span></span> |
| [<span data-ttu-id="c413a-118">Environment.OSVersion возвращает правильную версию операционной системы</span><span class="sxs-lookup"><span data-stu-id="c413a-118">Environment.OSVersion returns the correct operating system version</span></span>](#environmentosversion-returns-the-correct-operating-system-version) | <span data-ttu-id="c413a-119">5.0</span><span class="sxs-lookup"><span data-stu-id="c413a-119">5.0</span></span> |
| [<span data-ttu-id="c413a-120">Увеличена сложность LINQ OrderBy.First{OrDefault}</span><span class="sxs-lookup"><span data-stu-id="c413a-120">Complexity of LINQ OrderBy.First{OrDefault} increased</span></span>](#complexity-of-linq-orderbyfirstordefault-increased) | <span data-ttu-id="c413a-121">5.0</span><span class="sxs-lookup"><span data-stu-id="c413a-121">5.0</span></span> |
| [<span data-ttu-id="c413a-122">IntPtr и UIntPtr реализуют IFormattable</span><span class="sxs-lookup"><span data-stu-id="c413a-122">IntPtr and UIntPtr implement IFormattable</span></span>](#intptr-and-uintptr-implement-iformattable) | <span data-ttu-id="c413a-123">5.0</span><span class="sxs-lookup"><span data-stu-id="c413a-123">5.0</span></span> |
| [<span data-ttu-id="c413a-124">PrincipalPermissionAttribute устарел и является ошибочным</span><span class="sxs-lookup"><span data-stu-id="c413a-124">PrincipalPermissionAttribute is obsolete as error</span></span>](#principalpermissionattribute-is-obsolete-as-error) | <span data-ttu-id="c413a-125">5.0</span><span class="sxs-lookup"><span data-stu-id="c413a-125">5.0</span></span> |
| [<span data-ttu-id="c413a-126">Методы сериализации BinaryFormatter устарели и запрещены в приложениях ASP.NET</span><span class="sxs-lookup"><span data-stu-id="c413a-126">BinaryFormatter serialization methods are obsolete and prohibited in ASP.NET apps</span></span>](#binaryformatter-serialization-methods-are-obsolete-and-prohibited-in-aspnet-apps) | <span data-ttu-id="c413a-127">5.0</span><span class="sxs-lookup"><span data-stu-id="c413a-127">5.0</span></span> |
| [<span data-ttu-id="c413a-128">Пути к коду в кодировке UTF-7 устарели</span><span class="sxs-lookup"><span data-stu-id="c413a-128">UTF-7 code paths are obsolete</span></span>](#utf-7-code-paths-are-obsolete) | <span data-ttu-id="c413a-129">5.0</span><span class="sxs-lookup"><span data-stu-id="c413a-129">5.0</span></span> |
| [<span data-ttu-id="c413a-130">Vector\<T> всегда вызывает исключение NotSupportedException для неподдерживаемых типов</span><span class="sxs-lookup"><span data-stu-id="c413a-130">Vector\<T> always throws NotSupportedException for unsupported types</span></span>](#vectort-always-throws-notsupportedexception-for-unsupported-types) | <span data-ttu-id="c413a-131">5.0</span><span class="sxs-lookup"><span data-stu-id="c413a-131">5.0</span></span> |
| [<span data-ttu-id="c413a-132">По умолчанию ActivityIdFormat имеет значение W3C</span><span class="sxs-lookup"><span data-stu-id="c413a-132">Default ActivityIdFormat is W3C</span></span>](#default-activityidformat-is-w3c) | <span data-ttu-id="c413a-133">5.0</span><span class="sxs-lookup"><span data-stu-id="c413a-133">5.0</span></span> |
| [<span data-ttu-id="c413a-134">Изменение в поведении для Vector2.Lerp и Vector4.Lerp</span><span class="sxs-lookup"><span data-stu-id="c413a-134">Behavior change for Vector2.Lerp and Vector4.Lerp</span></span>](#behavior-change-for-vector2lerp-and-vector4lerp) | <span data-ttu-id="c413a-135">5.0</span><span class="sxs-lookup"><span data-stu-id="c413a-135">5.0</span></span> |
| [<span data-ttu-id="c413a-136">Методы SSE и SSE2 CompareGreaterThan корректно обрабатывают входные данные, которые не являются числом</span><span class="sxs-lookup"><span data-stu-id="c413a-136">SSE and SSE2 CompareGreaterThan methods properly handle NaN inputs</span></span>](#sse-and-sse2-comparegreaterthan-methods-properly-handle-nan-inputs) | <span data-ttu-id="c413a-137">5.0</span><span class="sxs-lookup"><span data-stu-id="c413a-137">5.0</span></span> |
| [<span data-ttu-id="c413a-138">Теперь CounterSet.CreateCounterSetInstance создает исключение InvalidOperationException, если экземпляр уже существует</span><span class="sxs-lookup"><span data-stu-id="c413a-138">CounterSet.CreateCounterSetInstance now throws InvalidOperationException if instance already exist</span></span>](#countersetcreatecountersetinstance-now-throws-invalidoperationexception-if-instance-already-exists) | <span data-ttu-id="c413a-139">5.0</span><span class="sxs-lookup"><span data-stu-id="c413a-139">5.0</span></span> |
| [<span data-ttu-id="c413a-140">Удален пакет Microsoft.DotNet.PlatformAbstractions</span><span class="sxs-lookup"><span data-stu-id="c413a-140">Microsoft.DotNet.PlatformAbstractions package removed</span></span>](#microsoftdotnetplatformabstractions-package-removed) | <span data-ttu-id="c413a-141">5.0</span><span class="sxs-lookup"><span data-stu-id="c413a-141">5.0</span></span> |
| [<span data-ttu-id="c413a-142">Интерфейсы API, сообщающие версию, теперь сообщают версию продукта, а не файла</span><span class="sxs-lookup"><span data-stu-id="c413a-142">APIs that report version now report product and not file version</span></span>](#apis-that-report-version-now-report-product-and-not-file-version) | <span data-ttu-id="c413a-143">3.0</span><span class="sxs-lookup"><span data-stu-id="c413a-143">3.0</span></span> |
| [<span data-ttu-id="c413a-144">Пользовательские экземпляры EncoderFallbackBuffer не поддерживают рекурсивный откат</span><span class="sxs-lookup"><span data-stu-id="c413a-144">Custom EncoderFallbackBuffer instances cannot fall back recursively</span></span>](#custom-encoderfallbackbuffer-instances-cannot-fall-back-recursively) | <span data-ttu-id="c413a-145">3.0</span><span class="sxs-lookup"><span data-stu-id="c413a-145">3.0</span></span> |
| [<span data-ttu-id="c413a-146">Изменено поведение форматирования и анализа при наличии плавающей запятой</span><span class="sxs-lookup"><span data-stu-id="c413a-146">Floating point formatting and parsing behavior changes</span></span>](#floating-point-formatting-and-parsing-behavior-changed) | <span data-ttu-id="c413a-147">3.0</span><span class="sxs-lookup"><span data-stu-id="c413a-147">3.0</span></span> |
| [<span data-ttu-id="c413a-148">Операции синтаксического анализа с плавающей запятой больше не завершаются ошибкой и не вызывают исключение OverflowException</span><span class="sxs-lookup"><span data-stu-id="c413a-148">Floating-point parsing operations no longer fail or throw an OverflowException</span></span>](#floating-point-parsing-operations-no-longer-fail-or-throw-an-overflowexception) | <span data-ttu-id="c413a-149">3.0</span><span class="sxs-lookup"><span data-stu-id="c413a-149">3.0</span></span> |
| [<span data-ttu-id="c413a-150">Исключение InvalidAsynchronousStateException перенесено в другую сборку</span><span class="sxs-lookup"><span data-stu-id="c413a-150">InvalidAsynchronousStateException moved to another assembly</span></span>](#invalidasynchronousstateexception-moved-to-another-assembly) | <span data-ttu-id="c413a-151">3.0</span><span class="sxs-lookup"><span data-stu-id="c413a-151">3.0</span></span> |
| [<span data-ttu-id="c413a-152">Замена неправильно сформированных последовательностей байтов в кодировке UTF-8 в соответствии с правилами Юникода</span><span class="sxs-lookup"><span data-stu-id="c413a-152">Replacing ill-formed UTF-8 byte sequences follows Unicode guidelines</span></span>](#replacing-ill-formed-utf-8-byte-sequences-follows-unicode-guidelines) | <span data-ttu-id="c413a-153">3.0</span><span class="sxs-lookup"><span data-stu-id="c413a-153">3.0</span></span> |
| [<span data-ttu-id="c413a-154">Класс TypeDescriptionProviderAttribute перенесен в другую сборку</span><span class="sxs-lookup"><span data-stu-id="c413a-154">TypeDescriptionProviderAttribute moved to another assembly</span></span>](#typedescriptionproviderattribute-moved-to-another-assembly) | <span data-ttu-id="c413a-155">3.0</span><span class="sxs-lookup"><span data-stu-id="c413a-155">3.0</span></span> |
| [<span data-ttu-id="c413a-156">ZipArchiveEntry больше не обрабатывает архивы с несогласованными размерами записей</span><span class="sxs-lookup"><span data-stu-id="c413a-156">ZipArchiveEntry no longer handles archives with inconsistent entry sizes</span></span>](#ziparchiveentry-no-longer-handles-archives-with-inconsistent-entry-sizes) | <span data-ttu-id="c413a-157">3.0</span><span class="sxs-lookup"><span data-stu-id="c413a-157">3.0</span></span> |
| [<span data-ttu-id="c413a-158">FieldInfo.SetValue вызывает исключение для статических полей и полей только для инициализации</span><span class="sxs-lookup"><span data-stu-id="c413a-158">FieldInfo.SetValue throws exception for static, init-only fields</span></span>](#fieldinfosetvalue-throws-exception-for-static-init-only-fields) | <span data-ttu-id="c413a-159">3.0</span><span class="sxs-lookup"><span data-stu-id="c413a-159">3.0</span></span> |
| [<span data-ttu-id="c413a-160">Во встроенные типы структур добавлены частные поля</span><span class="sxs-lookup"><span data-stu-id="c413a-160">Private fields added to built-in struct types</span></span>](#private-fields-added-to-built-in-struct-types) | <span data-ttu-id="c413a-161">2.1</span><span class="sxs-lookup"><span data-stu-id="c413a-161">2.1</span></span> |
| [<span data-ttu-id="c413a-162">Изменено значение по умолчанию для UseShellExecute</span><span class="sxs-lookup"><span data-stu-id="c413a-162">Change in default value of UseShellExecute</span></span>](#change-in-default-value-of-useshellexecute) | <span data-ttu-id="c413a-163">2.1</span><span class="sxs-lookup"><span data-stu-id="c413a-163">2.1</span></span> |
| [<span data-ttu-id="c413a-164">Версии OpenSSL в macOS</span><span class="sxs-lookup"><span data-stu-id="c413a-164">OpenSSL versions on macOS</span></span>](#openssl-versions-on-macos) | <span data-ttu-id="c413a-165">2.1</span><span class="sxs-lookup"><span data-stu-id="c413a-165">2.1</span></span> |
| [<span data-ttu-id="c413a-166">Исключение UnauthorizedAccessException, вызванное FileSystemInfo.Attributes</span><span class="sxs-lookup"><span data-stu-id="c413a-166">UnauthorizedAccessException thrown by FileSystemInfo.Attributes</span></span>](#unauthorizedaccessexception-thrown-by-filesysteminfoattributes) | <span data-ttu-id="c413a-167">1.0</span><span class="sxs-lookup"><span data-stu-id="c413a-167">1.0</span></span> |
| [<span data-ttu-id="c413a-168">Обработка исключений с поврежденным состоянием процесса не поддерживается</span><span class="sxs-lookup"><span data-stu-id="c413a-168">Handling corrupted-process-state exceptions is not supported</span></span>](#handling-corrupted-state-exceptions-is-not-supported) | <span data-ttu-id="c413a-169">1.0</span><span class="sxs-lookup"><span data-stu-id="c413a-169">1.0</span></span> |
| [<span data-ttu-id="c413a-170">Для свойств UriBuilder больше не добавляются начальные символы</span><span class="sxs-lookup"><span data-stu-id="c413a-170">UriBuilder properties no longer prepend leading characters</span></span>](#uribuilder-properties-no-longer-prepend-leading-characters) | <span data-ttu-id="c413a-171">1.0</span><span class="sxs-lookup"><span data-stu-id="c413a-171">1.0</span></span> |
| [<span data-ttu-id="c413a-172">Process.StartInfo выдает исключение InvalidOperationException для процессов, которые не были запущены</span><span class="sxs-lookup"><span data-stu-id="c413a-172">Process.StartInfo throws InvalidOperationException for processes you didn't start</span></span>](#processstartinfo-throws-invalidoperationexception-for-processes-you-didnt-start) | <span data-ttu-id="c413a-173">1.0</span><span class="sxs-lookup"><span data-stu-id="c413a-173">1.0</span></span> |

## <a name="net-50"></a><span data-ttu-id="c413a-174">.NET 5.0</span><span class="sxs-lookup"><span data-stu-id="c413a-174">.NET 5.0</span></span>

[!INCLUDE [obsolete-consoleloggeroptions-properties](../../../includes/core-changes/corefx/5.0/obsolete-consoleloggeroptions-properties.md)]

***

[!INCLUDE [hardware-instrinsics-issupported-checks](../../../includes/core-changes/corefx/5.0/hardware-instrinsics-issupported-checks.md)]

***

[!INCLUDE [reference-assembly-parameter-names](../../../includes/core-changes/corefx/5.0/reference-assembly-parameter-names.md)]

***

[!INCLUDE [non-ascii-chars-in-uri-parsed-correctly](../../../includes/core-changes/corefx/5.0/non-ascii-chars-in-uri-parsed-correctly.md)]

***

[!INCLUDE [unc-path-recognition-unix](../../../includes/core-changes/corefx/5.0/unc-path-recognition-unix.md)]

***

[!INCLUDE [environment-osversion-returns-correct-version](../../../includes/core-changes/corefx/5.0/environment-osversion-returns-correct-version.md)]

***

[!INCLUDE [orderby-firstordefault-complexity-increase](../../../includes/core-changes/corefx/5.0/orderby-firstordefault-complexity-increase.md)]

***

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

## <a name="net-core-30"></a><span data-ttu-id="c413a-175">.NET Core 3.0</span><span class="sxs-lookup"><span data-stu-id="c413a-175">.NET Core 3.0</span></span>

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

## <a name="net-core-21"></a><span data-ttu-id="c413a-176">.NET Core 2.1</span><span class="sxs-lookup"><span data-stu-id="c413a-176">.NET Core 2.1</span></span>

[!INCLUDE[Private fields added to built-in struct types](~/includes/core-changes/corefx/2.1/instantiate-struct.md)]

***

[!INCLUDE[Change in default value of UseShellExecute](~/includes/core-changes/corefx/2.1/process-start-changes.md)]

***

[!INCLUDE [OpenSSL versions on macOS](../../../includes/core-changes/corefx/openssl-dependencies-macos.md)]

***

## <a name="net-core-10"></a><span data-ttu-id="c413a-177">.NET Core 1.0</span><span class="sxs-lookup"><span data-stu-id="c413a-177">.NET Core 1.0</span></span>

[!INCLUDE [UnauthorizedAccessException thrown by FileSystemInfo.Attributes](~/includes/core-changes/corefx/1.0/filesysteminfo-attributes-exceptions.md)]

***

[!INCLUDE [corrupted-state-exceptions](~/includes/core-changes/corefx/1.0/corrupted-state-exceptions.md)]

***

[!INCLUDE [uribuilder-behavior-changes](../../../includes/core-changes/corefx/1.0/uribuilder-behavior-changes.md)]

***

[!INCLUDE [startinfo-throws-exception](../../../includes/core-changes/corefx/1.0/startinfo-throws-exception.md)]

***
