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
ms.openlocfilehash: 8d88222215eb31e1c63f3b26079517c4b088e81b
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/24/2020
ms.locfileid: "95728840"
---
# <a name="iclrruntimehost-interface"></a><span data-ttu-id="8a74c-102">Интерфейс ICLRRuntimeHost</span><span class="sxs-lookup"><span data-stu-id="8a74c-102">ICLRRuntimeHost Interface</span></span>

<span data-ttu-id="8a74c-103">Предоставляет функциональные возможности, аналогичные интерфейсу [ICorRuntimeHost](icorruntimehost-interface.md) , предоставленному в .NET Framework версии 1, со следующими изменениями:</span><span class="sxs-lookup"><span data-stu-id="8a74c-103">Provides functionality similar to that of the [ICorRuntimeHost](icorruntimehost-interface.md) interface provided in the .NET Framework version 1, with the following changes:</span></span>  
  
- <span data-ttu-id="8a74c-104">Добавление метода [SetHostControl](iclrruntimehost-sethostcontrol-method.md) для задания интерфейса элемента управления ведущего приложения.</span><span class="sxs-lookup"><span data-stu-id="8a74c-104">The addition of the [SetHostControl](iclrruntimehost-sethostcontrol-method.md) method to set the host control interface.</span></span>  
  
- <span data-ttu-id="8a74c-105">Пропуск некоторых методов, предоставляемых `ICorRuntimeHost` .</span><span class="sxs-lookup"><span data-stu-id="8a74c-105">The omission of some methods provided by `ICorRuntimeHost`.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="8a74c-106">Методы</span><span class="sxs-lookup"><span data-stu-id="8a74c-106">Methods</span></span>  
  
