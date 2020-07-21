---
title: События безопасности (трассировка событий Windows)
description: Ознакомьтесь с событиями ETW безопасности, которые возникают во время проверки строгого имени и проверки Authenticode в .NET.
ms.date: 03/30/2017
helpviewer_keywords:
- security events [.NET Framework]
- ETW, security events (CLR)
ms.assetid: 0ed69f73-5c01-4514-bd63-979c6e38d41d
ms.openlocfilehash: 2fd2d450223cd16a7791b8f6c67afe6bcb954eb3
ms.sourcegitcommit: cf5a800a33de64d0aad6d115ffcc935f32375164
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/20/2020
ms.locfileid: "86474219"
---
# <a name="security-etw-events"></a><span data-ttu-id="a6fa6-103">События безопасности (трассировка событий Windows)</span><span class="sxs-lookup"><span data-stu-id="a6fa6-103">Security ETW Events</span></span>

<span data-ttu-id="a6fa6-104">События безопасности создаются при проверке строгого имени и проверке Authenticode.</span><span class="sxs-lookup"><span data-stu-id="a6fa6-104">Security events are raised during strong name verification and Authenticode verification.</span></span>  

## <a name="strongnameverificationstart_v1-and-strongnameverificationstop_v1-events"></a><span data-ttu-id="a6fa6-105">События StrongNameVerificationStart_V1 и StrongNameVerificationStop_V1</span><span class="sxs-lookup"><span data-stu-id="a6fa6-105">StrongNameVerificationStart_V1 and StrongNameVerificationStop_V1 Events</span></span>  
 <span data-ttu-id="a6fa6-106">В таблице ниже показаны ключевое слово и уровень.</span><span class="sxs-lookup"><span data-stu-id="a6fa6-106">The following table shows the keyword and level.</span></span> <span data-ttu-id="a6fa6-107">(Дополнительные сведения см. в разделе [CLR ETW Keywords and Levels](clr-etw-keywords-and-levels.md).)</span><span class="sxs-lookup"><span data-stu-id="a6fa6-107">(For more information, see [CLR ETW Keywords and Levels](clr-etw-keywords-and-levels.md).)</span></span>  
  
|<span data-ttu-id="a6fa6-108">Ключевое слово для вызова события</span><span class="sxs-lookup"><span data-stu-id="a6fa6-108">Keyword for raising the event</span></span>|<span data-ttu-id="a6fa6-109">Level</span><span class="sxs-lookup"><span data-stu-id="a6fa6-109">Level</span></span>|  
|-----------------------------------|-----------|  
|<span data-ttu-id="a6fa6-110">`SecurityKeyword` (0x400)</span><span class="sxs-lookup"><span data-stu-id="a6fa6-110">`SecurityKeyword` (0x400)</span></span>|<span data-ttu-id="a6fa6-111">Информационный (4)</span><span class="sxs-lookup"><span data-stu-id="a6fa6-111">Informational(4)</span></span>|  
  
 <span data-ttu-id="a6fa6-112">В таблице ниже представлены сведения о событии.</span><span class="sxs-lookup"><span data-stu-id="a6fa6-112">The following table shows the event information.</span></span>  
  
|<span data-ttu-id="a6fa6-113">Событие</span><span class="sxs-lookup"><span data-stu-id="a6fa6-113">Event</span></span>|<span data-ttu-id="a6fa6-114">Идентификатор события</span><span class="sxs-lookup"><span data-stu-id="a6fa6-114">Event ID</span></span>|<span data-ttu-id="a6fa6-115">Условие вызова</span><span class="sxs-lookup"><span data-stu-id="a6fa6-115">Raised when</span></span>|  
|-----------|--------------|-----------------|  
|`StrongNameVerificationStart_V1`|<span data-ttu-id="a6fa6-116">181</span><span class="sxs-lookup"><span data-stu-id="a6fa6-116">181</span></span>|<span data-ttu-id="a6fa6-117">Начало проверки строгого имени.</span><span class="sxs-lookup"><span data-stu-id="a6fa6-117">Start of strong name verification.</span></span>|  
|`StrongNameVerificationStop_V1`|<span data-ttu-id="a6fa6-118">182</span><span class="sxs-lookup"><span data-stu-id="a6fa6-118">182</span></span>|<span data-ttu-id="a6fa6-119">Окончание проверки строгого имени.</span><span class="sxs-lookup"><span data-stu-id="a6fa6-119">End of strong name verification.</span></span>|  
  
 <span data-ttu-id="a6fa6-120">В таблице ниже представлены данные события.</span><span class="sxs-lookup"><span data-stu-id="a6fa6-120">The following table shows the event data.</span></span>  
  
