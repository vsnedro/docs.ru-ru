---
title: Неподдерживаемые API в .NET Core
titleSuffix: ''
description: Узнайте, какие API-интерфейсы из .NET Framework всегда вызывают исключение в .NET Core.
ms.date: 12/23/2019
ms.openlocfilehash: 941e9149c7679afe4a888149108d0a9a28e5e7ab
ms.sourcegitcommit: de7f589de07a9979b6ac28f54c3e534a617d9425
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/05/2020
ms.locfileid: "82794602"
---
# <a name="apis-that-always-throw-exceptions-on-net-core"></a><span data-ttu-id="6387d-103">API, которые всегда создают исключения в .NET Core</span><span class="sxs-lookup"><span data-stu-id="6387d-103">APIs that always throw exceptions on .NET Core</span></span>

<span data-ttu-id="6387d-104">Следующие API всегда будут вызывать исключение <xref:System.PlatformNotSupportedException> в .NET Core на всех платформах или на их подмножестве.</span><span class="sxs-lookup"><span data-stu-id="6387d-104">The following APIs will always throw a <xref:System.PlatformNotSupportedException> on .NET Core on all or a subset of platforms.</span></span>

<span data-ttu-id="6387d-105">В этой статье затронутые члены API упорядочиваются по пространствам имен.</span><span class="sxs-lookup"><span data-stu-id="6387d-105">This article organizes the affected API members by namespace.</span></span>

