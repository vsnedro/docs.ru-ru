---
title: Функция CreateDebuggingInterfaceFromVersion
ms.date: 03/30/2017
api_name:
- CreateDebuggingInterfaceFromVersion
api_location:
- mscoree.dll
- mscoreei.dll
api_type:
- DLLExport
f1_keywords:
- CreateDebuggingInterfaceFromVersion
helpviewer_keywords:
- CreateDebuggingInterfaceFromVersion function [.NET Framework hosting]
ms.assetid: a746a849-463c-44f5-a2f0-9e812ed8bcc3
topic_type:
- apiref
ms.openlocfilehash: b68fbc713374642c9f55d49ee51a88c5785cf4b2
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/24/2020
ms.locfileid: "95727878"
---
# <a name="createdebugginginterfacefromversion-function"></a><span data-ttu-id="308b1-102">Функция CreateDebuggingInterfaceFromVersion</span><span class="sxs-lookup"><span data-stu-id="308b1-102">CreateDebuggingInterfaceFromVersion Function</span></span>

<span data-ttu-id="308b1-103">Создает объект [ICorDebug](../debugging/icordebug-interface.md) на основе указанных сведений о версии.</span><span class="sxs-lookup"><span data-stu-id="308b1-103">Creates an [ICorDebug](../debugging/icordebug-interface.md) object based on the specified version information.</span></span>  
  
 <span data-ttu-id="308b1-104">Эта функция является устаревшей в .NET Framework 4.</span><span class="sxs-lookup"><span data-stu-id="308b1-104">This function is obsolete in the .NET Framework 4.</span></span> <span data-ttu-id="308b1-105">Вместо этого для получения интерфейса для среды CLR 2,0 используйте метод [ICLRRuntimeInfo::](iclrruntimeinfo-getinterface-method.md) coclass и укажите идентификатор класса CLSID_CLRDebuggingLegacy и идентификатор интерфейса IID_ICorDebug.</span><span class="sxs-lookup"><span data-stu-id="308b1-105">Instead, to get an interface for the common language runtime (CLR) 2.0, use the [ICLRRuntimeInfo::GetInterface](iclrruntimeinfo-getinterface-method.md) method and specify the class identifier CLSID_CLRDebuggingLegacy and the interface identifier IID_ICorDebug.</span></span> <span data-ttu-id="308b1-106">Чтобы получить интерфейс для CLR 4 или более поздней версии, вызовите функцию [клркреатеинстанце](clrcreateinstance-function.md) и укажите идентификатор класса CLSID_CLRDebugging и идентификатор интерфейса IID_ICLRDebugging.</span><span class="sxs-lookup"><span data-stu-id="308b1-106">To get an interface for CLR 4 or later, call the [CLRCreateInstance](clrcreateinstance-function.md) function and specify the class identifier CLSID_CLRDebugging and the interface identifier IID_ICLRDebugging.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="308b1-107">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="308b1-107">Syntax</span></span>  
  