|<span data-ttu-id="a6fa6-121">Имя поля</span><span class="sxs-lookup"><span data-stu-id="a6fa6-121">Field name</span></span>|<span data-ttu-id="a6fa6-122">Тип данных</span><span class="sxs-lookup"><span data-stu-id="a6fa6-122">Data type</span></span>|<span data-ttu-id="a6fa6-123">Описание</span><span class="sxs-lookup"><span data-stu-id="a6fa6-123">Description</span></span>|  
|----------------|---------------|-----------------|  
|<span data-ttu-id="a6fa6-124">VerificationFlags</span><span class="sxs-lookup"><span data-stu-id="a6fa6-124">VerificationFlags</span></span>|<span data-ttu-id="a6fa6-125">win:UInt32</span><span class="sxs-lookup"><span data-stu-id="a6fa6-125">win:UInt32</span></span>|<span data-ttu-id="a6fa6-126">Флаги проверки.</span><span class="sxs-lookup"><span data-stu-id="a6fa6-126">The verification flags.</span></span>|  
|<span data-ttu-id="a6fa6-127">ErrorCode</span><span class="sxs-lookup"><span data-stu-id="a6fa6-127">ErrorCode</span></span>|<span data-ttu-id="a6fa6-128">win:UInt32</span><span class="sxs-lookup"><span data-stu-id="a6fa6-128">win:UInt32</span></span>|<span data-ttu-id="a6fa6-129">Код ошибки HResult.</span><span class="sxs-lookup"><span data-stu-id="a6fa6-129">The HResult error code.</span></span>|  
|<span data-ttu-id="a6fa6-130">FullyQualifiedAssemblyName</span><span class="sxs-lookup"><span data-stu-id="a6fa6-130">FullyQualifiedAssemblyName</span></span>|<span data-ttu-id="a6fa6-131">win:UnicodeString</span><span class="sxs-lookup"><span data-stu-id="a6fa6-131">win:UnicodeString</span></span>|<span data-ttu-id="a6fa6-132">Полное имя сборки.</span><span class="sxs-lookup"><span data-stu-id="a6fa6-132">The fully qualified assembly name.</span></span>|  
|<span data-ttu-id="a6fa6-133">ClrInstanceID</span><span class="sxs-lookup"><span data-stu-id="a6fa6-133">ClrInstanceID</span></span>|<span data-ttu-id="a6fa6-134">win:UInt16</span><span class="sxs-lookup"><span data-stu-id="a6fa6-134">win:UInt16</span></span>|<span data-ttu-id="a6fa6-135">Уникальный идентификатор экземпляра CLR или CoreCLR.</span><span class="sxs-lookup"><span data-stu-id="a6fa6-135">Unique ID for the instance of CLR or CoreCLR.</span></span>|  

## <a name="authenticodeverificationstart_v1-and-authenticodeverificationstop_v1-events"></a><span data-ttu-id="a6fa6-136">События AuthenticodeVerificationStart_V1 и AuthenticodeVerificationStop_V1</span><span class="sxs-lookup"><span data-stu-id="a6fa6-136">AuthenticodeVerificationStart_V1 and AuthenticodeVerificationStop_V1 Events</span></span>  
 <span data-ttu-id="a6fa6-137">В таблице ниже показаны ключевое слово и уровень.</span><span class="sxs-lookup"><span data-stu-id="a6fa6-137">The following table shows the keyword and level.</span></span>  
  
|<span data-ttu-id="a6fa6-138">Ключевое слово для вызова события</span><span class="sxs-lookup"><span data-stu-id="a6fa6-138">Keyword for raising the event</span></span>|<span data-ttu-id="a6fa6-139">Level</span><span class="sxs-lookup"><span data-stu-id="a6fa6-139">Level</span></span>|  
|-----------------------------------|-----------|  
|<span data-ttu-id="a6fa6-140">`SecurityKeyword` (0x400)</span><span class="sxs-lookup"><span data-stu-id="a6fa6-140">`SecurityKeyword` (0x400)</span></span>|<span data-ttu-id="a6fa6-141">Информационный (4)</span><span class="sxs-lookup"><span data-stu-id="a6fa6-141">Informational(4)</span></span>|  
  
 <span data-ttu-id="a6fa6-142">В таблице ниже представлены сведения о событии.</span><span class="sxs-lookup"><span data-stu-id="a6fa6-142">The following table shows the event information.</span></span>  
  
