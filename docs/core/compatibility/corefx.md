---
title: Критические изменения в библиотеке базовых классов
description: В этой статье приведен список критических изменений в основных библиотеках .NET.
ms.date: 07/27/2020
ms.openlocfilehash: c8eb5ec7d2bb1879a38a18337463230c7b731d29
ms.sourcegitcommit: d3c09791297f0edc468a4849a5f11ef62e0e90fd
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/12/2020
ms.locfileid: "88137490"
---
# <a name="core-net-libraries-breaking-changes"></a><span data-ttu-id="3206c-103">Критические изменения в основных библиотеках .NET</span><span class="sxs-lookup"><span data-stu-id="3206c-103">Core .NET libraries breaking changes</span></span>

<span data-ttu-id="3206c-104">Основные библиотеки .NET предоставляет примитивы и другие общие типы, используемые в .NET Core.</span><span class="sxs-lookup"><span data-stu-id="3206c-104">The core .NET libraries provide the primitives and other general types used by .NET Core.</span></span>

<span data-ttu-id="3206c-105">На этой странице описаны следующие критические изменения:</span><span class="sxs-lookup"><span data-stu-id="3206c-105">The following breaking changes are documented on this page:</span></span>

| <span data-ttu-id="3206c-106">Критическое изменение</span><span class="sxs-lookup"><span data-stu-id="3206c-106">Breaking change</span></span> | <span data-ttu-id="3206c-107">Представленная версия</span><span class="sxs-lookup"><span data-stu-id="3206c-107">Version introduced</span></span> |
| - | :-: |
| [<span data-ttu-id="3206c-108">Увеличена сложность LINQ OrderBy.First{OrDefault}</span><span class="sxs-lookup"><span data-stu-id="3206c-108">Complexity of LINQ OrderBy.First{OrDefault} increased</span></span>](#complexity-of-linq-orderbyfirstordefault-increased) | <span data-ttu-id="3206c-109">5.0</span><span class="sxs-lookup"><span data-stu-id="3206c-109">5.0</span></span> |
| [<span data-ttu-id="3206c-110">IntPtr и UIntPtr реализуют IFormattable</span><span class="sxs-lookup"><span data-stu-id="3206c-110">IntPtr and UIntPtr implement IFormattable</span></span>](#intptr-and-uintptr-implement-iformattable) | <span data-ttu-id="3206c-111">5.0</span><span class="sxs-lookup"><span data-stu-id="3206c-111">5.0</span></span> |
| [<span data-ttu-id="3206c-112">PrincipalPermissionAttribute устарел и является ошибочным</span><span class="sxs-lookup"><span data-stu-id="3206c-112">PrincipalPermissionAttribute is obsolete as error</span></span>](#principalpermissionattribute-is-obsolete-as-error) | <span data-ttu-id="3206c-113">5.0</span><span class="sxs-lookup"><span data-stu-id="3206c-113">5.0</span></span> |
| [<span data-ttu-id="3206c-114">Методы сериализации BinaryFormatter устарели и запрещены в приложениях ASP.NET</span><span class="sxs-lookup"><span data-stu-id="3206c-114">BinaryFormatter serialization methods are obsolete and prohibited in ASP.NET apps</span></span>](#binaryformatter-serialization-methods-are-obsolete-and-prohibited-in-aspnet-apps) | <span data-ttu-id="3206c-115">5.0</span><span class="sxs-lookup"><span data-stu-id="3206c-115">5.0</span></span> |
| [<span data-ttu-id="3206c-116">Пути к коду в кодировке UTF-7 устарели</span><span class="sxs-lookup"><span data-stu-id="3206c-116">UTF-7 code paths are obsolete</span></span>](#utf-7-code-paths-are-obsolete) | <span data-ttu-id="3206c-117">5.0</span><span class="sxs-lookup"><span data-stu-id="3206c-117">5.0</span></span> |
| [<span data-ttu-id="3206c-118">Vector\<T> всегда вызывает исключение NotSupportedException для неподдерживаемых типов</span><span class="sxs-lookup"><span data-stu-id="3206c-118">Vector\<T> always throws NotSupportedException for unsupported types</span></span>](#vectort-always-throws-notsupportedexception-for-unsupported-types) | <span data-ttu-id="3206c-119">5.0</span><span class="sxs-lookup"><span data-stu-id="3206c-119">5.0</span></span> |
| [<span data-ttu-id="3206c-120">По умолчанию ActivityIdFormat имеет значение W3C</span><span class="sxs-lookup"><span data-stu-id="3206c-120">Default ActivityIdFormat is W3C</span></span>](#default-activityidformat-is-w3c) | <span data-ttu-id="3206c-121">5.0</span><span class="sxs-lookup"><span data-stu-id="3206c-121">5.0</span></span> |
| [<span data-ttu-id="3206c-122">Изменение в поведении для Vector2.Lerp и Vector4.Lerp</span><span class="sxs-lookup"><span data-stu-id="3206c-122">Behavior change for Vector2.Lerp and Vector4.Lerp</span></span>](#behavior-change-for-vector2lerp-and-vector4lerp) | <span data-ttu-id="3206c-123">5.0</span><span class="sxs-lookup"><span data-stu-id="3206c-123">5.0</span></span> |
| [<span data-ttu-id="3206c-124">Методы SSE и SSE2 CompareGreaterThan корректно обрабатывают входные данные, которые не являются числом</span><span class="sxs-lookup"><span data-stu-id="3206c-124">SSE and SSE2 CompareGreaterThan methods properly handle NaN inputs</span></span>](#sse-and-sse2-comparegreaterthan-methods-properly-handle-nan-inputs) | <span data-ttu-id="3206c-125">5.0</span><span class="sxs-lookup"><span data-stu-id="3206c-125">5.0</span></span> |
| [<span data-ttu-id="3206c-126">Теперь CounterSet.CreateCounterSetInstance создает исключение InvalidOperationException, если экземпляр уже существует</span><span class="sxs-lookup"><span data-stu-id="3206c-126">CounterSet.CreateCounterSetInstance now throws InvalidOperationException if instance already exist</span></span>](#countersetcreatecountersetinstance-now-throws-invalidoperationexception-if-instance-already-exists) | <span data-ttu-id="3206c-127">5.0</span><span class="sxs-lookup"><span data-stu-id="3206c-127">5.0</span></span> |
| [<span data-ttu-id="3206c-128">Удален пакет Microsoft.DotNet.PlatformAbstractions</span><span class="sxs-lookup"><span data-stu-id="3206c-128">Microsoft.DotNet.PlatformAbstractions package removed</span></span>](#microsoftdotnetplatformabstractions-package-removed) | <span data-ttu-id="3206c-129">5.0</span><span class="sxs-lookup"><span data-stu-id="3206c-129">5.0</span></span> |
| [<span data-ttu-id="3206c-130">Интерфейсы API, сообщающие версию, теперь сообщают версию продукта, а не файла</span><span class="sxs-lookup"><span data-stu-id="3206c-130">APIs that report version now report product and not file version</span></span>](#apis-that-report-version-now-report-product-and-not-file-version) | <span data-ttu-id="3206c-131">3.0</span><span class="sxs-lookup"><span data-stu-id="3206c-131">3.0</span></span> |
| [<span data-ttu-id="3206c-132">Пользовательские экземпляры EncoderFallbackBuffer не поддерживают рекурсивный откат</span><span class="sxs-lookup"><span data-stu-id="3206c-132">Custom EncoderFallbackBuffer instances cannot fall back recursively</span></span>](#custom-encoderfallbackbuffer-instances-cannot-fall-back-recursively) | <span data-ttu-id="3206c-133">3.0</span><span class="sxs-lookup"><span data-stu-id="3206c-133">3.0</span></span> |
| [<span data-ttu-id="3206c-134">Изменено поведение форматирования и анализа при наличии плавающей запятой</span><span class="sxs-lookup"><span data-stu-id="3206c-134">Floating point formatting and parsing behavior changes</span></span>](#floating-point-formatting-and-parsing-behavior-changed) | <span data-ttu-id="3206c-135">3.0</span><span class="sxs-lookup"><span data-stu-id="3206c-135">3.0</span></span> |
| [<span data-ttu-id="3206c-136">Операции синтаксического анализа с плавающей запятой больше не завершаются ошибкой и не вызывают исключение OverflowException</span><span class="sxs-lookup"><span data-stu-id="3206c-136">Floating-point parsing operations no longer fail or throw an OverflowException</span></span>](#floating-point-parsing-operations-no-longer-fail-or-throw-an-overflowexception) | <span data-ttu-id="3206c-137">3.0</span><span class="sxs-lookup"><span data-stu-id="3206c-137">3.0</span></span> |
| [<span data-ttu-id="3206c-138">Исключение InvalidAsynchronousStateException перенесено в другую сборку</span><span class="sxs-lookup"><span data-stu-id="3206c-138">InvalidAsynchronousStateException moved to another assembly</span></span>](#invalidasynchronousstateexception-moved-to-another-assembly) | <span data-ttu-id="3206c-139">3.0</span><span class="sxs-lookup"><span data-stu-id="3206c-139">3.0</span></span> |
| [<span data-ttu-id="3206c-140">Замена неправильно сформированных последовательностей байтов в кодировке UTF-8 в соответствии с правилами Юникода</span><span class="sxs-lookup"><span data-stu-id="3206c-140">Replacing ill-formed UTF-8 byte sequences follows Unicode guidelines</span></span>](#replacing-ill-formed-utf-8-byte-sequences-follows-unicode-guidelines) | <span data-ttu-id="3206c-141">3.0</span><span class="sxs-lookup"><span data-stu-id="3206c-141">3.0</span></span> |
| [<span data-ttu-id="3206c-142">Класс TypeDescriptionProviderAttribute перенесен в другую сборку</span><span class="sxs-lookup"><span data-stu-id="3206c-142">TypeDescriptionProviderAttribute moved to another assembly</span></span>](#typedescriptionproviderattribute-moved-to-another-assembly) | <span data-ttu-id="3206c-143">3.0</span><span class="sxs-lookup"><span data-stu-id="3206c-143">3.0</span></span> |
| [<span data-ttu-id="3206c-144">ZipArchiveEntry больше не обрабатывает архивы с несогласованными размерами записей</span><span class="sxs-lookup"><span data-stu-id="3206c-144">ZipArchiveEntry no longer handles archives with inconsistent entry sizes</span></span>](#ziparchiveentry-no-longer-handles-archives-with-inconsistent-entry-sizes) | <span data-ttu-id="3206c-145">3.0</span><span class="sxs-lookup"><span data-stu-id="3206c-145">3.0</span></span> |
| [<span data-ttu-id="3206c-146">FieldInfo.SetValue вызывает исключение для статических полей и полей только для инициализации</span><span class="sxs-lookup"><span data-stu-id="3206c-146">FieldInfo.SetValue throws exception for static, init-only fields</span></span>](#fieldinfosetvalue-throws-exception-for-static-init-only-fields) | <span data-ttu-id="3206c-147">3.0</span><span class="sxs-lookup"><span data-stu-id="3206c-147">3.0</span></span> |
| [<span data-ttu-id="3206c-148">Во встроенные типы структур добавлены частные поля</span><span class="sxs-lookup"><span data-stu-id="3206c-148">Private fields added to built-in struct types</span></span>](#private-fields-added-to-built-in-struct-types) | <span data-ttu-id="3206c-149">2.1</span><span class="sxs-lookup"><span data-stu-id="3206c-149">2.1</span></span> |
| [<span data-ttu-id="3206c-150">Изменено значение по умолчанию для UseShellExecute</span><span class="sxs-lookup"><span data-stu-id="3206c-150">Change in default value of UseShellExecute</span></span>](#change-in-default-value-of-useshellexecute) | <span data-ttu-id="3206c-151">2.1</span><span class="sxs-lookup"><span data-stu-id="3206c-151">2.1</span></span> |
| [<span data-ttu-id="3206c-152">Версии OpenSSL в macOS</span><span class="sxs-lookup"><span data-stu-id="3206c-152">OpenSSL versions on macOS</span></span>](#openssl-versions-on-macos) | <span data-ttu-id="3206c-153">2.1</span><span class="sxs-lookup"><span data-stu-id="3206c-153">2.1</span></span> |
| [<span data-ttu-id="3206c-154">Исключение UnauthorizedAccessException, вызванное FileSystemInfo.Attributes</span><span class="sxs-lookup"><span data-stu-id="3206c-154">UnauthorizedAccessException thrown by FileSystemInfo.Attributes</span></span>](#unauthorizedaccessexception-thrown-by-filesysteminfoattributes) | <span data-ttu-id="3206c-155">1.0</span><span class="sxs-lookup"><span data-stu-id="3206c-155">1.0</span></span> |
| [<span data-ttu-id="3206c-156">Обработка исключений с поврежденным состоянием процесса не поддерживается</span><span class="sxs-lookup"><span data-stu-id="3206c-156">Handling corrupted-process-state exceptions is not supported</span></span>](#handling-corrupted-state-exceptions-is-not-supported) | <span data-ttu-id="3206c-157">1.0</span><span class="sxs-lookup"><span data-stu-id="3206c-157">1.0</span></span> |
| [<span data-ttu-id="3206c-158">Для свойств UriBuilder больше не добавляются начальные символы</span><span class="sxs-lookup"><span data-stu-id="3206c-158">UriBuilder properties no longer prepend leading characters</span></span>](#uribuilder-properties-no-longer-prepend-leading-characters) | <span data-ttu-id="3206c-159">1.0</span><span class="sxs-lookup"><span data-stu-id="3206c-159">1.0</span></span> |
| [<span data-ttu-id="3206c-160">Process.StartInfo выдает исключение InvalidOperationException для процессов, которые не были запущены</span><span class="sxs-lookup"><span data-stu-id="3206c-160">Process.StartInfo throws InvalidOperationException for processes you didn't start</span></span>](#processstartinfo-throws-invalidoperationexception-for-processes-you-didnt-start) | <span data-ttu-id="3206c-161">1.0</span><span class="sxs-lookup"><span data-stu-id="3206c-161">1.0</span></span> |

## <a name="net-50"></a><span data-ttu-id="3206c-162">.NET 5.0</span><span class="sxs-lookup"><span data-stu-id="3206c-162">.NET 5.0</span></span>

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

## <a name="net-core-30"></a><span data-ttu-id="3206c-163">.NET Core 3.0</span><span class="sxs-lookup"><span data-stu-id="3206c-163">.NET Core 3.0</span></span>

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

## <a name="net-core-21"></a><span data-ttu-id="3206c-164">.NET Core 2.1</span><span class="sxs-lookup"><span data-stu-id="3206c-164">.NET Core 2.1</span></span>

[!INCLUDE[Private fields added to built-in struct types](~/includes/core-changes/corefx/2.1/instantiate-struct.md)]

***

[!INCLUDE[Change in default value of UseShellExecute](~/includes/core-changes/corefx/2.1/process-start-changes.md)]

***

[!INCLUDE [OpenSSL versions on macOS](../../../includes/core-changes/corefx/openssl-dependencies-macos.md)]

***

## <a name="net-core-10"></a><span data-ttu-id="3206c-165">.NET Core 1.0</span><span class="sxs-lookup"><span data-stu-id="3206c-165">.NET Core 1.0</span></span>

[!INCLUDE [UnauthorizedAccessException thrown by FileSystemInfo.Attributes](~/includes/core-changes/corefx/1.0/filesysteminfo-attributes-exceptions.md)]

***

[!INCLUDE [corrupted-state-exceptions](~/includes/core-changes/corefx/1.0/corrupted-state-exceptions.md)]

***

[!INCLUDE [uribuilder-behavior-changes](../../../includes/core-changes/corefx/1.0/uribuilder-behavior-changes.md)]

***

[!INCLUDE [startinfo-throws-exception](../../../includes/core-changes/corefx/1.0/startinfo-throws-exception.md)]

***
