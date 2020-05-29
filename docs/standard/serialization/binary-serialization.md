---
title: Двоичная сериализация
description: В этой статье описываются двоичная сериализация и типы, для которых она поддерживается в .NET Core. Обратите внимание на опасности двоичной сериализации и узнайте об альтернативах.
ms.date: 01/02/2018
helpviewer_keywords:
- binary serialization
- serialization, about serialization
- deserialization
- binary serialization, about serialization
- binary serialization, .net core serialization
- serialization, cross-framework
ms.assetid: 2b1ea3be-1152-4032-b2b3-07794054c405
author: ViktorHofer
ms.openlocfilehash: 4ed76437b743da842d6ba07d29fe7985f824abf0
ms.sourcegitcommit: 9a4488a3625866335e83a20da5e9c5286b1f034c
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/15/2020
ms.locfileid: "83421284"
---
# <a name="binary-serialization"></a><span data-ttu-id="a887f-104">Двоичная сериализация</span><span class="sxs-lookup"><span data-stu-id="a887f-104">Binary serialization</span></span>

<span data-ttu-id="a887f-105">Сериализацию можно представить как процесс сохранения состояния объекта в среду хранения.</span><span class="sxs-lookup"><span data-stu-id="a887f-105">Serialization can be defined as the process of storing the state of an object to a storage medium.</span></span> <span data-ttu-id="a887f-106">Во время этого процесса открытые и закрытые поля объекта и имя класса, включая сборку с классом, преобразуются в поток байтов, который затем записывается в поток данных.</span><span class="sxs-lookup"><span data-stu-id="a887f-106">During this process, the public and private fields of the object and the name of the class, including the assembly containing the class, are converted to a stream of bytes, which is then written to a data stream.</span></span> <span data-ttu-id="a887f-107">После десериализации объекта создается точная копия исходного объекта.</span><span class="sxs-lookup"><span data-stu-id="a887f-107">When the object is subsequently deserialized, an exact clone of the original object is created.</span></span>

<span data-ttu-id="a887f-108">При реализации механизма сериализации в объектно-ориентированной среде следует сделать выбор между простотой и гибкостью использования.</span><span class="sxs-lookup"><span data-stu-id="a887f-108">When implementing a serialization mechanism in an object-oriented environment, you have to make a number of tradeoffs between ease of use and flexibility.</span></span> <span data-ttu-id="a887f-109">Процесс можно в значительной степени автоматизировать при условии сохранения над ним достаточного контроля.</span><span class="sxs-lookup"><span data-stu-id="a887f-109">The process can be automated to a large extent, provided you are given sufficient control over the process.</span></span> <span data-ttu-id="a887f-110">Например, могут возникать ситуации, при которых недостаточно простой двоичной сериализации или по какой-либо причине необходимо определить сериализуемые поля в классе.</span><span class="sxs-lookup"><span data-stu-id="a887f-110">For example, situations may arise where simple binary serialization is not sufficient, or there might be a specific reason to decide which fields in a class need to be serialized.</span></span> <span data-ttu-id="a887f-111">В следующих разделах исследуется надежный механизм сериализации с использованием платформы .NET и отмечается ряд важных особенностей, которые позволяют настраивать процесс в соответствии с собственными потребностями.</span><span class="sxs-lookup"><span data-stu-id="a887f-111">The following sections examine the robust serialization mechanism provided with .NET and highlight a number of important features that allow you to customize the process to meet your needs.</span></span>

> [!NOTE]
> <span data-ttu-id="a887f-112">Состояние объекта, закодированного в UTF-8 или UTF-7, не сохраняется, если этот объект сериализуется и десериализуется с использованием различных версий .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="a887f-112">The state of a UTF-8 or UTF-7 encoded object is not preserved if the object is serialized and deserialized using different .NET Framework versions.</span></span>

[!INCLUDE [binary-serialization-warning](../../../includes/binary-serialization-warning.md)]

<span data-ttu-id="a887f-113">Двоичная сериализация позволяет изменять закрытые члены внутри объекта и, следовательно, изменять их состояние.</span><span class="sxs-lookup"><span data-stu-id="a887f-113">Binary serialization allows modifying private members inside an object and therefore changing the state of it.</span></span> <span data-ttu-id="a887f-114">По этой причине рекомендуется использовать другие платформы сериализации, например <xref:System.Text.Json?displayProperty=fullName>, которые работают на основе общедоступных API.</span><span class="sxs-lookup"><span data-stu-id="a887f-114">Because of this, other serialization frameworks, like <xref:System.Text.Json?displayProperty=fullName>, that operate on the public API surface are recommended.</span></span>

## <a name="net-core"></a><span data-ttu-id="a887f-115">.NET Core</span><span class="sxs-lookup"><span data-stu-id="a887f-115">.NET Core</span></span>

