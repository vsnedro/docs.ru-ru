---
title: Интерфейс ICLRRuntimeHost
ms.date: 03/30/2017
api_name:
- ICLRRuntimeHost
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRRuntimeHost
helpviewer_keywords:
- ICLRRuntimeHost interface [.NET Framework hosting]
ms.assetid: cb0c5f65-3791-47bc-b833-2f84f4101ba5
topic_type:
- apiref
ms.openlocfilehash: dd1aa4089a981d82ae1403189343694a065a701d
ms.sourcegitcommit: 0926684d8d34f4c6b5acce58d2193db093cb9cf2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/20/2020
ms.locfileid: "83703661"
---
# <a name="iclrruntimehost-interface"></a><span data-ttu-id="72980-102">Интерфейс ICLRRuntimeHost</span><span class="sxs-lookup"><span data-stu-id="72980-102">ICLRRuntimeHost Interface</span></span>
<span data-ttu-id="72980-103">Предоставляет функциональные возможности, аналогичные интерфейсу [ICorRuntimeHost](icorruntimehost-interface.md) , предоставленному в .NET Framework версии 1, со следующими изменениями:</span><span class="sxs-lookup"><span data-stu-id="72980-103">Provides functionality similar to that of the [ICorRuntimeHost](icorruntimehost-interface.md) interface provided in the .NET Framework version 1, with the following changes:</span></span>  
  
- <span data-ttu-id="72980-104">Добавление метода [SetHostControl](iclrruntimehost-sethostcontrol-method.md) для задания интерфейса элемента управления ведущего приложения.</span><span class="sxs-lookup"><span data-stu-id="72980-104">The addition of the [SetHostControl](iclrruntimehost-sethostcontrol-method.md) method to set the host control interface.</span></span>  
  
- <span data-ttu-id="72980-105">Пропуск некоторых методов, предоставляемых `ICorRuntimeHost` .</span><span class="sxs-lookup"><span data-stu-id="72980-105">The omission of some methods provided by `ICorRuntimeHost`.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="72980-106">Методы</span><span class="sxs-lookup"><span data-stu-id="72980-106">Methods</span></span>  
  
