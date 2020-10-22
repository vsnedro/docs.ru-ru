---
title: Неподдерживаемые API в .NET Core и .NET версии 5 и более поздних
titleSuffix: ''
description: Узнайте, какие интерфейсы API .NET всегда вызывают исключение в .NET Core и .NET 5.0 и более поздних версиях.
ms.date: 10/13/2020
ms.openlocfilehash: 0164ebff51de82d548a02f9fde754c1052a9c2b5
ms.sourcegitcommit: ff5a4eb5cffbcac9521bc44a907a118cd7e8638d
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/17/2020
ms.locfileid: "92159343"
---
# <a name="apis-that-always-throw-exceptions-on-net-core-and-net-5"></a><span data-ttu-id="248c3-103">API, которые всегда создают исключения в .NET Core и .NET версии 5 и более поздних</span><span class="sxs-lookup"><span data-stu-id="248c3-103">APIs that always throw exceptions on .NET Core and .NET 5+</span></span>

<span data-ttu-id="248c3-104">Следующие API всегда будут вызывать исключение <xref:System.PlatformNotSupportedException> в .NET версии 5.0 и более поздних (включая все версии .NET Core) на всех платформах или на их подмножестве.</span><span class="sxs-lookup"><span data-stu-id="248c3-104">The following APIs will always throw a <xref:System.PlatformNotSupportedException> on .NET 5.0 and later versions (including all versions of .NET Core) on all or a subset of platforms.</span></span>

<span data-ttu-id="248c3-105">В этой статье затронутые API упорядочиваются по пространствам имен.</span><span class="sxs-lookup"><span data-stu-id="248c3-105">This article organizes the affected APIs by namespace.</span></span>

