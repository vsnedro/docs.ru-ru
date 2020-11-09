---
title: Неподдерживаемые API в .NET Core и .NET версии 5 и более поздних
titleSuffix: ''
description: Узнайте, какие интерфейсы API .NET всегда вызывают исключение в .NET Core и .NET 5.0 и более поздних версиях.
ms.date: 10/13/2020
ms.openlocfilehash: 51d73557a48910d9cb1c4d3cdced34dfe4d849d8
ms.sourcegitcommit: 6bef8abde346c59771a35f4f76bf037ff61c5ba3
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/06/2020
ms.locfileid: "94329785"
---
# <a name="apis-that-always-throw-exceptions-on-net-core-and-net-5"></a><span data-ttu-id="0ee71-103">API, которые всегда создают исключения в .NET Core и .NET версии 5 и более поздних</span><span class="sxs-lookup"><span data-stu-id="0ee71-103">APIs that always throw exceptions on .NET Core and .NET 5+</span></span>

<span data-ttu-id="0ee71-104">Следующие API всегда будут вызывать исключение <xref:System.PlatformNotSupportedException> в .NET версии 5.0 и более поздних (включая все версии .NET Core) на всех платформах или на их подмножестве.</span><span class="sxs-lookup"><span data-stu-id="0ee71-104">The following APIs will always throw a <xref:System.PlatformNotSupportedException> on .NET 5.0 and later versions (including all versions of .NET Core) on all or a subset of platforms.</span></span>

<span data-ttu-id="0ee71-105">В этой статье затронутые API упорядочиваются по пространствам имен.</span><span class="sxs-lookup"><span data-stu-id="0ee71-105">This article organizes the affected APIs by namespace.</span></span>