|<span data-ttu-id="8a74c-107">Метод</span><span class="sxs-lookup"><span data-stu-id="8a74c-107">Method</span></span>|<span data-ttu-id="8a74c-108">Описание</span><span class="sxs-lookup"><span data-stu-id="8a74c-108">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="8a74c-109">Метод ExecuteApplication</span><span class="sxs-lookup"><span data-stu-id="8a74c-109">ExecuteApplication Method</span></span>](iclrruntimehost-executeapplication-method.md)|<span data-ttu-id="8a74c-110">Используется в сценариях развертывания ClickOnce на основе манифеста для указания приложения, которое должно быть активировано в новом домене.</span><span class="sxs-lookup"><span data-stu-id="8a74c-110">Used in manifest-based ClickOnce deployment scenarios to specify the application to be activated in a new domain.</span></span>|  
|[<span data-ttu-id="8a74c-111">Метод ExecuteInAppDomain</span><span class="sxs-lookup"><span data-stu-id="8a74c-111">ExecuteInAppDomain Method</span></span>](iclrruntimehost-executeinappdomain-method.md)|<span data-ttu-id="8a74c-112">Указывает, <xref:System.AppDomain> в котором следует выполнить указанный управляемый код.</span><span class="sxs-lookup"><span data-stu-id="8a74c-112">Specifies the <xref:System.AppDomain> in which to execute the specified managed code.</span></span>|  
|[<span data-ttu-id="8a74c-113">Метод ExecuteInDefaultAppDomain</span><span class="sxs-lookup"><span data-stu-id="8a74c-113">ExecuteInDefaultAppDomain Method</span></span>](iclrruntimehost-executeindefaultappdomain-method.md)|<span data-ttu-id="8a74c-114">Вызывает указанный метод указанного типа в указанной сборке.</span><span class="sxs-lookup"><span data-stu-id="8a74c-114">Invokes the specified method of the specified type in the specified assembly.</span></span>|  
|[<span data-ttu-id="8a74c-115">Метод GetCLRControl</span><span class="sxs-lookup"><span data-stu-id="8a74c-115">GetCLRControl Method</span></span>](iclrruntimehost-getclrcontrol-method.md)|<span data-ttu-id="8a74c-116">Возвращает указатель интерфейса типа [ICLRControl](iclrcontrol-interface.md) , который может использоваться узлами для настройки аспектов среды CLR.</span><span class="sxs-lookup"><span data-stu-id="8a74c-116">Gets an interface pointer of type [ICLRControl](iclrcontrol-interface.md) that hosts can use to customize aspects of the common language runtime (CLR).</span></span>|  
|[<span data-ttu-id="8a74c-117">Метод GetCurrentAppDomainId</span><span class="sxs-lookup"><span data-stu-id="8a74c-117">GetCurrentAppDomainId Method</span></span>](iclrruntimehost-getcurrentappdomainid-method.md)|<span data-ttu-id="8a74c-118">Возвращает числовой идентификатор объекта <xref:System.AppDomain> , который выполняется в данный момент.</span><span class="sxs-lookup"><span data-stu-id="8a74c-118">Gets the numeric identifier of the <xref:System.AppDomain> that is currently executing.</span></span>|  
|[<span data-ttu-id="8a74c-119">Метод SetHostControl</span><span class="sxs-lookup"><span data-stu-id="8a74c-119">SetHostControl Method</span></span>](iclrruntimehost-sethostcontrol-method.md)|<span data-ttu-id="8a74c-120">Задает интерфейс элемента управления ведущего приложения.</span><span class="sxs-lookup"><span data-stu-id="8a74c-120">Sets the host control interface.</span></span> <span data-ttu-id="8a74c-121">`SetHostControl`Перед вызовом необходимо вызвать `Start` .</span><span class="sxs-lookup"><span data-stu-id="8a74c-121">You must call `SetHostControl` before calling `Start`.</span></span>|  
|[<span data-ttu-id="8a74c-122">Метод Start</span><span class="sxs-lookup"><span data-stu-id="8a74c-122">Start Method</span></span>](iclrruntimehost-start-method.md)|<span data-ttu-id="8a74c-123">Инициализирует среду CLR в процессе.</span><span class="sxs-lookup"><span data-stu-id="8a74c-123">Initializes the CLR into a process.</span></span>|  
|[<span data-ttu-id="8a74c-124">Метод Stop</span><span class="sxs-lookup"><span data-stu-id="8a74c-124">Stop Method</span></span>](iclrruntimehost-stop-method.md)|<span data-ttu-id="8a74c-125">Останавливает выполнение кода средой выполнения.</span><span class="sxs-lookup"><span data-stu-id="8a74c-125">Stops the execution of code by the runtime.</span></span>|  
|[<span data-ttu-id="8a74c-126">Метод UnloadAppDomain</span><span class="sxs-lookup"><span data-stu-id="8a74c-126">UnloadAppDomain Method</span></span>](iclrruntimehost-unloadappdomain-method.md)|<span data-ttu-id="8a74c-127">Выгружает объект <xref:System.AppDomain> , соответствующий указанному числовому идентификатору.</span><span class="sxs-lookup"><span data-stu-id="8a74c-127">Unloads the <xref:System.AppDomain> that corresponds to the specified numeric identifier.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="8a74c-128">Комментарии</span><span class="sxs-lookup"><span data-stu-id="8a74c-128">Remarks</span></span>  

 <span data-ttu-id="8a74c-129">Начиная с .NET Framework 4, используйте интерфейс [ICLRMetaHost](iclrmetahost-interface.md) для получения указателя на интерфейс [ICLRRuntimeInfo](iclrruntimeinfo-interface.md) , а затем вызовите метод [ICLRRuntimeInfo::-interface](iclrruntimeinfo-getinterface-method.md) , чтобы получить указатель на `ICLRRuntimeHost` .</span><span class="sxs-lookup"><span data-stu-id="8a74c-129">Starting with the .NET Framework 4, use the [ICLRMetaHost](iclrmetahost-interface.md) interface to get a pointer to the [ICLRRuntimeInfo](iclrruntimeinfo-interface.md) interface, and then call the [ICLRRuntimeInfo::GetInterface](iclrruntimeinfo-getinterface-method.md) method to get a pointer to `ICLRRuntimeHost`.</span></span> <span data-ttu-id="8a74c-130">В более ранних версиях .NET Framework узел получает указатель на `ICLRRuntimeHost` экземпляр, вызывая [CorBindToRuntimeEx](corbindtoruntimeex-function.md) или [корбиндтокуррентрунтиме](corbindtocurrentruntime-function.md).</span><span class="sxs-lookup"><span data-stu-id="8a74c-130">In earlier versions of the .NET Framework, the host gets a pointer to an `ICLRRuntimeHost` instance by calling [CorBindToRuntimeEx](corbindtoruntimeex-function.md) or [CorBindToCurrentRuntime](corbindtocurrentruntime-function.md).</span></span> <span data-ttu-id="8a74c-131">Чтобы реализовать реализации любой из технологий, предоставляемых в .NET Framework версии 2,0, необходимо использовать `ICLRRuntimeHost` вместо `ICorRuntimeHost` .</span><span class="sxs-lookup"><span data-stu-id="8a74c-131">To provide implementations of any of the technologies provided in the .NET Framework version 2.0, you must use `ICLRRuntimeHost` instead of `ICorRuntimeHost`.</span></span>  
  
