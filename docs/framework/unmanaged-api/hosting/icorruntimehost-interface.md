---
title: Интерфейс ICorRuntimeHost
ms.date: 03/30/2017
api_name:
- ICorRuntimeHost
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICorRuntimeHost
helpviewer_keywords:
- ICorRuntimeHost interface [.NET Framework hosting]
ms.assetid: 4369533d-7834-4497-bc37-bfea0ad737b1
topic_type:
- apiref
ms.openlocfilehash: 9fcb5e189af9f72de7635aad550a5e8ab5522dbd
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/24/2020
ms.locfileid: "95720624"
---
# <a name="icorruntimehost-interface"></a><span data-ttu-id="45e79-102">Интерфейс ICorRuntimeHost</span><span class="sxs-lookup"><span data-stu-id="45e79-102">ICorRuntimeHost Interface</span></span>

<span data-ttu-id="45e79-103">Предоставляет методы, позволяющие основному приложению запускать и прекращать работу среды CLR, создавать и настраивать домены приложений, получать доступ к домену по умолчанию и перечислять все домены, выполняющиеся в процессе.</span><span class="sxs-lookup"><span data-stu-id="45e79-103">Provides methods that enable the host to start and stop the common language runtime (CLR) explicitly, to create and configure application domains, to access the default domain, and to enumerate all domains running in the process.</span></span>  
  
 <span data-ttu-id="45e79-104">В .NET Framework версии 2,0 этот интерфейс заменен [ICLRRuntimeHost](iclrruntimehost-interface.md).</span><span class="sxs-lookup"><span data-stu-id="45e79-104">In the .NET Framework version 2.0, this interface is superceded by [ICLRRuntimeHost](iclrruntimehost-interface.md).</span></span>  
  
## <a name="methods"></a><span data-ttu-id="45e79-105">Методы</span><span class="sxs-lookup"><span data-stu-id="45e79-105">Methods</span></span>  
  