> [!NOTE]
>
> - <span data-ttu-id="0ee71-106">Эта статья все еще находится в процессе написания.</span><span class="sxs-lookup"><span data-stu-id="0ee71-106">This article is a work-in-progress.</span></span> <span data-ttu-id="0ee71-107">Это не полный список API-интерфейсов, создающих исключения в .NET версии 5 и более поздних.</span><span class="sxs-lookup"><span data-stu-id="0ee71-107">It is not a complete list of APIs that throw exceptions on .NET 5+.</span></span>
> - <span data-ttu-id="0ee71-108">В этой статье не рассматриваются явные реализации интерфейса для двоичной сериализации, которые вызываются в .NET версии 5 и более поздних.</span><span class="sxs-lookup"><span data-stu-id="0ee71-108">This article does not include the explicit interface implementations for binary serialization that throw on .NET 5+.</span></span> <span data-ttu-id="0ee71-109">Дополнительные сведения см. в разделе [Двоичная сериализация в .NET Core](../../standard/serialization/binary-serialization.md#net-core).</span><span class="sxs-lookup"><span data-stu-id="0ee71-109">For more information, see [Binary serialization in .NET Core](../../standard/serialization/binary-serialization.md#net-core).</span></span>

## <a name="system"></a><span data-ttu-id="0ee71-110">Система</span><span class="sxs-lookup"><span data-stu-id="0ee71-110">System</span></span>

| <span data-ttu-id="0ee71-111">Участник</span><span class="sxs-lookup"><span data-stu-id="0ee71-111">Member</span></span> | <span data-ttu-id="0ee71-112">Платформы, которые вызывают исключение</span><span class="sxs-lookup"><span data-stu-id="0ee71-112">Platforms that throw</span></span> |
| - | - |
| <xref:System.AppDomain.CreateDomain%2A?displayProperty=nameWithType> | <span data-ttu-id="0ee71-113">Все</span><span class="sxs-lookup"><span data-stu-id="0ee71-113">All</span></span> |
| <xref:System.AppDomain.ExecuteAssembly(System.String,System.String[],System.Byte[],System.Configuration.Assemblies.AssemblyHashAlgorithm)?displayProperty=nameWithType> | <span data-ttu-id="0ee71-114">Все</span><span class="sxs-lookup"><span data-stu-id="0ee71-114">All</span></span> |
| <xref:System.Console.CapsLock?displayProperty=nameWithType> | <span data-ttu-id="0ee71-115">Linux и macOS</span><span class="sxs-lookup"><span data-stu-id="0ee71-115">Linux and macOS</span></span> |
| <xref:System.Console.NumberLock?displayProperty=nameWithType> | <span data-ttu-id="0ee71-116">Linux и macOS</span><span class="sxs-lookup"><span data-stu-id="0ee71-116">Linux and macOS</span></span> |
| <xref:System.Delegate.GetObjectData(System.Runtime.Serialization.SerializationInfo,System.Runtime.Serialization.StreamingContext)?displayProperty=nameWithType> | <span data-ttu-id="0ee71-117">Все</span><span class="sxs-lookup"><span data-stu-id="0ee71-117">All</span></span> |
| <xref:System.Exception.SerializeObjectState?displayProperty=nameWithType> | <span data-ttu-id="0ee71-118">Все</span><span class="sxs-lookup"><span data-stu-id="0ee71-118">All</span></span> |
| <xref:System.MarshalByRefObject.GetLifetimeService?displayProperty=nameWithType> | <span data-ttu-id="0ee71-119">Все</span><span class="sxs-lookup"><span data-stu-id="0ee71-119">All</span></span> |
| <xref:System.MarshalByRefObject.InitializeLifetimeService?displayProperty=nameWithType> | <span data-ttu-id="0ee71-120">Все</span><span class="sxs-lookup"><span data-stu-id="0ee71-120">All</span></span> |
| <xref:System.OperatingSystem.GetObjectData(System.Runtime.Serialization.SerializationInfo,System.Runtime.Serialization.StreamingContext)?displayProperty=nameWithType> | <span data-ttu-id="0ee71-121">Все</span><span class="sxs-lookup"><span data-stu-id="0ee71-121">All</span></span> |
| <xref:System.Type.ReflectionOnlyGetType(System.String,System.Boolean,System.Boolean)?displayProperty=nameWithType> | <span data-ttu-id="0ee71-122">Все</span><span class="sxs-lookup"><span data-stu-id="0ee71-122">All</span></span> |

## <a name="systemcodedomcompiler"></a><span data-ttu-id="0ee71-123">System.CodeDom.Compiler</span><span class="sxs-lookup"><span data-stu-id="0ee71-123">System.CodeDom.Compiler</span></span>

| <span data-ttu-id="0ee71-124">Участник</span><span class="sxs-lookup"><span data-stu-id="0ee71-124">Member</span></span> | <span data-ttu-id="0ee71-125">Платформы, которые вызывают исключение</span><span class="sxs-lookup"><span data-stu-id="0ee71-125">Platforms that throw</span></span> |
| - | - |
| <xref:System.CodeDom.Compiler.CodeDomProvider.CompileAssemblyFromDom%2A?displayProperty=nameWithType> | <span data-ttu-id="0ee71-126">Все</span><span class="sxs-lookup"><span data-stu-id="0ee71-126">All</span></span> |
| <xref:System.CodeDom.Compiler.CodeDomProvider.CompileAssemblyFromFile%2A?displayProperty=nameWithType> | <span data-ttu-id="0ee71-127">Все</span><span class="sxs-lookup"><span data-stu-id="0ee71-127">All</span></span> |
| <xref:System.CodeDom.Compiler.CodeDomProvider.CompileAssemblyFromSource%2A?displayProperty=nameWithType> | <span data-ttu-id="0ee71-128">Все</span><span class="sxs-lookup"><span data-stu-id="0ee71-128">All</span></span> |

## <a name="systemcollectionsspecialized"></a><span data-ttu-id="0ee71-129">System.Collections.Specialized</span><span class="sxs-lookup"><span data-stu-id="0ee71-129">System.Collections.Specialized</span></span>

| <span data-ttu-id="0ee71-130">Участник</span><span class="sxs-lookup"><span data-stu-id="0ee71-130">Member</span></span> | <span data-ttu-id="0ee71-131">Платформы, которые вызывают исключение</span><span class="sxs-lookup"><span data-stu-id="0ee71-131">Platforms that throw</span></span> |
| - | - |
| <xref:System.Collections.Specialized.NameObjectCollectionBase.%23ctor(System.Runtime.Serialization.SerializationInfo,System.Runtime.Serialization.StreamingContext)> | <span data-ttu-id="0ee71-132">Все</span><span class="sxs-lookup"><span data-stu-id="0ee71-132">All</span></span> |
| <xref:System.Collections.Specialized.NameObjectCollectionBase.GetObjectData(System.Runtime.Serialization.SerializationInfo,System.Runtime.Serialization.StreamingContext)?displayProperty=nameWithType> | <span data-ttu-id="0ee71-133">Все</span><span class="sxs-lookup"><span data-stu-id="0ee71-133">All</span></span> |
| <xref:System.Collections.Specialized.NameObjectCollectionBase.OnDeserialization(System.Object)?displayProperty=nameWithType> | <span data-ttu-id="0ee71-134">Все</span><span class="sxs-lookup"><span data-stu-id="0ee71-134">All</span></span> |

## <a name="systemconfiguration"></a><span data-ttu-id="0ee71-135">System.Configuration</span><span class="sxs-lookup"><span data-stu-id="0ee71-135">System.Configuration</span></span>

| <span data-ttu-id="0ee71-136">Участник</span><span class="sxs-lookup"><span data-stu-id="0ee71-136">Member</span></span> | <span data-ttu-id="0ee71-137">Платформы, которые вызывают исключение</span><span class="sxs-lookup"><span data-stu-id="0ee71-137">Platforms that throw</span></span> |
| - | - |
| <span data-ttu-id="0ee71-138"><xref:System.Configuration.RsaProtectedConfigurationProvider?displayProperty=nameWithType> (все члены)</span><span class="sxs-lookup"><span data-stu-id="0ee71-138"><xref:System.Configuration.RsaProtectedConfigurationProvider?displayProperty=nameWithType> (all members)</span></span> | <span data-ttu-id="0ee71-139">Все</span><span class="sxs-lookup"><span data-stu-id="0ee71-139">All</span></span> |

## <a name="systemconsole"></a><span data-ttu-id="0ee71-140">System.Console</span><span class="sxs-lookup"><span data-stu-id="0ee71-140">System.Console</span></span>

| <span data-ttu-id="0ee71-141">Участник</span><span class="sxs-lookup"><span data-stu-id="0ee71-141">Member</span></span> | <span data-ttu-id="0ee71-142">Платформы, которые вызывают исключение</span><span class="sxs-lookup"><span data-stu-id="0ee71-142">Platforms that throw</span></span> |
| - | - |
| <xref:System.Console.Beep?displayProperty=nameWithType> | <span data-ttu-id="0ee71-143">Linux и macOS</span><span class="sxs-lookup"><span data-stu-id="0ee71-143">Linux and macOS</span></span> |
| <span data-ttu-id="0ee71-144"><xref:System.Console.BufferHeight?displayProperty=nameWithType> (только установка)</span><span class="sxs-lookup"><span data-stu-id="0ee71-144"><xref:System.Console.BufferHeight?displayProperty=nameWithType> (set only)</span></span> | <span data-ttu-id="0ee71-145">Linux и macOS</span><span class="sxs-lookup"><span data-stu-id="0ee71-145">Linux and macOS</span></span> |
| <span data-ttu-id="0ee71-146"><xref:System.Console.BufferWidth?displayProperty=nameWithType> (только установка)</span><span class="sxs-lookup"><span data-stu-id="0ee71-146"><xref:System.Console.BufferWidth?displayProperty=nameWithType> (set only)</span></span> | <span data-ttu-id="0ee71-147">Linux и macOS</span><span class="sxs-lookup"><span data-stu-id="0ee71-147">Linux and macOS</span></span> |
| <span data-ttu-id="0ee71-148"><xref:System.Console.CursorSize?displayProperty=nameWithType> (только установка)</span><span class="sxs-lookup"><span data-stu-id="0ee71-148"><xref:System.Console.CursorSize?displayProperty=nameWithType> (set only)</span></span> | <span data-ttu-id="0ee71-149">Linux и macOS</span><span class="sxs-lookup"><span data-stu-id="0ee71-149">Linux and macOS</span></span> |
| <span data-ttu-id="0ee71-150"><xref:System.Console.CursorVisible?displayProperty=nameWithType> (только получение)</span><span class="sxs-lookup"><span data-stu-id="0ee71-150"><xref:System.Console.CursorVisible?displayProperty=nameWithType> (get only)</span></span> | <span data-ttu-id="0ee71-151">Linux и macOS</span><span class="sxs-lookup"><span data-stu-id="0ee71-151">Linux and macOS</span></span> |
| <xref:System.Console.MoveBufferArea%2A?displayProperty=nameWithType> | <span data-ttu-id="0ee71-152">Linux и macOS</span><span class="sxs-lookup"><span data-stu-id="0ee71-152">Linux and macOS</span></span> |
| <xref:System.Console.SetWindowPosition%2A?displayProperty=nameWithType> | <span data-ttu-id="0ee71-153">Linux и macOS</span><span class="sxs-lookup"><span data-stu-id="0ee71-153">Linux and macOS</span></span> |
| <xref:System.Console.SetWindowSize%2A?displayProperty=nameWithType> | <span data-ttu-id="0ee71-154">Linux и macOS</span><span class="sxs-lookup"><span data-stu-id="0ee71-154">Linux and macOS</span></span> |
| <span data-ttu-id="0ee71-155"><xref:System.Console.Title?displayProperty=nameWithType> (только получение)</span><span class="sxs-lookup"><span data-stu-id="0ee71-155"><xref:System.Console.Title?displayProperty=nameWithType> (get only)</span></span> | <span data-ttu-id="0ee71-156">Linux и macOS</span><span class="sxs-lookup"><span data-stu-id="0ee71-156">Linux and macOS</span></span> |
| <span data-ttu-id="0ee71-157"><xref:System.Console.WindowHeight?displayProperty=nameWithType> (только установка)</span><span class="sxs-lookup"><span data-stu-id="0ee71-157"><xref:System.Console.WindowHeight?displayProperty=nameWithType> (set only)</span></span> | <span data-ttu-id="0ee71-158">Linux и macOS</span><span class="sxs-lookup"><span data-stu-id="0ee71-158">Linux and macOS</span></span> |
| <span data-ttu-id="0ee71-159"><xref:System.Console.WindowLeft?displayProperty=nameWithType> (только установка)</span><span class="sxs-lookup"><span data-stu-id="0ee71-159"><xref:System.Console.WindowLeft?displayProperty=nameWithType> (set only)</span></span> | <span data-ttu-id="0ee71-160">Linux и macOS</span><span class="sxs-lookup"><span data-stu-id="0ee71-160">Linux and macOS</span></span> |
| <span data-ttu-id="0ee71-161"><xref:System.Console.WindowTop?displayProperty=nameWithType> (только установка)</span><span class="sxs-lookup"><span data-stu-id="0ee71-161"><xref:System.Console.WindowTop?displayProperty=nameWithType> (set only)</span></span> | <span data-ttu-id="0ee71-162">Linux и macOS</span><span class="sxs-lookup"><span data-stu-id="0ee71-162">Linux and macOS</span></span> |
| <span data-ttu-id="0ee71-163"><xref:System.Console.WindowWidth?displayProperty=nameWithType> (только установка)</span><span class="sxs-lookup"><span data-stu-id="0ee71-163"><xref:System.Console.WindowWidth?displayProperty=nameWithType> (set only)</span></span> | <span data-ttu-id="0ee71-164">Linux и macOS</span><span class="sxs-lookup"><span data-stu-id="0ee71-164">Linux and macOS</span></span> |

## <a name="systemdatacommon"></a><span data-ttu-id="0ee71-165">System.Data.Common</span><span class="sxs-lookup"><span data-stu-id="0ee71-165">System.Data.Common</span></span>

| <span data-ttu-id="0ee71-166">Участник</span><span class="sxs-lookup"><span data-stu-id="0ee71-166">Member</span></span> | <span data-ttu-id="0ee71-167">Платформы, которые вызывают исключение</span><span class="sxs-lookup"><span data-stu-id="0ee71-167">Platforms that throw</span></span> |
| - | - |
| <span data-ttu-id="0ee71-168"><xref:System.Data.Common.DbDataReader.GetSchemaTable%2A?displayProperty=nameWithType> (вызывает <xref:System.NotSupportedException>)</span><span class="sxs-lookup"><span data-stu-id="0ee71-168"><xref:System.Data.Common.DbDataReader.GetSchemaTable%2A?displayProperty=nameWithType> (throws <xref:System.NotSupportedException>)</span></span> | <span data-ttu-id="0ee71-169">Все</span><span class="sxs-lookup"><span data-stu-id="0ee71-169">All</span></span> |

## <a name="systemdiagnosticsprocess"></a><span data-ttu-id="0ee71-170">System.Diagnostics.Process</span><span class="sxs-lookup"><span data-stu-id="0ee71-170">System.Diagnostics.Process</span></span>

| <span data-ttu-id="0ee71-171">Участник</span><span class="sxs-lookup"><span data-stu-id="0ee71-171">Member</span></span> | <span data-ttu-id="0ee71-172">Платформы, которые вызывают исключение</span><span class="sxs-lookup"><span data-stu-id="0ee71-172">Platforms that throw</span></span> |
| - | - |
| <span data-ttu-id="0ee71-173"><xref:System.Diagnostics.Process.MaxWorkingSet?displayProperty=nameWithType> (только установка)</span><span class="sxs-lookup"><span data-stu-id="0ee71-173"><xref:System.Diagnostics.Process.MaxWorkingSet?displayProperty=nameWithType> (set only)</span></span> | <span data-ttu-id="0ee71-174">Linux</span><span class="sxs-lookup"><span data-stu-id="0ee71-174">Linux</span></span> |
| <span data-ttu-id="0ee71-175"><xref:System.Diagnostics.Process.MinWorkingSet?displayProperty=nameWithType> (только установка)</span><span class="sxs-lookup"><span data-stu-id="0ee71-175"><xref:System.Diagnostics.Process.MinWorkingSet?displayProperty=nameWithType> (set only)</span></span> | <span data-ttu-id="0ee71-176">Linux</span><span class="sxs-lookup"><span data-stu-id="0ee71-176">Linux</span></span> |
| <xref:System.Diagnostics.Process.ProcessorAffinity?displayProperty=nameWithType> | <span data-ttu-id="0ee71-177">macOS</span><span class="sxs-lookup"><span data-stu-id="0ee71-177">macOS</span></span> |
| <xref:System.Diagnostics.Process.MainWindowHandle?displayProperty=nameWithType> | <span data-ttu-id="0ee71-178">Linux и macOS</span><span class="sxs-lookup"><span data-stu-id="0ee71-178">Linux and macOS</span></span> |
| <xref:System.Diagnostics.Process.Start%2A?displayProperty=nameWithType> | <span data-ttu-id="0ee71-179">Linux и macOS</span><span class="sxs-lookup"><span data-stu-id="0ee71-179">Linux and macOS</span></span> |
| <xref:System.Diagnostics.ProcessStartInfo.UserName?displayProperty=nameWithType> | <span data-ttu-id="0ee71-180">Linux и macOS</span><span class="sxs-lookup"><span data-stu-id="0ee71-180">Linux and macOS</span></span> |
| <xref:System.Diagnostics.ProcessStartInfo.PasswordInClearText?displayProperty=nameWithType> | <span data-ttu-id="0ee71-181">Linux и macOS</span><span class="sxs-lookup"><span data-stu-id="0ee71-181">Linux and macOS</span></span> |
| <xref:System.Diagnostics.ProcessStartInfo.Domain?displayProperty=nameWithType> | <span data-ttu-id="0ee71-182">Linux и macOS</span><span class="sxs-lookup"><span data-stu-id="0ee71-182">Linux and macOS</span></span> |
| <xref:System.Diagnostics.ProcessStartInfo.LoadUserProfile?displayProperty=nameWithType> | <span data-ttu-id="0ee71-183">Linux и macOS</span><span class="sxs-lookup"><span data-stu-id="0ee71-183">Linux and macOS</span></span> |
| <span data-ttu-id="0ee71-184"><xref:System.Diagnostics.ProcessThread.BasePriority?displayProperty=nameWithType> (только установка)</span><span class="sxs-lookup"><span data-stu-id="0ee71-184"><xref:System.Diagnostics.ProcessThread.BasePriority?displayProperty=nameWithType> (set only)</span></span> | <span data-ttu-id="0ee71-185">Linux и macOS</span><span class="sxs-lookup"><span data-stu-id="0ee71-185">Linux and macOS</span></span> |
| <span data-ttu-id="0ee71-186"><xref:System.Diagnostics.ProcessThread.BasePriority?displayProperty=nameWithType> (только получение)</span><span class="sxs-lookup"><span data-stu-id="0ee71-186"><xref:System.Diagnostics.ProcessThread.BasePriority?displayProperty=nameWithType> (get only)</span></span> | <span data-ttu-id="0ee71-187">macOS</span><span class="sxs-lookup"><span data-stu-id="0ee71-187">macOS</span></span> |
| <span data-ttu-id="0ee71-188"><xref:System.Diagnostics.ProcessThread.ProcessorAffinity?displayProperty=nameWithType> (только установка)</span><span class="sxs-lookup"><span data-stu-id="0ee71-188"><xref:System.Diagnostics.ProcessThread.ProcessorAffinity?displayProperty=nameWithType> (set only)</span></span> | <span data-ttu-id="0ee71-189">Linux и macOS</span><span class="sxs-lookup"><span data-stu-id="0ee71-189">Linux and macOS</span></span> |

## <a name="systemio"></a><span data-ttu-id="0ee71-190">System.IO</span><span class="sxs-lookup"><span data-stu-id="0ee71-190">System.IO</span></span>

| <span data-ttu-id="0ee71-191">Участник</span><span class="sxs-lookup"><span data-stu-id="0ee71-191">Member</span></span> | <span data-ttu-id="0ee71-192">Платформы, которые вызывают исключение</span><span class="sxs-lookup"><span data-stu-id="0ee71-192">Platforms that throw</span></span> |
| - | - |
| <xref:System.IO.FileSystemInfo.%23ctor(System.Runtime.Serialization.SerializationInfo,System.Runtime.Serialization.StreamingContext)> | <span data-ttu-id="0ee71-193">Все</span><span class="sxs-lookup"><span data-stu-id="0ee71-193">All</span></span> |
| <xref:System.IO.FileSystemInfo.GetObjectData(System.Runtime.Serialization.SerializationInfo,System.Runtime.Serialization.StreamingContext)?displayProperty=nameWithType> | <span data-ttu-id="0ee71-194">Все</span><span class="sxs-lookup"><span data-stu-id="0ee71-194">All</span></span> |

## <a name="systemiopipes"></a><span data-ttu-id="0ee71-195">System.IO.Pipes</span><span class="sxs-lookup"><span data-stu-id="0ee71-195">System.IO.Pipes</span></span>

| <span data-ttu-id="0ee71-196">Участник</span><span class="sxs-lookup"><span data-stu-id="0ee71-196">Member</span></span> | <span data-ttu-id="0ee71-197">Платформы, которые вызывают исключение</span><span class="sxs-lookup"><span data-stu-id="0ee71-197">Platforms that throw</span></span> |
| - | - |
| <xref:System.IO.Pipes.NamedPipeClientStream.NumberOfServerInstances?displayProperty=nameWithType> | <span data-ttu-id="0ee71-198">Linux и macOS</span><span class="sxs-lookup"><span data-stu-id="0ee71-198">Linux and macOS</span></span> |
| <xref:System.IO.Pipes.NamedPipeServerStream.GetImpersonationUserName?displayProperty=nameWithType> | <span data-ttu-id="0ee71-199">Linux и macOS</span><span class="sxs-lookup"><span data-stu-id="0ee71-199">Linux and macOS</span></span> |
| <xref:System.IO.Pipes.PipeStream.InBufferSize?displayProperty=nameWithType> | <span data-ttu-id="0ee71-200">Linux и macOS</span><span class="sxs-lookup"><span data-stu-id="0ee71-200">Linux and macOS</span></span> |
| <xref:System.IO.Pipes.PipeStream.OutBufferSize?displayProperty=nameWithType> | <span data-ttu-id="0ee71-201">Linux и macOS</span><span class="sxs-lookup"><span data-stu-id="0ee71-201">Linux and macOS</span></span> |
| <span data-ttu-id="0ee71-202"><xref:System.IO.Pipes.PipeStream.ReadMode?displayProperty=nameWithType> (только установка)</span><span class="sxs-lookup"><span data-stu-id="0ee71-202"><xref:System.IO.Pipes.PipeStream.ReadMode?displayProperty=nameWithType> (set only)</span></span> | <span data-ttu-id="0ee71-203">Linux и macOS</span><span class="sxs-lookup"><span data-stu-id="0ee71-203">Linux and macOS</span></span> |
| <xref:System.IO.Pipes.PipeStream.WaitForPipeDrain?displayProperty=nameWithType> | <span data-ttu-id="0ee71-204">Linux и macOS</span><span class="sxs-lookup"><span data-stu-id="0ee71-204">Linux and macOS</span></span> |

## <a name="systemmedia"></a><span data-ttu-id="0ee71-205">System.Media</span><span class="sxs-lookup"><span data-stu-id="0ee71-205">System.Media</span></span>

| <span data-ttu-id="0ee71-206">Участник</span><span class="sxs-lookup"><span data-stu-id="0ee71-206">Member</span></span> | <span data-ttu-id="0ee71-207">Платформы, которые вызывают исключение</span><span class="sxs-lookup"><span data-stu-id="0ee71-207">Platforms that throw</span></span> |
| - | - |
| <xref:System.Media.SoundPlayer.%23ctor(System.Runtime.Serialization.SerializationInfo,System.Runtime.Serialization.StreamingContext)> | <span data-ttu-id="0ee71-208">Все</span><span class="sxs-lookup"><span data-stu-id="0ee71-208">All</span></span> |

## <a name="systemnet"></a><span data-ttu-id="0ee71-209">System.Net</span><span class="sxs-lookup"><span data-stu-id="0ee71-209">System.Net</span></span>

| <span data-ttu-id="0ee71-210">Участник</span><span class="sxs-lookup"><span data-stu-id="0ee71-210">Member</span></span> | <span data-ttu-id="0ee71-211">Платформы, которые вызывают исключение</span><span class="sxs-lookup"><span data-stu-id="0ee71-211">Platforms that throw</span></span> |
| - | - |
| <xref:System.Net.AuthenticationManager.Authenticate(System.String,System.Net.WebRequest,System.Net.ICredentials)?displayProperty=nameWithType> | <span data-ttu-id="0ee71-212">Все</span><span class="sxs-lookup"><span data-stu-id="0ee71-212">All</span></span> |
| <xref:System.Net.AuthenticationManager.PreAuthenticate(System.Net.WebRequest,System.Net.ICredentials)?displayProperty=nameWithType> | <span data-ttu-id="0ee71-213">Все</span><span class="sxs-lookup"><span data-stu-id="0ee71-213">All</span></span> |
| <xref:System.Net.FileWebRequest.%23ctor(System.Runtime.Serialization.SerializationInfo,System.Runtime.Serialization.StreamingContext)> | <span data-ttu-id="0ee71-214">Все</span><span class="sxs-lookup"><span data-stu-id="0ee71-214">All</span></span> |
| <xref:System.Net.FileWebRequest.GetObjectData(System.Runtime.Serialization.SerializationInfo,System.Runtime.Serialization.StreamingContext)?displayProperty=nameWithType> | <span data-ttu-id="0ee71-215">Все</span><span class="sxs-lookup"><span data-stu-id="0ee71-215">All</span></span> |
| <xref:System.Net.FileWebResponse.%23ctor(System.Runtime.Serialization.SerializationInfo,System.Runtime.Serialization.StreamingContext)> | <span data-ttu-id="0ee71-216">Все</span><span class="sxs-lookup"><span data-stu-id="0ee71-216">All</span></span> |
| <xref:System.Net.FileWebResponse.GetObjectData(System.Runtime.Serialization.SerializationInfo,System.Runtime.Serialization.StreamingContext)?displayProperty=nameWithType> | <span data-ttu-id="0ee71-217">Все</span><span class="sxs-lookup"><span data-stu-id="0ee71-217">All</span></span> |
| <xref:System.Net.HttpWebRequest.%23ctor(System.Runtime.Serialization.SerializationInfo,System.Runtime.Serialization.StreamingContext)> | <span data-ttu-id="0ee71-218">Все</span><span class="sxs-lookup"><span data-stu-id="0ee71-218">All</span></span> |
| <xref:System.Net.HttpWebRequest.GetObjectData(System.Runtime.Serialization.SerializationInfo,System.Runtime.Serialization.StreamingContext)?displayProperty=nameWithType> | <span data-ttu-id="0ee71-219">Все</span><span class="sxs-lookup"><span data-stu-id="0ee71-219">All</span></span> |
| <xref:System.Net.HttpWebResponse.%23ctor(System.Runtime.Serialization.SerializationInfo,System.Runtime.Serialization.StreamingContext)> | <span data-ttu-id="0ee71-220">Все</span><span class="sxs-lookup"><span data-stu-id="0ee71-220">All</span></span> |
| <xref:System.Net.HttpWebResponse.GetObjectData(System.Runtime.Serialization.SerializationInfo,System.Runtime.Serialization.StreamingContext)?displayProperty=nameWithType> | <span data-ttu-id="0ee71-221">Все</span><span class="sxs-lookup"><span data-stu-id="0ee71-221">All</span></span> |
| <xref:System.Net.WebProxy.%23ctor(System.Runtime.Serialization.SerializationInfo,System.Runtime.Serialization.StreamingContext)> | <span data-ttu-id="0ee71-222">Все</span><span class="sxs-lookup"><span data-stu-id="0ee71-222">All</span></span> |
| <xref:System.Net.WebProxy.GetDefaultProxy?displayProperty=nameWithType> | <span data-ttu-id="0ee71-223">Все</span><span class="sxs-lookup"><span data-stu-id="0ee71-223">All</span></span> |
| <xref:System.Net.WebProxy.GetObjectData%2A?displayProperty=nameWithType> | <span data-ttu-id="0ee71-224">Все</span><span class="sxs-lookup"><span data-stu-id="0ee71-224">All</span></span> |
| <xref:System.Net.WebRequest.%23ctor(System.Runtime.Serialization.SerializationInfo,System.Runtime.Serialization.StreamingContext)> | <span data-ttu-id="0ee71-225">Все</span><span class="sxs-lookup"><span data-stu-id="0ee71-225">All</span></span> |
| <xref:System.Net.WebRequest.GetObjectData(System.Runtime.Serialization.SerializationInfo,System.Runtime.Serialization.StreamingContext)?displayProperty=nameWithType> | <span data-ttu-id="0ee71-226">Все</span><span class="sxs-lookup"><span data-stu-id="0ee71-226">All</span></span> |
| <xref:System.Net.WebResponse.%23ctor(System.Runtime.Serialization.SerializationInfo,System.Runtime.Serialization.StreamingContext)> | <span data-ttu-id="0ee71-227">Все</span><span class="sxs-lookup"><span data-stu-id="0ee71-227">All</span></span> |
| <xref:System.Net.WebResponse.GetObjectData(System.Runtime.Serialization.SerializationInfo,System.Runtime.Serialization.StreamingContext)?displayProperty=nameWithType> | <span data-ttu-id="0ee71-228">Все</span><span class="sxs-lookup"><span data-stu-id="0ee71-228">All</span></span> |

## <a name="systemnetnetworkinformation"></a><span data-ttu-id="0ee71-229">System.Net.NetworkInformation</span><span class="sxs-lookup"><span data-stu-id="0ee71-229">System.Net.NetworkInformation</span></span>

| <span data-ttu-id="0ee71-230">Участник</span><span class="sxs-lookup"><span data-stu-id="0ee71-230">Member</span></span> | <span data-ttu-id="0ee71-231">Платформы, которые вызывают исключение</span><span class="sxs-lookup"><span data-stu-id="0ee71-231">Platforms that throw</span></span> |
| - | - |
| <xref:System.Net.NetworkInformation.Ping.Send%2A?displayProperty=nameWithType> | <span data-ttu-id="0ee71-232">Windows (UWP)</span><span class="sxs-lookup"><span data-stu-id="0ee71-232">Windows (UWP)</span></span> |

## <a name="systemnetsockets"></a><span data-ttu-id="0ee71-233">System.Net.Sockets</span><span class="sxs-lookup"><span data-stu-id="0ee71-233">System.Net.Sockets</span></span>

| <span data-ttu-id="0ee71-234">Участник</span><span class="sxs-lookup"><span data-stu-id="0ee71-234">Member</span></span> | <span data-ttu-id="0ee71-235">Платформы, которые вызывают исключение</span><span class="sxs-lookup"><span data-stu-id="0ee71-235">Platforms that throw</span></span> |
| - | - |
| <xref:System.Net.Sockets.Socket.%23ctor(System.Net.Sockets.SocketInformation)> | <span data-ttu-id="0ee71-236">Все</span><span class="sxs-lookup"><span data-stu-id="0ee71-236">All</span></span> |
| <xref:System.Net.Sockets.Socket.DuplicateAndClose(System.Int32)?displayProperty=nameWithType> | <span data-ttu-id="0ee71-237">Все</span><span class="sxs-lookup"><span data-stu-id="0ee71-237">All</span></span> |

## <a name="systemnetwebsockets"></a><span data-ttu-id="0ee71-238">System.Net.WebSockets</span><span class="sxs-lookup"><span data-stu-id="0ee71-238">System.Net.WebSockets</span></span>

| <span data-ttu-id="0ee71-239">Участник</span><span class="sxs-lookup"><span data-stu-id="0ee71-239">Member</span></span> | <span data-ttu-id="0ee71-240">Платформы, которые вызывают исключение</span><span class="sxs-lookup"><span data-stu-id="0ee71-240">Platforms that throw</span></span> |
| - | - |
| <xref:System.Net.WebSockets.WebSocket.RegisterPrefixes?displayProperty=nameWithType> | <span data-ttu-id="0ee71-241">Все</span><span class="sxs-lookup"><span data-stu-id="0ee71-241">All</span></span> |

## <a name="systemreflection"></a><span data-ttu-id="0ee71-242">System.Reflection</span><span class="sxs-lookup"><span data-stu-id="0ee71-242">System.Reflection</span></span>

| <span data-ttu-id="0ee71-243">Участник</span><span class="sxs-lookup"><span data-stu-id="0ee71-243">Member</span></span> | <span data-ttu-id="0ee71-244">Платформы, которые вызывают исключение</span><span class="sxs-lookup"><span data-stu-id="0ee71-244">Platforms that throw</span></span> |
| - | - |
| <xref:System.Reflection.Assembly.ReflectionOnlyLoad%2A?displayProperty=nameWithType> | <span data-ttu-id="0ee71-245">Все</span><span class="sxs-lookup"><span data-stu-id="0ee71-245">All</span></span> |
| <xref:System.Reflection.Assembly.ReflectionOnlyLoadFrom(System.String)?displayProperty=nameWithType> | <span data-ttu-id="0ee71-246">Все</span><span class="sxs-lookup"><span data-stu-id="0ee71-246">All</span></span> |
| <xref:System.Reflection.AssemblyName.GetObjectData(System.Runtime.Serialization.SerializationInfo,System.Runtime.Serialization.StreamingContext)?displayProperty=nameWithType> | <span data-ttu-id="0ee71-247">Все</span><span class="sxs-lookup"><span data-stu-id="0ee71-247">All</span></span> |
| <xref:System.Reflection.AssemblyName.OnDeserialization(System.Object)?displayProperty=nameWithType> | <span data-ttu-id="0ee71-248">Все</span><span class="sxs-lookup"><span data-stu-id="0ee71-248">All</span></span> |
| <xref:System.Reflection.StrongNameKeyPair.%23ctor(System.String)> | <span data-ttu-id="0ee71-249">Все</span><span class="sxs-lookup"><span data-stu-id="0ee71-249">All</span></span> |
| <xref:System.Reflection.StrongNameKeyPair.%23ctor(System.Runtime.Serialization.SerializationInfo,System.Runtime.Serialization.StreamingContext)> | <span data-ttu-id="0ee71-250">Все</span><span class="sxs-lookup"><span data-stu-id="0ee71-250">All</span></span> |
| <xref:System.Reflection.StrongNameKeyPair.PublicKey?displayProperty=nameWithType> | <span data-ttu-id="0ee71-251">Все</span><span class="sxs-lookup"><span data-stu-id="0ee71-251">All</span></span> |

## <a name="systemruntimecompilerservices"></a><span data-ttu-id="0ee71-252">System.Runtime.CompilerServices</span><span class="sxs-lookup"><span data-stu-id="0ee71-252">System.Runtime.CompilerServices</span></span>

| <span data-ttu-id="0ee71-253">Участник</span><span class="sxs-lookup"><span data-stu-id="0ee71-253">Member</span></span> | <span data-ttu-id="0ee71-254">Платформы, которые вызывают исключение</span><span class="sxs-lookup"><span data-stu-id="0ee71-254">Platforms that throw</span></span> |
| - | - |
| <xref:System.Runtime.CompilerServices.DebugInfoGenerator.CreatePdbGenerator?displayProperty=nameWithType> | <span data-ttu-id="0ee71-255">Все</span><span class="sxs-lookup"><span data-stu-id="0ee71-255">All</span></span> |

## <a name="systemruntimeinteropservices"></a><span data-ttu-id="0ee71-256">System.Runtime.InteropServices</span><span class="sxs-lookup"><span data-stu-id="0ee71-256">System.Runtime.InteropServices</span></span>

| <span data-ttu-id="0ee71-257">Участник</span><span class="sxs-lookup"><span data-stu-id="0ee71-257">Member</span></span> | <span data-ttu-id="0ee71-258">Платформы, которые вызывают исключение</span><span class="sxs-lookup"><span data-stu-id="0ee71-258">Platforms that throw</span></span> |
| - | - |
| <xref:System.Runtime.InteropServices.Marshal.GetIDispatchForObject(System.Object)?displayProperty=nameWithType> | <span data-ttu-id="0ee71-259">Все</span><span class="sxs-lookup"><span data-stu-id="0ee71-259">All</span></span> |
| <xref:System.Runtime.InteropServices.RuntimeEnvironment.SystemConfigurationFile?displayProperty=nameWithType> | <span data-ttu-id="0ee71-260">Все</span><span class="sxs-lookup"><span data-stu-id="0ee71-260">All</span></span> |
| <xref:System.Runtime.InteropServices.RuntimeEnvironment.GetRuntimeInterfaceAsIntPtr(System.Guid,System.Guid)?displayProperty=nameWithType> | <span data-ttu-id="0ee71-261">Все</span><span class="sxs-lookup"><span data-stu-id="0ee71-261">All</span></span> |
| <xref:System.Runtime.InteropServices.RuntimeEnvironment.GetRuntimeInterfaceAsObject(System.Guid,System.Guid)?displayProperty=nameWithType> | <span data-ttu-id="0ee71-262">Все</span><span class="sxs-lookup"><span data-stu-id="0ee71-262">All</span></span> |
| <xref:System.Runtime.InteropServices.WindowsRuntime.WindowsRuntimeMarshal.StringToHString(System.String)?displayProperty=nameWithType> | <span data-ttu-id="0ee71-263">Linux и macOS</span><span class="sxs-lookup"><span data-stu-id="0ee71-263">Linux and macOS</span></span> |
| <xref:System.Runtime.InteropServices.WindowsRuntime.WindowsRuntimeMarshal.PtrToStringHString(System.IntPtr)?displayProperty=nameWithType> | <span data-ttu-id="0ee71-264">Linux и macOS</span><span class="sxs-lookup"><span data-stu-id="0ee71-264">Linux and macOS</span></span> |
| <xref:System.Runtime.InteropServices.WindowsRuntime.WindowsRuntimeMarshal.FreeHString(System.IntPtr)?displayProperty=nameWithType> | <span data-ttu-id="0ee71-265">Linux и macOS</span><span class="sxs-lookup"><span data-stu-id="0ee71-265">Linux and macOS</span></span> |

## <a name="systemruntimeserialization"></a><span data-ttu-id="0ee71-266">System.Runtime.Serialization</span><span class="sxs-lookup"><span data-stu-id="0ee71-266">System.Runtime.Serialization</span></span>

| <span data-ttu-id="0ee71-267">Участник</span><span class="sxs-lookup"><span data-stu-id="0ee71-267">Member</span></span> | <span data-ttu-id="0ee71-268">Платформы, которые вызывают исключение</span><span class="sxs-lookup"><span data-stu-id="0ee71-268">Platforms that throw</span></span> |
| - | - |
| <xref:System.Runtime.Serialization.XsdDataContractExporter.Schemas?displayProperty=nameWithType> | <span data-ttu-id="0ee71-269">Все</span><span class="sxs-lookup"><span data-stu-id="0ee71-269">All</span></span> |

## <a name="systemsecurity"></a><span data-ttu-id="0ee71-270">System.Security</span><span class="sxs-lookup"><span data-stu-id="0ee71-270">System.Security</span></span>

| <span data-ttu-id="0ee71-271">Участник</span><span class="sxs-lookup"><span data-stu-id="0ee71-271">Member</span></span> | <span data-ttu-id="0ee71-272">Платформы, которые вызывают исключение</span><span class="sxs-lookup"><span data-stu-id="0ee71-272">Platforms that throw</span></span> |
| - | - |
| <xref:System.Security.CodeAccessPermission.Deny?displayProperty=nameWithType> | <span data-ttu-id="0ee71-273">Все</span><span class="sxs-lookup"><span data-stu-id="0ee71-273">All</span></span> |
| <xref:System.Security.CodeAccessPermission.PermitOnly?displayProperty=nameWithType> | <span data-ttu-id="0ee71-274">Все</span><span class="sxs-lookup"><span data-stu-id="0ee71-274">All</span></span> |
| <xref:System.Security.PermissionSet.ConvertPermissionSet(System.String,System.Byte[],System.String)?displayProperty=nameWithType> | <span data-ttu-id="0ee71-275">Все</span><span class="sxs-lookup"><span data-stu-id="0ee71-275">All</span></span> |
| <xref:System.Security.PermissionSet.Deny?displayProperty=nameWithType> | <span data-ttu-id="0ee71-276">Все</span><span class="sxs-lookup"><span data-stu-id="0ee71-276">All</span></span> |
| <xref:System.Security.PermissionSet.PermitOnly?displayProperty=nameWithType> | <span data-ttu-id="0ee71-277">Все</span><span class="sxs-lookup"><span data-stu-id="0ee71-277">All</span></span> |
| <xref:System.Security.SecurityContext.Capture?displayProperty=nameWithType> | <span data-ttu-id="0ee71-278">Все</span><span class="sxs-lookup"><span data-stu-id="0ee71-278">All</span></span> |
| <xref:System.Security.SecurityContext.CreateCopy?displayProperty=nameWithType> | <span data-ttu-id="0ee71-279">Все</span><span class="sxs-lookup"><span data-stu-id="0ee71-279">All</span></span> |
| <xref:System.Security.SecurityContext.Dispose?displayProperty=nameWithType> | <span data-ttu-id="0ee71-280">Все</span><span class="sxs-lookup"><span data-stu-id="0ee71-280">All</span></span> |
| <xref:System.Security.SecurityContext.IsFlowSuppressed?displayProperty=nameWithType> | <span data-ttu-id="0ee71-281">Все</span><span class="sxs-lookup"><span data-stu-id="0ee71-281">All</span></span> |
| <xref:System.Security.SecurityContext.IsWindowsIdentityFlowSuppressed?displayProperty=nameWithType> | <span data-ttu-id="0ee71-282">Все</span><span class="sxs-lookup"><span data-stu-id="0ee71-282">All</span></span> |
| <xref:System.Security.SecurityContext.RestoreFlow?displayProperty=nameWithType> | <span data-ttu-id="0ee71-283">Все</span><span class="sxs-lookup"><span data-stu-id="0ee71-283">All</span></span> |
| <xref:System.Security.SecurityContext.Run(System.Security.SecurityContext,System.Threading.ContextCallback,System.Object)?displayProperty=nameWithType> | <span data-ttu-id="0ee71-284">Все</span><span class="sxs-lookup"><span data-stu-id="0ee71-284">All</span></span> |
| <xref:System.Security.SecurityContext.SuppressFlow?displayProperty=nameWithType> | <span data-ttu-id="0ee71-285">Все</span><span class="sxs-lookup"><span data-stu-id="0ee71-285">All</span></span> |
| <xref:System.Security.SecurityContext.SuppressFlowWindowsIdentity?displayProperty=nameWithType> | <span data-ttu-id="0ee71-286">Все</span><span class="sxs-lookup"><span data-stu-id="0ee71-286">All</span></span> |

## <a name="systemsecurityclaims"></a><span data-ttu-id="0ee71-287">System.Security.Claims</span><span class="sxs-lookup"><span data-stu-id="0ee71-287">System.Security.Claims</span></span>

| <span data-ttu-id="0ee71-288">Участник</span><span class="sxs-lookup"><span data-stu-id="0ee71-288">Member</span></span> | <span data-ttu-id="0ee71-289">Платформы, которые вызывают исключение</span><span class="sxs-lookup"><span data-stu-id="0ee71-289">Platforms that throw</span></span> |
| - | - |
| <xref:System.Security.Claims.ClaimsPrincipal.%23ctor(System.Runtime.Serialization.SerializationInfo,System.Runtime.Serialization.StreamingContext)> | <span data-ttu-id="0ee71-290">Все</span><span class="sxs-lookup"><span data-stu-id="0ee71-290">All</span></span> |
| <xref:System.Security.Claims.ClaimsPrincipal.GetObjectData(System.Runtime.Serialization.SerializationInfo,System.Runtime.Serialization.StreamingContext)?displayProperty=nameWithType> | <span data-ttu-id="0ee71-291">Все</span><span class="sxs-lookup"><span data-stu-id="0ee71-291">All</span></span> |
| <xref:System.Security.Claims.ClaimsIdentity.%23ctor(System.Runtime.Serialization.SerializationInfo)> | <span data-ttu-id="0ee71-292">Все</span><span class="sxs-lookup"><span data-stu-id="0ee71-292">All</span></span> |
| <xref:System.Security.Claims.ClaimsIdentity.%23ctor(System.Runtime.Serialization.SerializationInfo,System.Runtime.Serialization.StreamingContext)> | <span data-ttu-id="0ee71-293">Все</span><span class="sxs-lookup"><span data-stu-id="0ee71-293">All</span></span> |
| <xref:System.Security.Claims.ClaimsIdentity.GetObjectData(System.Runtime.Serialization.SerializationInfo,System.Runtime.Serialization.StreamingContext)?displayProperty=nameWithType> | <span data-ttu-id="0ee71-294">Все</span><span class="sxs-lookup"><span data-stu-id="0ee71-294">All</span></span> |

## <a name="systemsecuritycryptography"></a><span data-ttu-id="0ee71-295">System.Security.Cryptography</span><span class="sxs-lookup"><span data-stu-id="0ee71-295">System.Security.Cryptography</span></span>

| <span data-ttu-id="0ee71-296">Участник</span><span class="sxs-lookup"><span data-stu-id="0ee71-296">Member</span></span> | <span data-ttu-id="0ee71-297">Платформы, которые вызывают исключение</span><span class="sxs-lookup"><span data-stu-id="0ee71-297">Platforms that throw</span></span> |
| - | - |
| <xref:System.Security.Cryptography.AsymmetricAlgorithm.Create(System.String)?displayProperty=nameWithType> | <span data-ttu-id="0ee71-298">Все</span><span class="sxs-lookup"><span data-stu-id="0ee71-298">All</span></span> |
| <xref:System.Security.Cryptography.CspKeyContainerInfo.%23ctor%2A> | <span data-ttu-id="0ee71-299">Linux и macOS</span><span class="sxs-lookup"><span data-stu-id="0ee71-299">Linux and macOS</span></span> |
| <xref:System.Security.Cryptography.CspKeyContainerInfo.Accessible?displayProperty=nameWithType> | <span data-ttu-id="0ee71-300">Linux и macOS</span><span class="sxs-lookup"><span data-stu-id="0ee71-300">Linux and macOS</span></span> |
| <xref:System.Security.Cryptography.CspKeyContainerInfo.Exportable?displayProperty=nameWithType> | <span data-ttu-id="0ee71-301">Linux и macOS</span><span class="sxs-lookup"><span data-stu-id="0ee71-301">Linux and macOS</span></span> |
| <xref:System.Security.Cryptography.CspKeyContainerInfo.HardwareDevice?displayProperty=nameWithType> | <span data-ttu-id="0ee71-302">Linux и macOS</span><span class="sxs-lookup"><span data-stu-id="0ee71-302">Linux and macOS</span></span> |
| <xref:System.Security.Cryptography.CspKeyContainerInfo.KeyContainerName?displayProperty=nameWithType> | <span data-ttu-id="0ee71-303">Linux и macOS</span><span class="sxs-lookup"><span data-stu-id="0ee71-303">Linux and macOS</span></span> |
| <xref:System.Security.Cryptography.CspKeyContainerInfo.KeyNumber?displayProperty=nameWithType> | <span data-ttu-id="0ee71-304">Linux и macOS</span><span class="sxs-lookup"><span data-stu-id="0ee71-304">Linux and macOS</span></span> |
| <xref:System.Security.Cryptography.CspKeyContainerInfo.MachineKeyStore?displayProperty=nameWithType> | <span data-ttu-id="0ee71-305">Linux и macOS</span><span class="sxs-lookup"><span data-stu-id="0ee71-305">Linux and macOS</span></span> |
| <xref:System.Security.Cryptography.CspKeyContainerInfo.Protected?displayProperty=nameWithType> | <span data-ttu-id="0ee71-306">Linux и macOS</span><span class="sxs-lookup"><span data-stu-id="0ee71-306">Linux and macOS</span></span> |
| <xref:System.Security.Cryptography.CspKeyContainerInfo.ProviderName?displayProperty=nameWithType> | <span data-ttu-id="0ee71-307">Linux и macOS</span><span class="sxs-lookup"><span data-stu-id="0ee71-307">Linux and macOS</span></span> |
| <xref:System.Security.Cryptography.CspKeyContainerInfo.ProviderType?displayProperty=nameWithType> | <span data-ttu-id="0ee71-308">Linux и macOS</span><span class="sxs-lookup"><span data-stu-id="0ee71-308">Linux and macOS</span></span> |
| <xref:System.Security.Cryptography.CspKeyContainerInfo.RandomlyGenerated?displayProperty=nameWithType> | <span data-ttu-id="0ee71-309">Linux и macOS</span><span class="sxs-lookup"><span data-stu-id="0ee71-309">Linux and macOS</span></span> |
| <xref:System.Security.Cryptography.CspKeyContainerInfo.Removable?displayProperty=nameWithType> | <span data-ttu-id="0ee71-310">Linux и macOS</span><span class="sxs-lookup"><span data-stu-id="0ee71-310">Linux and macOS</span></span> |
| <xref:System.Security.Cryptography.CspKeyContainerInfo.UniqueKeyContainerName?displayProperty=nameWithType> | <span data-ttu-id="0ee71-311">Linux и macOS</span><span class="sxs-lookup"><span data-stu-id="0ee71-311">Linux and macOS</span></span> |
| <xref:System.Security.Cryptography.HashAlgorithm.Create?displayProperty=nameWithType> | <span data-ttu-id="0ee71-312">Все</span><span class="sxs-lookup"><span data-stu-id="0ee71-312">All</span></span> |
| <xref:System.Security.Cryptography.HMAC.Create?displayProperty=nameWithType> | <span data-ttu-id="0ee71-313">Все</span><span class="sxs-lookup"><span data-stu-id="0ee71-313">All</span></span> |
| <xref:System.Security.Cryptography.HMAC.Create(System.String)?displayProperty=nameWithType> | <span data-ttu-id="0ee71-314">Все</span><span class="sxs-lookup"><span data-stu-id="0ee71-314">All</span></span> |
| <xref:System.Security.Cryptography.HMAC.HashCore%2A?displayProperty=nameWithType> | <span data-ttu-id="0ee71-315">Все</span><span class="sxs-lookup"><span data-stu-id="0ee71-315">All</span></span> |
| <xref:System.Security.Cryptography.HMAC.HashFinal%2A?displayProperty=nameWithType> | <span data-ttu-id="0ee71-316">Все</span><span class="sxs-lookup"><span data-stu-id="0ee71-316">All</span></span> |
| <xref:System.Security.Cryptography.HMAC.Initialize%2A?displayProperty=nameWithType> | <span data-ttu-id="0ee71-317">Все</span><span class="sxs-lookup"><span data-stu-id="0ee71-317">All</span></span> |
| <xref:System.Security.Cryptography.KeyedHashAlgorithm.Create?displayProperty=nameWithType> | <span data-ttu-id="0ee71-318">Все</span><span class="sxs-lookup"><span data-stu-id="0ee71-318">All</span></span> |
| <xref:System.Security.Cryptography.KeyedHashAlgorithm.Create(System.String)?displayProperty=nameWithType> | <span data-ttu-id="0ee71-319">Все</span><span class="sxs-lookup"><span data-stu-id="0ee71-319">All</span></span> |
| <xref:System.Security.Cryptography.ProtectedData.Protect%2A?displayProperty=nameWithType> | <span data-ttu-id="0ee71-320">Linux и macOS</span><span class="sxs-lookup"><span data-stu-id="0ee71-320">Linux and macOS</span></span> |
| <xref:System.Security.Cryptography.ProtectedData.Unprotect%2A?displayProperty=nameWithType> | <span data-ttu-id="0ee71-321">Linux и macOS</span><span class="sxs-lookup"><span data-stu-id="0ee71-321">Linux and macOS</span></span> |
| <xref:System.Security.Cryptography.RSA.FromXmlString%2A?displayProperty=nameWithType> | <span data-ttu-id="0ee71-322">Все</span><span class="sxs-lookup"><span data-stu-id="0ee71-322">All</span></span> |
| <xref:System.Security.Cryptography.RSA.ToXmlString%2A?displayProperty=nameWithType> | <span data-ttu-id="0ee71-323">Все</span><span class="sxs-lookup"><span data-stu-id="0ee71-323">All</span></span> |
| <xref:System.Security.Cryptography.SymmetricAlgorithm.Create?displayProperty=nameWithType> | <span data-ttu-id="0ee71-324">Все</span><span class="sxs-lookup"><span data-stu-id="0ee71-324">All</span></span> |
| <xref:System.Security.Cryptography.SymmetricAlgorithm.Create(System.String)?displayProperty=nameWithType> | <span data-ttu-id="0ee71-325">Все</span><span class="sxs-lookup"><span data-stu-id="0ee71-325">All</span></span> |

## <a name="systemsecuritycryptographypkcs"></a><span data-ttu-id="0ee71-326">System.Security.Cryptography.Pkcs</span><span class="sxs-lookup"><span data-stu-id="0ee71-326">System.Security.Cryptography.Pkcs</span></span>

| <span data-ttu-id="0ee71-327">Участник</span><span class="sxs-lookup"><span data-stu-id="0ee71-327">Member</span></span> | <span data-ttu-id="0ee71-328">Платформы, которые вызывают исключение</span><span class="sxs-lookup"><span data-stu-id="0ee71-328">Platforms that throw</span></span> |
| - | - |
| <xref:System.Security.Cryptography.Pkcs.CmsSigner.%23ctor(System.Security.Cryptography.CspParameters)> | <span data-ttu-id="0ee71-329">Все</span><span class="sxs-lookup"><span data-stu-id="0ee71-329">All</span></span> |
| <xref:System.Security.Cryptography.Pkcs.SignerInfo.ComputeCounterSignature?displayProperty=nameWithType> | <span data-ttu-id="0ee71-330">Все</span><span class="sxs-lookup"><span data-stu-id="0ee71-330">All</span></span> |

## <a name="systemsecuritycryptographyx509certificates"></a><span data-ttu-id="0ee71-331">System.Security.Cryptography.X509Certificates</span><span class="sxs-lookup"><span data-stu-id="0ee71-331">System.Security.Cryptography.X509Certificates</span></span>

| <span data-ttu-id="0ee71-332">Участник</span><span class="sxs-lookup"><span data-stu-id="0ee71-332">Member</span></span> | <span data-ttu-id="0ee71-333">Платформы, которые вызывают исключение</span><span class="sxs-lookup"><span data-stu-id="0ee71-333">Platforms that throw</span></span> |
| - | - |
| <xref:System.Security.Cryptography.X509Certificates.X509Certificate.%23ctor(System.Runtime.Serialization.SerializationInfo,System.Runtime.Serialization.StreamingContext)> | <span data-ttu-id="0ee71-334">All</span><span class="sxs-lookup"><span data-stu-id="0ee71-334">All</span></span> |
| <xref:System.Security.Cryptography.X509Certificates.X509Certificate.Import%2A?displayProperty=nameWithType> | <span data-ttu-id="0ee71-335">Все</span><span class="sxs-lookup"><span data-stu-id="0ee71-335">All</span></span> |
| <xref:System.Security.Cryptography.X509Certificates.X509Certificate2.%23ctor(System.Runtime.Serialization.SerializationInfo,System.Runtime.Serialization.StreamingContext)> | <span data-ttu-id="0ee71-336">Все</span><span class="sxs-lookup"><span data-stu-id="0ee71-336">All</span></span> |
| <span data-ttu-id="0ee71-337"><xref:System.Security.Cryptography.X509Certificates.X509Certificate2.PrivateKey?displayProperty=nameWithType> (только установка)</span><span class="sxs-lookup"><span data-stu-id="0ee71-337"><xref:System.Security.Cryptography.X509Certificates.X509Certificate2.PrivateKey?displayProperty=nameWithType> (set only)</span></span> | <span data-ttu-id="0ee71-338">Все</span><span class="sxs-lookup"><span data-stu-id="0ee71-338">All</span></span> |

## <a name="systemsecurityauthenticationextendedprotection"></a><span data-ttu-id="0ee71-339">System.Security.Authentication.ExtendedProtection</span><span class="sxs-lookup"><span data-stu-id="0ee71-339">System.Security.Authentication.ExtendedProtection</span></span>

| <span data-ttu-id="0ee71-340">Участник</span><span class="sxs-lookup"><span data-stu-id="0ee71-340">Member</span></span> | <span data-ttu-id="0ee71-341">Платформы, которые вызывают исключение</span><span class="sxs-lookup"><span data-stu-id="0ee71-341">Platforms that throw</span></span> |
| - | - |
| <xref:System.Security.Authentication.ExtendedProtection.ExtendedProtectionPolicy.%23ctor(System.Runtime.Serialization.SerializationInfo,System.Runtime.Serialization.StreamingContext)> | <span data-ttu-id="0ee71-342">Все</span><span class="sxs-lookup"><span data-stu-id="0ee71-342">All</span></span> |

## <a name="systemsecuritypolicy"></a><span data-ttu-id="0ee71-343">System.Security.Policy</span><span class="sxs-lookup"><span data-stu-id="0ee71-343">System.Security.Policy</span></span>

| <span data-ttu-id="0ee71-344">Участник</span><span class="sxs-lookup"><span data-stu-id="0ee71-344">Member</span></span> | <span data-ttu-id="0ee71-345">Платформы, которые вызывают исключение</span><span class="sxs-lookup"><span data-stu-id="0ee71-345">Platforms that throw</span></span> |
| - | - |
| <xref:System.Security.Policy.Hash.GetObjectData(System.Runtime.Serialization.SerializationInfo,System.Runtime.Serialization.StreamingContext)?displayProperty=nameWithType> | <span data-ttu-id="0ee71-346">Все</span><span class="sxs-lookup"><span data-stu-id="0ee71-346">All</span></span> |

## <a name="systemserviceprocessservicecontroller"></a><span data-ttu-id="0ee71-347">System.ServiceProcess.ServiceController</span><span class="sxs-lookup"><span data-stu-id="0ee71-347">System.ServiceProcess.ServiceController</span></span>

| <span data-ttu-id="0ee71-348">Участник</span><span class="sxs-lookup"><span data-stu-id="0ee71-348">Member</span></span> | <span data-ttu-id="0ee71-349">Платформы, которые вызывают исключение</span><span class="sxs-lookup"><span data-stu-id="0ee71-349">Platforms that throw</span></span> |
| - | - |
| <xref:System.ServiceProcess.TimeoutException.%23ctor(System.Runtime.Serialization.SerializationInfo,System.Runtime.Serialization.StreamingContext)> | <span data-ttu-id="0ee71-350">Все</span><span class="sxs-lookup"><span data-stu-id="0ee71-350">All</span></span> |

## <a name="systemtextregularexpressions"></a><span data-ttu-id="0ee71-351">System.Text.RegularExpressions</span><span class="sxs-lookup"><span data-stu-id="0ee71-351">System.Text.RegularExpressions</span></span>

| <span data-ttu-id="0ee71-352">Участник</span><span class="sxs-lookup"><span data-stu-id="0ee71-352">Member</span></span> | <span data-ttu-id="0ee71-353">Платформы, которые вызывают исключение</span><span class="sxs-lookup"><span data-stu-id="0ee71-353">Platforms that throw</span></span> |
| - | - |
| <xref:System.Text.RegularExpressions.Regex.CompileToAssembly%2A?displayProperty=nameWithType> | <span data-ttu-id="0ee71-354">Все</span><span class="sxs-lookup"><span data-stu-id="0ee71-354">All</span></span> |

## <a name="systemthreading"></a><span data-ttu-id="0ee71-355">System.Threading</span><span class="sxs-lookup"><span data-stu-id="0ee71-355">System.Threading</span></span>

| <span data-ttu-id="0ee71-356">Участник</span><span class="sxs-lookup"><span data-stu-id="0ee71-356">Member</span></span> | <span data-ttu-id="0ee71-357">Платформы, которые вызывают исключение</span><span class="sxs-lookup"><span data-stu-id="0ee71-357">Platforms that throw</span></span> |
| - | - |
| <xref:System.Threading.CompressedStack.GetObjectData(System.Runtime.Serialization.SerializationInfo,System.Runtime.Serialization.StreamingContext)?displayProperty=nameWithType> | <span data-ttu-id="0ee71-358">All</span><span class="sxs-lookup"><span data-stu-id="0ee71-358">All</span></span> |
| <xref:System.Threading.ExecutionContext.GetObjectData(System.Runtime.Serialization.SerializationInfo,System.Runtime.Serialization.StreamingContext)?displayProperty=nameWithType> | <span data-ttu-id="0ee71-359">Все</span><span class="sxs-lookup"><span data-stu-id="0ee71-359">All</span></span> |
| <xref:System.Threading.Thread.Abort%2A?displayProperty=nameWithType> | <span data-ttu-id="0ee71-360">Все</span><span class="sxs-lookup"><span data-stu-id="0ee71-360">All</span></span> |
| <xref:System.Threading.Thread.ResetAbort?displayProperty=nameWithType> | <span data-ttu-id="0ee71-361">Все</span><span class="sxs-lookup"><span data-stu-id="0ee71-361">All</span></span> |
| <xref:System.Threading.Thread.Resume?displayProperty=nameWithType> | <span data-ttu-id="0ee71-362">Все</span><span class="sxs-lookup"><span data-stu-id="0ee71-362">All</span></span> |
| <xref:System.Threading.Thread.Suspend?displayProperty=nameWithType> | <span data-ttu-id="0ee71-363">Все</span><span class="sxs-lookup"><span data-stu-id="0ee71-363">All</span></span> |

## <a name="systemxml"></a><span data-ttu-id="0ee71-364">System.Xml</span><span class="sxs-lookup"><span data-stu-id="0ee71-364">System.Xml</span></span>

| <span data-ttu-id="0ee71-365">Участник</span><span class="sxs-lookup"><span data-stu-id="0ee71-365">Member</span></span> | <span data-ttu-id="0ee71-366">Платформы, которые вызывают исключение</span><span class="sxs-lookup"><span data-stu-id="0ee71-366">Platforms that throw</span></span> |
| - | - |
| <xref:System.Xml.XmlDictionaryReader.CreateMtomReader(System.Byte[],System.Int32,System.Int32,System.Text.Encoding[],System.String,System.Xml.XmlDictionaryReaderQuotas,System.Int32,System.Xml.OnXmlDictionaryReaderClose)?displayProperty=nameWithType> | <span data-ttu-id="0ee71-367">All</span><span class="sxs-lookup"><span data-stu-id="0ee71-367">All</span></span> |
| <xref:System.Xml.XmlDictionaryReader.CreateMtomReader(System.IO.Stream,System.Text.Encoding[],System.String,System.Xml.XmlDictionaryReaderQuotas,System.Int32,System.Xml.OnXmlDictionaryReaderClose)?displayProperty=nameWithType> | <span data-ttu-id="0ee71-368">Все</span><span class="sxs-lookup"><span data-stu-id="0ee71-368">All</span></span> |
| <xref:System.Xml.XmlDictionaryWriter.CreateMtomWriter(System.IO.Stream,System.Text.Encoding,System.Int32,System.String,System.String,System.String,System.Boolean,System.Boolean)?displayProperty=nameWithType> | <span data-ttu-id="0ee71-369">Все</span><span class="sxs-lookup"><span data-stu-id="0ee71-369">All</span></span> |

## <a name="see-also"></a><span data-ttu-id="0ee71-370">См. также</span><span class="sxs-lookup"><span data-stu-id="0ee71-370">See also</span></span>

- [<span data-ttu-id="0ee71-371">Критические изменения для миграции с .NET Framework на .NET Core</span><span class="sxs-lookup"><span data-stu-id="0ee71-371">Breaking changes for migration from .NET Framework to .NET Core</span></span>](fx-core.md)
- [<span data-ttu-id="0ee71-372">Двоичная сериализация в .NET Core</span><span class="sxs-lookup"><span data-stu-id="0ee71-372">Binary serialization in .NET Core</span></span>](../../standard/serialization/binary-serialization.md#net-core)
- [<span data-ttu-id="0ee71-373">Анализатор переносимости .NET</span><span class="sxs-lookup"><span data-stu-id="0ee71-373">.NET portability analyzer</span></span>](../../standard/analyzers/portability-analyzer.md)