> [!IMPORTANT]
> <span data-ttu-id="8a74c-132">Не вызывайте метод [Start](iclrruntimehost-start-method.md) перед вызовом метода [ExecuteApplication](iclrruntimehost-executeapplication-method.md) для активации приложения на основе манифеста.</span><span class="sxs-lookup"><span data-stu-id="8a74c-132">Do not call the [Start](iclrruntimehost-start-method.md) method before calling the [ExecuteApplication](iclrruntimehost-executeapplication-method.md) method to activate a manifest-based application.</span></span> <span data-ttu-id="8a74c-133">Если `Start` метод вызывается первым, `ExecuteApplication` вызов метода завершится ошибкой.</span><span class="sxs-lookup"><span data-stu-id="8a74c-133">If the `Start` method is called first, the `ExecuteApplication` method call will fail.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="8a74c-134">Требования</span><span class="sxs-lookup"><span data-stu-id="8a74c-134">Requirements</span></span>  

 <span data-ttu-id="8a74c-135">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="8a74c-135">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="8a74c-136">**Заголовок:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="8a74c-136">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="8a74c-137">**Библиотека:** Включается в качестве ресурса в MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="8a74c-137">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="8a74c-138">**.NET Framework версии:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="8a74c-138">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8a74c-139">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="8a74c-139">See also</span></span>

- [<span data-ttu-id="8a74c-140">Функция CorBindToCurrentRuntime</span><span class="sxs-lookup"><span data-stu-id="8a74c-140">CorBindToCurrentRuntime Function</span></span>](corbindtocurrentruntime-function.md)
- [<span data-ttu-id="8a74c-141">Функция CorBindToRuntimeEx</span><span class="sxs-lookup"><span data-stu-id="8a74c-141">CorBindToRuntimeEx Function</span></span>](corbindtoruntimeex-function.md)
- [<span data-ttu-id="8a74c-142">Интерфейс ICLRControl</span><span class="sxs-lookup"><span data-stu-id="8a74c-142">ICLRControl Interface</span></span>](iclrcontrol-interface.md)
- [<span data-ttu-id="8a74c-143">Интерфейс ICorRuntimeHost</span><span class="sxs-lookup"><span data-stu-id="8a74c-143">ICorRuntimeHost Interface</span></span>](icorruntimehost-interface.md)
- [<span data-ttu-id="8a74c-144">Интерфейсы размещения</span><span class="sxs-lookup"><span data-stu-id="8a74c-144">Hosting Interfaces</span></span>](hosting-interfaces.md)
- [<span data-ttu-id="8a74c-145">Кокласс CLRRuntimeHost</span><span class="sxs-lookup"><span data-stu-id="8a74c-145">CLRRuntimeHost Coclass</span></span>](clrruntimehost-coclass.md)