|<span data-ttu-id="72980-107">Метод</span><span class="sxs-lookup"><span data-stu-id="72980-107">Method</span></span>|<span data-ttu-id="72980-108">Описание</span><span class="sxs-lookup"><span data-stu-id="72980-108">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="72980-109">Метод ExecuteApplication</span><span class="sxs-lookup"><span data-stu-id="72980-109">ExecuteApplication Method</span></span>](iclrruntimehost-executeapplication-method.md)|<span data-ttu-id="72980-110">Используется в сценариях развертывания ClickOnce на основе манифеста для указания приложения, которое должно быть активировано в новом домене.</span><span class="sxs-lookup"><span data-stu-id="72980-110">Used in manifest-based ClickOnce deployment scenarios to specify the application to be activated in a new domain.</span></span>|  
|[<span data-ttu-id="72980-111">Метод ExecuteInAppDomain</span><span class="sxs-lookup"><span data-stu-id="72980-111">ExecuteInAppDomain Method</span></span>](iclrruntimehost-executeinappdomain-method.md)|<span data-ttu-id="72980-112">Указывает, <xref:System.AppDomain> в котором следует выполнить указанный управляемый код.</span><span class="sxs-lookup"><span data-stu-id="72980-112">Specifies the <xref:System.AppDomain> in which to execute the specified managed code.</span></span>|  
|[<span data-ttu-id="72980-113">Метод ExecuteInDefaultAppDomain</span><span class="sxs-lookup"><span data-stu-id="72980-113">ExecuteInDefaultAppDomain Method</span></span>](iclrruntimehost-executeindefaultappdomain-method.md)|<span data-ttu-id="72980-114">Вызывает указанный метод указанного типа в указанной сборке.</span><span class="sxs-lookup"><span data-stu-id="72980-114">Invokes the specified method of the specified type in the specified assembly.</span></span>|  
|[<span data-ttu-id="72980-115">Метод GetCLRControl</span><span class="sxs-lookup"><span data-stu-id="72980-115">GetCLRControl Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-getclrcontrol-method.md)|<span data-ttu-id="72980-116">Возвращает указатель интерфейса типа [ICLRControl](iclrcontrol-interface.md) , который может использоваться узлами для настройки аспектов среды CLR.</span><span class="sxs-lookup"><span data-stu-id="72980-116">Gets an interface pointer of type [ICLRControl](iclrcontrol-interface.md) that hosts can use to customize aspects of the common language runtime (CLR).</span></span>|  
|[<span data-ttu-id="72980-117">Метод GetCurrentAppDomainId</span><span class="sxs-lookup"><span data-stu-id="72980-117">GetCurrentAppDomainId Method</span></span>](iclrruntimehost-getcurrentappdomainid-method.md)|<span data-ttu-id="72980-118">Возвращает числовой идентификатор объекта <xref:System.AppDomain> , который выполняется в данный момент.</span><span class="sxs-lookup"><span data-stu-id="72980-118">Gets the numeric identifier of the <xref:System.AppDomain> that is currently executing.</span></span>|  
|[<span data-ttu-id="72980-119">Метод SetHostControl</span><span class="sxs-lookup"><span data-stu-id="72980-119">SetHostControl Method</span></span>](iclrruntimehost-sethostcontrol-method.md)|<span data-ttu-id="72980-120">Задает интерфейс элемента управления ведущего приложения.</span><span class="sxs-lookup"><span data-stu-id="72980-120">Sets the host control interface.</span></span> <span data-ttu-id="72980-121">`SetHostControl`Перед вызовом необходимо вызвать `Start` .</span><span class="sxs-lookup"><span data-stu-id="72980-121">You must call `SetHostControl` before calling `Start`.</span></span>|  
|[<span data-ttu-id="72980-122">Метод Start</span><span class="sxs-lookup"><span data-stu-id="72980-122">Start Method</span></span>](iclrruntimehost-start-method.md)|<span data-ttu-id="72980-123">Инициализирует среду CLR в процессе.</span><span class="sxs-lookup"><span data-stu-id="72980-123">Initializes the CLR into a process.</span></span>|  
|[<span data-ttu-id="72980-124">Метод Stop</span><span class="sxs-lookup"><span data-stu-id="72980-124">Stop Method</span></span>](iclrruntimehost-stop-method.md)|<span data-ttu-id="72980-125">Останавливает выполнение кода средой выполнения.</span><span class="sxs-lookup"><span data-stu-id="72980-125">Stops the execution of code by the runtime.</span></span>|  
|[<span data-ttu-id="72980-126">Метод UnloadAppDomain</span><span class="sxs-lookup"><span data-stu-id="72980-126">UnloadAppDomain Method</span></span>](iclrruntimehost-unloadappdomain-method.md)|<span data-ttu-id="72980-127">Выгружает объект <xref:System.AppDomain> , соответствующий указанному числовому идентификатору.</span><span class="sxs-lookup"><span data-stu-id="72980-127">Unloads the <xref:System.AppDomain> that corresponds to the specified numeric identifier.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="72980-128">Комментарии</span><span class="sxs-lookup"><span data-stu-id="72980-128">Remarks</span></span>  
 <span data-ttu-id="72980-129">Начиная с .NET Framework 4, используйте интерфейс [ICLRMetaHost](../../../../docs/framework/unmanaged-api/hosting/iclrmetahost-interface.md) для получения указателя на интерфейс [ICLRRuntimeInfo](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-interface.md) , а затем вызовите метод [ICLRRuntimeInfo::-interface](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-getinterface-method.md) , чтобы получить указатель на `ICLRRuntimeHost` .</span><span class="sxs-lookup"><span data-stu-id="72980-129">Starting with the .NET Framework 4, use the [ICLRMetaHost](../../../../docs/framework/unmanaged-api/hosting/iclrmetahost-interface.md) interface to get a pointer to the [ICLRRuntimeInfo](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-interface.md) interface, and then call the [ICLRRuntimeInfo::GetInterface](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-getinterface-method.md) method to get a pointer to `ICLRRuntimeHost`.</span></span> <span data-ttu-id="72980-130">В более ранних версиях .NET Framework узел получает указатель на `ICLRRuntimeHost` экземпляр, вызывая [CorBindToRuntimeEx](../../../../docs/framework/unmanaged-api/hosting/corbindtoruntimeex-function.md) или [корбиндтокуррентрунтиме](corbindtocurrentruntime-function.md).</span><span class="sxs-lookup"><span data-stu-id="72980-130">In earlier versions of the .NET Framework, the host gets a pointer to an `ICLRRuntimeHost` instance by calling [CorBindToRuntimeEx](../../../../docs/framework/unmanaged-api/hosting/corbindtoruntimeex-function.md) or [CorBindToCurrentRuntime](corbindtocurrentruntime-function.md).</span></span> <span data-ttu-id="72980-131">Чтобы реализовать реализации любой из технологий, предоставляемых в .NET Framework версии 2,0, необходимо использовать `ICLRRuntimeHost` вместо `ICorRuntimeHost` .</span><span class="sxs-lookup"><span data-stu-id="72980-131">To provide implementations of any of the technologies provided in the .NET Framework version 2.0, you must use `ICLRRuntimeHost` instead of `ICorRuntimeHost`.</span></span>  
  