|<span data-ttu-id="a6fa6-143">Событие</span><span class="sxs-lookup"><span data-stu-id="a6fa6-143">Event</span></span>|<span data-ttu-id="a6fa6-144">Идентификатор события</span><span class="sxs-lookup"><span data-stu-id="a6fa6-144">Event ID</span></span>|<span data-ttu-id="a6fa6-145">Условие вызова</span><span class="sxs-lookup"><span data-stu-id="a6fa6-145">Raised when</span></span>|  
|-----------|--------------|-----------------|  
|`AuthenticodeVerificationStart_V1`|<span data-ttu-id="a6fa6-146">183</span><span class="sxs-lookup"><span data-stu-id="a6fa6-146">183</span></span>|<span data-ttu-id="a6fa6-147">Начало проверки Authenticode.</span><span class="sxs-lookup"><span data-stu-id="a6fa6-147">Start of Authenticode verification.</span></span>|  
|`AuthenticodeVerificationStop_V1`|<span data-ttu-id="a6fa6-148">184</span><span class="sxs-lookup"><span data-stu-id="a6fa6-148">184</span></span>|<span data-ttu-id="a6fa6-149">Окончание проверки Authenticode.</span><span class="sxs-lookup"><span data-stu-id="a6fa6-149">End of Authenticode verification.</span></span>|  
  
 <span data-ttu-id="a6fa6-150">В таблице ниже представлены данные события.</span><span class="sxs-lookup"><span data-stu-id="a6fa6-150">The following table shows the event data.</span></span>  
  
|<span data-ttu-id="a6fa6-151">Имя поля</span><span class="sxs-lookup"><span data-stu-id="a6fa6-151">Field name</span></span>|<span data-ttu-id="a6fa6-152">Тип данных</span><span class="sxs-lookup"><span data-stu-id="a6fa6-152">Data type</span></span>|<span data-ttu-id="a6fa6-153">Описание</span><span class="sxs-lookup"><span data-stu-id="a6fa6-153">Description</span></span>|  
|----------------|---------------|-----------------|  
|<span data-ttu-id="a6fa6-154">VerificationFlags</span><span class="sxs-lookup"><span data-stu-id="a6fa6-154">VerificationFlags</span></span>|<span data-ttu-id="a6fa6-155">win:UInt32</span><span class="sxs-lookup"><span data-stu-id="a6fa6-155">win:UInt32</span></span>|<span data-ttu-id="a6fa6-156">Флаги проверки.</span><span class="sxs-lookup"><span data-stu-id="a6fa6-156">The verification flags.</span></span>|  
|<span data-ttu-id="a6fa6-157">ErrorCode</span><span class="sxs-lookup"><span data-stu-id="a6fa6-157">ErrorCode</span></span>|<span data-ttu-id="a6fa6-158">win:UInt32</span><span class="sxs-lookup"><span data-stu-id="a6fa6-158">win:UInt32</span></span>|<span data-ttu-id="a6fa6-159">Код ошибки HResult.</span><span class="sxs-lookup"><span data-stu-id="a6fa6-159">The HResult error code.</span></span>|  
|<span data-ttu-id="a6fa6-160">ModulePath</span><span class="sxs-lookup"><span data-stu-id="a6fa6-160">ModulePath</span></span>|<span data-ttu-id="a6fa6-161">win:UnicodeString</span><span class="sxs-lookup"><span data-stu-id="a6fa6-161">win:UnicodeString</span></span>|<span data-ttu-id="a6fa6-162">Путь к модулю.</span><span class="sxs-lookup"><span data-stu-id="a6fa6-162">The module path.</span></span>|  
|<span data-ttu-id="a6fa6-163">ClrInstanceID</span><span class="sxs-lookup"><span data-stu-id="a6fa6-163">ClrInstanceID</span></span>|<span data-ttu-id="a6fa6-164">win:UInt16</span><span class="sxs-lookup"><span data-stu-id="a6fa6-164">win:UInt16</span></span>|<span data-ttu-id="a6fa6-165">Уникальный идентификатор экземпляра CLR или CoreCLR.</span><span class="sxs-lookup"><span data-stu-id="a6fa6-165">Unique ID for the instance of CLR or CoreCLR.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="a6fa6-166">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="a6fa6-166">See also</span></span>

- [<span data-ttu-id="a6fa6-167">События трассировки событий Windows в среде CLR</span><span class="sxs-lookup"><span data-stu-id="a6fa6-167">CLR ETW Events</span></span>](clr-etw-events.md)