> [!NOTE]
>
> - <span data-ttu-id="248c3-106">Эта статья все еще находится в процессе написания.</span><span class="sxs-lookup"><span data-stu-id="248c3-106">This article is a work-in-progress.</span></span> <span data-ttu-id="248c3-107">Это не полный список API-интерфейсов, создающих исключения в .NET версии 5 и более поздних.</span><span class="sxs-lookup"><span data-stu-id="248c3-107">It is not a complete list of APIs that throw exceptions on .NET 5+.</span></span>
> - <span data-ttu-id="248c3-108">В этой статье не рассматриваются явные реализации интерфейса для двоичной сериализации, которые вызываются в .NET версии 5 и более поздних.</span><span class="sxs-lookup"><span data-stu-id="248c3-108">This article does not include the explicit interface implementations for binary serialization that throw on .NET 5+.</span></span> <span data-ttu-id="248c3-109">Дополнительные сведения см. в разделе [Двоичная сериализация в .NET Core](../../standard/serialization/binary-serialization.md#net-core).</span><span class="sxs-lookup"><span data-stu-id="248c3-109">For more information, see [Binary serialization in .NET Core](../../standard/serialization/binary-serialization.md#net-core).</span></span>

## <a name="system"></a><span data-ttu-id="248c3-110">Система</span><span class="sxs-lookup"><span data-stu-id="248c3-110">System</span></span>

| <span data-ttu-id="248c3-111">Участник</span><span class="sxs-lookup"><span data-stu-id="248c3-111">Member</span></span> | <span data-ttu-id="248c3-112">Платформы, которые вызывают исключение</span><span class="sxs-lookup"><span data-stu-id="248c3-112">Platforms that throw</span></span> |
| - | - |
| <xref:System.AppDomain.CreateDomain%2A?displayProperty=nameWithType> | <span data-ttu-id="248c3-113">Все</span><span class="sxs-lookup"><span data-stu-id="248c3-113">All</span></span> |
| <xref:System.AppDomain.ExecuteAssembly(System.String,System.String[],System.Byte[],System.Configuration.Assemblies.AssemblyHashAlgorithm)?displayProperty=nameWithType> | <span data-ttu-id="248c3-114">Все</span><span class="sxs-lookup"><span data-stu-id="248c3-114">All</span></span> |
| <xref:System.Console.CapsLock?displayProperty=nameWithType> | <span data-ttu-id="248c3-115">Linux и macOS</span><span class="sxs-lookup"><span data-stu-id="248c3-115">Linux and macOS</span></span> |
| <xref:System.Console.NumberLock?displayProperty=nameWithType> | <span data-ttu-id="248c3-116">Linux и macOS</span><span class="sxs-lookup"><span data-stu-id="248c3-116">Linux and macOS</span></span> |
| <xref:System.Delegate.GetObjectData(System.Runtime.Serialization.SerializationInfo,System.Runtime.Serialization.StreamingContext)?displayProperty=nameWithType> | <span data-ttu-id="248c3-117">Все</span><span class="sxs-lookup"><span data-stu-id="248c3-117">All</span></span> |
| <xref:System.Exception.SerializeObjectState?displayProperty=nameWithType> | <span data-ttu-id="248c3-118">Все</span><span class="sxs-lookup"><span data-stu-id="248c3-118">All</span></span> |
| <xref:System.MarshalByRefObject.GetLifetimeService?displayProperty=nameWithType> | <span data-ttu-id="248c3-119">Все</span><span class="sxs-lookup"><span data-stu-id="248c3-119">All</span></span> |
| <xref:System.MarshalByRefObject.InitializeLifetimeService?displayProperty=nameWithType> | <span data-ttu-id="248c3-120">Все</span><span class="sxs-lookup"><span data-stu-id="248c3-120">All</span></span> |
| <xref:System.OperatingSystem.GetObjectData(System.Runtime.Serialization.SerializationInfo,System.Runtime.Serialization.StreamingContext)?displayProperty=nameWithType> | <span data-ttu-id="248c3-121">Все</span><span class="sxs-lookup"><span data-stu-id="248c3-121">All</span></span> |
| <xref:System.Type.ReflectionOnlyGetType(System.String,System.Boolean,System.Boolean)?displayProperty=nameWithType> | <span data-ttu-id="248c3-122">Все</span><span class="sxs-lookup"><span data-stu-id="248c3-122">All</span></span> |

## <a name="systemcodedomcompiler"></a><span data-ttu-id="248c3-123">System.CodeDom.Compiler</span><span class="sxs-lookup"><span data-stu-id="248c3-123">System.CodeDom.Compiler</span></span>

| <span data-ttu-id="248c3-124">Участник</span><span class="sxs-lookup"><span data-stu-id="248c3-124">Member</span></span> | <span data-ttu-id="248c3-125">Платформы, которые вызывают исключение</span><span class="sxs-lookup"><span data-stu-id="248c3-125">Platforms that throw</span></span> |
| - | - |
| <xref:System.CodeDom.Compiler.CodeDomProvider.CompileAssemblyFromDom%2A?displayProperty=nameWithType> | <span data-ttu-id="248c3-126">Все</span><span class="sxs-lookup"><span data-stu-id="248c3-126">All</span></span> |
| <xref:System.CodeDom.Compiler.CodeDomProvider.CompileAssemblyFromFile%2A?displayProperty=nameWithType> | <span data-ttu-id="248c3-127">Все</span><span class="sxs-lookup"><span data-stu-id="248c3-127">All</span></span> |
| <xref:System.CodeDom.Compiler.CodeDomProvider.CompileAssemblyFromSource%2A?displayProperty=nameWithType> | <span data-ttu-id="248c3-128">Все</span><span class="sxs-lookup"><span data-stu-id="248c3-128">All</span></span> |

## <a name="systemcollectionsspecialized"></a><span data-ttu-id="248c3-129">System.Collections.Specialized</span><span class="sxs-lookup"><span data-stu-id="248c3-129">System.Collections.Specialized</span></span>

| <span data-ttu-id="248c3-130">Участник</span><span class="sxs-lookup"><span data-stu-id="248c3-130">Member</span></span> | <span data-ttu-id="248c3-131">Платформы, которые вызывают исключение</span><span class="sxs-lookup"><span data-stu-id="248c3-131">Platforms that throw</span></span> |
| - | - |
| <xref:System.Collections.Specialized.NameObjectCollectionBase.%23ctor(System.Runtime.Serialization.SerializationInfo,System.Runtime.Serialization.StreamingContext)> | <span data-ttu-id="248c3-132">Все</span><span class="sxs-lookup"><span data-stu-id="248c3-132">All</span></span> |
| <xref:System.Collections.Specialized.NameObjectCollectionBase.GetObjectData(System.Runtime.Serialization.SerializationInfo,System.Runtime.Serialization.StreamingContext)?displayProperty=nameWithType> | <span data-ttu-id="248c3-133">Все</span><span class="sxs-lookup"><span data-stu-id="248c3-133">All</span></span> |
| <xref:System.Collections.Specialized.NameObjectCollectionBase.OnDeserialization(System.Object)?displayProperty=nameWithType> | <span data-ttu-id="248c3-134">Все</span><span class="sxs-lookup"><span data-stu-id="248c3-134">All</span></span> |

## <a name="systemconfiguration"></a><span data-ttu-id="248c3-135">System.Configuration</span><span class="sxs-lookup"><span data-stu-id="248c3-135">System.Configuration</span></span>

| <span data-ttu-id="248c3-136">Участник</span><span class="sxs-lookup"><span data-stu-id="248c3-136">Member</span></span> | <span data-ttu-id="248c3-137">Платформы, которые вызывают исключение</span><span class="sxs-lookup"><span data-stu-id="248c3-137">Platforms that throw</span></span> |
| - | - |
| <span data-ttu-id="248c3-138"><xref:System.Configuration.RsaProtectedConfigurationProvider?displayProperty=nameWithType> (все члены)</span><span class="sxs-lookup"><span data-stu-id="248c3-138"><xref:System.Configuration.RsaProtectedConfigurationProvider?displayProperty=nameWithType> (all members)</span></span> | <span data-ttu-id="248c3-139">Все</span><span class="sxs-lookup"><span data-stu-id="248c3-139">All</span></span> |

## <a name="systemconsole"></a><span data-ttu-id="248c3-140">System.Console</span><span class="sxs-lookup"><span data-stu-id="248c3-140">System.Console</span></span>

| <span data-ttu-id="248c3-141">Участник</span><span class="sxs-lookup"><span data-stu-id="248c3-141">Member</span></span> | <span data-ttu-id="248c3-142">Платформы, которые вызывают исключение</span><span class="sxs-lookup"><span data-stu-id="248c3-142">Platforms that throw</span></span> |
| - | - |
| <xref:System.Console.Beep?displayProperty=nameWithType> | <span data-ttu-id="248c3-143">Linux и macOS</span><span class="sxs-lookup"><span data-stu-id="248c3-143">Linux and macOS</span></span> |
| <span data-ttu-id="248c3-144"><xref:System.Console.BufferHeight?displayProperty=nameWithType> (только установка)</span><span class="sxs-lookup"><span data-stu-id="248c3-144"><xref:System.Console.BufferHeight?displayProperty=nameWithType> (set only)</span></span> | <span data-ttu-id="248c3-145">Linux и macOS</span><span class="sxs-lookup"><span data-stu-id="248c3-145">Linux and macOS</span></span> |
| <span data-ttu-id="248c3-146"><xref:System.Console.BufferWidth?displayProperty=nameWithType> (только установка)</span><span class="sxs-lookup"><span data-stu-id="248c3-146"><xref:System.Console.BufferWidth?displayProperty=nameWithType> (set only)</span></span> | <span data-ttu-id="248c3-147">Linux и macOS</span><span class="sxs-lookup"><span data-stu-id="248c3-147">Linux and macOS</span></span> |
| <span data-ttu-id="248c3-148"><xref:System.Console.CursorSize?displayProperty=nameWithType> (только установка)</span><span class="sxs-lookup"><span data-stu-id="248c3-148"><xref:System.Console.CursorSize?displayProperty=nameWithType> (set only)</span></span> | <span data-ttu-id="248c3-149">Linux и macOS</span><span class="sxs-lookup"><span data-stu-id="248c3-149">Linux and macOS</span></span> |
| <span data-ttu-id="248c3-150"><xref:System.Console.CursorVisible?displayProperty=nameWithType> (только получение)</span><span class="sxs-lookup"><span data-stu-id="248c3-150"><xref:System.Console.CursorVisible?displayProperty=nameWithType> (get only)</span></span> | <span data-ttu-id="248c3-151">Linux и macOS</span><span class="sxs-lookup"><span data-stu-id="248c3-151">Linux and macOS</span></span> |
| <xref:System.Console.MoveBufferArea%2A?displayProperty=nameWithType> | <span data-ttu-id="248c3-152">Linux и macOS</span><span class="sxs-lookup"><span data-stu-id="248c3-152">Linux and macOS</span></span> |
| <xref:System.Console.SetWindowPosition%2A?displayProperty=nameWithType> | <span data-ttu-id="248c3-153">Linux и macOS</span><span class="sxs-lookup"><span data-stu-id="248c3-153">Linux and macOS</span></span> |
| <xref:System.Console.SetWindowSize%2A?displayProperty=nameWithType> | <span data-ttu-id="248c3-154">Linux и macOS</span><span class="sxs-lookup"><span data-stu-id="248c3-154">Linux and macOS</span></span> |
| <span data-ttu-id="248c3-155"><xref:System.Console.Title?displayProperty=nameWithType> (только получение)</span><span class="sxs-lookup"><span data-stu-id="248c3-155"><xref:System.Console.Title?displayProperty=nameWithType> (get only)</span></span> | <span data-ttu-id="248c3-156">Linux и macOS</span><span class="sxs-lookup"><span data-stu-id="248c3-156">Linux and macOS</span></span> |
| <span data-ttu-id="248c3-157"><xref:System.Console.WindowHeight?displayProperty=nameWithType> (только установка)</span><span class="sxs-lookup"><span data-stu-id="248c3-157"><xref:System.Console.WindowHeight?displayProperty=nameWithType> (set only)</span></span> | <span data-ttu-id="248c3-158">Linux и macOS</span><span class="sxs-lookup"><span data-stu-id="248c3-158">Linux and macOS</span></span> |
| <span data-ttu-id="248c3-159"><xref:System.Console.WindowLeft?displayProperty=nameWithType> (только установка)</span><span class="sxs-lookup"><span data-stu-id="248c3-159"><xref:System.Console.WindowLeft?displayProperty=nameWithType> (set only)</span></span> | <span data-ttu-id="248c3-160">Linux и macOS</span><span class="sxs-lookup"><span data-stu-id="248c3-160">Linux and macOS</span></span> |
| <span data-ttu-id="248c3-161"><xref:System.Console.WindowTop?displayProperty=nameWithType> (только установка)</span><span class="sxs-lookup"><span data-stu-id="248c3-161"><xref:System.Console.WindowTop?displayProperty=nameWithType> (set only)</span></span> | <span data-ttu-id="248c3-162">Linux и macOS</span><span class="sxs-lookup"><span data-stu-id="248c3-162">Linux and macOS</span></span> |
| <span data-ttu-id="248c3-163"><xref:System.Console.WindowWidth?displayProperty=nameWithType> (только установка)</span><span class="sxs-lookup"><span data-stu-id="248c3-163"><xref:System.Console.WindowWidth?displayProperty=nameWithType> (set only)</span></span> | <span data-ttu-id="248c3-164">Linux и macOS</span><span class="sxs-lookup"><span data-stu-id="248c3-164">Linux and macOS</span></span> |

## <a name="systemdatacommon"></a><span data-ttu-id="248c3-165">System.Data.Common</span><span class="sxs-lookup"><span data-stu-id="248c3-165">System.Data.Common</span></span>

| <span data-ttu-id="248c3-166">Участник</span><span class="sxs-lookup"><span data-stu-id="248c3-166">Member</span></span> | <span data-ttu-id="248c3-167">Платформы, которые вызывают исключение</span><span class="sxs-lookup"><span data-stu-id="248c3-167">Platforms that throw</span></span> |
| - | - |
| <span data-ttu-id="248c3-168"><xref:System.Data.Common.DbDataReader.GetSchemaTable%2A?displayProperty=nameWithType> (вызывает <xref:System.NotSupportedException>)</span><span class="sxs-lookup"><span data-stu-id="248c3-168"><xref:System.Data.Common.DbDataReader.GetSchemaTable%2A?displayProperty=nameWithType> (throws <xref:System.NotSupportedException>)</span></span> | <span data-ttu-id="248c3-169">Все</span><span class="sxs-lookup"><span data-stu-id="248c3-169">All</span></span> |

## <a name="systemdiagnosticsprocess"></a><span data-ttu-id="248c3-170">System.Diagnostics.Process</span><span class="sxs-lookup"><span data-stu-id="248c3-170">System.Diagnostics.Process</span></span>

| <span data-ttu-id="248c3-171">Участник</span><span class="sxs-lookup"><span data-stu-id="248c3-171">Member</span></span> | <span data-ttu-id="248c3-172">Платформы, которые вызывают исключение</span><span class="sxs-lookup"><span data-stu-id="248c3-172">Platforms that throw</span></span> |
| - | - |
| <span data-ttu-id="248c3-173"><xref:System.Diagnostics.Process.MaxWorkingSet?displayProperty=nameWithType> (только установка)</span><span class="sxs-lookup"><span data-stu-id="248c3-173"><xref:System.Diagnostics.Process.MaxWorkingSet?displayProperty=nameWithType> (set only)</span></span> | <span data-ttu-id="248c3-174">Linux</span><span class="sxs-lookup"><span data-stu-id="248c3-174">Linux</span></span> |
| <span data-ttu-id="248c3-175"><xref:System.Diagnostics.Process.MinWorkingSet?displayProperty=nameWithType> (только установка)</span><span class="sxs-lookup"><span data-stu-id="248c3-175"><xref:System.Diagnostics.Process.MinWorkingSet?displayProperty=nameWithType> (set only)</span></span> | <span data-ttu-id="248c3-176">Linux</span><span class="sxs-lookup"><span data-stu-id="248c3-176">Linux</span></span> |
| <xref:System.Diagnostics.Process.ProcessorAffinity?displayProperty=nameWithType> | <span data-ttu-id="248c3-177">macOS</span><span class="sxs-lookup"><span data-stu-id="248c3-177">macOS</span></span> |
| <xref:System.Diagnostics.Process.MainWindowHandle?displayProperty=nameWithType> | <span data-ttu-id="248c3-178">Linux и macOS</span><span class="sxs-lookup"><span data-stu-id="248c3-178">Linux and macOS</span></span> |
| <xref:System.Diagnostics.Process.Start%2A?displayProperty=nameWithType> | <span data-ttu-id="248c3-179">Linux и macOS</span><span class="sxs-lookup"><span data-stu-id="248c3-179">Linux and macOS</span></span> |
| <xref:System.Diagnostics.ProcessStartInfo.UserName?displayProperty=nameWithType> | <span data-ttu-id="248c3-180">Linux и macOS</span><span class="sxs-lookup"><span data-stu-id="248c3-180">Linux and macOS</span></span> |
| <xref:System.Diagnostics.ProcessStartInfo.PasswordInClearText?displayProperty=nameWithType> | <span data-ttu-id="248c3-181">Linux и macOS</span><span class="sxs-lookup"><span data-stu-id="248c3-181">Linux and macOS</span></span> |
| <xref:System.Diagnostics.ProcessStartInfo.Domain?displayProperty=nameWithType> | <span data-ttu-id="248c3-182">Linux и macOS</span><span class="sxs-lookup"><span data-stu-id="248c3-182">Linux and macOS</span></span> |
| <xref:System.Diagnostics.ProcessStartInfo.LoadUserProfile?displayProperty=nameWithType> | <span data-ttu-id="248c3-183">Linux и macOS</span><span class="sxs-lookup"><span data-stu-id="248c3-183">Linux and macOS</span></span> |
| <span data-ttu-id="248c3-184"><xref:System.Diagnostics.ProcessThread.BasePriority?displayProperty=nameWithType> (только установка)</span><span class="sxs-lookup"><span data-stu-id="248c3-184"><xref:System.Diagnostics.ProcessThread.BasePriority?displayProperty=nameWithType> (set only)</span></span> | <span data-ttu-id="248c3-185">Linux и macOS</span><span class="sxs-lookup"><span data-stu-id="248c3-185">Linux and macOS</span></span> |
| <span data-ttu-id="248c3-186"><xref:System.Diagnostics.ProcessThread.BasePriority?displayProperty=nameWithType> (только получение)</span><span class="sxs-lookup"><span data-stu-id="248c3-186"><xref:System.Diagnostics.ProcessThread.BasePriority?displayProperty=nameWithType> (get only)</span></span> | <span data-ttu-id="248c3-187">macOS</span><span class="sxs-lookup"><span data-stu-id="248c3-187">macOS</span></span> |
| <span data-ttu-id="248c3-188"><xref:System.Diagnostics.ProcessThread.ProcessorAffinity?displayProperty=nameWithType> (только установка)</span><span class="sxs-lookup"><span data-stu-id="248c3-188"><xref:System.Diagnostics.ProcessThread.ProcessorAffinity?displayProperty=nameWithType> (set only)</span></span> | <span data-ttu-id="248c3-189">Linux и macOS</span><span class="sxs-lookup"><span data-stu-id="248c3-189">Linux and macOS</span></span> |

## <a name="systemio"></a><span data-ttu-id="248c3-190">System.IO</span><span class="sxs-lookup"><span data-stu-id="248c3-190">System.IO</span></span>

| <span data-ttu-id="248c3-191">Участник</span><span class="sxs-lookup"><span data-stu-id="248c3-191">Member</span></span> | <span data-ttu-id="248c3-192">Платформы, которые вызывают исключение</span><span class="sxs-lookup"><span data-stu-id="248c3-192">Platforms that throw</span></span> |
| - | - |
| <xref:System.IO.FileSystemInfo.%23ctor(System.Runtime.Serialization.SerializationInfo,System.Runtime.Serialization.StreamingContext)> | <span data-ttu-id="248c3-193">Все</span><span class="sxs-lookup"><span data-stu-id="248c3-193">All</span></span> |
| <xref:System.IO.FileSystemInfo.GetObjectData(System.Runtime.Serialization.SerializationInfo,System.Runtime.Serialization.StreamingContext)?displayProperty=nameWithType> | <span data-ttu-id="248c3-194">Все</span><span class="sxs-lookup"><span data-stu-id="248c3-194">All</span></span> |

## <a name="systemiopipes"></a><span data-ttu-id="248c3-195">System.IO.Pipes</span><span class="sxs-lookup"><span data-stu-id="248c3-195">System.IO.Pipes</span></span>

| <span data-ttu-id="248c3-196">Участник</span><span class="sxs-lookup"><span data-stu-id="248c3-196">Member</span></span> | <span data-ttu-id="248c3-197">Платформы, которые вызывают исключение</span><span class="sxs-lookup"><span data-stu-id="248c3-197">Platforms that throw</span></span> |
| - | - |
| <xref:System.IO.Pipes.NamedPipeClientStream.NumberOfServerInstances?displayProperty=nameWithType> | <span data-ttu-id="248c3-198">Linux и macOS</span><span class="sxs-lookup"><span data-stu-id="248c3-198">Linux and macOS</span></span> |
| <xref:System.IO.Pipes.NamedPipeServerStream.GetImpersonationUserName?displayProperty=nameWithType> | <span data-ttu-id="248c3-199">Linux и macOS</span><span class="sxs-lookup"><span data-stu-id="248c3-199">Linux and macOS</span></span> |
| <xref:System.IO.Pipes.PipeStream.InBufferSize?displayProperty=nameWithType> | <span data-ttu-id="248c3-200">Linux и macOS</span><span class="sxs-lookup"><span data-stu-id="248c3-200">Linux and macOS</span></span> |
| <xref:System.IO.Pipes.PipeStream.OutBufferSize?displayProperty=nameWithType> | <span data-ttu-id="248c3-201">Linux и macOS</span><span class="sxs-lookup"><span data-stu-id="248c3-201">Linux and macOS</span></span> |
| <span data-ttu-id="248c3-202"><xref:System.IO.Pipes.PipeStream.ReadMode?displayProperty=nameWithType> (только установка)</span><span class="sxs-lookup"><span data-stu-id="248c3-202"><xref:System.IO.Pipes.PipeStream.ReadMode?displayProperty=nameWithType> (set only)</span></span> | <span data-ttu-id="248c3-203">Linux и macOS</span><span class="sxs-lookup"><span data-stu-id="248c3-203">Linux and macOS</span></span> |
| <xref:System.IO.Pipes.PipeStream.WaitForPipeDrain?displayProperty=nameWithType> | <span data-ttu-id="248c3-204">Linux и macOS</span><span class="sxs-lookup"><span data-stu-id="248c3-204">Linux and macOS</span></span> |

## <a name="systemmedia"></a><span data-ttu-id="248c3-205">System.Media</span><span class="sxs-lookup"><span data-stu-id="248c3-205">System.Media</span></span>

| <span data-ttu-id="248c3-206">Участник</span><span class="sxs-lookup"><span data-stu-id="248c3-206">Member</span></span> | <span data-ttu-id="248c3-207">Платформы, которые вызывают исключение</span><span class="sxs-lookup"><span data-stu-id="248c3-207">Platforms that throw</span></span> |
| - | - |
| <xref:System.Media.SoundPlayer.%23ctor(System.Runtime.Serialization.SerializationInfo,System.Runtime.Serialization.StreamingContext)> | <span data-ttu-id="248c3-208">Все</span><span class="sxs-lookup"><span data-stu-id="248c3-208">All</span></span> |

## <a name="systemnet"></a><span data-ttu-id="248c3-209">System.Net</span><span class="sxs-lookup"><span data-stu-id="248c3-209">System.Net</span></span>

| <span data-ttu-id="248c3-210">Участник</span><span class="sxs-lookup"><span data-stu-id="248c3-210">Member</span></span> | <span data-ttu-id="248c3-211">Платформы, которые вызывают исключение</span><span class="sxs-lookup"><span data-stu-id="248c3-211">Platforms that throw</span></span> |
| - | - |
| <xref:System.Net.AuthenticationManager.Authenticate(System.String,System.Net.WebRequest,System.Net.ICredentials)?displayProperty=nameWithType> | <span data-ttu-id="248c3-212">Все</span><span class="sxs-lookup"><span data-stu-id="248c3-212">All</span></span> |
| <xref:System.Net.AuthenticationManager.PreAuthenticate(System.Net.WebRequest,System.Net.ICredentials)?displayProperty=nameWithType> | <span data-ttu-id="248c3-213">Все</span><span class="sxs-lookup"><span data-stu-id="248c3-213">All</span></span> |
| <xref:System.Net.FileWebRequest.%23ctor(System.Runtime.Serialization.SerializationInfo,System.Runtime.Serialization.StreamingContext)> | <span data-ttu-id="248c3-214">Все</span><span class="sxs-lookup"><span data-stu-id="248c3-214">All</span></span> |
| <xref:System.Net.FileWebRequest.GetObjectData(System.Runtime.Serialization.SerializationInfo,System.Runtime.Serialization.StreamingContext)?displayProperty=nameWithType> | <span data-ttu-id="248c3-215">Все</span><span class="sxs-lookup"><span data-stu-id="248c3-215">All</span></span> |
| <xref:System.Net.FileWebResponse.%23ctor(System.Runtime.Serialization.SerializationInfo,System.Runtime.Serialization.StreamingContext)> | <span data-ttu-id="248c3-216">Все</span><span class="sxs-lookup"><span data-stu-id="248c3-216">All</span></span> |
| <xref:System.Net.FileWebResponse.GetObjectData(System.Runtime.Serialization.SerializationInfo,System.Runtime.Serialization.StreamingContext)?displayProperty=nameWithType> | <span data-ttu-id="248c3-217">Все</span><span class="sxs-lookup"><span data-stu-id="248c3-217">All</span></span> |
| <xref:System.Net.HttpWebRequest.%23ctor(System.Runtime.Serialization.SerializationInfo,System.Runtime.Serialization.StreamingContext)> | <span data-ttu-id="248c3-218">Все</span><span class="sxs-lookup"><span data-stu-id="248c3-218">All</span></span> |
| <xref:System.Net.HttpWebRequest.GetObjectData(System.Runtime.Serialization.SerializationInfo,System.Runtime.Serialization.StreamingContext)?displayProperty=nameWithType> | <span data-ttu-id="248c3-219">Все</span><span class="sxs-lookup"><span data-stu-id="248c3-219">All</span></span> |
| <xref:System.Net.HttpWebResponse.%23ctor(System.Runtime.Serialization.SerializationInfo,System.Runtime.Serialization.StreamingContext)> | <span data-ttu-id="248c3-220">Все</span><span class="sxs-lookup"><span data-stu-id="248c3-220">All</span></span> |
| <xref:System.Net.HttpWebResponse.GetObjectData(System.Runtime.Serialization.SerializationInfo,System.Runtime.Serialization.StreamingContext)?displayProperty=nameWithType> | <span data-ttu-id="248c3-221">Все</span><span class="sxs-lookup"><span data-stu-id="248c3-221">All</span></span> |
| <xref:System.Net.WebProxy.%23ctor(System.Runtime.Serialization.SerializationInfo,System.Runtime.Serialization.StreamingContext)> | <span data-ttu-id="248c3-222">Все</span><span class="sxs-lookup"><span data-stu-id="248c3-222">All</span></span> |
| <xref:System.Net.WebProxy.GetDefaultProxy?displayProperty=nameWithType> | <span data-ttu-id="248c3-223">Все</span><span class="sxs-lookup"><span data-stu-id="248c3-223">All</span></span> |
| <xref:System.Net.WebProxy.GetObjectData%2A?displayProperty=nameWithType> | <span data-ttu-id="248c3-224">Все</span><span class="sxs-lookup"><span data-stu-id="248c3-224">All</span></span> |
| <xref:System.Net.WebRequest.%23ctor(System.Runtime.Serialization.SerializationInfo,System.Runtime.Serialization.StreamingContext)> | <span data-ttu-id="248c3-225">Все</span><span class="sxs-lookup"><span data-stu-id="248c3-225">All</span></span> |
| <xref:System.Net.WebRequest.GetObjectData(System.Runtime.Serialization.SerializationInfo,System.Runtime.Serialization.StreamingContext)?displayProperty=nameWithType> | <span data-ttu-id="248c3-226">Все</span><span class="sxs-lookup"><span data-stu-id="248c3-226">All</span></span> |
| <xref:System.Net.WebResponse.%23ctor(System.Runtime.Serialization.SerializationInfo,System.Runtime.Serialization.StreamingContext)> | <span data-ttu-id="248c3-227">Все</span><span class="sxs-lookup"><span data-stu-id="248c3-227">All</span></span> |
| <xref:System.Net.WebResponse.GetObjectData(System.Runtime.Serialization.SerializationInfo,System.Runtime.Serialization.StreamingContext)?displayProperty=nameWithType> | <span data-ttu-id="248c3-228">Все</span><span class="sxs-lookup"><span data-stu-id="248c3-228">All</span></span> |

## <a name="systemnetnetworkinformation"></a><span data-ttu-id="248c3-229">System.Net.NetworkInformation</span><span class="sxs-lookup"><span data-stu-id="248c3-229">System.Net.NetworkInformation</span></span>

| <span data-ttu-id="248c3-230">Участник</span><span class="sxs-lookup"><span data-stu-id="248c3-230">Member</span></span> | <span data-ttu-id="248c3-231">Платформы, которые вызывают исключение</span><span class="sxs-lookup"><span data-stu-id="248c3-231">Platforms that throw</span></span> |
| - | - |
| <xref:System.Net.NetworkInformation.Ping.Send%2A?displayProperty=nameWithType> | <span data-ttu-id="248c3-232">Windows (UWP)</span><span class="sxs-lookup"><span data-stu-id="248c3-232">Windows (UWP)</span></span> |

## <a name="systemnetsockets"></a><span data-ttu-id="248c3-233">System.Net.Sockets</span><span class="sxs-lookup"><span data-stu-id="248c3-233">System.Net.Sockets</span></span>

| <span data-ttu-id="248c3-234">Участник</span><span class="sxs-lookup"><span data-stu-id="248c3-234">Member</span></span> | <span data-ttu-id="248c3-235">Платформы, которые вызывают исключение</span><span class="sxs-lookup"><span data-stu-id="248c3-235">Platforms that throw</span></span> |
| - | - |
| <xref:System.Net.Sockets.Socket.%23ctor(System.Net.Sockets.SocketInformation)> | <span data-ttu-id="248c3-236">Все</span><span class="sxs-lookup"><span data-stu-id="248c3-236">All</span></span> |
| <xref:System.Net.Sockets.Socket.DuplicateAndClose(System.Int32)?displayProperty=nameWithType> | <span data-ttu-id="248c3-237">Все</span><span class="sxs-lookup"><span data-stu-id="248c3-237">All</span></span> |

## <a name="systemnetwebsockets"></a><span data-ttu-id="248c3-238">System.Net.WebSockets</span><span class="sxs-lookup"><span data-stu-id="248c3-238">System.Net.WebSockets</span></span>

| <span data-ttu-id="248c3-239">Участник</span><span class="sxs-lookup"><span data-stu-id="248c3-239">Member</span></span> | <span data-ttu-id="248c3-240">Платформы, которые вызывают исключение</span><span class="sxs-lookup"><span data-stu-id="248c3-240">Platforms that throw</span></span> |
| - | - |
| <xref:System.Net.WebSockets.WebSocket.RegisterPrefixes?displayProperty=nameWithType> | <span data-ttu-id="248c3-241">Все</span><span class="sxs-lookup"><span data-stu-id="248c3-241">All</span></span> |

## <a name="systemreflection"></a><span data-ttu-id="248c3-242">System.Reflection</span><span class="sxs-lookup"><span data-stu-id="248c3-242">System.Reflection</span></span>

| <span data-ttu-id="248c3-243">Участник</span><span class="sxs-lookup"><span data-stu-id="248c3-243">Member</span></span> | <span data-ttu-id="248c3-244">Платформы, которые вызывают исключение</span><span class="sxs-lookup"><span data-stu-id="248c3-244">Platforms that throw</span></span> |
| - | - |
| <xref:System.Reflection.Assembly.ReflectionOnlyLoad%2A?displayProperty=nameWithType> | <span data-ttu-id="248c3-245">Все</span><span class="sxs-lookup"><span data-stu-id="248c3-245">All</span></span> |
| <xref:System.Reflection.Assembly.ReflectionOnlyLoadFrom(System.String)?displayProperty=nameWithType> | <span data-ttu-id="248c3-246">Все</span><span class="sxs-lookup"><span data-stu-id="248c3-246">All</span></span> |
| <xref:System.Reflection.AssemblyName.GetObjectData(System.Runtime.Serialization.SerializationInfo,System.Runtime.Serialization.StreamingContext)?displayProperty=nameWithType> | <span data-ttu-id="248c3-247">Все</span><span class="sxs-lookup"><span data-stu-id="248c3-247">All</span></span> |
| <xref:System.Reflection.AssemblyName.OnDeserialization(System.Object)?displayProperty=nameWithType> | <span data-ttu-id="248c3-248">Все</span><span class="sxs-lookup"><span data-stu-id="248c3-248">All</span></span> |
| <xref:System.Reflection.StrongNameKeyPair.%23ctor(System.String)> | <span data-ttu-id="248c3-249">Все</span><span class="sxs-lookup"><span data-stu-id="248c3-249">All</span></span> |
| <xref:System.Reflection.StrongNameKeyPair.%23ctor(System.Runtime.Serialization.SerializationInfo,System.Runtime.Serialization.StreamingContext)> | <span data-ttu-id="248c3-250">Все</span><span class="sxs-lookup"><span data-stu-id="248c3-250">All</span></span> |
| <xref:System.Reflection.StrongNameKeyPair.PublicKey?displayProperty=nameWithType> | <span data-ttu-id="248c3-251">Все</span><span class="sxs-lookup"><span data-stu-id="248c3-251">All</span></span> |

## <a name="systemruntimecompilerservices"></a><span data-ttu-id="248c3-252">System.Runtime.CompilerServices</span><span class="sxs-lookup"><span data-stu-id="248c3-252">System.Runtime.CompilerServices</span></span>

| <span data-ttu-id="248c3-253">Участник</span><span class="sxs-lookup"><span data-stu-id="248c3-253">Member</span></span> | <span data-ttu-id="248c3-254">Платформы, которые вызывают исключение</span><span class="sxs-lookup"><span data-stu-id="248c3-254">Platforms that throw</span></span> |
| - | - |
| <xref:System.Runtime.CompilerServices.DebugInfoGenerator.CreatePdbGenerator?displayProperty=nameWithType> | <span data-ttu-id="248c3-255">Все</span><span class="sxs-lookup"><span data-stu-id="248c3-255">All</span></span> |

## <a name="systemruntimeinteropservices"></a><span data-ttu-id="248c3-256">System.Runtime.InteropServices</span><span class="sxs-lookup"><span data-stu-id="248c3-256">System.Runtime.InteropServices</span></span>

| <span data-ttu-id="248c3-257">Участник</span><span class="sxs-lookup"><span data-stu-id="248c3-257">Member</span></span> | <span data-ttu-id="248c3-258">Платформы, которые вызывают исключение</span><span class="sxs-lookup"><span data-stu-id="248c3-258">Platforms that throw</span></span> |
| - | - |
| <xref:System.Runtime.InteropServices.Marshal.GetIDispatchForObject(System.Object)?displayProperty=nameWithType> | <span data-ttu-id="248c3-259">Все</span><span class="sxs-lookup"><span data-stu-id="248c3-259">All</span></span> |
| <xref:System.Runtime.InteropServices.RuntimeEnvironment.SystemConfigurationFile?displayProperty=nameWithType> | <span data-ttu-id="248c3-260">Все</span><span class="sxs-lookup"><span data-stu-id="248c3-260">All</span></span> |
| <xref:System.Runtime.InteropServices.RuntimeEnvironment.GetRuntimeInterfaceAsIntPtr(System.Guid,System.Guid)?displayProperty=nameWithType> | <span data-ttu-id="248c3-261">Все</span><span class="sxs-lookup"><span data-stu-id="248c3-261">All</span></span> |
| <xref:System.Runtime.InteropServices.RuntimeEnvironment.GetRuntimeInterfaceAsObject(System.Guid,System.Guid)?displayProperty=nameWithType> | <span data-ttu-id="248c3-262">Все</span><span class="sxs-lookup"><span data-stu-id="248c3-262">All</span></span> |
| <xref:System.Runtime.InteropServices.WindowsRuntime.WindowsRuntimeMarshal.StringToHString(System.String)?displayProperty=nameWithType> | <span data-ttu-id="248c3-263">Linux и macOS</span><span class="sxs-lookup"><span data-stu-id="248c3-263">Linux and macOS</span></span> |
| <xref:System.Runtime.InteropServices.WindowsRuntime.WindowsRuntimeMarshal.PtrToStringHString(System.IntPtr)?displayProperty=nameWithType> | <span data-ttu-id="248c3-264">Linux и macOS</span><span class="sxs-lookup"><span data-stu-id="248c3-264">Linux and macOS</span></span> |
| <xref:System.Runtime.InteropServices.WindowsRuntime.WindowsRuntimeMarshal.FreeHString(System.IntPtr)?displayProperty=nameWithType> | <span data-ttu-id="248c3-265">Linux и macOS</span><span class="sxs-lookup"><span data-stu-id="248c3-265">Linux and macOS</span></span> |

## <a name="systemruntimeserialization"></a><span data-ttu-id="248c3-266">System.Runtime.Serialization</span><span class="sxs-lookup"><span data-stu-id="248c3-266">System.Runtime.Serialization</span></span>

| <span data-ttu-id="248c3-267">Участник</span><span class="sxs-lookup"><span data-stu-id="248c3-267">Member</span></span> | <span data-ttu-id="248c3-268">Платформы, которые вызывают исключение</span><span class="sxs-lookup"><span data-stu-id="248c3-268">Platforms that throw</span></span> |
| - | - |
| <xref:System.Runtime.Serialization.XsdDataContractExporter.Schemas?displayProperty=nameWithType> | <span data-ttu-id="248c3-269">Все</span><span class="sxs-lookup"><span data-stu-id="248c3-269">All</span></span> |

## <a name="systemsecurity"></a><span data-ttu-id="248c3-270">System.Security</span><span class="sxs-lookup"><span data-stu-id="248c3-270">System.Security</span></span>

| <span data-ttu-id="248c3-271">Участник</span><span class="sxs-lookup"><span data-stu-id="248c3-271">Member</span></span> | <span data-ttu-id="248c3-272">Платформы, которые вызывают исключение</span><span class="sxs-lookup"><span data-stu-id="248c3-272">Platforms that throw</span></span> |
| - | - |
| <xref:System.Security.CodeAccessPermission.Deny?displayProperty=nameWithType> | <span data-ttu-id="248c3-273">Все</span><span class="sxs-lookup"><span data-stu-id="248c3-273">All</span></span> |
| <xref:System.Security.CodeAccessPermission.PermitOnly?displayProperty=nameWithType> | <span data-ttu-id="248c3-274">Все</span><span class="sxs-lookup"><span data-stu-id="248c3-274">All</span></span> |
| <xref:System.Security.PermissionSet.ConvertPermissionSet(System.String,System.Byte[],System.String)?displayProperty=nameWithType> | <span data-ttu-id="248c3-275">Все</span><span class="sxs-lookup"><span data-stu-id="248c3-275">All</span></span> |
| <xref:System.Security.PermissionSet.Deny?displayProperty=nameWithType> | <span data-ttu-id="248c3-276">Все</span><span class="sxs-lookup"><span data-stu-id="248c3-276">All</span></span> |
| <xref:System.Security.PermissionSet.PermitOnly?displayProperty=nameWithType> | <span data-ttu-id="248c3-277">Все</span><span class="sxs-lookup"><span data-stu-id="248c3-277">All</span></span> |
| <xref:System.Security.SecurityContext.Capture?displayProperty=nameWithType> | <span data-ttu-id="248c3-278">Все</span><span class="sxs-lookup"><span data-stu-id="248c3-278">All</span></span> |
| <xref:System.Security.SecurityContext.CreateCopy?displayProperty=nameWithType> | <span data-ttu-id="248c3-279">Все</span><span class="sxs-lookup"><span data-stu-id="248c3-279">All</span></span> |
| <xref:System.Security.SecurityContext.Dispose?displayProperty=nameWithType> | <span data-ttu-id="248c3-280">Все</span><span class="sxs-lookup"><span data-stu-id="248c3-280">All</span></span> |
| <xref:System.Security.SecurityContext.IsFlowSuppressed?displayProperty=nameWithType> | <span data-ttu-id="248c3-281">Все</span><span class="sxs-lookup"><span data-stu-id="248c3-281">All</span></span> |
| <xref:System.Security.SecurityContext.IsWindowsIdentityFlowSuppressed?displayProperty=nameWithType> | <span data-ttu-id="248c3-282">Все</span><span class="sxs-lookup"><span data-stu-id="248c3-282">All</span></span> |
| <xref:System.Security.SecurityContext.RestoreFlow?displayProperty=nameWithType> | <span data-ttu-id="248c3-283">Все</span><span class="sxs-lookup"><span data-stu-id="248c3-283">All</span></span> |
| <xref:System.Security.SecurityContext.Run(System.Security.SecurityContext,System.Threading.ContextCallback,System.Object)?displayProperty=nameWithType> | <span data-ttu-id="248c3-284">Все</span><span class="sxs-lookup"><span data-stu-id="248c3-284">All</span></span> |
| <xref:System.Security.SecurityContext.SuppressFlow?displayProperty=nameWithType> | <span data-ttu-id="248c3-285">Все</span><span class="sxs-lookup"><span data-stu-id="248c3-285">All</span></span> |
| <xref:System.Security.SecurityContext.SuppressFlowWindowsIdentity?displayProperty=nameWithType> | <span data-ttu-id="248c3-286">Все</span><span class="sxs-lookup"><span data-stu-id="248c3-286">All</span></span> |

## <a name="systemsecurityclaims"></a><span data-ttu-id="248c3-287">System.Security.Claims</span><span class="sxs-lookup"><span data-stu-id="248c3-287">System.Security.Claims</span></span>

| <span data-ttu-id="248c3-288">Участник</span><span class="sxs-lookup"><span data-stu-id="248c3-288">Member</span></span> | <span data-ttu-id="248c3-289">Платформы, которые вызывают исключение</span><span class="sxs-lookup"><span data-stu-id="248c3-289">Platforms that throw</span></span> |
| - | - |
| <xref:System.Security.Claims.ClaimsPrincipal.%23ctor> | <span data-ttu-id="248c3-290">Все</span><span class="sxs-lookup"><span data-stu-id="248c3-290">All</span></span> |
| <xref:System.Security.Claims.ClaimsPrincipal.GetObjectData(System.Runtime.Serialization.SerializationInfo,System.Runtime.Serialization.StreamingContext)?displayProperty=nameWithType> | <span data-ttu-id="248c3-291">Все</span><span class="sxs-lookup"><span data-stu-id="248c3-291">All</span></span> |
| <xref:System.Security.Claims.ClaimsIdentity.%23ctor(System.Runtime.Serialization.SerializationInfo)> | <span data-ttu-id="248c3-292">Все</span><span class="sxs-lookup"><span data-stu-id="248c3-292">All</span></span> |
| <xref:System.Security.Claims.ClaimsIdentity.%23ctor(System.Runtime.Serialization.SerializationInfo,System.Runtime.Serialization.StreamingContext)> | <span data-ttu-id="248c3-293">Все</span><span class="sxs-lookup"><span data-stu-id="248c3-293">All</span></span> |
| <xref:System.Security.Claims.ClaimsIdentity.GetObjectData(System.Runtime.Serialization.SerializationInfo,System.Runtime.Serialization.StreamingContext)?displayProperty=nameWithType> | <span data-ttu-id="248c3-294">Все</span><span class="sxs-lookup"><span data-stu-id="248c3-294">All</span></span> |

## <a name="systemsecuritycryptography"></a><span data-ttu-id="248c3-295">System.Security.Cryptography</span><span class="sxs-lookup"><span data-stu-id="248c3-295">System.Security.Cryptography</span></span>

| <span data-ttu-id="248c3-296">Участник</span><span class="sxs-lookup"><span data-stu-id="248c3-296">Member</span></span> | <span data-ttu-id="248c3-297">Платформы, которые вызывают исключение</span><span class="sxs-lookup"><span data-stu-id="248c3-297">Platforms that throw</span></span> |
| - | - |
| <xref:System.Security.Cryptography.AsymmetricAlgorithm.Create(System.String)?displayProperty=nameWithType> | <span data-ttu-id="248c3-298">Все</span><span class="sxs-lookup"><span data-stu-id="248c3-298">All</span></span> |
| <xref:System.Security.Cryptography.CspKeyContainerInfo.%23ctor%2A> | <span data-ttu-id="248c3-299">Linux и macOS</span><span class="sxs-lookup"><span data-stu-id="248c3-299">Linux and macOS</span></span> |
| <xref:System.Security.Cryptography.CspKeyContainerInfo.Accessible?displayProperty=nameWithType> | <span data-ttu-id="248c3-300">Linux и macOS</span><span class="sxs-lookup"><span data-stu-id="248c3-300">Linux and macOS</span></span> |
| <xref:System.Security.Cryptography.CspKeyContainerInfo.Exportable?displayProperty=nameWithType> | <span data-ttu-id="248c3-301">Linux и macOS</span><span class="sxs-lookup"><span data-stu-id="248c3-301">Linux and macOS</span></span> |
| <xref:System.Security.Cryptography.CspKeyContainerInfo.HardwareDevice?displayProperty=nameWithType> | <span data-ttu-id="248c3-302">Linux и macOS</span><span class="sxs-lookup"><span data-stu-id="248c3-302">Linux and macOS</span></span> |
| <xref:System.Security.Cryptography.CspKeyContainerInfo.KeyContainerName?displayProperty=nameWithType> | <span data-ttu-id="248c3-303">Linux и macOS</span><span class="sxs-lookup"><span data-stu-id="248c3-303">Linux and macOS</span></span> |
| <xref:System.Security.Cryptography.CspKeyContainerInfo.KeyNumber?displayProperty=nameWithType> | <span data-ttu-id="248c3-304">Linux и macOS</span><span class="sxs-lookup"><span data-stu-id="248c3-304">Linux and macOS</span></span> |
| <xref:System.Security.Cryptography.CspKeyContainerInfo.MachineKeyStore?displayProperty=nameWithType> | <span data-ttu-id="248c3-305">Linux и macOS</span><span class="sxs-lookup"><span data-stu-id="248c3-305">Linux and macOS</span></span> |
| <xref:System.Security.Cryptography.CspKeyContainerInfo.Protected?displayProperty=nameWithType> | <span data-ttu-id="248c3-306">Linux и macOS</span><span class="sxs-lookup"><span data-stu-id="248c3-306">Linux and macOS</span></span> |
| <xref:System.Security.Cryptography.CspKeyContainerInfo.ProviderName?displayProperty=nameWithType> | <span data-ttu-id="248c3-307">Linux и macOS</span><span class="sxs-lookup"><span data-stu-id="248c3-307">Linux and macOS</span></span> |
| <xref:System.Security.Cryptography.CspKeyContainerInfo.ProviderType?displayProperty=nameWithType> | <span data-ttu-id="248c3-308">Linux и macOS</span><span class="sxs-lookup"><span data-stu-id="248c3-308">Linux and macOS</span></span> |
| <xref:System.Security.Cryptography.CspKeyContainerInfo.RandomlyGenerated?displayProperty=nameWithType> | <span data-ttu-id="248c3-309">Linux и macOS</span><span class="sxs-lookup"><span data-stu-id="248c3-309">Linux and macOS</span></span> |
| <xref:System.Security.Cryptography.CspKeyContainerInfo.Removable?displayProperty=nameWithType> | <span data-ttu-id="248c3-310">Linux и macOS</span><span class="sxs-lookup"><span data-stu-id="248c3-310">Linux and macOS</span></span> |
| <xref:System.Security.Cryptography.CspKeyContainerInfo.UniqueKeyContainerName?displayProperty=nameWithType> | <span data-ttu-id="248c3-311">Linux и macOS</span><span class="sxs-lookup"><span data-stu-id="248c3-311">Linux and macOS</span></span> |
| <xref:System.Security.Cryptography.HashAlgorithm.Create?displayProperty=nameWithType> | <span data-ttu-id="248c3-312">Все</span><span class="sxs-lookup"><span data-stu-id="248c3-312">All</span></span> |
| <xref:System.Security.Cryptography.HMAC.Create?displayProperty=nameWithType> | <span data-ttu-id="248c3-313">Все</span><span class="sxs-lookup"><span data-stu-id="248c3-313">All</span></span> |
| <xref:System.Security.Cryptography.HMAC.Create(System.String)?displayProperty=nameWithType> | <span data-ttu-id="248c3-314">Все</span><span class="sxs-lookup"><span data-stu-id="248c3-314">All</span></span> |
| <xref:System.Security.Cryptography.HMAC.HashCore%2A?displayProperty=nameWithType> | <span data-ttu-id="248c3-315">Все</span><span class="sxs-lookup"><span data-stu-id="248c3-315">All</span></span> |
| <xref:System.Security.Cryptography.HMAC.HashFinal%2A?displayProperty=nameWithType> | <span data-ttu-id="248c3-316">Все</span><span class="sxs-lookup"><span data-stu-id="248c3-316">All</span></span> |
| <xref:System.Security.Cryptography.HMAC.Initialize%2A?displayProperty=nameWithType> | <span data-ttu-id="248c3-317">Все</span><span class="sxs-lookup"><span data-stu-id="248c3-317">All</span></span> |
| <xref:System.Security.Cryptography.KeyedHashAlgorithm.Create?displayProperty=nameWithType> | <span data-ttu-id="248c3-318">Все</span><span class="sxs-lookup"><span data-stu-id="248c3-318">All</span></span> |
| <xref:System.Security.Cryptography.KeyedHashAlgorithm.Create(System.String)?displayProperty=nameWithType> | <span data-ttu-id="248c3-319">Все</span><span class="sxs-lookup"><span data-stu-id="248c3-319">All</span></span> |
| <xref:System.Security.Cryptography.ProtectedData.Protect%2A?displayProperty=nameWithType> | <span data-ttu-id="248c3-320">Linux и macOS</span><span class="sxs-lookup"><span data-stu-id="248c3-320">Linux and macOS</span></span> |
| <xref:System.Security.Cryptography.ProtectedData.Unprotect%2A?displayProperty=nameWithType> | <span data-ttu-id="248c3-321">Linux и macOS</span><span class="sxs-lookup"><span data-stu-id="248c3-321">Linux and macOS</span></span> |
| <xref:System.Security.Cryptography.RSA.FromXmlString%2A?displayProperty=nameWithType> | <span data-ttu-id="248c3-322">Все</span><span class="sxs-lookup"><span data-stu-id="248c3-322">All</span></span> |
| <xref:System.Security.Cryptography.RSA.ToXmlString%2A?displayProperty=nameWithType> | <span data-ttu-id="248c3-323">Все</span><span class="sxs-lookup"><span data-stu-id="248c3-323">All</span></span> |
| <xref:System.Security.Cryptography.SymmetricAlgorithm.Create?displayProperty=nameWithType> | <span data-ttu-id="248c3-324">Все</span><span class="sxs-lookup"><span data-stu-id="248c3-324">All</span></span> |
| <xref:System.Security.Cryptography.SymmetricAlgorithm.Create(System.String)?displayProperty=nameWithType> | <span data-ttu-id="248c3-325">Все</span><span class="sxs-lookup"><span data-stu-id="248c3-325">All</span></span> |

## <a name="systemsecuritycryptographypkcs"></a><span data-ttu-id="248c3-326">System.Security.Cryptography.Pkcs</span><span class="sxs-lookup"><span data-stu-id="248c3-326">System.Security.Cryptography.Pkcs</span></span>

| <span data-ttu-id="248c3-327">Участник</span><span class="sxs-lookup"><span data-stu-id="248c3-327">Member</span></span> | <span data-ttu-id="248c3-328">Платформы, которые вызывают исключение</span><span class="sxs-lookup"><span data-stu-id="248c3-328">Platforms that throw</span></span> |
| - | - |
| <xref:System.Security.Cryptography.Pkcs.CmsSigner.%23ctor(System.Security.Cryptography.CspParameters)> | <span data-ttu-id="248c3-329">Все</span><span class="sxs-lookup"><span data-stu-id="248c3-329">All</span></span> |
| <xref:System.Security.Cryptography.Pkcs.SignerInfo.ComputeCounterSignature?displayProperty=nameWithType> | <span data-ttu-id="248c3-330">Все</span><span class="sxs-lookup"><span data-stu-id="248c3-330">All</span></span> |

## <a name="systemsecuritycryptographyx509certificates"></a><span data-ttu-id="248c3-331">System.Security.Cryptography.X509Certificates</span><span class="sxs-lookup"><span data-stu-id="248c3-331">System.Security.Cryptography.X509Certificates</span></span>

| <span data-ttu-id="248c3-332">Участник</span><span class="sxs-lookup"><span data-stu-id="248c3-332">Member</span></span> | <span data-ttu-id="248c3-333">Платформы, которые вызывают исключение</span><span class="sxs-lookup"><span data-stu-id="248c3-333">Platforms that throw</span></span> |
| - | - |
| <xref:System.Security.Cryptography.X509Certificates.X509Certificate.%23ctor(System.Runtime.Serialization.SerializationInfo,System.Runtime.Serialization.StreamingContext)> | <span data-ttu-id="248c3-334">All</span><span class="sxs-lookup"><span data-stu-id="248c3-334">All</span></span> |
| <xref:System.Security.Cryptography.X509Certificates.X509Certificate.Import%2A?displayProperty=nameWithType> | <span data-ttu-id="248c3-335">Все</span><span class="sxs-lookup"><span data-stu-id="248c3-335">All</span></span> |
| <xref:System.Security.Cryptography.X509Certificates.X509Certificate2.%23ctor(System.Runtime.Serialization.SerializationInfo,System.Runtime.Serialization.StreamingContext)> | <span data-ttu-id="248c3-336">Все</span><span class="sxs-lookup"><span data-stu-id="248c3-336">All</span></span> |
| <span data-ttu-id="248c3-337"><xref:System.Security.Cryptography.X509Certificates.X509Certificate2.PrivateKey?displayProperty=nameWithType> (только установка)</span><span class="sxs-lookup"><span data-stu-id="248c3-337"><xref:System.Security.Cryptography.X509Certificates.X509Certificate2.PrivateKey?displayProperty=nameWithType> (set only)</span></span> | <span data-ttu-id="248c3-338">Все</span><span class="sxs-lookup"><span data-stu-id="248c3-338">All</span></span> |

## <a name="systemsecurityauthenticationextendedprotection"></a><span data-ttu-id="248c3-339">System.Security.Authentication.ExtendedProtection</span><span class="sxs-lookup"><span data-stu-id="248c3-339">System.Security.Authentication.ExtendedProtection</span></span>

| <span data-ttu-id="248c3-340">Участник</span><span class="sxs-lookup"><span data-stu-id="248c3-340">Member</span></span> | <span data-ttu-id="248c3-341">Платформы, которые вызывают исключение</span><span class="sxs-lookup"><span data-stu-id="248c3-341">Platforms that throw</span></span> |
| - | - |
| <xref:System.Security.Authentication.ExtendedProtection.ExtendedProtectionPolicy.%23ctor(System.Runtime.Serialization.SerializationInfo,System.Runtime.Serialization.StreamingContext)> | <span data-ttu-id="248c3-342">Все</span><span class="sxs-lookup"><span data-stu-id="248c3-342">All</span></span> |

## <a name="systemsecuritypolicy"></a><span data-ttu-id="248c3-343">System.Security.Policy</span><span class="sxs-lookup"><span data-stu-id="248c3-343">System.Security.Policy</span></span>

| <span data-ttu-id="248c3-344">Участник</span><span class="sxs-lookup"><span data-stu-id="248c3-344">Member</span></span> | <span data-ttu-id="248c3-345">Платформы, которые вызывают исключение</span><span class="sxs-lookup"><span data-stu-id="248c3-345">Platforms that throw</span></span> |
| - | - |
| <xref:System.Security.Policy.Hash.GetObjectData(System.Runtime.Serialization.SerializationInfo,System.Runtime.Serialization.StreamingContext)?displayProperty=nameWithType> | <span data-ttu-id="248c3-346">Все</span><span class="sxs-lookup"><span data-stu-id="248c3-346">All</span></span> |

## <a name="systemserviceprocessservicecontroller"></a><span data-ttu-id="248c3-347">System.ServiceProcess.ServiceController</span><span class="sxs-lookup"><span data-stu-id="248c3-347">System.ServiceProcess.ServiceController</span></span>

| <span data-ttu-id="248c3-348">Участник</span><span class="sxs-lookup"><span data-stu-id="248c3-348">Member</span></span> | <span data-ttu-id="248c3-349">Платформы, которые вызывают исключение</span><span class="sxs-lookup"><span data-stu-id="248c3-349">Platforms that throw</span></span> |
| - | - |
| <xref:System.ServiceProcess.TimeoutException.%23ctor(System.Runtime.Serialization.SerializationInfo,System.Runtime.Serialization.StreamingContext)> | <span data-ttu-id="248c3-350">Все</span><span class="sxs-lookup"><span data-stu-id="248c3-350">All</span></span> |

## <a name="systemtextregularexpressions"></a><span data-ttu-id="248c3-351">System.Text.RegularExpressions</span><span class="sxs-lookup"><span data-stu-id="248c3-351">System.Text.RegularExpressions</span></span>

| <span data-ttu-id="248c3-352">Участник</span><span class="sxs-lookup"><span data-stu-id="248c3-352">Member</span></span> | <span data-ttu-id="248c3-353">Платформы, которые вызывают исключение</span><span class="sxs-lookup"><span data-stu-id="248c3-353">Platforms that throw</span></span> |
| - | - |
| <xref:System.Text.RegularExpressions.Regex.CompileToAssembly%2A?displayProperty=nameWithType> | <span data-ttu-id="248c3-354">Все</span><span class="sxs-lookup"><span data-stu-id="248c3-354">All</span></span> |

## <a name="systemthreading"></a><span data-ttu-id="248c3-355">System.Threading</span><span class="sxs-lookup"><span data-stu-id="248c3-355">System.Threading</span></span>

| <span data-ttu-id="248c3-356">Участник</span><span class="sxs-lookup"><span data-stu-id="248c3-356">Member</span></span> | <span data-ttu-id="248c3-357">Платформы, которые вызывают исключение</span><span class="sxs-lookup"><span data-stu-id="248c3-357">Platforms that throw</span></span> |
| - | - |
| <xref:System.Threading.CompressedStack.GetObjectData(System.Runtime.Serialization.SerializationInfo,System.Runtime.Serialization.StreamingContext)?displayProperty=nameWithType> | <span data-ttu-id="248c3-358">All</span><span class="sxs-lookup"><span data-stu-id="248c3-358">All</span></span> |
| <xref:System.Threading.ExecutionContext.GetObjectData(System.Runtime.Serialization.SerializationInfo,System.Runtime.Serialization.StreamingContext)?displayProperty=nameWithType> | <span data-ttu-id="248c3-359">Все</span><span class="sxs-lookup"><span data-stu-id="248c3-359">All</span></span> |
| <xref:System.Threading.Thread.Abort%2A?displayProperty=nameWithType> | <span data-ttu-id="248c3-360">Все</span><span class="sxs-lookup"><span data-stu-id="248c3-360">All</span></span> |
| <xref:System.Threading.Thread.ResetAbort?displayProperty=nameWithType> | <span data-ttu-id="248c3-361">Все</span><span class="sxs-lookup"><span data-stu-id="248c3-361">All</span></span> |
| <xref:System.Threading.Thread.Resume?displayProperty=nameWithType> | <span data-ttu-id="248c3-362">Все</span><span class="sxs-lookup"><span data-stu-id="248c3-362">All</span></span> |
| <xref:System.Threading.Thread.Suspend?displayProperty=nameWithType> | <span data-ttu-id="248c3-363">Все</span><span class="sxs-lookup"><span data-stu-id="248c3-363">All</span></span> |

## <a name="systemxml"></a><span data-ttu-id="248c3-364">System.Xml</span><span class="sxs-lookup"><span data-stu-id="248c3-364">System.Xml</span></span>

| <span data-ttu-id="248c3-365">Участник</span><span class="sxs-lookup"><span data-stu-id="248c3-365">Member</span></span> | <span data-ttu-id="248c3-366">Платформы, которые вызывают исключение</span><span class="sxs-lookup"><span data-stu-id="248c3-366">Platforms that throw</span></span> |
| - | - |
| <xref:System.Xml.XmlDictionaryReader.CreateMtomReader(System.Byte[],System.Int32,System.Int32,System.Text.Encoding[],System.String,System.Xml.XmlDictionaryReaderQuotas,System.Int32,System.Xml.OnXmlDictionaryReaderClose)?displayProperty=nameWithType> | <span data-ttu-id="248c3-367">All</span><span class="sxs-lookup"><span data-stu-id="248c3-367">All</span></span> |
| <xref:System.Xml.XmlDictionaryReader.CreateMtomReader(System.IO.Stream,System.Text.Encoding[],System.String,System.Xml.XmlDictionaryReaderQuotas,System.Int32,System.Xml.OnXmlDictionaryReaderClose)?displayProperty=nameWithType> | <span data-ttu-id="248c3-368">Все</span><span class="sxs-lookup"><span data-stu-id="248c3-368">All</span></span> |
| <xref:System.Xml.XmlDictionaryWriter.CreateMtomWriter(System.IO.Stream,System.Text.Encoding,System.Int32,System.String,System.String,System.String,System.Boolean,System.Boolean)?displayProperty=nameWithType> | <span data-ttu-id="248c3-369">Все</span><span class="sxs-lookup"><span data-stu-id="248c3-369">All</span></span> |

## <a name="see-also"></a><span data-ttu-id="248c3-370">См. также</span><span class="sxs-lookup"><span data-stu-id="248c3-370">See also</span></span>

- [<span data-ttu-id="248c3-371">Критические изменения для миграции с .NET Framework на .NET Core</span><span class="sxs-lookup"><span data-stu-id="248c3-371">Breaking changes for migration from .NET Framework to .NET Core</span></span>](fx-core.md)
- [<span data-ttu-id="248c3-372">Двоичная сериализация в .NET Core</span><span class="sxs-lookup"><span data-stu-id="248c3-372">Binary serialization in .NET Core</span></span>](../../standard/serialization/binary-serialization.md#net-core)
- [<span data-ttu-id="248c3-373">Анализатор переносимости .NET</span><span class="sxs-lookup"><span data-stu-id="248c3-373">.NET portability analyzer</span></span>](../../standard/analyzers/portability-analyzer.md)
