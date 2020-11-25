---
title: Функция CreateCordbObject
ms.date: 03/30/2017
api_name:
- CreateCoredbObject
api_location:
- mscordbi_macx86.dll
api_type:
- COM
f1_keywords:
- CreateCordbObject
helpviewer_keywords:
- remote debugging API [Silverlight]
- CreateCordbObject function
- Silverlight, remote debugging
ms.assetid: b259821d-4fa7-464d-85cf-304dfffc8089
topic_type:
- apiref
ms.openlocfilehash: eccdfcb60b2d2b5d652ccac948c01c16e7cb828d
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/24/2020
ms.locfileid: "95725980"
---
# <a name="createcordbobject-function"></a><span data-ttu-id="d4d0c-102">Функция CreateCordbObject</span><span class="sxs-lookup"><span data-stu-id="d4d0c-102">CreateCordbObject Function</span></span>

<span data-ttu-id="d4d0c-103">Создает интерфейс отладчика ([ICorDebug](icordebug-interface.md)), который предоставляет функциональные возможности для создания экземпляра управляемого сеанса отладки на удаленном процессе.</span><span class="sxs-lookup"><span data-stu-id="d4d0c-103">Creates a debugger interface ([ICorDebug](icordebug-interface.md)) that provides functionality for instantiating a managed debugging session on a remote process.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d4d0c-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="d4d0c-104">Syntax</span></span>  
  
```cpp  
HRESULT CordbCreateObject (  
       [in]  int         iDebuggerVersion,
       [out] IUnknown**  ppCordb  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="d4d0c-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="d4d0c-105">Parameters</span></span>  

 `iDebuggerVersion`  
 <span data-ttu-id="d4d0c-106">[in] Версия отладчика целевого процесса.</span><span class="sxs-lookup"><span data-stu-id="d4d0c-106">[in] Debugger version of the target process.</span></span> <span data-ttu-id="d4d0c-107">Для удаленной отладки этот параметр должен иметь значение CorDebugVersion_2_0.</span><span class="sxs-lookup"><span data-stu-id="d4d0c-107">This parameter must be CorDebugVersion_2_0 for remote debugging.</span></span>  
  
 `ppCordb`  
 <span data-ttu-id="d4d0c-108">заполняет Указатель на указатель на объект, который будет приведен к интерфейсу [ICorDebug](icordebug-interface.md) и возвращен.</span><span class="sxs-lookup"><span data-stu-id="d4d0c-108">[out] Pointer to a pointer to an object that will be cast to an [ICorDebug](icordebug-interface.md) interface and returned.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="d4d0c-109">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="d4d0c-109">Return Value</span></span>  

 <span data-ttu-id="d4d0c-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="d4d0c-110">S_OK</span></span>  
 <span data-ttu-id="d4d0c-111">Количество сред CLR в процессе успешно определено, и соответствующие массивы дескрипторов и путей заполнены должным образом.</span><span class="sxs-lookup"><span data-stu-id="d4d0c-111">The number of CLRs in the process was successfully determined, and the corresponding handle and path arrays were properly filled.</span></span>  
  
 <span data-ttu-id="d4d0c-112">E_INVALIDARG</span><span class="sxs-lookup"><span data-stu-id="d4d0c-112">E_INVALIDARG</span></span>  
 <span data-ttu-id="d4d0c-113">Параметр `ppCordb` имеет значение null, или параметр `iDebuggerVersion` не имеет значение CorDebugVersion_2_0.</span><span class="sxs-lookup"><span data-stu-id="d4d0c-113">`ppCordb` is null, or `iDebuggerVersion` is not CorDebugVersion_2_0.</span></span>  
  
 <span data-ttu-id="d4d0c-114">E_OUTOFMEMORY</span><span class="sxs-lookup"><span data-stu-id="d4d0c-114">E_OUTOFMEMORY</span></span>  
 <span data-ttu-id="d4d0c-115">Не удается выделить достаточно памяти для `ppCordb`.</span><span class="sxs-lookup"><span data-stu-id="d4d0c-115">Unable to allocate enough memory for `ppCordb`</span></span>  
  
 <span data-ttu-id="d4d0c-116">E_FAIL (или другие коды возврата E_)</span><span class="sxs-lookup"><span data-stu-id="d4d0c-116">E_FAIL (or other E_ return codes)</span></span>  
 <span data-ttu-id="d4d0c-117">Прочие сбои.</span><span class="sxs-lookup"><span data-stu-id="d4d0c-117">Other failures.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="d4d0c-118">Комментарии</span><span class="sxs-lookup"><span data-stu-id="d4d0c-118">Remarks</span></span>  

 <span data-ttu-id="d4d0c-119">Интерфейс [ICorDebug](icordebug-interface.md) , возвращаемый в, `ppCordb` является интерфейсом отладки верхнего уровня для всех управляемых служб отладки.</span><span class="sxs-lookup"><span data-stu-id="d4d0c-119">The [ICorDebug](icordebug-interface.md) interface that is returned in `ppCordb` is the top-level debugging interface for all managed debugging services.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d4d0c-120">Требования</span><span class="sxs-lookup"><span data-stu-id="d4d0c-120">Requirements</span></span>  

 <span data-ttu-id="d4d0c-121">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="d4d0c-121">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d4d0c-122">**Заголовок:** Кореклрремотедебуггингинтерфацес. h</span><span class="sxs-lookup"><span data-stu-id="d4d0c-122">**Header:** CoreClrRemoteDebuggingInterfaces.h</span></span>  
  
 <span data-ttu-id="d4d0c-123">**Библиотека:** mscordbi_macx86.dll</span><span class="sxs-lookup"><span data-stu-id="d4d0c-123">**Library:** mscordbi_macx86.dll</span></span>  
  
 <span data-ttu-id="d4d0c-124">**.NET Framework версии:** 3,5 SP1</span><span class="sxs-lookup"><span data-stu-id="d4d0c-124">**.NET Framework Versions:** 3.5 SP1</span></span>