```cpp  
HRESULT CreateDebuggingInterfaceFromVersion (  
    [in]  int      iDebuggerVersion,
    [in]  LPCWSTR  szDebuggeeVersion,
    [out] IUnknown **ppCordb  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="308b1-108">Параметры</span><span class="sxs-lookup"><span data-stu-id="308b1-108">Parameters</span></span>  

 `iDebuggerVersion`  
 <span data-ttu-id="308b1-109">окне Версия `ICorDebug` , ожидаемая отладчиком.</span><span class="sxs-lookup"><span data-stu-id="308b1-109">[in] The version of `ICorDebug` that is expected by the debugger.</span></span> <span data-ttu-id="308b1-110">Допустимые значения см. в описании перечисления [CorDebugInterfaceVersion](../debugging/cordebuginterfaceversion-enumeration.md) .</span><span class="sxs-lookup"><span data-stu-id="308b1-110">See the [CorDebugInterfaceVersion](../debugging/cordebuginterfaceversion-enumeration.md) enumeration for valid values.</span></span>  
  
 `szDebuggeeVersion`  
 <span data-ttu-id="308b1-111">окне Версия среды CLR, связанная с приложением или процессом для отладки.</span><span class="sxs-lookup"><span data-stu-id="308b1-111">[in] The common language runtime version associated with the application or process to be debugged.</span></span> <span data-ttu-id="308b1-112">Сведения о получении этого значения см. в описании метода [GetVersionFromProcess](getversionfromprocess-function.md) или [жетрекуестедрунтимеверсион](getrequestedruntimeversion-function.md) .</span><span class="sxs-lookup"><span data-stu-id="308b1-112">See the [GetVersionFromProcess](getversionfromprocess-function.md) or [GetRequestedRuntimeVersion](getrequestedruntimeversion-function.md) method for information on retrieving this value.</span></span>  
  
 `ppCordb`  
 <span data-ttu-id="308b1-113">заполняет Расположение, которое получает указатель на `ICorDebug` объект.</span><span class="sxs-lookup"><span data-stu-id="308b1-113">[out] The location that receives a pointer to the `ICorDebug` object.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="308b1-114">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="308b1-114">Return Value</span></span>  

 <span data-ttu-id="308b1-115">Этот метод возвращает стандартные коды ошибок COM, определенные в файле WinError. h, а также следующие значения.</span><span class="sxs-lookup"><span data-stu-id="308b1-115">This method returns standard COM error codes as defined in the WinError.h file in addition to the following values.</span></span>  
  
|<span data-ttu-id="308b1-116">Код возврата</span><span class="sxs-lookup"><span data-stu-id="308b1-116">Return code</span></span>|<span data-ttu-id="308b1-117">Описание</span><span class="sxs-lookup"><span data-stu-id="308b1-117">Description</span></span>|  
|-----------------|-----------------|  
|<span data-ttu-id="308b1-118">S_OK</span><span class="sxs-lookup"><span data-stu-id="308b1-118">S_OK</span></span>|<span data-ttu-id="308b1-119">Метод завершился успешно.</span><span class="sxs-lookup"><span data-stu-id="308b1-119">The method completed successfully.</span></span>|  
|<span data-ttu-id="308b1-120">E_INVALIDARG</span><span class="sxs-lookup"><span data-stu-id="308b1-120">E_INVALIDARG</span></span>|<span data-ttu-id="308b1-121">`szDebuggeeVersion` или `ppCordb` имеет значение null, или строка версии неверна.</span><span class="sxs-lookup"><span data-stu-id="308b1-121">`szDebuggeeVersion` or `ppCordb` is null, or the version string is incorrect.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="308b1-122">Комментарии</span><span class="sxs-lookup"><span data-stu-id="308b1-122">Remarks</span></span>  

 <span data-ttu-id="308b1-123">`szDebuggeeVersion`Параметр сопоставляется с соответствующей версией MSCorDbi.dll.</span><span class="sxs-lookup"><span data-stu-id="308b1-123">The `szDebuggeeVersion` parameter maps to the corresponding version of MSCorDbi.dll.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="308b1-124">Требования</span><span class="sxs-lookup"><span data-stu-id="308b1-124">Requirements</span></span>  

 <span data-ttu-id="308b1-125">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="308b1-125">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="308b1-126">**Заголовок:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="308b1-126">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="308b1-127">**Библиотека:** MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="308b1-127">**Library:** MSCorEE.dll</span></span>  
  
 <span data-ttu-id="308b1-128">**.NET Framework версии:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="308b1-128">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="308b1-129">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="308b1-129">See also</span></span>

- [<span data-ttu-id="308b1-130">Устаревшие функции размещения CLR</span><span class="sxs-lookup"><span data-stu-id="308b1-130">Deprecated CLR Hosting Functions</span></span>](deprecated-clr-hosting-functions.md)