> [!IMPORTANT]
> <span data-ttu-id="72980-132">Не вызывайте метод [Start](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-start-method.md) перед вызовом метода [ExecuteApplication](iclrruntimehost-executeapplication-method.md) для активации приложения на основе манифеста.</span><span class="sxs-lookup"><span data-stu-id="72980-132">Do not call the [Start](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-start-method.md) method before calling the [ExecuteApplication](iclrruntimehost-executeapplication-method.md) method to activate a manifest-based application.</span></span> <span data-ttu-id="72980-133">Если `Start` метод вызывается первым, `ExecuteApplication` вызов метода завершится ошибкой.</span><span class="sxs-lookup"><span data-stu-id="72980-133">If the `Start` method is called first, the `ExecuteApplication` method call will fail.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="72980-134">Требования</span><span class="sxs-lookup"><span data-stu-id="72980-134">Requirements</span></span>  
 <span data-ttu-id="72980-135">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="72980-135">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="72980-136">**Заголовок:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="72980-136">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="72980-137">**Библиотека:** Включается в качестве ресурса в библиотеку MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="72980-137">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="72980-138">**.NET Framework версии:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="72980-138">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="72980-139">См. также статью</span><span class="sxs-lookup"><span data-stu-id="72980-139">See also</span></span>

- [<span data-ttu-id="72980-140">Функция CorBindToCurrentRuntime</span><span class="sxs-lookup"><span data-stu-id="72980-140">CorBindToCurrentRuntime Function</span></span>](corbindtocurrentruntime-function.md)
- [<span data-ttu-id="72980-141">Функция CorBindToRuntimeEx</span><span class="sxs-lookup"><span data-stu-id="72980-141">CorBindToRuntimeEx Function</span></span>](corbindtoruntimeex-function.md)
- [<span data-ttu-id="72980-142">Интерфейс ICLRControl</span><span class="sxs-lookup"><span data-stu-id="72980-142">ICLRControl Interface</span></span>](iclrcontrol-interface.md)
- [<span data-ttu-id="72980-143">Интерфейс ICorRuntimeHost</span><span class="sxs-lookup"><span data-stu-id="72980-143">ICorRuntimeHost Interface</span></span>](icorruntimehost-interface.md)
- [<span data-ttu-id="72980-144">Интерфейсы размещения</span><span class="sxs-lookup"><span data-stu-id="72980-144">Hosting Interfaces</span></span>](hosting-interfaces.md)
- [<span data-ttu-id="72980-145">Кокласс CLRRuntimeHost</span><span class="sxs-lookup"><span data-stu-id="72980-145">CLRRuntimeHost Coclass</span></span>](clrruntimehost-coclass.md)