<span data-ttu-id="a887f-116">.NET Core поддерживает двоичную сериализацию для подмножества типов.</span><span class="sxs-lookup"><span data-stu-id="a887f-116">.NET Core supports binary serialization for a subset of types.</span></span> <span data-ttu-id="a887f-117">Список поддерживаемых типов приведен в разделе [Сериализуемые типы](#serializable-types) ниже.</span><span class="sxs-lookup"><span data-stu-id="a887f-117">You can see the list of supported types in the [Serializable types](#serializable-types) section that follows.</span></span> <span data-ttu-id="a887f-118">Для указанных типов гарантируется возможность сериализации между .NET Framework версии 4.5.1 или более поздними версиями и между .NET Core 2.0 и более поздними версиями.</span><span class="sxs-lookup"><span data-stu-id="a887f-118">The listed types are guaranteed to be serializable between .NET Framework 4.5.1 and later versions and between .NET Core 2.0 and later versions.</span></span> <span data-ttu-id="a887f-119">Другие реализации .NET (например, Mono) официально не поддерживаются, но также должны работать.</span><span class="sxs-lookup"><span data-stu-id="a887f-119">Other .NET implementations, such as Mono, aren't officially supported but should also work.</span></span>

### <a name="serializable-types"></a><span data-ttu-id="a887f-120">Сериализуемые типы</span><span class="sxs-lookup"><span data-stu-id="a887f-120">Serializable types</span></span>

> [!div class="mx-tdCol2BreakAll"]
> | <span data-ttu-id="a887f-121">Type</span><span class="sxs-lookup"><span data-stu-id="a887f-121">Type</span></span> | <span data-ttu-id="a887f-122">Примечания</span><span class="sxs-lookup"><span data-stu-id="a887f-122">Notes</span></span> |
> | - | - |
> | <xref:Microsoft.CSharp.RuntimeBinder.RuntimeBinderException?displayProperty=nameWithType> | <span data-ttu-id="a887f-123">Начиная с .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="a887f-123">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:Microsoft.CSharp.RuntimeBinder.RuntimeBinderInternalCompilerException?displayProperty=nameWithType> | <span data-ttu-id="a887f-124">Начиная с .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="a887f-124">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.AccessViolationException?displayProperty=nameWithType> | <span data-ttu-id="a887f-125">Начиная с .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="a887f-125">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.AggregateException?displayProperty=nameWithType> | <span data-ttu-id="a887f-126">Начиная с .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="a887f-126">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.AppDomainUnloadedException?displayProperty=nameWithType> | <span data-ttu-id="a887f-127">Начиная с .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="a887f-127">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.ApplicationException?displayProperty=nameWithType> | <span data-ttu-id="a887f-128">Начиная с .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="a887f-128">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.ArgumentException?displayProperty=nameWithType> | <span data-ttu-id="a887f-129">Начиная с .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="a887f-129">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.ArgumentNullException?displayProperty=nameWithType> | <span data-ttu-id="a887f-130">Начиная с .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="a887f-130">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.ArgumentOutOfRangeException?displayProperty=nameWithType> | <span data-ttu-id="a887f-131">Начиная с .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="a887f-131">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.ArithmeticException?displayProperty=nameWithType> | <span data-ttu-id="a887f-132">Начиная с .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="a887f-132">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Array?displayProperty=nameWithType> | |
> | <xref:System.ArraySegment%601?displayProperty=nameWithType> | |
> | <xref:System.ArrayTypeMismatchException?displayProperty=nameWithType> | <span data-ttu-id="a887f-133">Начиная с .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="a887f-133">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Attribute?displayProperty=nameWithType> | |
> | <xref:System.BadImageFormatException?displayProperty=nameWithType> | <span data-ttu-id="a887f-134">Начиная с .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="a887f-134">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Boolean?displayProperty=nameWithType> | |
> | <xref:System.Byte?displayProperty=nameWithType> | |
> | <xref:System.CannotUnloadAppDomainException?displayProperty=nameWithType> | <span data-ttu-id="a887f-135">Начиная с .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="a887f-135">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Char?displayProperty=nameWithType> | |
> | <xref:System.Collections.ArrayList?displayProperty=nameWithType> | |
> | <xref:System.Collections.BitArray?displayProperty=nameWithType> | |
> | <xref:System.Collections.Comparer?displayProperty=nameWithType> | |
> | <xref:System.Collections.DictionaryEntry?displayProperty=nameWithType> | |
> | <xref:System.Collections.Generic.Comparer%601?displayProperty=nameWithType> | |
> | <xref:System.Collections.Generic.Dictionary%602?displayProperty=nameWithType> | |
> | <xref:System.Collections.Generic.EqualityComparer%601?displayProperty=nameWithType> | |
> | <xref:System.Collections.Generic.HashSet%601?displayProperty=nameWithType> | |
> | <xref:System.Collections.Generic.KeyNotFoundException?displayProperty=nameWithType> | <span data-ttu-id="a887f-136">Начиная с .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="a887f-136">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Collections.Generic.KeyValuePair%602?displayProperty=nameWithType> | |
> | <xref:System.Collections.Generic.LinkedList%601?displayProperty=nameWithType> | |
> | <xref:System.Collections.Generic.List%601?displayProperty=nameWithType> | |
> | <xref:System.Collections.Generic.Queue%601?displayProperty=nameWithType> | |
> | <xref:System.Collections.Generic.SortedDictionary%602?displayProperty=nameWithType> | |
> | <xref:System.Collections.Generic.SortedList%602?displayProperty=nameWithType> | |
> | <xref:System.Collections.Generic.SortedSet%601?displayProperty=nameWithType> | |
> | <xref:System.Collections.Generic.Stack%601?displayProperty=nameWithType> | |
> | <xref:System.Collections.Hashtable?displayProperty=nameWithType> | |
> | <xref:System.Collections.ObjectModel.Collection%601?displayProperty=nameWithType> | |
> | <xref:System.Collections.ObjectModel.KeyedCollection%602?displayProperty=nameWithType> | |
> | <xref:System.Collections.ObjectModel.ObservableCollection%601?displayProperty=nameWithType> | |
> | <xref:System.Collections.ObjectModel.ReadOnlyCollection%601?displayProperty=nameWithType> | |
> | <xref:System.Collections.ObjectModel.ReadOnlyDictionary%602?displayProperty=nameWithType> | |
> | <xref:System.Collections.ObjectModel.ReadOnlyObservableCollection%601?displayProperty=nameWithType> | |
> | <xref:System.Collections.Queue?displayProperty=nameWithType> | |
> | <xref:System.Collections.SortedList?displayProperty=nameWithType> | |
> | <xref:System.Collections.Specialized.HybridDictionary?displayProperty=nameWithType> | |
> | <xref:System.Collections.Specialized.ListDictionary?displayProperty=nameWithType> | |
> | <xref:System.Collections.Specialized.OrderedDictionary?displayProperty=nameWithType> | |
> | <xref:System.Collections.Specialized.StringCollection?displayProperty=nameWithType> | |
> | <xref:System.Collections.Specialized.StringDictionary?displayProperty=nameWithType> | |
> | <xref:System.Collections.Stack?displayProperty=nameWithType> | |
> | `System.Collections.Generic.NonRandomizedStringEqualityComparer` | <span data-ttu-id="a887f-137">Начиная с .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="a887f-137">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.ComponentModel.BindingList%601?displayProperty=nameWithType> | |
> | <xref:System.ComponentModel.DataAnnotations.ValidationException?displayProperty=nameWithType> | <span data-ttu-id="a887f-138">Начиная с .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="a887f-138">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.ComponentModel.Design.CheckoutException?displayProperty=nameWithType> | <span data-ttu-id="a887f-139">Начиная с .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="a887f-139">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.ComponentModel.InvalidAsynchronousStateException?displayProperty=nameWithType> | <span data-ttu-id="a887f-140">Начиная с .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="a887f-140">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.ComponentModel.InvalidEnumArgumentException?displayProperty=nameWithType> | <span data-ttu-id="a887f-141">Начиная с .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="a887f-141">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.ComponentModel.LicenseException?displayProperty=nameWithType> | <span data-ttu-id="a887f-142">Начиная с .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="a887f-142">Starting in .NET Core 2.0.4.</span></span><br/><span data-ttu-id="a887f-143">Сериализация из .NET Framework в .NET Core не поддерживается.</span><span class="sxs-lookup"><span data-stu-id="a887f-143">Serialization from .NET Framework to .NET Core is not supported.</span></span> |
> | <xref:System.ComponentModel.WarningException?displayProperty=nameWithType> | <span data-ttu-id="a887f-144">Начиная с .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="a887f-144">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.ComponentModel.Win32Exception?displayProperty=nameWithType> | <span data-ttu-id="a887f-145">Начиная с .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="a887f-145">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Configuration.ConfigurationErrorsException?displayProperty=nameWithType> | <span data-ttu-id="a887f-146">Начиная с .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="a887f-146">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Configuration.ConfigurationException?displayProperty=nameWithType> | <span data-ttu-id="a887f-147">Начиная с .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="a887f-147">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Configuration.Provider.ProviderException?displayProperty=nameWithType> | <span data-ttu-id="a887f-148">Начиная с .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="a887f-148">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Configuration.SettingsPropertyIsReadOnlyException?displayProperty=nameWithType> | <span data-ttu-id="a887f-149">Начиная с .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="a887f-149">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Configuration.SettingsPropertyNotFoundException?displayProperty=nameWithType> | <span data-ttu-id="a887f-150">Начиная с .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="a887f-150">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Configuration.SettingsPropertyWrongTypeException?displayProperty=nameWithType> | <span data-ttu-id="a887f-151">Начиная с .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="a887f-151">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.ContextMarshalException?displayProperty=nameWithType> | <span data-ttu-id="a887f-152">Начиная с .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="a887f-152">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.DBNull?displayProperty=nameWithType> | <span data-ttu-id="a887f-153">Начиная с .NET Core 2.0.2 и более поздних версий.</span><span class="sxs-lookup"><span data-stu-id="a887f-153">Starting in .NET Core 2.0.2 and later versions.</span></span> |
> | <xref:System.Data.Common.DbException?displayProperty=nameWithType> | <span data-ttu-id="a887f-154">Начиная с .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="a887f-154">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Data.ConstraintException?displayProperty=nameWithType> | <span data-ttu-id="a887f-155">Начиная с .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="a887f-155">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Data.DBConcurrencyException?displayProperty=nameWithType> | <span data-ttu-id="a887f-156">Начиная с .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="a887f-156">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Data.DataException?displayProperty=nameWithType> | <span data-ttu-id="a887f-157">Начиная с .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="a887f-157">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Data.DataSet?displayProperty=nameWithType> | |
> | <xref:System.Data.DataTable?displayProperty=nameWithType> | <span data-ttu-id="a887f-158">Если для `RemotingFormat` задано значение `SerializationFormat.Binary`, его можно использовать только в .NET Core 2.1 и более поздних версиях.</span><span class="sxs-lookup"><span data-stu-id="a887f-158">If you set `RemotingFormat` to `SerializationFormat.Binary`, it can only be exchanged with .NET Core 2.1 and later versions.</span></span> |
> | <xref:System.Data.DeletedRowInaccessibleException?displayProperty=nameWithType> | <span data-ttu-id="a887f-159">Начиная с .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="a887f-159">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Data.DuplicateNameException?displayProperty=nameWithType> | <span data-ttu-id="a887f-160">Начиная с .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="a887f-160">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Data.EvaluateException?displayProperty=nameWithType> | <span data-ttu-id="a887f-161">Начиная с .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="a887f-161">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Data.InRowChangingEventException?displayProperty=nameWithType> | <span data-ttu-id="a887f-162">Начиная с .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="a887f-162">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Data.InvalidConstraintException?displayProperty=nameWithType> | <span data-ttu-id="a887f-163">Начиная с .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="a887f-163">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Data.InvalidExpressionException?displayProperty=nameWithType> | <span data-ttu-id="a887f-164">Начиная с .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="a887f-164">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Data.MissingPrimaryKeyException?displayProperty=nameWithType> | <span data-ttu-id="a887f-165">Начиная с .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="a887f-165">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Data.NoNullAllowedException?displayProperty=nameWithType> | <span data-ttu-id="a887f-166">Начиная с .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="a887f-166">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Data.Odbc.OdbcException?displayProperty=nameWithType> | <span data-ttu-id="a887f-167">Начиная с .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="a887f-167">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Data.OperationAbortedException?displayProperty=nameWithType> | <span data-ttu-id="a887f-168">Начиная с .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="a887f-168">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Data.PropertyCollection?displayProperty=nameWithType> | |
> | <xref:System.Data.ReadOnlyException?displayProperty=nameWithType> | <span data-ttu-id="a887f-169">Начиная с .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="a887f-169">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Data.RowNotInTableException?displayProperty=nameWithType> | <span data-ttu-id="a887f-170">Начиная с .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="a887f-170">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Data.SqlClient.SqlException?displayProperty=nameWithType> | <span data-ttu-id="a887f-171">Начиная с .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="a887f-171">Starting in .NET Core 2.0.4.</span></span><br/><span data-ttu-id="a887f-172">Сериализация из .NET Framework в .NET Core не поддерживается</span><span class="sxs-lookup"><span data-stu-id="a887f-172">Serialization from .NET Framework to .NET Core is not supported</span></span> |
> | <xref:System.Data.SqlTypes.SqlAlreadyFilledException?displayProperty=nameWithType> | <span data-ttu-id="a887f-173">Начиная с .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="a887f-173">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Data.SqlTypes.SqlBoolean?displayProperty=nameWithType> | |
> | <xref:System.Data.SqlTypes.SqlByte?displayProperty=nameWithType> | |
> | <xref:System.Data.SqlTypes.SqlDateTime?displayProperty=nameWithType> | |
> | <xref:System.Data.SqlTypes.SqlDouble?displayProperty=nameWithType> | |
> | <xref:System.Data.SqlTypes.SqlGuid?displayProperty=nameWithType> | |
> | <xref:System.Data.SqlTypes.SqlInt16?displayProperty=nameWithType> | |
> | <xref:System.Data.SqlTypes.SqlInt32?displayProperty=nameWithType> | |
> | <xref:System.Data.SqlTypes.SqlInt64?displayProperty=nameWithType> | |
> | <xref:System.Data.SqlTypes.SqlNotFilledException?displayProperty=nameWithType> | <span data-ttu-id="a887f-174">Начиная с .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="a887f-174">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Data.SqlTypes.SqlNullValueException?displayProperty=nameWithType> | <span data-ttu-id="a887f-175">Начиная с .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="a887f-175">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Data.SqlTypes.SqlString?displayProperty=nameWithType> | |
> | <xref:System.Data.SqlTypes.SqlTruncateException?displayProperty=nameWithType> | <span data-ttu-id="a887f-176">Начиная с .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="a887f-176">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Data.SqlTypes.SqlTypeException?displayProperty=nameWithType> | <span data-ttu-id="a887f-177">Начиная с .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="a887f-177">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Data.StrongTypingException?displayProperty=nameWithType> | <span data-ttu-id="a887f-178">Начиная с .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="a887f-178">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Data.SyntaxErrorException?displayProperty=nameWithType> | <span data-ttu-id="a887f-179">Начиная с .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="a887f-179">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Data.VersionNotFoundException?displayProperty=nameWithType> | <span data-ttu-id="a887f-180">Начиная с .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="a887f-180">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.DataMisalignedException?displayProperty=nameWithType> | <span data-ttu-id="a887f-181">Начиная с .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="a887f-181">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.DateTime?displayProperty=nameWithType> | |
> | <xref:System.DateTimeOffset?displayProperty=nameWithType> | |
> | <xref:System.Decimal?displayProperty=nameWithType> | |
> | `System.Diagnostics.Contracts.ContractException` | <span data-ttu-id="a887f-182">Начиная с .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="a887f-182">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Diagnostics.Tracing.EventSourceException?displayProperty=nameWithType> | <span data-ttu-id="a887f-183">Начиная с .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="a887f-183">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.IO.DirectoryNotFoundException?displayProperty=nameWithType> | <span data-ttu-id="a887f-184">Начиная с .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="a887f-184">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.DirectoryServices.AccountManagement.MultipleMatchesException?displayProperty=nameWithType> | <span data-ttu-id="a887f-185">Начиная с .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="a887f-185">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.DirectoryServices.AccountManagement.NoMatchingPrincipalException?displayProperty=nameWithType> | <span data-ttu-id="a887f-186">Начиная с .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="a887f-186">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.DirectoryServices.AccountManagement.PasswordException?displayProperty=nameWithType> | <span data-ttu-id="a887f-187">Начиная с .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="a887f-187">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.DirectoryServices.AccountManagement.PrincipalException?displayProperty=nameWithType> | <span data-ttu-id="a887f-188">Начиная с .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="a887f-188">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.DirectoryServices.AccountManagement.PrincipalExistsException?displayProperty=nameWithType> | <span data-ttu-id="a887f-189">Начиная с .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="a887f-189">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.DirectoryServices.AccountManagement.PrincipalOperationException?displayProperty=nameWithType> | <span data-ttu-id="a887f-190">Начиная с .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="a887f-190">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.DirectoryServices.AccountManagement.PrincipalServerDownException?displayProperty=nameWithType> | <span data-ttu-id="a887f-191">Начиная с .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="a887f-191">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.DirectoryServices.ActiveDirectory.ActiveDirectoryObjectExistsException?displayProperty=nameWithType> | <span data-ttu-id="a887f-192">Начиная с .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="a887f-192">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.DirectoryServices.ActiveDirectory.ActiveDirectoryObjectNotFoundException?displayProperty=nameWithType> | <span data-ttu-id="a887f-193">Начиная с .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="a887f-193">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.DirectoryServices.ActiveDirectory.ActiveDirectoryOperationException?displayProperty=nameWithType> | <span data-ttu-id="a887f-194">Начиная с .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="a887f-194">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.DirectoryServices.ActiveDirectory.ActiveDirectoryServerDownException?displayProperty=nameWithType> | <span data-ttu-id="a887f-195">Начиная с .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="a887f-195">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.DirectoryServices.ActiveDirectory.ForestTrustCollisionException?displayProperty=nameWithType> | <span data-ttu-id="a887f-196">Начиная с .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="a887f-196">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.DirectoryServices.ActiveDirectory.SyncFromAllServersOperationException?displayProperty=nameWithType> | <span data-ttu-id="a887f-197">Начиная с .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="a887f-197">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.DirectoryServices.DirectoryServicesCOMException?displayProperty=nameWithType> | <span data-ttu-id="a887f-198">Начиная с .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="a887f-198">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.DirectoryServices.Protocols.BerConversionException?displayProperty=nameWithType> | <span data-ttu-id="a887f-199">Начиная с .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="a887f-199">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.DirectoryServices.Protocols.DirectoryException?displayProperty=nameWithType> | <span data-ttu-id="a887f-200">Начиная с .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="a887f-200">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.DirectoryServices.Protocols.DirectoryOperationException?displayProperty=nameWithType> | <span data-ttu-id="a887f-201">Начиная с .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="a887f-201">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.DirectoryServices.Protocols.LdapException?displayProperty=nameWithType> | <span data-ttu-id="a887f-202">Начиная с .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="a887f-202">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.DirectoryServices.Protocols.TlsOperationException?displayProperty=nameWithType> | <span data-ttu-id="a887f-203">Начиная с .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="a887f-203">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.DivideByZeroException?displayProperty=nameWithType> | <span data-ttu-id="a887f-204">Начиная с .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="a887f-204">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.DllNotFoundException?displayProperty=nameWithType> | <span data-ttu-id="a887f-205">Начиная с .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="a887f-205">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Double?displayProperty=nameWithType> | |
> | <xref:System.Drawing.Color?displayProperty=nameWithType> | |
> | <xref:System.Drawing.Point?displayProperty=nameWithType> | |
> | <xref:System.Drawing.PointF?displayProperty=nameWithType> | |
> | <xref:System.Drawing.Rectangle?displayProperty=nameWithType> | |
> | <xref:System.Drawing.RectangleF?displayProperty=nameWithType> | |
> | <xref:System.Drawing.Size?displayProperty=nameWithType> | |
> | <xref:System.Drawing.SizeF?displayProperty=nameWithType> | |
> | <xref:System.DuplicateWaitObjectException?displayProperty=nameWithType> | <span data-ttu-id="a887f-206">Начиная с .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="a887f-206">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.EntryPointNotFoundException?displayProperty=nameWithType> | <span data-ttu-id="a887f-207">Начиная с .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="a887f-207">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Enum?displayProperty=nameWithType> | |
> | <xref:System.EventArgs?displayProperty=nameWithType> | <span data-ttu-id="a887f-208">Начиная с .NET Core 2.0.6.</span><span class="sxs-lookup"><span data-stu-id="a887f-208">Starting in .NET Core 2.0.6.</span></span> |
> | <xref:System.Exception?displayProperty=nameWithType> | |
> | <xref:System.ExecutionEngineException?displayProperty=nameWithType> | <span data-ttu-id="a887f-209">Начиная с .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="a887f-209">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.FieldAccessException?displayProperty=nameWithType> | <span data-ttu-id="a887f-210">Начиная с .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="a887f-210">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.FormatException?displayProperty=nameWithType> | <span data-ttu-id="a887f-211">Начиная с .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="a887f-211">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Globalization.CompareInfo?displayProperty=nameWithType> | |
> | <xref:System.Globalization.CultureNotFoundException?displayProperty=nameWithType> | <span data-ttu-id="a887f-212">Начиная с .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="a887f-212">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Globalization.SortVersion?displayProperty=nameWithType> | |
> | <xref:System.Guid?displayProperty=nameWithType> | |
> | `System.IO.Compression.ZLibException` | <span data-ttu-id="a887f-213">Начиная с .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="a887f-213">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.IO.DriveNotFoundException?displayProperty=nameWithType> | <span data-ttu-id="a887f-214">Начиная с .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="a887f-214">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.IO.EndOfStreamException?displayProperty=nameWithType> | <span data-ttu-id="a887f-215">Начиная с .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="a887f-215">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.IO.FileFormatException?displayProperty=nameWithType> | <span data-ttu-id="a887f-216">Начиная с .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="a887f-216">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.IO.FileLoadException?displayProperty=nameWithType> | <span data-ttu-id="a887f-217">Начиная с .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="a887f-217">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.IO.FileNotFoundException?displayProperty=nameWithType> | <span data-ttu-id="a887f-218">Начиная с .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="a887f-218">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.IO.IOException?displayProperty=nameWithType> | <span data-ttu-id="a887f-219">Начиная с .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="a887f-219">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.IO.InternalBufferOverflowException?displayProperty=nameWithType> | <span data-ttu-id="a887f-220">Начиная с .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="a887f-220">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.IO.InvalidDataException?displayProperty=nameWithType> | <span data-ttu-id="a887f-221">Начиная с .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="a887f-221">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.IO.IsolatedStorage.IsolatedStorageException?displayProperty=nameWithType> | <span data-ttu-id="a887f-222">Начиная с .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="a887f-222">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.IO.PathTooLongException?displayProperty=nameWithType> | <span data-ttu-id="a887f-223">Начиная с .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="a887f-223">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.IndexOutOfRangeException?displayProperty=nameWithType> | <span data-ttu-id="a887f-224">Начиная с .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="a887f-224">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.InsufficientExecutionStackException?displayProperty=nameWithType> | <span data-ttu-id="a887f-225">Начиная с .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="a887f-225">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.InsufficientMemoryException?displayProperty=nameWithType> | <span data-ttu-id="a887f-226">Начиная с .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="a887f-226">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Int16?displayProperty=nameWithType> | |
> | <xref:System.Int32?displayProperty=nameWithType> | |
> | <xref:System.Int64?displayProperty=nameWithType> | |
> | <xref:System.IntPtr?displayProperty=nameWithType> | |
> | <xref:System.InvalidCastException?displayProperty=nameWithType> | <span data-ttu-id="a887f-227">Начиная с .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="a887f-227">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.InvalidOperationException?displayProperty=nameWithType> | <span data-ttu-id="a887f-228">Начиная с .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="a887f-228">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.InvalidProgramException?displayProperty=nameWithType> | <span data-ttu-id="a887f-229">Начиная с .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="a887f-229">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.InvalidTimeZoneException?displayProperty=nameWithType> | <span data-ttu-id="a887f-230">Начиная с .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="a887f-230">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.MemberAccessException?displayProperty=nameWithType> | <span data-ttu-id="a887f-231">Начиная с .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="a887f-231">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.MethodAccessException?displayProperty=nameWithType> | <span data-ttu-id="a887f-232">Начиная с .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="a887f-232">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.MissingFieldException?displayProperty=nameWithType> | <span data-ttu-id="a887f-233">Начиная с .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="a887f-233">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.MissingMemberException?displayProperty=nameWithType> | <span data-ttu-id="a887f-234">Начиная с .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="a887f-234">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.MissingMethodException?displayProperty=nameWithType> | <span data-ttu-id="a887f-235">Начиная с .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="a887f-235">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.MulticastNotSupportedException?displayProperty=nameWithType> | <span data-ttu-id="a887f-236">Начиная с .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="a887f-236">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Net.Cookie?displayProperty=nameWithType> | |
> | <xref:System.Net.CookieCollection?displayProperty=nameWithType> | |
> | <xref:System.Net.CookieContainer?displayProperty=nameWithType> | |
> | <xref:System.Net.CookieException?displayProperty=nameWithType> | <span data-ttu-id="a887f-237">Начиная с .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="a887f-237">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Net.HttpListenerException?displayProperty=nameWithType> | <span data-ttu-id="a887f-238">Начиная с .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="a887f-238">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Net.Mail.SmtpException?displayProperty=nameWithType> | <span data-ttu-id="a887f-239">Начиная с .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="a887f-239">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Net.Mail.SmtpFailedRecipientException?displayProperty=nameWithType> | <span data-ttu-id="a887f-240">Начиная с .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="a887f-240">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Net.Mail.SmtpFailedRecipientsException?displayProperty=nameWithType> | <span data-ttu-id="a887f-241">Начиная с .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="a887f-241">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Net.NetworkInformation.NetworkInformationException?displayProperty=nameWithType> | <span data-ttu-id="a887f-242">Начиная с .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="a887f-242">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Net.NetworkInformation.PingException?displayProperty=nameWithType> | <span data-ttu-id="a887f-243">Начиная с .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="a887f-243">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Net.ProtocolViolationException?displayProperty=nameWithType> | <span data-ttu-id="a887f-244">Начиная с .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="a887f-244">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Net.Sockets.SocketException?displayProperty=nameWithType> | <span data-ttu-id="a887f-245">Начиная с .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="a887f-245">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Net.WebException?displayProperty=nameWithType> | <span data-ttu-id="a887f-246">Начиная с .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="a887f-246">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Net.WebSockets.WebSocketException?displayProperty=nameWithType> | <span data-ttu-id="a887f-247">Начиная с .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="a887f-247">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.NotFiniteNumberException?displayProperty=nameWithType> | <span data-ttu-id="a887f-248">Начиная с .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="a887f-248">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.NotImplementedException?displayProperty=nameWithType> | <span data-ttu-id="a887f-249">Начиная с .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="a887f-249">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.NotSupportedException?displayProperty=nameWithType> | <span data-ttu-id="a887f-250">Начиная с .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="a887f-250">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.NullReferenceException?displayProperty=nameWithType> | <span data-ttu-id="a887f-251">Начиная с .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="a887f-251">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Nullable%601?displayProperty=nameWithType> | |
> | <xref:System.Numerics.BigInteger?displayProperty=nameWithType> | |
> | <xref:System.Numerics.Complex?displayProperty=nameWithType> | |
> | <xref:System.Object?displayProperty=nameWithType> | |
> | <xref:System.ObjectDisposedException?displayProperty=nameWithType> | <span data-ttu-id="a887f-252">Начиная с .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="a887f-252">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.OperationCanceledException?displayProperty=nameWithType> | <span data-ttu-id="a887f-253">Начиная с .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="a887f-253">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.OutOfMemoryException?displayProperty=nameWithType> | <span data-ttu-id="a887f-254">Начиная с .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="a887f-254">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.OverflowException?displayProperty=nameWithType> | <span data-ttu-id="a887f-255">Начиная с .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="a887f-255">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.PlatformNotSupportedException?displayProperty=nameWithType> | <span data-ttu-id="a887f-256">Начиная с .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="a887f-256">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.RankException?displayProperty=nameWithType> | <span data-ttu-id="a887f-257">Начиная с .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="a887f-257">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Reflection.AmbiguousMatchException?displayProperty=nameWithType> | <span data-ttu-id="a887f-258">Начиная с .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="a887f-258">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Reflection.CustomAttributeFormatException?displayProperty=nameWithType> | <span data-ttu-id="a887f-259">Начиная с .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="a887f-259">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Reflection.InvalidFilterCriteriaException?displayProperty=nameWithType> | <span data-ttu-id="a887f-260">Начиная с .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="a887f-260">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Reflection.ReflectionTypeLoadException?displayProperty=nameWithType> | <span data-ttu-id="a887f-261">Начиная с .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="a887f-261">Starting in .NET Core 2.0.4.</span></span><br/><span data-ttu-id="a887f-262">Сериализация из .NET Framework в .NET Core не поддерживается.</span><span class="sxs-lookup"><span data-stu-id="a887f-262">Serialization from .NET Framework to .NET Core is not supported.</span></span> |
> | <xref:System.Reflection.TargetException?displayProperty=nameWithType> | <span data-ttu-id="a887f-263">Начиная с .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="a887f-263">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Reflection.TargetInvocationException?displayProperty=nameWithType> | <span data-ttu-id="a887f-264">Начиная с .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="a887f-264">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Reflection.TargetParameterCountException?displayProperty=nameWithType> | <span data-ttu-id="a887f-265">Начиная с .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="a887f-265">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Resources.MissingManifestResourceException?displayProperty=nameWithType> | <span data-ttu-id="a887f-266">Начиная с .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="a887f-266">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Resources.MissingSatelliteAssemblyException?displayProperty=nameWithType> | <span data-ttu-id="a887f-267">Начиная с .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="a887f-267">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Runtime.CompilerServices.RuntimeWrappedException?displayProperty=nameWithType> | <span data-ttu-id="a887f-268">Начиная с .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="a887f-268">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Runtime.InteropServices.COMException?displayProperty=nameWithType> | <span data-ttu-id="a887f-269">Начиная с .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="a887f-269">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Runtime.InteropServices.ExternalException?displayProperty=nameWithType> | <span data-ttu-id="a887f-270">Начиная с .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="a887f-270">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Runtime.InteropServices.InvalidComObjectException?displayProperty=nameWithType> | <span data-ttu-id="a887f-271">Начиная с .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="a887f-271">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Runtime.InteropServices.InvalidOleVariantTypeException?displayProperty=nameWithType> | <span data-ttu-id="a887f-272">Начиная с .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="a887f-272">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Runtime.InteropServices.MarshalDirectiveException?displayProperty=nameWithType> | <span data-ttu-id="a887f-273">Начиная с .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="a887f-273">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Runtime.InteropServices.SEHException?displayProperty=nameWithType> | <span data-ttu-id="a887f-274">Начиная с .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="a887f-274">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Runtime.InteropServices.SafeArrayRankMismatchException?displayProperty=nameWithType> | <span data-ttu-id="a887f-275">Начиная с .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="a887f-275">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Runtime.InteropServices.SafeArrayTypeMismatchException?displayProperty=nameWithType> | <span data-ttu-id="a887f-276">Начиная с .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="a887f-276">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Runtime.Serialization.InvalidDataContractException?displayProperty=nameWithType> | <span data-ttu-id="a887f-277">Начиная с .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="a887f-277">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Runtime.Serialization.SerializationException?displayProperty=nameWithType> | <span data-ttu-id="a887f-278">Начиная с .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="a887f-278">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.SByte?displayProperty=nameWithType> | |
> | <xref:System.Security.AccessControl.PrivilegeNotHeldException?displayProperty=nameWithType> | <span data-ttu-id="a887f-279">Начиная с .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="a887f-279">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Security.Authentication.AuthenticationException?displayProperty=nameWithType> | <span data-ttu-id="a887f-280">Начиная с .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="a887f-280">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Security.Authentication.InvalidCredentialException?displayProperty=nameWithType> | <span data-ttu-id="a887f-281">Начиная с .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="a887f-281">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Security.Cryptography.CryptographicException?displayProperty=nameWithType> | <span data-ttu-id="a887f-282">Начиная с .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="a887f-282">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Security.Cryptography.CryptographicUnexpectedOperationException?displayProperty=nameWithType> | <span data-ttu-id="a887f-283">Начиная с .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="a887f-283">Starting in .NET Core 2.0.4.</span></span> |
> | `System.Security.Cryptography.Xml.CryptoSignedXmlRecursionException` | <span data-ttu-id="a887f-284">Начиная с .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="a887f-284">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Security.HostProtectionException?displayProperty=nameWithType> | <span data-ttu-id="a887f-285">Начиная с .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="a887f-285">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Security.Policy.PolicyException?displayProperty=nameWithType> | <span data-ttu-id="a887f-286">Начиная с .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="a887f-286">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Security.Principal.IdentityNotMappedException?displayProperty=nameWithType> | <span data-ttu-id="a887f-287">Начиная с .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="a887f-287">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Security.SecurityException?displayProperty=nameWithType> | <span data-ttu-id="a887f-288">Начиная с .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="a887f-288">Starting in .NET Core 2.0.4.</span></span><br/><span data-ttu-id="a887f-289">Данные сериализации ограничены.</span><span class="sxs-lookup"><span data-stu-id="a887f-289">Limited serialization data.</span></span> |
> | <xref:System.Security.VerificationException?displayProperty=nameWithType> | <span data-ttu-id="a887f-290">Начиная с .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="a887f-290">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Security.XmlSyntaxException?displayProperty=nameWithType> | <span data-ttu-id="a887f-291">Начиная с .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="a887f-291">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.ServiceProcess.TimeoutException?displayProperty=nameWithType> | <span data-ttu-id="a887f-292">Начиная с .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="a887f-292">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Single?displayProperty=nameWithType> | |
> | <xref:System.StackOverflowException?displayProperty=nameWithType> | <span data-ttu-id="a887f-293">Начиная с .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="a887f-293">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.String?displayProperty=nameWithType> | |
> | <xref:System.StringComparer?displayProperty=nameWithType> | |
> | <xref:System.SystemException?displayProperty=nameWithType> | <span data-ttu-id="a887f-294">Начиная с .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="a887f-294">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Text.DecoderFallbackException?displayProperty=nameWithType> | <span data-ttu-id="a887f-295">Начиная с .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="a887f-295">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Text.EncoderFallbackException?displayProperty=nameWithType> | <span data-ttu-id="a887f-296">Начиная с .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="a887f-296">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Text.RegularExpressions.RegexMatchTimeoutException?displayProperty=nameWithType> | <span data-ttu-id="a887f-297">Начиная с .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="a887f-297">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Text.StringBuilder?displayProperty=nameWithType> | |
> | <xref:System.Threading.AbandonedMutexException?displayProperty=nameWithType> | <span data-ttu-id="a887f-298">Начиная с .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="a887f-298">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Threading.BarrierPostPhaseException?displayProperty=nameWithType> | <span data-ttu-id="a887f-299">Начиная с .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="a887f-299">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Threading.LockRecursionException?displayProperty=nameWithType> | <span data-ttu-id="a887f-300">Начиная с .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="a887f-300">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Threading.SemaphoreFullException?displayProperty=nameWithType> | <span data-ttu-id="a887f-301">Начиная с .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="a887f-301">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Threading.SynchronizationLockException?displayProperty=nameWithType> | <span data-ttu-id="a887f-302">Начиная с .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="a887f-302">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Threading.Tasks.TaskCanceledException?displayProperty=nameWithType> | <span data-ttu-id="a887f-303">Начиная с .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="a887f-303">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Threading.Tasks.TaskSchedulerException?displayProperty=nameWithType> | <span data-ttu-id="a887f-304">Начиная с .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="a887f-304">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Threading.ThreadAbortException?displayProperty=nameWithType> | <span data-ttu-id="a887f-305">Начиная с .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="a887f-305">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Threading.ThreadInterruptedException?displayProperty=nameWithType> | <span data-ttu-id="a887f-306">Начиная с .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="a887f-306">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Threading.ThreadStartException?displayProperty=nameWithType> | <span data-ttu-id="a887f-307">Начиная с .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="a887f-307">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Threading.ThreadStateException?displayProperty=nameWithType> | <span data-ttu-id="a887f-308">Начиная с .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="a887f-308">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Threading.WaitHandleCannotBeOpenedException?displayProperty=nameWithType> | <span data-ttu-id="a887f-309">Начиная с .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="a887f-309">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.TimeSpan?displayProperty=nameWithType> | |
> | <xref:System.TimeZoneInfo.AdjustmentRule?displayProperty=nameWithType> | |
> | <xref:System.TimeZoneInfo?displayProperty=nameWithType> | |
> | <xref:System.TimeZoneNotFoundException?displayProperty=nameWithType> | <span data-ttu-id="a887f-310">Начиная с .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="a887f-310">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.TimeoutException?displayProperty=nameWithType> | <span data-ttu-id="a887f-311">Начиная с .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="a887f-311">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Transactions.TransactionAbortedException?displayProperty=nameWithType> | <span data-ttu-id="a887f-312">Начиная с .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="a887f-312">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Transactions.TransactionException?displayProperty=nameWithType> | <span data-ttu-id="a887f-313">Начиная с .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="a887f-313">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Transactions.TransactionInDoubtException?displayProperty=nameWithType> | <span data-ttu-id="a887f-314">Начиная с .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="a887f-314">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Transactions.TransactionManagerCommunicationException?displayProperty=nameWithType> | <span data-ttu-id="a887f-315">Начиная с .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="a887f-315">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Transactions.TransactionPromotionException?displayProperty=nameWithType> | <span data-ttu-id="a887f-316">Начиная с .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="a887f-316">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Tuple?displayProperty=nameWithType> | |
> | <xref:System.TypeAccessException?displayProperty=nameWithType> | <span data-ttu-id="a887f-317">Начиная с .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="a887f-317">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.TypeInitializationException?displayProperty=nameWithType> | <span data-ttu-id="a887f-318">Начиная с .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="a887f-318">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.TypeLoadException?displayProperty=nameWithType> | <span data-ttu-id="a887f-319">Начиная с .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="a887f-319">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.TypeUnloadedException?displayProperty=nameWithType> | <span data-ttu-id="a887f-320">Начиная с .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="a887f-320">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.UInt16?displayProperty=nameWithType> | |
> | <xref:System.UInt32?displayProperty=nameWithType> | |
> | <xref:System.UInt64?displayProperty=nameWithType> | |
> | <xref:System.UIntPtr?displayProperty=nameWithType> | |
> | <xref:System.UnauthorizedAccessException?displayProperty=nameWithType> | <span data-ttu-id="a887f-321">Начиная с .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="a887f-321">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Uri?displayProperty=nameWithType> | |
> | <xref:System.UriFormatException?displayProperty=nameWithType> | <span data-ttu-id="a887f-322">Начиная с .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="a887f-322">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.ValueTuple?displayProperty=nameWithType> | <span data-ttu-id="a887f-323">Не подлежит сериализации в .NET Framework 4.7 и более ранних версиях.</span><span class="sxs-lookup"><span data-stu-id="a887f-323">Not serializable in .NET Framework 4.7 and earlier versions.</span></span> |
> | <xref:System.ValueType?displayProperty=nameWithType> | |
> | <xref:System.Version?displayProperty=nameWithType> | |
> | <xref:System.WeakReference%601?displayProperty=nameWithType> | |
> | <xref:System.WeakReference?displayProperty=nameWithType> | |
> | <xref:System.Xml.Schema.XmlSchemaException?displayProperty=nameWithType> | <span data-ttu-id="a887f-324">Начиная с .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="a887f-324">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Xml.Schema.XmlSchemaInferenceException?displayProperty=nameWithType> | <span data-ttu-id="a887f-325">Начиная с .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="a887f-325">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Xml.Schema.XmlSchemaValidationException?displayProperty=nameWithType> | <span data-ttu-id="a887f-326">Начиная с .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="a887f-326">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Xml.XPath.XPathException?displayProperty=nameWithType> | <span data-ttu-id="a887f-327">Начиная с .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="a887f-327">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Xml.XmlException?displayProperty=nameWithType> | <span data-ttu-id="a887f-328">Начиная с .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="a887f-328">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Xml.Xsl.XsltCompileException?displayProperty=nameWithType> | <span data-ttu-id="a887f-329">Начиная с .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="a887f-329">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Xml.Xsl.XsltException?displayProperty=nameWithType> | <span data-ttu-id="a887f-330">Начиная с .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="a887f-330">Starting in .NET Core 2.0.4.</span></span> |

## <a name="see-also"></a><span data-ttu-id="a887f-331">См. также</span><span class="sxs-lookup"><span data-stu-id="a887f-331">See also</span></span>

- <xref:System.Runtime.Serialization>\
<span data-ttu-id="a887f-332">Содержит классы, которые можно использовать для сериализации и десериализации объектов.</span><span class="sxs-lookup"><span data-stu-id="a887f-332">Contains classes that can be used for serializing and deserializing objects.</span></span>

- <span data-ttu-id="a887f-333">[Сериализация XML и SOAP](../../../docs/standard/serialization/xml-and-soap-serialization.md)</span><span class="sxs-lookup"><span data-stu-id="a887f-333">[XML and SOAP Serialization](../../../docs/standard/serialization/xml-and-soap-serialization.md)</span></span>\
<span data-ttu-id="a887f-334">Описывает механизм XML-сериализации , входящий в среду CLR.</span><span class="sxs-lookup"><span data-stu-id="a887f-334">Describes the XML serialization mechanism that is included with the common language runtime.</span></span>

- <span data-ttu-id="a887f-335">[Безопасность и сериализация](../../../docs/framework/misc/security-and-serialization.md)</span><span class="sxs-lookup"><span data-stu-id="a887f-335">[Security and Serialization](../../../docs/framework/misc/security-and-serialization.md)</span></span>\
<span data-ttu-id="a887f-336">Содержит рекомендации по написанию безопасного кода, выполняющего сериализацию.</span><span class="sxs-lookup"><span data-stu-id="a887f-336">Describes the secure coding guidelines to follow when writing code that performs serialization.</span></span>

- <span data-ttu-id="a887f-337">[Удаленное взаимодействие .NET](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/72x4h507(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="a887f-337">[.NET Remoting](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/72x4h507(v=vs.100))</span></span>\
<span data-ttu-id="a887f-338">Описываются различные методы удаленного взаимодействия.</span><span class="sxs-lookup"><span data-stu-id="a887f-338">Describes the various methods Starting in .NET Framework for remote communications.</span></span>

- <span data-ttu-id="a887f-339">[Веб-службы XML, созданные с помощью ASP.NET, и клиенты веб-служб с поддержкой XML](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/7bkzywba(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="a887f-339">[XML Web Services Created Using ASP.NET and XML Web Service Clients](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/7bkzywba(v=vs.100))</span></span>\
<span data-ttu-id="a887f-340">Статьи, посвященные программированию веб-служб XML, созданных с помощью ASP.NET.</span><span class="sxs-lookup"><span data-stu-id="a887f-340">Articles that describe and explain how to program XML Web services created using ASP.NET.</span></span>