|<span data-ttu-id="45e79-106">Метод</span><span class="sxs-lookup"><span data-stu-id="45e79-106">Method</span></span>|<span data-ttu-id="45e79-107">Описание</span><span class="sxs-lookup"><span data-stu-id="45e79-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="45e79-108">Метод CloseEnum</span><span class="sxs-lookup"><span data-stu-id="45e79-108">CloseEnum Method</span></span>](icorruntimehost-closeenum-method.md)|<span data-ttu-id="45e79-109">Сбрасывает перечислитель домена обратно в начало списка доменов.</span><span class="sxs-lookup"><span data-stu-id="45e79-109">Resets a domain enumerator back to the beginning of the domain list.</span></span>|  
|[<span data-ttu-id="45e79-110">Метод CreateDomain</span><span class="sxs-lookup"><span data-stu-id="45e79-110">CreateDomain Method</span></span>](icorruntimehost-createdomain-method.md)|<span data-ttu-id="45e79-111">Создает домен приложения.</span><span class="sxs-lookup"><span data-stu-id="45e79-111">Creates an application domain.</span></span> <span data-ttu-id="45e79-112">Вызывающий объект получает указатель интерфейса типа <xref:System._AppDomain> на экземпляр типа <xref:System.AppDomain?displayProperty=nameWithType> .</span><span class="sxs-lookup"><span data-stu-id="45e79-112">The caller receives an interface pointer of type <xref:System._AppDomain> to an instance of type <xref:System.AppDomain?displayProperty=nameWithType>.</span></span>|  
|[<span data-ttu-id="45e79-113">Метод CreateDomainEx</span><span class="sxs-lookup"><span data-stu-id="45e79-113">CreateDomainEx Method</span></span>](icorruntimehost-createdomainex-method.md)|<span data-ttu-id="45e79-114">Создает домен приложения.</span><span class="sxs-lookup"><span data-stu-id="45e79-114">Creates an application domain.</span></span> <span data-ttu-id="45e79-115">Этот метод позволяет вызывающему объекту передать экземпляр IAppDomainSetup для настройки дополнительных функций возвращаемого <xref:System._AppDomain> экземпляра.</span><span class="sxs-lookup"><span data-stu-id="45e79-115">This method allows the caller to pass an IAppDomainSetup instance to configure additional features of the returned <xref:System._AppDomain> instance.</span></span>|  
|[<span data-ttu-id="45e79-116">Метод CreateDomainSetup</span><span class="sxs-lookup"><span data-stu-id="45e79-116">CreateDomainSetup Method</span></span>](icorruntimehost-createdomainsetup-method.md)|<span data-ttu-id="45e79-117">Возвращает указатель интерфейса типа `IAppDomainSetup` на <xref:System.AppDomainSetup> экземпляр.</span><span class="sxs-lookup"><span data-stu-id="45e79-117">Gets an interface pointer of type `IAppDomainSetup` to an <xref:System.AppDomainSetup> instance.</span></span> <span data-ttu-id="45e79-118">`IAppDomainSetup` предоставляет методы для настройки аспектов домена приложения перед его созданием.</span><span class="sxs-lookup"><span data-stu-id="45e79-118">`IAppDomainSetup` provides methods to configure aspects of an application domain before it is created.</span></span>|  
|[<span data-ttu-id="45e79-119">Метод CreateEvidence</span><span class="sxs-lookup"><span data-stu-id="45e79-119">CreateEvidence Method</span></span>](icorruntimehost-createevidence-method.md)|<span data-ttu-id="45e79-120">Возвращает указатель интерфейса типа <xref:System.Security.Principal.IIdentity> , который позволяет основному приложению создавать доказательства безопасности для передачи в [CreateDomain](icorruntimehost-createdomain-method.md) или [CreateDomainEx](icorruntimehost-createdomainex-method.md).</span><span class="sxs-lookup"><span data-stu-id="45e79-120">Gets an interface pointer of type <xref:System.Security.Principal.IIdentity>, which allows the host to create security evidence to pass to [CreateDomain](icorruntimehost-createdomain-method.md) or [CreateDomainEx](icorruntimehost-createdomainex-method.md).</span></span>|  
|[<span data-ttu-id="45e79-121">Метод CreateLogicalThreadState</span><span class="sxs-lookup"><span data-stu-id="45e79-121">CreateLogicalThreadState Method</span></span>](icorruntimehost-createlogicalthreadstate-method.md)|<span data-ttu-id="45e79-122">Не используется.</span><span class="sxs-lookup"><span data-stu-id="45e79-122">Do not use.</span></span>|  
|[<span data-ttu-id="45e79-123">Метод CurrentDomain</span><span class="sxs-lookup"><span data-stu-id="45e79-123">CurrentDomain Method</span></span>](icorruntimehost-currentdomain-method.md)|<span data-ttu-id="45e79-124">Возвращает указатель интерфейса типа <xref:System._AppDomain> , который представляет домен, загруженный в текущем потоке.</span><span class="sxs-lookup"><span data-stu-id="45e79-124">Gets an interface pointer of type <xref:System._AppDomain> that represents the domain loaded on the current thread.</span></span>|  
|[<span data-ttu-id="45e79-125">Метод DeleteLogicalThreadState</span><span class="sxs-lookup"><span data-stu-id="45e79-125">DeleteLogicalThreadState Method</span></span>](icorruntimehost-deletelogicalthreadstate-method.md)|<span data-ttu-id="45e79-126">Не используется.</span><span class="sxs-lookup"><span data-stu-id="45e79-126">Do not use.</span></span>|  
|[<span data-ttu-id="45e79-127">Метод EnumDomains</span><span class="sxs-lookup"><span data-stu-id="45e79-127">EnumDomains Method</span></span>](icorruntimehost-enumdomains-method.md)|<span data-ttu-id="45e79-128">Возвращает перечислитель для доменов в текущем процессе.</span><span class="sxs-lookup"><span data-stu-id="45e79-128">Gets an enumerator for the domains in the current process.</span></span>|  
|[<span data-ttu-id="45e79-129">Метод настройки</span><span class="sxs-lookup"><span data-stu-id="45e79-129">GetConfiguration Method</span></span>](icorruntimehost-getconfiguration-method.md)|<span data-ttu-id="45e79-130">Возвращает объект, позволяющий ведущему приложению указать конфигурацию обратного вызова среды CLR.</span><span class="sxs-lookup"><span data-stu-id="45e79-130">Gets an object that allows the host to specify the callback configuration of the CLR.</span></span>|  
|[<span data-ttu-id="45e79-131">Метод GetDefaultDomain</span><span class="sxs-lookup"><span data-stu-id="45e79-131">GetDefaultDomain Method</span></span>](icorruntimehost-getdefaultdomain-method.md)|<span data-ttu-id="45e79-132">Возвращает указатель интерфейса типа <xref:System._AppDomain> , представляющий домен по умолчанию для текущего процесса.</span><span class="sxs-lookup"><span data-stu-id="45e79-132">Gets an interface pointer of type <xref:System._AppDomain> that represents the default domain for the current process.</span></span>|  
|[<span data-ttu-id="45e79-133">Метод LocksHeldByLogicalThread</span><span class="sxs-lookup"><span data-stu-id="45e79-133">LocksHeldByLogicalThread Method</span></span>](icorruntimehost-locksheldbylogicalthread-method.md)|<span data-ttu-id="45e79-134">Не используется.</span><span class="sxs-lookup"><span data-stu-id="45e79-134">Do not use.</span></span>|  
|[<span data-ttu-id="45e79-135">Метод MapFile</span><span class="sxs-lookup"><span data-stu-id="45e79-135">MapFile Method</span></span>](icorruntimehost-mapfile-method.md)|<span data-ttu-id="45e79-136">Сопоставляет указанный файл с памятью.</span><span class="sxs-lookup"><span data-stu-id="45e79-136">Maps the specified file into memory.</span></span> <span data-ttu-id="45e79-137">Этот метод устарел.</span><span class="sxs-lookup"><span data-stu-id="45e79-137">This method is obsolete.</span></span>|  
|[<span data-ttu-id="45e79-138">Метод NextDomain</span><span class="sxs-lookup"><span data-stu-id="45e79-138">NextDomain Method</span></span>](icorruntimehost-nextdomain-method.md)|<span data-ttu-id="45e79-139">Возвращает указатель интерфейса на следующий домен в перечислении.</span><span class="sxs-lookup"><span data-stu-id="45e79-139">Gets an interface pointer to the next domain in the enumeration.</span></span>|  
|[<span data-ttu-id="45e79-140">Метод Start</span><span class="sxs-lookup"><span data-stu-id="45e79-140">Start Method</span></span>](icorruntimehost-start-method.md)|<span data-ttu-id="45e79-141">Запускает среду CLR.</span><span class="sxs-lookup"><span data-stu-id="45e79-141">Starts the CLR.</span></span>|  
|[<span data-ttu-id="45e79-142">Метод Stop</span><span class="sxs-lookup"><span data-stu-id="45e79-142">Stop Method</span></span>](icorruntimehost-stop-method.md)|<span data-ttu-id="45e79-143">Останавливает выполнение кода в среде выполнения для текущего процесса.</span><span class="sxs-lookup"><span data-stu-id="45e79-143">Stops the execution of code in the runtime for the current process.</span></span>|  
|[<span data-ttu-id="45e79-144">Метод SwitchInLogicalThreadState</span><span class="sxs-lookup"><span data-stu-id="45e79-144">SwitchInLogicalThreadState Method</span></span>](icorruntimehost-switchinlogicalthreadstate-method.md)|<span data-ttu-id="45e79-145">Не используется.</span><span class="sxs-lookup"><span data-stu-id="45e79-145">Do not use.</span></span>|  
|[<span data-ttu-id="45e79-146">Метод SwitchOutLogicalThreadState</span><span class="sxs-lookup"><span data-stu-id="45e79-146">SwitchOutLogicalThreadState Method</span></span>](icorruntimehost-switchoutlogicalthreadstate-method.md)|<span data-ttu-id="45e79-147">Не используется.</span><span class="sxs-lookup"><span data-stu-id="45e79-147">Do not use.</span></span>|  
|[<span data-ttu-id="45e79-148">Метод UnloadDomain</span><span class="sxs-lookup"><span data-stu-id="45e79-148">UnloadDomain Method</span></span>](icorruntimehost-unloaddomain-method.md)|<span data-ttu-id="45e79-149">Выгружает указанный домен приложения из текущего процесса.</span><span class="sxs-lookup"><span data-stu-id="45e79-149">Unloads the specified application domain from the current process.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="45e79-150">Требования</span><span class="sxs-lookup"><span data-stu-id="45e79-150">Requirements</span></span>  

 <span data-ttu-id="45e79-151">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="45e79-151">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="45e79-152">**Заголовок:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="45e79-152">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="45e79-153">**Библиотека:** Включается в качестве ресурса в MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="45e79-153">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="45e79-154">**.NET Framework версии:** 1,0, 1,1</span><span class="sxs-lookup"><span data-stu-id="45e79-154">**.NET Framework Versions:** 1.0, 1.1</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="45e79-155">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="45e79-155">See also</span></span>

- <xref:System.AppDomain>
- [<span data-ttu-id="45e79-156">Размещение</span><span class="sxs-lookup"><span data-stu-id="45e79-156">Hosting</span></span>](index.md)
- [<span data-ttu-id="45e79-157">Интерфейс ICLRRuntimeHost</span><span class="sxs-lookup"><span data-stu-id="45e79-157">ICLRRuntimeHost Interface</span></span>](iclrruntimehost-interface.md)
- <span data-ttu-id="45e79-158">[Хост-приложения среды выполнения](/previous-versions/dotnet/netframework-4.0/a51xd4ze(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="45e79-158">[Runtime Hosts](/previous-versions/dotnet/netframework-4.0/a51xd4ze(v=vs.100))</span></span>
- [<span data-ttu-id="45e79-159">Интерфейсы размещения</span><span class="sxs-lookup"><span data-stu-id="45e79-159">Hosting Interfaces</span></span>](hosting-interfaces.md)
- [<span data-ttu-id="45e79-160">Компонентный класс CorRuntimeHost</span><span class="sxs-lookup"><span data-stu-id="45e79-160">CorRuntimeHost Coclass</span></span>](corruntimehost-coclass.md)