> [!NOTE]
>
> - <span data-ttu-id="6387d-106">Эта статья все еще находится в процессе написания.</span><span class="sxs-lookup"><span data-stu-id="6387d-106">This article is a work-in-progress.</span></span> <span data-ttu-id="6387d-107">Это не полный список API-интерфейсов, создающих исключения в .NET Core.</span><span class="sxs-lookup"><span data-stu-id="6387d-107">It is not a complete list of APIs that throw exceptions on .NET Core.</span></span>
> - <span data-ttu-id="6387d-108">В этой статье не рассматриваются явные реализации интерфейса для двоичной сериализации, которые вызываются в .NET Core.</span><span class="sxs-lookup"><span data-stu-id="6387d-108">This article does not include the explicit interface implementations for binary serialization that throw on .NET Core.</span></span> <span data-ttu-id="6387d-109">Дополнительные сведения см. в разделе [Двоичная сериализация в .NET Core](../../standard/serialization/binary-serialization.md#net-core).</span><span class="sxs-lookup"><span data-stu-id="6387d-109">For more information, see [Binary serialization in .NET Core](../../standard/serialization/binary-serialization.md#net-core).</span></span>

## <a name="system"></a><span data-ttu-id="6387d-110">Система</span><span class="sxs-lookup"><span data-stu-id="6387d-110">System</span></span>

| <span data-ttu-id="6387d-111">Участник</span><span class="sxs-lookup"><span data-stu-id="6387d-111">Member</span></span> | <span data-ttu-id="6387d-112">Платформы, которые вызывают исключение</span><span class="sxs-lookup"><span data-stu-id="6387d-112">Platforms that throw</span></span> |
| - | - |
| <xref:System.AppDomain.CreateDomain%2A?displayProperty=nameWithType> | <span data-ttu-id="6387d-113">Все</span><span class="sxs-lookup"><span data-stu-id="6387d-113">All</span></span> |
| <xref:System.AppDomain.ExecuteAssembly(System.String,System.String[],System.Byte[],System.Configuration.Assemblies.AssemblyHashAlgorithm)?displayProperty=nameWithType> | <span data-ttu-id="6387d-114">Все</span><span class="sxs-lookup"><span data-stu-id="6387d-114">All</span></span> |
| <xref:System.Console.CapsLock?displayProperty=nameWithType> | <span data-ttu-id="6387d-115">Linux и macOS</span><span class="sxs-lookup"><span data-stu-id="6387d-115">Linux and macOS</span></span> |
| <xref:System.Console.NumberLock?displayProperty=nameWithType> | <span data-ttu-id="6387d-116">Linux и macOS</span><span class="sxs-lookup"><span data-stu-id="6387d-116">Linux and macOS</span></span> |
| <xref:System.Delegate.GetObjectData(System.Runtime.Serialization.SerializationInfo,System.Runtime.Serialization.StreamingContext)?displayProperty=nameWithType> | <span data-ttu-id="6387d-117">Все</span><span class="sxs-lookup"><span data-stu-id="6387d-117">All</span></span> |
| <xref:System.Exception.SerializeObjectState?displayProperty=nameWithType> | <span data-ttu-id="6387d-118">Все</span><span class="sxs-lookup"><span data-stu-id="6387d-118">All</span></span> |
| <xref:System.MarshalByRefObject.GetLifetimeService?displayProperty=nameWithType> | <span data-ttu-id="6387d-119">Все</span><span class="sxs-lookup"><span data-stu-id="6387d-119">All</span></span> |
| <xref:System.MarshalByRefObject.InitializeLifetimeService?displayProperty=nameWithType> | <span data-ttu-id="6387d-120">Все</span><span class="sxs-lookup"><span data-stu-id="6387d-120">All</span></span> |
| <xref:System.OperatingSystem.GetObjectData(System.Runtime.Serialization.SerializationInfo,System.Runtime.Serialization.StreamingContext)?displayProperty=nameWithType> | <span data-ttu-id="6387d-121">Все</span><span class="sxs-lookup"><span data-stu-id="6387d-121">All</span></span> |
| <xref:System.Type.ReflectionOnlyGetType(System.String,System.Boolean,System.Boolean)?displayProperty=nameWithType> | <span data-ttu-id="6387d-122">Все</span><span class="sxs-lookup"><span data-stu-id="6387d-122">All</span></span> |

## <a name="systemcodedomcompiler"></a><span data-ttu-id="6387d-123">System.CodeDom.Compiler</span><span class="sxs-lookup"><span data-stu-id="6387d-123">System.CodeDom.Compiler</span></span>

| <span data-ttu-id="6387d-124">Участник</span><span class="sxs-lookup"><span data-stu-id="6387d-124">Member</span></span> | <span data-ttu-id="6387d-125">Платформы, которые вызывают исключение</span><span class="sxs-lookup"><span data-stu-id="6387d-125">Platforms that throw</span></span> |
| - | - |
| <xref:System.CodeDom.Compiler.CodeDomProvider.CompileAssemblyFromDom%2A?displayProperty=nameWithType> | <span data-ttu-id="6387d-126">Все</span><span class="sxs-lookup"><span data-stu-id="6387d-126">All</span></span> |
| <xref:System.CodeDom.Compiler.CodeDomProvider.CompileAssemblyFromFile%2A?displayProperty=nameWithType> | <span data-ttu-id="6387d-127">Все</span><span class="sxs-lookup"><span data-stu-id="6387d-127">All</span></span> |
| <xref:System.CodeDom.Compiler.CodeDomProvider.CompileAssemblyFromSource%2A?displayProperty=nameWithType> | <span data-ttu-id="6387d-128">Все</span><span class="sxs-lookup"><span data-stu-id="6387d-128">All</span></span> |

## <a name="systemcollectionsspecialized"></a><span data-ttu-id="6387d-129">System.Collections.Specialized</span><span class="sxs-lookup"><span data-stu-id="6387d-129">System.Collections.Specialized</span></span>

| <span data-ttu-id="6387d-130">Участник</span><span class="sxs-lookup"><span data-stu-id="6387d-130">Member</span></span> | <span data-ttu-id="6387d-131">Платформы, которые вызывают исключение</span><span class="sxs-lookup"><span data-stu-id="6387d-131">Platforms that throw</span></span> |
| - | - |
| <xref:System.Collections.Specialized.NameObjectCollectionBase.%23ctor(System.Runtime.Serialization.SerializationInfo,System.Runtime.Serialization.StreamingContext)> | <span data-ttu-id="6387d-132">Все</span><span class="sxs-lookup"><span data-stu-id="6387d-132">All</span></span> |
| <xref:System.Collections.Specialized.NameObjectCollectionBase.GetObjectData(System.Runtime.Serialization.SerializationInfo,System.Runtime.Serialization.StreamingContext)?displayProperty=nameWithType> | <span data-ttu-id="6387d-133">Все</span><span class="sxs-lookup"><span data-stu-id="6387d-133">All</span></span> |
| <xref:System.Collections.Specialized.NameObjectCollectionBase.OnDeserialization(System.Object)?displayProperty=nameWithType> | <span data-ttu-id="6387d-134">Все</span><span class="sxs-lookup"><span data-stu-id="6387d-134">All</span></span> |

## <a name="systemconfiguration"></a><span data-ttu-id="6387d-135">System.Configuration</span><span class="sxs-lookup"><span data-stu-id="6387d-135">System.Configuration</span></span>

| <span data-ttu-id="6387d-136">Участник</span><span class="sxs-lookup"><span data-stu-id="6387d-136">Member</span></span> | <span data-ttu-id="6387d-137">Платформы, которые вызывают исключение</span><span class="sxs-lookup"><span data-stu-id="6387d-137">Platforms that throw</span></span> |
| - | - |
| <span data-ttu-id="6387d-138"><xref:System.Configuration.RsaProtectedConfigurationProvider?displayProperty=nameWithType> (все члены)</span><span class="sxs-lookup"><span data-stu-id="6387d-138"><xref:System.Configuration.RsaProtectedConfigurationProvider?displayProperty=nameWithType> (all members)</span></span> | <span data-ttu-id="6387d-139">Все</span><span class="sxs-lookup"><span data-stu-id="6387d-139">All</span></span> |

## <a name="systemconsole"></a><span data-ttu-id="6387d-140">System.Console</span><span class="sxs-lookup"><span data-stu-id="6387d-140">System.Console</span></span>

| <span data-ttu-id="6387d-141">Участник</span><span class="sxs-lookup"><span data-stu-id="6387d-141">Member</span></span> | <span data-ttu-id="6387d-142">Платформы, которые вызывают исключение</span><span class="sxs-lookup"><span data-stu-id="6387d-142">Platforms that throw</span></span> |
| - | - |
| <xref:System.Console.Beep?displayProperty=nameWithType> | <span data-ttu-id="6387d-143">Linux и macOS</span><span class="sxs-lookup"><span data-stu-id="6387d-143">Linux and macOS</span></span> |
| <span data-ttu-id="6387d-144"><xref:System.Console.BufferHeight?displayProperty=nameWithType> (только установка)</span><span class="sxs-lookup"><span data-stu-id="6387d-144"><xref:System.Console.BufferHeight?displayProperty=nameWithType> (set only)</span></span> | <span data-ttu-id="6387d-145">Linux и macOS</span><span class="sxs-lookup"><span data-stu-id="6387d-145">Linux and macOS</span></span> |
| <span data-ttu-id="6387d-146"><xref:System.Console.BufferWidth?displayProperty=nameWithType> (только установка)</span><span class="sxs-lookup"><span data-stu-id="6387d-146"><xref:System.Console.BufferWidth?displayProperty=nameWithType> (set only)</span></span> | <span data-ttu-id="6387d-147">Linux и macOS</span><span class="sxs-lookup"><span data-stu-id="6387d-147">Linux and macOS</span></span> |
| <span data-ttu-id="6387d-148"><xref:System.Console.CursorSize?displayProperty=nameWithType> (только установка)</span><span class="sxs-lookup"><span data-stu-id="6387d-148"><xref:System.Console.CursorSize?displayProperty=nameWithType> (set only)</span></span> | <span data-ttu-id="6387d-149">Linux и macOS</span><span class="sxs-lookup"><span data-stu-id="6387d-149">Linux and macOS</span></span> |
| <span data-ttu-id="6387d-150"><xref:System.Console.CursorVisible?displayProperty=nameWithType> (только получение)</span><span class="sxs-lookup"><span data-stu-id="6387d-150"><xref:System.Console.CursorVisible?displayProperty=nameWithType> (get only)</span></span> | <span data-ttu-id="6387d-151">Linux и macOS</span><span class="sxs-lookup"><span data-stu-id="6387d-151">Linux and macOS</span></span> |
| <xref:System.Console.MoveBufferArea%2A?displayProperty=nameWithType> | <span data-ttu-id="6387d-152">Linux и macOS</span><span class="sxs-lookup"><span data-stu-id="6387d-152">Linux and macOS</span></span> |
| <xref:System.Console.SetWindowPosition%2A?displayProperty=nameWithType> | <span data-ttu-id="6387d-153">Linux и macOS</span><span class="sxs-lookup"><span data-stu-id="6387d-153">Linux and macOS</span></span> |
| <xref:System.Console.SetWindowSize%2A?displayProperty=nameWithType> | <span data-ttu-id="6387d-154">Linux и macOS</span><span class="sxs-lookup"><span data-stu-id="6387d-154">Linux and macOS</span></span> |
| <span data-ttu-id="6387d-155"><xref:System.Console.Title?displayProperty=nameWithType> (только получение)</span><span class="sxs-lookup"><span data-stu-id="6387d-155"><xref:System.Console.Title?displayProperty=nameWithType> (get only)</span></span> | <span data-ttu-id="6387d-156">Linux и macOS</span><span class="sxs-lookup"><span data-stu-id="6387d-156">Linux and macOS</span></span> |
| <span data-ttu-id="6387d-157"><xref:System.Console.WindowHeight?displayProperty=nameWithType> (только установка)</span><span class="sxs-lookup"><span data-stu-id="6387d-157"><xref:System.Console.WindowHeight?displayProperty=nameWithType> (set only)</span></span> | <span data-ttu-id="6387d-158">Linux и macOS</span><span class="sxs-lookup"><span data-stu-id="6387d-158">Linux and macOS</span></span> |
| <span data-ttu-id="6387d-159"><xref:System.Console.WindowLeft?displayProperty=nameWithType> (только установка)</span><span class="sxs-lookup"><span data-stu-id="6387d-159"><xref:System.Console.WindowLeft?displayProperty=nameWithType> (set only)</span></span> | <span data-ttu-id="6387d-160">Linux и macOS</span><span class="sxs-lookup"><span data-stu-id="6387d-160">Linux and macOS</span></span> |
| <span data-ttu-id="6387d-161"><xref:System.Console.WindowTop?displayProperty=nameWithType> (только установка)</span><span class="sxs-lookup"><span data-stu-id="6387d-161"><xref:System.Console.WindowTop?displayProperty=nameWithType> (set only)</span></span> | <span data-ttu-id="6387d-162">Linux и macOS</span><span class="sxs-lookup"><span data-stu-id="6387d-162">Linux and macOS</span></span> |
| <span data-ttu-id="6387d-163"><xref:System.Console.WindowWidth?displayProperty=nameWithType> (только установка)</span><span class="sxs-lookup"><span data-stu-id="6387d-163"><xref:System.Console.WindowWidth?displayProperty=nameWithType> (set only)</span></span> | <span data-ttu-id="6387d-164">Linux и macOS</span><span class="sxs-lookup"><span data-stu-id="6387d-164">Linux and macOS</span></span> |

## <a name="systemdatacommon"></a><span data-ttu-id="6387d-165">System.Data.Common</span><span class="sxs-lookup"><span data-stu-id="6387d-165">System.Data.Common</span></span>

| <span data-ttu-id="6387d-166">Участник</span><span class="sxs-lookup"><span data-stu-id="6387d-166">Member</span></span> | <span data-ttu-id="6387d-167">Платформы, которые вызывают исключение</span><span class="sxs-lookup"><span data-stu-id="6387d-167">Platforms that throw</span></span> |
| - | - |
| <span data-ttu-id="6387d-168"><xref:System.Data.Common.DbDataReader.GetSchemaTable%2A?displayProperty=nameWithType> (вызывает <xref:System.NotSupportedException>)</span><span class="sxs-lookup"><span data-stu-id="6387d-168"><xref:System.Data.Common.DbDataReader.GetSchemaTable%2A?displayProperty=nameWithType> (throws <xref:System.NotSupportedException>)</span></span> | <span data-ttu-id="6387d-169">Все</span><span class="sxs-lookup"><span data-stu-id="6387d-169">All</span></span> |

## <a name="systemdiagnosticsprocess"></a><span data-ttu-id="6387d-170">System.Diagnostics.Process</span><span class="sxs-lookup"><span data-stu-id="6387d-170">System.Diagnostics.Process</span></span>

| <span data-ttu-id="6387d-171">Участник</span><span class="sxs-lookup"><span data-stu-id="6387d-171">Member</span></span> | <span data-ttu-id="6387d-172">Платформы, которые вызывают исключение</span><span class="sxs-lookup"><span data-stu-id="6387d-172">Platforms that throw</span></span> |
| - | - |
| <span data-ttu-id="6387d-173"><xref:System.Diagnostics.Process.MaxWorkingSet?displayProperty=nameWithType> (только установка)</span><span class="sxs-lookup"><span data-stu-id="6387d-173"><xref:System.Diagnostics.Process.MaxWorkingSet?displayProperty=nameWithType> (set only)</span></span> | <span data-ttu-id="6387d-174">Linux</span><span class="sxs-lookup"><span data-stu-id="6387d-174">Linux</span></span> |
| <span data-ttu-id="6387d-175"><xref:System.Diagnostics.Process.MinWorkingSet?displayProperty=nameWithType> (только установка)</span><span class="sxs-lookup"><span data-stu-id="6387d-175"><xref:System.Diagnostics.Process.MinWorkingSet?displayProperty=nameWithType> (set only)</span></span> | <span data-ttu-id="6387d-176">Linux</span><span class="sxs-lookup"><span data-stu-id="6387d-176">Linux</span></span> |
| <xref:System.Diagnostics.Process.ProcessorAffinity?displayProperty=nameWithType> | <span data-ttu-id="6387d-177">macOS</span><span class="sxs-lookup"><span data-stu-id="6387d-177">macOS</span></span> |
| <xref:System.Diagnostics.Process.MainWindowHandle?displayProperty=nameWithType> | <span data-ttu-id="6387d-178">Linux и macOS</span><span class="sxs-lookup"><span data-stu-id="6387d-178">Linux and macOS</span></span> |
| <xref:System.Diagnostics.Process.Start%2A?displayProperty=nameWithType> | <span data-ttu-id="6387d-179">Linux и macOS</span><span class="sxs-lookup"><span data-stu-id="6387d-179">Linux and macOS</span></span> |
| <xref:System.Diagnostics.ProcessStartInfo.UserName?displayProperty=nameWithType> | <span data-ttu-id="6387d-180">Linux и macOS</span><span class="sxs-lookup"><span data-stu-id="6387d-180">Linux and macOS</span></span> |
| <xref:System.Diagnostics.ProcessStartInfo.PasswordInClearText?displayProperty=nameWithType> | <span data-ttu-id="6387d-181">Linux и macOS</span><span class="sxs-lookup"><span data-stu-id="6387d-181">Linux and macOS</span></span> |
| <xref:System.Diagnostics.ProcessStartInfo.Domain?displayProperty=nameWithType> | <span data-ttu-id="6387d-182">Linux и macOS</span><span class="sxs-lookup"><span data-stu-id="6387d-182">Linux and macOS</span></span> |
| <xref:System.Diagnostics.ProcessStartInfo.LoadUserProfile?displayProperty=nameWithType> | <span data-ttu-id="6387d-183">Linux и macOS</span><span class="sxs-lookup"><span data-stu-id="6387d-183">Linux and macOS</span></span> |
| <span data-ttu-id="6387d-184"><xref:System.Diagnostics.ProcessThread.BasePriority?displayProperty=nameWithType> (только установка)</span><span class="sxs-lookup"><span data-stu-id="6387d-184"><xref:System.Diagnostics.ProcessThread.BasePriority?displayProperty=nameWithType> (set only)</span></span> | <span data-ttu-id="6387d-185">Linux и macOS</span><span class="sxs-lookup"><span data-stu-id="6387d-185">Linux and macOS</span></span> |
| <span data-ttu-id="6387d-186"><xref:System.Diagnostics.ProcessThread.BasePriority?displayProperty=nameWithType> (только получение)</span><span class="sxs-lookup"><span data-stu-id="6387d-186"><xref:System.Diagnostics.ProcessThread.BasePriority?displayProperty=nameWithType> (get only)</span></span> | <span data-ttu-id="6387d-187">macOS</span><span class="sxs-lookup"><span data-stu-id="6387d-187">macOS</span></span> |
| <span data-ttu-id="6387d-188"><xref:System.Diagnostics.ProcessThread.ProcessorAffinity?displayProperty=nameWithType> (только установка)</span><span class="sxs-lookup"><span data-stu-id="6387d-188"><xref:System.Diagnostics.ProcessThread.ProcessorAffinity?displayProperty=nameWithType> (set only)</span></span> | <span data-ttu-id="6387d-189">Linux и macOS</span><span class="sxs-lookup"><span data-stu-id="6387d-189">Linux and macOS</span></span> |

## <a name="systemio"></a><span data-ttu-id="6387d-190">System.IO</span><span class="sxs-lookup"><span data-stu-id="6387d-190">System.IO</span></span>

| <span data-ttu-id="6387d-191">Участник</span><span class="sxs-lookup"><span data-stu-id="6387d-191">Member</span></span> | <span data-ttu-id="6387d-192">Платформы, которые вызывают исключение</span><span class="sxs-lookup"><span data-stu-id="6387d-192">Platforms that throw</span></span> |
| - | - |
| <xref:System.IO.FileSystemInfo.%23ctor(System.Runtime.Serialization.SerializationInfo,System.Runtime.Serialization.StreamingContext)> | <span data-ttu-id="6387d-193">Все</span><span class="sxs-lookup"><span data-stu-id="6387d-193">All</span></span> |
| <xref:System.IO.FileSystemInfo.GetObjectData(System.Runtime.Serialization.SerializationInfo,System.Runtime.Serialization.StreamingContext)?displayProperty=nameWithType> | <span data-ttu-id="6387d-194">Все</span><span class="sxs-lookup"><span data-stu-id="6387d-194">All</span></span> |

## <a name="systemiopipes"></a><span data-ttu-id="6387d-195">System.IO.Pipes</span><span class="sxs-lookup"><span data-stu-id="6387d-195">System.IO.Pipes</span></span>

| <span data-ttu-id="6387d-196">Участник</span><span class="sxs-lookup"><span data-stu-id="6387d-196">Member</span></span> | <span data-ttu-id="6387d-197">Платформы, которые вызывают исключение</span><span class="sxs-lookup"><span data-stu-id="6387d-197">Platforms that throw</span></span> |
| - | - |
| <xref:System.IO.Pipes.NamedPipeClientStream.NumberOfServerInstances?displayProperty=nameWithType> | <span data-ttu-id="6387d-198">Linux и macOS</span><span class="sxs-lookup"><span data-stu-id="6387d-198">Linux and macOS</span></span> |
| <xref:System.IO.Pipes.NamedPipeServerStream.GetImpersonationUserName?displayProperty=nameWithType> | <span data-ttu-id="6387d-199">Linux и macOS</span><span class="sxs-lookup"><span data-stu-id="6387d-199">Linux and macOS</span></span> |
| <xref:System.IO.Pipes.PipeStream.InBufferSize?displayProperty=nameWithType> | <span data-ttu-id="6387d-200">Linux и macOS</span><span class="sxs-lookup"><span data-stu-id="6387d-200">Linux and macOS</span></span> |
| <xref:System.IO.Pipes.PipeStream.OutBufferSize?displayProperty=nameWithType> | <span data-ttu-id="6387d-201">Linux и macOS</span><span class="sxs-lookup"><span data-stu-id="6387d-201">Linux and macOS</span></span> |
| <span data-ttu-id="6387d-202"><xref:System.IO.Pipes.PipeStream.ReadMode?displayProperty=nameWithType> (только установка)</span><span class="sxs-lookup"><span data-stu-id="6387d-202"><xref:System.IO.Pipes.PipeStream.ReadMode?displayProperty=nameWithType> (set only)</span></span> | <span data-ttu-id="6387d-203">Linux и macOS</span><span class="sxs-lookup"><span data-stu-id="6387d-203">Linux and macOS</span></span> |
| <xref:System.IO.Pipes.PipeStream.WaitForPipeDrain?displayProperty=nameWithType> | <span data-ttu-id="6387d-204">Linux и macOS</span><span class="sxs-lookup"><span data-stu-id="6387d-204">Linux and macOS</span></span> |

## <a name="systemmedia"></a><span data-ttu-id="6387d-205">System.Media</span><span class="sxs-lookup"><span data-stu-id="6387d-205">System.Media</span></span>

| <span data-ttu-id="6387d-206">Участник</span><span class="sxs-lookup"><span data-stu-id="6387d-206">Member</span></span> | <span data-ttu-id="6387d-207">Платформы, которые вызывают исключение</span><span class="sxs-lookup"><span data-stu-id="6387d-207">Platforms that throw</span></span> |
| - | - |
| <xref:System.Media.SoundPlayer.%23ctor(System.Runtime.Serialization.SerializationInfo,System.Runtime.Serialization.StreamingContext)> | <span data-ttu-id="6387d-208">Все</span><span class="sxs-lookup"><span data-stu-id="6387d-208">All</span></span> |

## <a name="systemnet"></a><span data-ttu-id="6387d-209">System.Net</span><span class="sxs-lookup"><span data-stu-id="6387d-209">System.Net</span></span>

| <span data-ttu-id="6387d-210">Участник</span><span class="sxs-lookup"><span data-stu-id="6387d-210">Member</span></span> | <span data-ttu-id="6387d-211">Платформы, которые вызывают исключение</span><span class="sxs-lookup"><span data-stu-id="6387d-211">Platforms that throw</span></span> |
| - | - |
| <xref:System.Net.AuthenticationManager.Authenticate(System.String,System.Net.WebRequest,System.Net.ICredentials)?displayProperty=nameWithType> | <span data-ttu-id="6387d-212">Все</span><span class="sxs-lookup"><span data-stu-id="6387d-212">All</span></span> |
| <xref:System.Net.AuthenticationManager.PreAuthenticate(System.Net.WebRequest,System.Net.ICredentials)?displayProperty=nameWithType> | <span data-ttu-id="6387d-213">Все</span><span class="sxs-lookup"><span data-stu-id="6387d-213">All</span></span> |
| <xref:System.Net.FileWebRequest.%23ctor(System.Runtime.Serialization.SerializationInfo,System.Runtime.Serialization.StreamingContext)> | <span data-ttu-id="6387d-214">Все</span><span class="sxs-lookup"><span data-stu-id="6387d-214">All</span></span> |
| <xref:System.Net.FileWebRequest.GetObjectData(System.Runtime.Serialization.SerializationInfo,System.Runtime.Serialization.StreamingContext)?displayProperty=nameWithType> | <span data-ttu-id="6387d-215">Все</span><span class="sxs-lookup"><span data-stu-id="6387d-215">All</span></span> |
| <xref:System.Net.FileWebResponse.%23ctor(System.Runtime.Serialization.SerializationInfo,System.Runtime.Serialization.StreamingContext)> | <span data-ttu-id="6387d-216">Все</span><span class="sxs-lookup"><span data-stu-id="6387d-216">All</span></span> |
| <xref:System.Net.FileWebResponse.GetObjectData(System.Runtime.Serialization.SerializationInfo,System.Runtime.Serialization.StreamingContext)?displayProperty=nameWithType> | <span data-ttu-id="6387d-217">Все</span><span class="sxs-lookup"><span data-stu-id="6387d-217">All</span></span> |
| <xref:System.Net.HttpWebRequest.%23ctor(System.Runtime.Serialization.SerializationInfo,System.Runtime.Serialization.StreamingContext)> | <span data-ttu-id="6387d-218">Все</span><span class="sxs-lookup"><span data-stu-id="6387d-218">All</span></span> |
| <xref:System.Net.HttpWebRequest.GetObjectData(System.Runtime.Serialization.SerializationInfo,System.Runtime.Serialization.StreamingContext)?displayProperty=nameWithType> | <span data-ttu-id="6387d-219">Все</span><span class="sxs-lookup"><span data-stu-id="6387d-219">All</span></span> |
| <xref:System.Net.HttpWebResponse.%23ctor(System.Runtime.Serialization.SerializationInfo,System.Runtime.Serialization.StreamingContext)> | <span data-ttu-id="6387d-220">Все</span><span class="sxs-lookup"><span data-stu-id="6387d-220">All</span></span> |
| <xref:System.Net.HttpWebResponse.GetObjectData(System.Runtime.Serialization.SerializationInfo,System.Runtime.Serialization.StreamingContext)?displayProperty=nameWithType> | <span data-ttu-id="6387d-221">Все</span><span class="sxs-lookup"><span data-stu-id="6387d-221">All</span></span> |
| <xref:System.Net.WebProxy.%23ctor(System.Runtime.Serialization.SerializationInfo,System.Runtime.Serialization.StreamingContext)> | <span data-ttu-id="6387d-222">Все</span><span class="sxs-lookup"><span data-stu-id="6387d-222">All</span></span> |
| <xref:System.Net.WebProxy.GetDefaultProxy?displayProperty=nameWithType> | <span data-ttu-id="6387d-223">Все</span><span class="sxs-lookup"><span data-stu-id="6387d-223">All</span></span> |
| <xref:System.Net.WebProxy.GetObjectData%2A?displayProperty=nameWithType> | <span data-ttu-id="6387d-224">Все</span><span class="sxs-lookup"><span data-stu-id="6387d-224">All</span></span> |
| <xref:System.Net.WebRequest.%23ctor(System.Runtime.Serialization.SerializationInfo,System.Runtime.Serialization.StreamingContext)> | <span data-ttu-id="6387d-225">Все</span><span class="sxs-lookup"><span data-stu-id="6387d-225">All</span></span> |
| <xref:System.Net.WebRequest.GetObjectData(System.Runtime.Serialization.SerializationInfo,System.Runtime.Serialization.StreamingContext)?displayProperty=nameWithType> | <span data-ttu-id="6387d-226">Все</span><span class="sxs-lookup"><span data-stu-id="6387d-226">All</span></span> |
| <xref:System.Net.WebResponse.%23ctor(System.Runtime.Serialization.SerializationInfo,System.Runtime.Serialization.StreamingContext)> | <span data-ttu-id="6387d-227">Все</span><span class="sxs-lookup"><span data-stu-id="6387d-227">All</span></span> |
| <xref:System.Net.WebResponse.GetObjectData(System.Runtime.Serialization.SerializationInfo,System.Runtime.Serialization.StreamingContext)?displayProperty=nameWithType> | <span data-ttu-id="6387d-228">Все</span><span class="sxs-lookup"><span data-stu-id="6387d-228">All</span></span> |

## <a name="systemnetnetworkinformation"></a><span data-ttu-id="6387d-229">System.Net.NetworkInformation</span><span class="sxs-lookup"><span data-stu-id="6387d-229">System.Net.NetworkInformation</span></span>

| <span data-ttu-id="6387d-230">Участник</span><span class="sxs-lookup"><span data-stu-id="6387d-230">Member</span></span> | <span data-ttu-id="6387d-231">Платформы, которые вызывают исключение</span><span class="sxs-lookup"><span data-stu-id="6387d-231">Platforms that throw</span></span> |
| - | - |
| <xref:System.Net.NetworkInformation.Ping.Send%2A?displayProperty=nameWithType> | <span data-ttu-id="6387d-232">Windows (UWP)</span><span class="sxs-lookup"><span data-stu-id="6387d-232">Windows (UWP)</span></span> |

## <a name="systemnetsockets"></a><span data-ttu-id="6387d-233">System.Net.Sockets</span><span class="sxs-lookup"><span data-stu-id="6387d-233">System.Net.Sockets</span></span>

| <span data-ttu-id="6387d-234">Участник</span><span class="sxs-lookup"><span data-stu-id="6387d-234">Member</span></span> | <span data-ttu-id="6387d-235">Платформы, которые вызывают исключение</span><span class="sxs-lookup"><span data-stu-id="6387d-235">Platforms that throw</span></span> |
| - | - |
| <xref:System.Net.Sockets.Socket.%23ctor(System.Net.Sockets.SocketInformation)> | <span data-ttu-id="6387d-236">Все</span><span class="sxs-lookup"><span data-stu-id="6387d-236">All</span></span> |
| <xref:System.Net.Sockets.Socket.DuplicateAndClose(System.Int32)?displayProperty=nameWithType> | <span data-ttu-id="6387d-237">Все</span><span class="sxs-lookup"><span data-stu-id="6387d-237">All</span></span> |

## <a name="systemnetwebsockets"></a><span data-ttu-id="6387d-238">System.Net.WebSockets</span><span class="sxs-lookup"><span data-stu-id="6387d-238">System.Net.WebSockets</span></span>

| <span data-ttu-id="6387d-239">Участник</span><span class="sxs-lookup"><span data-stu-id="6387d-239">Member</span></span> | <span data-ttu-id="6387d-240">Платформы, которые вызывают исключение</span><span class="sxs-lookup"><span data-stu-id="6387d-240">Platforms that throw</span></span> |
| - | - |
| <xref:System.Net.WebSockets.WebSocket.RegisterPrefixes?displayProperty=nameWithType> | <span data-ttu-id="6387d-241">Все</span><span class="sxs-lookup"><span data-stu-id="6387d-241">All</span></span> |

## <a name="systemreflection"></a><span data-ttu-id="6387d-242">System.Reflection</span><span class="sxs-lookup"><span data-stu-id="6387d-242">System.Reflection</span></span>

| <span data-ttu-id="6387d-243">Участник</span><span class="sxs-lookup"><span data-stu-id="6387d-243">Member</span></span> | <span data-ttu-id="6387d-244">Платформы, которые вызывают исключение</span><span class="sxs-lookup"><span data-stu-id="6387d-244">Platforms that throw</span></span> |
| - | - |
| <xref:System.Reflection.Assembly.ReflectionOnlyLoad%2A?displayProperty=nameWithType> | <span data-ttu-id="6387d-245">Все</span><span class="sxs-lookup"><span data-stu-id="6387d-245">All</span></span> |
| <xref:System.Reflection.Assembly.ReflectionOnlyLoadFrom(System.String)?displayProperty=nameWithType> | <span data-ttu-id="6387d-246">Все</span><span class="sxs-lookup"><span data-stu-id="6387d-246">All</span></span> |
| <xref:System.Reflection.AssemblyName.GetObjectData(System.Runtime.Serialization.SerializationInfo,System.Runtime.Serialization.StreamingContext)?displayProperty=nameWithType> | <span data-ttu-id="6387d-247">Все</span><span class="sxs-lookup"><span data-stu-id="6387d-247">All</span></span> |
| <xref:System.Reflection.AssemblyName.OnDeserialization(System.Object)?displayProperty=nameWithType> | <span data-ttu-id="6387d-248">Все</span><span class="sxs-lookup"><span data-stu-id="6387d-248">All</span></span> |
| <xref:System.Reflection.StrongNameKeyPair.%23ctor(System.String)> | <span data-ttu-id="6387d-249">Все</span><span class="sxs-lookup"><span data-stu-id="6387d-249">All</span></span> |
| <xref:System.Reflection.StrongNameKeyPair.%23ctor(System.Runtime.Serialization.SerializationInfo,System.Runtime.Serialization.StreamingContext)> | <span data-ttu-id="6387d-250">Все</span><span class="sxs-lookup"><span data-stu-id="6387d-250">All</span></span> |
| <xref:System.Reflection.StrongNameKeyPair.PublicKey?displayProperty=nameWithType> | <span data-ttu-id="6387d-251">Все</span><span class="sxs-lookup"><span data-stu-id="6387d-251">All</span></span> |

## <a name="systemruntimecompilerservices"></a><span data-ttu-id="6387d-252">System.Runtime.CompilerServices</span><span class="sxs-lookup"><span data-stu-id="6387d-252">System.Runtime.CompilerServices</span></span>

| <span data-ttu-id="6387d-253">Участник</span><span class="sxs-lookup"><span data-stu-id="6387d-253">Member</span></span> | <span data-ttu-id="6387d-254">Платформы, которые вызывают исключение</span><span class="sxs-lookup"><span data-stu-id="6387d-254">Platforms that throw</span></span> |
| - | - |
| <xref:System.Runtime.CompilerServices.DebugInfoGenerator.CreatePdbGenerator?displayProperty=nameWithType> | <span data-ttu-id="6387d-255">Все</span><span class="sxs-lookup"><span data-stu-id="6387d-255">All</span></span> |

## <a name="systemruntimeinteropservices"></a><span data-ttu-id="6387d-256">System.Runtime.InteropServices</span><span class="sxs-lookup"><span data-stu-id="6387d-256">System.Runtime.InteropServices</span></span>

| <span data-ttu-id="6387d-257">Участник</span><span class="sxs-lookup"><span data-stu-id="6387d-257">Member</span></span> | <span data-ttu-id="6387d-258">Платформы, которые вызывают исключение</span><span class="sxs-lookup"><span data-stu-id="6387d-258">Platforms that throw</span></span> |
| - | - |
| <xref:System.Runtime.InteropServices.Marshal.GetIDispatchForObject(System.Object)?displayProperty=nameWithType> | <span data-ttu-id="6387d-259">Все</span><span class="sxs-lookup"><span data-stu-id="6387d-259">All</span></span> |
| <xref:System.Runtime.InteropServices.RuntimeEnvironment.SystemConfigurationFile?displayProperty=nameWithType> | <span data-ttu-id="6387d-260">Все</span><span class="sxs-lookup"><span data-stu-id="6387d-260">All</span></span> |
| <xref:System.Runtime.InteropServices.RuntimeEnvironment.GetRuntimeInterfaceAsIntPtr(System.Guid,System.Guid)?displayProperty=nameWithType> | <span data-ttu-id="6387d-261">Все</span><span class="sxs-lookup"><span data-stu-id="6387d-261">All</span></span> |
| <xref:System.Runtime.InteropServices.RuntimeEnvironment.GetRuntimeInterfaceAsObject(System.Guid,System.Guid)?displayProperty=nameWithType> | <span data-ttu-id="6387d-262">Все</span><span class="sxs-lookup"><span data-stu-id="6387d-262">All</span></span> |
| <xref:System.Runtime.InteropServices.WindowsRuntime.WindowsRuntimeMarshal.StringToHString(System.String)?displayProperty=nameWithType> | <span data-ttu-id="6387d-263">Linux и macOS</span><span class="sxs-lookup"><span data-stu-id="6387d-263">Linux and macOS</span></span> |
| <xref:System.Runtime.InteropServices.WindowsRuntime.WindowsRuntimeMarshal.PtrToStringHString(System.IntPtr)?displayProperty=nameWithType> | <span data-ttu-id="6387d-264">Linux и macOS</span><span class="sxs-lookup"><span data-stu-id="6387d-264">Linux and macOS</span></span> |
| <xref:System.Runtime.InteropServices.WindowsRuntime.WindowsRuntimeMarshal.FreeHString(System.IntPtr)?displayProperty=nameWithType> | <span data-ttu-id="6387d-265">Linux и macOS</span><span class="sxs-lookup"><span data-stu-id="6387d-265">Linux and macOS</span></span> |

## <a name="systemruntimeserialization"></a><span data-ttu-id="6387d-266">System.Runtime.Serialization</span><span class="sxs-lookup"><span data-stu-id="6387d-266">System.Runtime.Serialization</span></span>

| <span data-ttu-id="6387d-267">Участник</span><span class="sxs-lookup"><span data-stu-id="6387d-267">Member</span></span> | <span data-ttu-id="6387d-268">Платформы, которые вызывают исключение</span><span class="sxs-lookup"><span data-stu-id="6387d-268">Platforms that throw</span></span> |
| - | - |
| <xref:System.Runtime.Serialization.XsdDataContractExporter.Schemas?displayProperty=nameWithType> | <span data-ttu-id="6387d-269">Все</span><span class="sxs-lookup"><span data-stu-id="6387d-269">All</span></span> |

## <a name="systemsecurity"></a><span data-ttu-id="6387d-270">System.Security</span><span class="sxs-lookup"><span data-stu-id="6387d-270">System.Security</span></span>

| <span data-ttu-id="6387d-271">Участник</span><span class="sxs-lookup"><span data-stu-id="6387d-271">Member</span></span> | <span data-ttu-id="6387d-272">Платформы, которые вызывают исключение</span><span class="sxs-lookup"><span data-stu-id="6387d-272">Platforms that throw</span></span> |
| - | - |
| <xref:System.Security.CodeAccessPermission.Deny?displayProperty=nameWithType> | <span data-ttu-id="6387d-273">Все</span><span class="sxs-lookup"><span data-stu-id="6387d-273">All</span></span> |
| <xref:System.Security.CodeAccessPermission.PermitOnly?displayProperty=nameWithType> | <span data-ttu-id="6387d-274">Все</span><span class="sxs-lookup"><span data-stu-id="6387d-274">All</span></span> |
| <xref:System.Security.PermissionSet.ConvertPermissionSet(System.String,System.Byte[],System.String)?displayProperty=nameWithType> | <span data-ttu-id="6387d-275">Все</span><span class="sxs-lookup"><span data-stu-id="6387d-275">All</span></span> |
| <xref:System.Security.PermissionSet.Deny?displayProperty=nameWithType> | <span data-ttu-id="6387d-276">Все</span><span class="sxs-lookup"><span data-stu-id="6387d-276">All</span></span> |
| <xref:System.Security.PermissionSet.PermitOnly?displayProperty=nameWithType> | <span data-ttu-id="6387d-277">Все</span><span class="sxs-lookup"><span data-stu-id="6387d-277">All</span></span> |
| <xref:System.Security.SecurityContext.Capture?displayProperty=nameWithType> | <span data-ttu-id="6387d-278">Все</span><span class="sxs-lookup"><span data-stu-id="6387d-278">All</span></span> |
| <xref:System.Security.SecurityContext.CreateCopy?displayProperty=nameWithType> | <span data-ttu-id="6387d-279">Все</span><span class="sxs-lookup"><span data-stu-id="6387d-279">All</span></span> |
| <xref:System.Security.SecurityContext.Dispose?displayProperty=nameWithType> | <span data-ttu-id="6387d-280">Все</span><span class="sxs-lookup"><span data-stu-id="6387d-280">All</span></span> |
| <xref:System.Security.SecurityContext.IsFlowSuppressed?displayProperty=nameWithType> | <span data-ttu-id="6387d-281">Все</span><span class="sxs-lookup"><span data-stu-id="6387d-281">All</span></span> |
| <xref:System.Security.SecurityContext.IsWindowsIdentityFlowSuppressed?displayProperty=nameWithType> | <span data-ttu-id="6387d-282">Все</span><span class="sxs-lookup"><span data-stu-id="6387d-282">All</span></span> |
| <xref:System.Security.SecurityContext.RestoreFlow?displayProperty=nameWithType> | <span data-ttu-id="6387d-283">Все</span><span class="sxs-lookup"><span data-stu-id="6387d-283">All</span></span> |
| <xref:System.Security.SecurityContext.Run(System.Security.SecurityContext,System.Threading.ContextCallback,System.Object)?displayProperty=nameWithType> | <span data-ttu-id="6387d-284">Все</span><span class="sxs-lookup"><span data-stu-id="6387d-284">All</span></span> |
| <xref:System.Security.SecurityContext.SuppressFlow?displayProperty=nameWithType> | <span data-ttu-id="6387d-285">Все</span><span class="sxs-lookup"><span data-stu-id="6387d-285">All</span></span> |
| <xref:System.Security.SecurityContext.SuppressFlowWindowsIdentity?displayProperty=nameWithType> | <span data-ttu-id="6387d-286">Все</span><span class="sxs-lookup"><span data-stu-id="6387d-286">All</span></span> |

## <a name="systemsecurityclaims"></a><span data-ttu-id="6387d-287">System.Security.Claims</span><span class="sxs-lookup"><span data-stu-id="6387d-287">System.Security.Claims</span></span>

| <span data-ttu-id="6387d-288">Участник</span><span class="sxs-lookup"><span data-stu-id="6387d-288">Member</span></span> | <span data-ttu-id="6387d-289">Платформы, которые вызывают исключение</span><span class="sxs-lookup"><span data-stu-id="6387d-289">Platforms that throw</span></span> |
| - | - |
| <xref:System.Security.Claims.ClaimsPrincipal.%23ctor> | <span data-ttu-id="6387d-290">Все</span><span class="sxs-lookup"><span data-stu-id="6387d-290">All</span></span> |
| <xref:System.Security.Claims.ClaimsPrincipal.GetObjectData(System.Runtime.Serialization.SerializationInfo,System.Runtime.Serialization.StreamingContext)?displayProperty=nameWithType> | <span data-ttu-id="6387d-291">Все</span><span class="sxs-lookup"><span data-stu-id="6387d-291">All</span></span> |
| <xref:System.Security.Claims.ClaimsIdentity.%23ctor(System.Runtime.Serialization.SerializationInfo)> | <span data-ttu-id="6387d-292">Все</span><span class="sxs-lookup"><span data-stu-id="6387d-292">All</span></span> |
| <xref:System.Security.Claims.ClaimsIdentity.%23ctor(System.Runtime.Serialization.SerializationInfo,System.Runtime.Serialization.StreamingContext)> | <span data-ttu-id="6387d-293">Все</span><span class="sxs-lookup"><span data-stu-id="6387d-293">All</span></span> |
| <xref:System.Security.Claims.ClaimsIdentity.GetObjectData(System.Runtime.Serialization.SerializationInfo,System.Runtime.Serialization.StreamingContext)?displayProperty=nameWithType> | <span data-ttu-id="6387d-294">Все</span><span class="sxs-lookup"><span data-stu-id="6387d-294">All</span></span> |

## <a name="systemsecuritycryptography"></a><span data-ttu-id="6387d-295">System.Security.Cryptography</span><span class="sxs-lookup"><span data-stu-id="6387d-295">System.Security.Cryptography</span></span>

| <span data-ttu-id="6387d-296">Участник</span><span class="sxs-lookup"><span data-stu-id="6387d-296">Member</span></span> | <span data-ttu-id="6387d-297">Платформы, которые вызывают исключение</span><span class="sxs-lookup"><span data-stu-id="6387d-297">Platforms that throw</span></span> |
| - | - |
| <xref:System.Security.Cryptography.AsymmetricAlgorithm.Create(System.String)?displayProperty=nameWithType> | <span data-ttu-id="6387d-298">Все</span><span class="sxs-lookup"><span data-stu-id="6387d-298">All</span></span> |
| <xref:System.Security.Cryptography.CspKeyContainerInfo.%23ctor%2A> | <span data-ttu-id="6387d-299">Linux и macOS</span><span class="sxs-lookup"><span data-stu-id="6387d-299">Linux and macOS</span></span> |
| <xref:System.Security.Cryptography.CspKeyContainerInfo.Accessible?displayProperty=nameWithType> | <span data-ttu-id="6387d-300">Linux и macOS</span><span class="sxs-lookup"><span data-stu-id="6387d-300">Linux and macOS</span></span> |
| <xref:System.Security.Cryptography.CspKeyContainerInfo.Exportable?displayProperty=nameWithType> | <span data-ttu-id="6387d-301">Linux и macOS</span><span class="sxs-lookup"><span data-stu-id="6387d-301">Linux and macOS</span></span> |
| <xref:System.Security.Cryptography.CspKeyContainerInfo.HardwareDevice?displayProperty=nameWithType> | <span data-ttu-id="6387d-302">Linux и macOS</span><span class="sxs-lookup"><span data-stu-id="6387d-302">Linux and macOS</span></span> |
| <xref:System.Security.Cryptography.CspKeyContainerInfo.KeyContainerName?displayProperty=nameWithType> | <span data-ttu-id="6387d-303">Linux и macOS</span><span class="sxs-lookup"><span data-stu-id="6387d-303">Linux and macOS</span></span> |
| <xref:System.Security.Cryptography.CspKeyContainerInfo.KeyNumber?displayProperty=nameWithType> | <span data-ttu-id="6387d-304">Linux и macOS</span><span class="sxs-lookup"><span data-stu-id="6387d-304">Linux and macOS</span></span> |
| <xref:System.Security.Cryptography.CspKeyContainerInfo.MachineKeyStore?displayProperty=nameWithType> | <span data-ttu-id="6387d-305">Linux и macOS</span><span class="sxs-lookup"><span data-stu-id="6387d-305">Linux and macOS</span></span> |
| <xref:System.Security.Cryptography.CspKeyContainerInfo.Protected?displayProperty=nameWithType> | <span data-ttu-id="6387d-306">Linux и macOS</span><span class="sxs-lookup"><span data-stu-id="6387d-306">Linux and macOS</span></span> |
| <xref:System.Security.Cryptography.CspKeyContainerInfo.ProviderName?displayProperty=nameWithType> | <span data-ttu-id="6387d-307">Linux и macOS</span><span class="sxs-lookup"><span data-stu-id="6387d-307">Linux and macOS</span></span> |
| <xref:System.Security.Cryptography.CspKeyContainerInfo.ProviderType?displayProperty=nameWithType> | <span data-ttu-id="6387d-308">Linux и macOS</span><span class="sxs-lookup"><span data-stu-id="6387d-308">Linux and macOS</span></span> |
| <xref:System.Security.Cryptography.CspKeyContainerInfo.RandomlyGenerated?displayProperty=nameWithType> | <span data-ttu-id="6387d-309">Linux и macOS</span><span class="sxs-lookup"><span data-stu-id="6387d-309">Linux and macOS</span></span> |
| <xref:System.Security.Cryptography.CspKeyContainerInfo.Removable?displayProperty=nameWithType> | <span data-ttu-id="6387d-310">Linux и macOS</span><span class="sxs-lookup"><span data-stu-id="6387d-310">Linux and macOS</span></span> |
| <xref:System.Security.Cryptography.CspKeyContainerInfo.UniqueKeyContainerName?displayProperty=nameWithType> | <span data-ttu-id="6387d-311">Linux и macOS</span><span class="sxs-lookup"><span data-stu-id="6387d-311">Linux and macOS</span></span> |
| <xref:System.Security.Cryptography.HashAlgorithm.Create?displayProperty=nameWithType> | <span data-ttu-id="6387d-312">Все</span><span class="sxs-lookup"><span data-stu-id="6387d-312">All</span></span> |
| <xref:System.Security.Cryptography.HMAC.Create?displayProperty=nameWithType> | <span data-ttu-id="6387d-313">Все</span><span class="sxs-lookup"><span data-stu-id="6387d-313">All</span></span> |
| <xref:System.Security.Cryptography.HMAC.Create(System.String)?displayProperty=nameWithType> | <span data-ttu-id="6387d-314">Все</span><span class="sxs-lookup"><span data-stu-id="6387d-314">All</span></span> |
| <xref:System.Security.Cryptography.HMAC.HashCore%2A?displayProperty=nameWithType> | <span data-ttu-id="6387d-315">Все</span><span class="sxs-lookup"><span data-stu-id="6387d-315">All</span></span> |
| <xref:System.Security.Cryptography.HMAC.HashFinal%2A?displayProperty=nameWithType> | <span data-ttu-id="6387d-316">Все</span><span class="sxs-lookup"><span data-stu-id="6387d-316">All</span></span> |
| <xref:System.Security.Cryptography.HMAC.Initialize%2A?displayProperty=nameWithType> | <span data-ttu-id="6387d-317">Все</span><span class="sxs-lookup"><span data-stu-id="6387d-317">All</span></span> |
| <xref:System.Security.Cryptography.KeyedHashAlgorithm.Create?displayProperty=nameWithType> | <span data-ttu-id="6387d-318">Все</span><span class="sxs-lookup"><span data-stu-id="6387d-318">All</span></span> |
| <xref:System.Security.Cryptography.KeyedHashAlgorithm.Create(System.String)?displayProperty=nameWithType> | <span data-ttu-id="6387d-319">Все</span><span class="sxs-lookup"><span data-stu-id="6387d-319">All</span></span> |
| <xref:System.Security.Cryptography.ProtectedData.Protect%2A?displayProperty=nameWithType> | <span data-ttu-id="6387d-320">Linux и macOS</span><span class="sxs-lookup"><span data-stu-id="6387d-320">Linux and macOS</span></span> |
| <xref:System.Security.Cryptography.ProtectedData.Unprotect%2A?displayProperty=nameWithType> | <span data-ttu-id="6387d-321">Linux и macOS</span><span class="sxs-lookup"><span data-stu-id="6387d-321">Linux and macOS</span></span> |
| <xref:System.Security.Cryptography.RSA.FromXmlString%2A?displayProperty=nameWithType> | <span data-ttu-id="6387d-322">Все</span><span class="sxs-lookup"><span data-stu-id="6387d-322">All</span></span> |
| <xref:System.Security.Cryptography.RSA.ToXmlString%2A?displayProperty=nameWithType> | <span data-ttu-id="6387d-323">Все</span><span class="sxs-lookup"><span data-stu-id="6387d-323">All</span></span> |
| <xref:System.Security.Cryptography.SymmetricAlgorithm.Create?displayProperty=nameWithType> | <span data-ttu-id="6387d-324">Все</span><span class="sxs-lookup"><span data-stu-id="6387d-324">All</span></span> |
| <xref:System.Security.Cryptography.SymmetricAlgorithm.Create(System.String)?displayProperty=nameWithType> | <span data-ttu-id="6387d-325">Все</span><span class="sxs-lookup"><span data-stu-id="6387d-325">All</span></span> |

## <a name="systemsecuritycryptographypkcs"></a><span data-ttu-id="6387d-326">System.Security.Cryptography.Pkcs</span><span class="sxs-lookup"><span data-stu-id="6387d-326">System.Security.Cryptography.Pkcs</span></span>

| <span data-ttu-id="6387d-327">Участник</span><span class="sxs-lookup"><span data-stu-id="6387d-327">Member</span></span> | <span data-ttu-id="6387d-328">Платформы, которые вызывают исключение</span><span class="sxs-lookup"><span data-stu-id="6387d-328">Platforms that throw</span></span> |
| - | - |
| <xref:System.Security.Cryptography.Pkcs.CmsSigner.%23ctor(System.Security.Cryptography.CspParameters)> | <span data-ttu-id="6387d-329">Все</span><span class="sxs-lookup"><span data-stu-id="6387d-329">All</span></span> |
| <xref:System.Security.Cryptography.Pkcs.SignedCms.ComputeSignature(System.Security.Cryptography.Pkcs.CmsSigner,System.Boolean)?displayProperty=nameWithType> | <span data-ttu-id="6387d-330">Все</span><span class="sxs-lookup"><span data-stu-id="6387d-330">All</span></span> |
| <xref:System.Security.Cryptography.Pkcs.SignerInfo.ComputeCounterSignature?displayProperty=nameWithType> | <span data-ttu-id="6387d-331">Все</span><span class="sxs-lookup"><span data-stu-id="6387d-331">All</span></span> |

## <a name="systemsecuritycryptographyx509certificates"></a><span data-ttu-id="6387d-332">System.Security.Cryptography.X509Certificates</span><span class="sxs-lookup"><span data-stu-id="6387d-332">System.Security.Cryptography.X509Certificates</span></span>

| <span data-ttu-id="6387d-333">Участник</span><span class="sxs-lookup"><span data-stu-id="6387d-333">Member</span></span> | <span data-ttu-id="6387d-334">Платформы, которые вызывают исключение</span><span class="sxs-lookup"><span data-stu-id="6387d-334">Platforms that throw</span></span> |
| - | - |
| <xref:System.Security.Cryptography.X509Certificates.X509Certificate.%23ctor(System.Runtime.Serialization.SerializationInfo,System.Runtime.Serialization.StreamingContext)> | <span data-ttu-id="6387d-335">Все</span><span class="sxs-lookup"><span data-stu-id="6387d-335">All</span></span> |
| <xref:System.Security.Cryptography.X509Certificates.X509Certificate.Import%2A?displayProperty=nameWithType> | <span data-ttu-id="6387d-336">Все</span><span class="sxs-lookup"><span data-stu-id="6387d-336">All</span></span> |
| <xref:System.Security.Cryptography.X509Certificates.X509Certificate2.%23ctor(System.Runtime.Serialization.SerializationInfo,System.Runtime.Serialization.StreamingContext)> | <span data-ttu-id="6387d-337">Все</span><span class="sxs-lookup"><span data-stu-id="6387d-337">All</span></span> |
| <span data-ttu-id="6387d-338"><xref:System.Security.Cryptography.X509Certificates.X509Certificate2.PrivateKey?displayProperty=nameWithType> (только установка)</span><span class="sxs-lookup"><span data-stu-id="6387d-338"><xref:System.Security.Cryptography.X509Certificates.X509Certificate2.PrivateKey?displayProperty=nameWithType> (set only)</span></span> | <span data-ttu-id="6387d-339">Все</span><span class="sxs-lookup"><span data-stu-id="6387d-339">All</span></span> |

## <a name="systemsecurityauthenticationextendedprotection"></a><span data-ttu-id="6387d-340">System.Security.Authentication.ExtendedProtection</span><span class="sxs-lookup"><span data-stu-id="6387d-340">System.Security.Authentication.ExtendedProtection</span></span>

| <span data-ttu-id="6387d-341">Участник</span><span class="sxs-lookup"><span data-stu-id="6387d-341">Member</span></span> | <span data-ttu-id="6387d-342">Платформы, которые вызывают исключение</span><span class="sxs-lookup"><span data-stu-id="6387d-342">Platforms that throw</span></span> |
| - | - |
| <xref:System.Security.Authentication.ExtendedProtection.ExtendedProtectionPolicy.%23ctor(System.Runtime.Serialization.SerializationInfo,System.Runtime.Serialization.StreamingContext)> | <span data-ttu-id="6387d-343">Все</span><span class="sxs-lookup"><span data-stu-id="6387d-343">All</span></span> |

## <a name="systemsecuritypolicy"></a><span data-ttu-id="6387d-344">System.Security.Policy</span><span class="sxs-lookup"><span data-stu-id="6387d-344">System.Security.Policy</span></span>

| <span data-ttu-id="6387d-345">Участник</span><span class="sxs-lookup"><span data-stu-id="6387d-345">Member</span></span> | <span data-ttu-id="6387d-346">Платформы, которые вызывают исключение</span><span class="sxs-lookup"><span data-stu-id="6387d-346">Platforms that throw</span></span> |
| - | - |
| <xref:System.Security.Policy.Hash.GetObjectData(System.Runtime.Serialization.SerializationInfo,System.Runtime.Serialization.StreamingContext)?displayProperty=nameWithType> | <span data-ttu-id="6387d-347">Все</span><span class="sxs-lookup"><span data-stu-id="6387d-347">All</span></span> |

## <a name="systemserviceprocessservicecontroller"></a><span data-ttu-id="6387d-348">System.ServiceProcess.ServiceController</span><span class="sxs-lookup"><span data-stu-id="6387d-348">System.ServiceProcess.ServiceController</span></span>

| <span data-ttu-id="6387d-349">Участник</span><span class="sxs-lookup"><span data-stu-id="6387d-349">Member</span></span> | <span data-ttu-id="6387d-350">Платформы, которые вызывают исключение</span><span class="sxs-lookup"><span data-stu-id="6387d-350">Platforms that throw</span></span> |
| - | - |
| <xref:System.ServiceProcess.TimeoutException.%23ctor(System.Runtime.Serialization.SerializationInfo,System.Runtime.Serialization.StreamingContext)> | <span data-ttu-id="6387d-351">Все</span><span class="sxs-lookup"><span data-stu-id="6387d-351">All</span></span> |

## <a name="systemtextregularexpressions"></a><span data-ttu-id="6387d-352">System.Text.RegularExpressions</span><span class="sxs-lookup"><span data-stu-id="6387d-352">System.Text.RegularExpressions</span></span>

| <span data-ttu-id="6387d-353">Участник</span><span class="sxs-lookup"><span data-stu-id="6387d-353">Member</span></span> | <span data-ttu-id="6387d-354">Платформы, которые вызывают исключение</span><span class="sxs-lookup"><span data-stu-id="6387d-354">Platforms that throw</span></span> |
| - | - |
| <xref:System.Text.RegularExpressions.Regex.CompileToAssembly%2A?displayProperty=nameWithType> | <span data-ttu-id="6387d-355">Все</span><span class="sxs-lookup"><span data-stu-id="6387d-355">All</span></span> |

## <a name="systemthreading"></a><span data-ttu-id="6387d-356">System.Threading</span><span class="sxs-lookup"><span data-stu-id="6387d-356">System.Threading</span></span>

| <span data-ttu-id="6387d-357">Участник</span><span class="sxs-lookup"><span data-stu-id="6387d-357">Member</span></span> | <span data-ttu-id="6387d-358">Платформы, которые вызывают исключение</span><span class="sxs-lookup"><span data-stu-id="6387d-358">Platforms that throw</span></span> |
| - | - |
| <xref:System.Threading.CompressedStack.GetObjectData(System.Runtime.Serialization.SerializationInfo,System.Runtime.Serialization.StreamingContext)?displayProperty=nameWithType> | <span data-ttu-id="6387d-359">Все</span><span class="sxs-lookup"><span data-stu-id="6387d-359">All</span></span> |
| <xref:System.Threading.ExecutionContext.GetObjectData(System.Runtime.Serialization.SerializationInfo,System.Runtime.Serialization.StreamingContext)?displayProperty=nameWithType> | <span data-ttu-id="6387d-360">Все</span><span class="sxs-lookup"><span data-stu-id="6387d-360">All</span></span> |
| <xref:System.Threading.Thread.Abort%2A?displayProperty=nameWithType> | <span data-ttu-id="6387d-361">Все</span><span class="sxs-lookup"><span data-stu-id="6387d-361">All</span></span> |
| <xref:System.Threading.Thread.ResetAbort?displayProperty=nameWithType> | <span data-ttu-id="6387d-362">Все</span><span class="sxs-lookup"><span data-stu-id="6387d-362">All</span></span> |
| <xref:System.Threading.Thread.Resume?displayProperty=nameWithType> | <span data-ttu-id="6387d-363">Все</span><span class="sxs-lookup"><span data-stu-id="6387d-363">All</span></span> |
| <xref:System.Threading.Thread.Suspend?displayProperty=nameWithType> | <span data-ttu-id="6387d-364">Все</span><span class="sxs-lookup"><span data-stu-id="6387d-364">All</span></span> |

## <a name="systemxml"></a><span data-ttu-id="6387d-365">System.Xml</span><span class="sxs-lookup"><span data-stu-id="6387d-365">System.Xml</span></span>

| <span data-ttu-id="6387d-366">Участник</span><span class="sxs-lookup"><span data-stu-id="6387d-366">Member</span></span> | <span data-ttu-id="6387d-367">Платформы, которые вызывают исключение</span><span class="sxs-lookup"><span data-stu-id="6387d-367">Platforms that throw</span></span> |
| - | - |
| <xref:System.Xml.XmlDictionaryReader.CreateMtomReader(System.Byte[],System.Int32,System.Int32,System.Text.Encoding[],System.String,System.Xml.XmlDictionaryReaderQuotas,System.Int32,System.Xml.OnXmlDictionaryReaderClose)?displayProperty=nameWithType> | <span data-ttu-id="6387d-368">Все</span><span class="sxs-lookup"><span data-stu-id="6387d-368">All</span></span> |
| <xref:System.Xml.XmlDictionaryReader.CreateMtomReader(System.IO.Stream,System.Text.Encoding[],System.String,System.Xml.XmlDictionaryReaderQuotas,System.Int32,System.Xml.OnXmlDictionaryReaderClose)?displayProperty=nameWithType> | <span data-ttu-id="6387d-369">Все</span><span class="sxs-lookup"><span data-stu-id="6387d-369">All</span></span> |
| <xref:System.Xml.XmlDictionaryWriter.CreateMtomWriter(System.IO.Stream,System.Text.Encoding,System.Int32,System.String,System.String,System.String,System.Boolean,System.Boolean)?displayProperty=nameWithType> | <span data-ttu-id="6387d-370">Все</span><span class="sxs-lookup"><span data-stu-id="6387d-370">All</span></span> |

## <a name="see-also"></a><span data-ttu-id="6387d-371">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="6387d-371">See also</span></span>

- [<span data-ttu-id="6387d-372">Критические изменения для миграции с .NET Framework на .NET Core</span><span class="sxs-lookup"><span data-stu-id="6387d-372">Breaking changes for migration from .NET Framework to .NET Core</span></span>](fx-core.md)
- [<span data-ttu-id="6387d-373">Двоичная сериализация в .NET Core</span><span class="sxs-lookup"><span data-stu-id="6387d-373">Binary serialization in .NET Core</span></span>](../../standard/serialization/binary-serialization.md#net-core)
- [<span data-ttu-id="6387d-374">Анализатор переносимости .NET</span><span class="sxs-lookup"><span data-stu-id="6387d-374">.NET portability analyzer</span></span>](../../standard/analyzers/portability-analyzer.md)
