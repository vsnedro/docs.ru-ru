---
title: Функция CreateDebuggingInterfaceFromVersion Silverlight
ms.date: 03/30/2017
f1_keywords:
- CreateDebuggingInterfaceFromVersion
helpviewer_keywords:
- CreateDebuggingInterfaceFromVersion function
- debugging API [Silverlight]
- Silverlight, debugging
ms.assetid: 35c7a18f-133a-4584-bd25-bb338568b0c6
ms.openlocfilehash: f40345b09cae164660711b987f62130518736518
ms.sourcegitcommit: 488aced39b5f374bc0a139a4993616a54d15baf0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/12/2020
ms.locfileid: "83208628"
---
# <a name="createdebugginginterfacefromversion-function-for-silverlight"></a><span data-ttu-id="a21c6-102">Функция CreateDebuggingInterfaceFromVersion Silverlight</span><span class="sxs-lookup"><span data-stu-id="a21c6-102">CreateDebuggingInterfaceFromVersion Function for Silverlight</span></span>

<span data-ttu-id="a21c6-103">Принимает строку версии среды CLR, возвращаемую [функцией CreateVersionStringFromModule](createversionstringfrommodule-function.md), и возвращает соответствующий интерфейс отладчика (как правило, [ICorDebug](icordebug-interface.md)).</span><span class="sxs-lookup"><span data-stu-id="a21c6-103">Accepts a common language runtime (CLR) version string that is returned from the [CreateVersionStringFromModule function](createversionstringfrommodule-function.md), and returns a corresponding debugger interface (typically, [ICorDebug](icordebug-interface.md)).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a21c6-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="a21c6-104">Syntax</span></span>  
  
```cpp  
HRESULT CreateDebuggingInterfaceFromVersion (  
    [in]  LPCWSTR      szDebuggeeVersion,  
    [out] IUnknown**   ppCordb,  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="a21c6-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="a21c6-105">Parameters</span></span>  

 `szDebuggeeVersion`\
 <span data-ttu-id="a21c6-106">окне Строка версии среды CLR в целевом отлаживаемом объекте, возвращаемом [функцией CreateVersionStringFromModule](createversionstringfrommodule-function.md).</span><span class="sxs-lookup"><span data-stu-id="a21c6-106">[in] Version string of the CLR in the target debuggee, which is returned by the [CreateVersionStringFromModule function](createversionstringfrommodule-function.md).</span></span>  
  
 `ppCordb`\
 <span data-ttu-id="a21c6-107">[out] Указатель на COM-объект (`IUnknown`).</span><span class="sxs-lookup"><span data-stu-id="a21c6-107">[out] Pointer to a pointer to a COM object (`IUnknown`).</span></span> <span data-ttu-id="a21c6-108">Перед возвращением этот объект будет приведен к объекту [ICorDebug](icordebug-interface.md) .</span><span class="sxs-lookup"><span data-stu-id="a21c6-108">This object will be cast to an [ICorDebug](icordebug-interface.md) object before it is returned.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="a21c6-109">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="a21c6-109">Return Value</span></span>

 `S_OK`\
 <span data-ttu-id="a21c6-110">`ppCordb`ссылается на допустимый объект, реализующий интерфейс [интерфейса ICorDebug](icordebug-interface.md) .</span><span class="sxs-lookup"><span data-stu-id="a21c6-110">`ppCordb` references a valid object that implements the [ICorDebug interface](icordebug-interface.md) interface.</span></span>  
  
 `E_INVALIDARG`\
 <span data-ttu-id="a21c6-111">Либо `szDebuggeeVersion`, либо `ppCordb` имеет значение null.</span><span class="sxs-lookup"><span data-stu-id="a21c6-111">Either `szDebuggeeVersion` or `ppCordb` is null.</span></span>  
  
 `CORDBG_E_DEBUG_COMPONENT_MISSING`\
 <span data-ttu-id="a21c6-112">Не удалось найти компонент, который необходим для отладки среды CLR.</span><span class="sxs-lookup"><span data-stu-id="a21c6-112">A component that is necessary for CLR debugging cannot be located.</span></span> <span data-ttu-id="a21c6-113">_Mscordbi. dll_ или _мскордаккоре. dll_ не найдены в том же каталоге, что и Целевая библиотека CoreCLR. dll.</span><span class="sxs-lookup"><span data-stu-id="a21c6-113">Either _mscordbi.dll_ or _mscordaccore.dll_ was not found in the same directory as the target CoreCLR.dll.</span></span>  
  
 `CORDBG_E_INCOMPATIBLE_PROTOCOL`\
 <span data-ttu-id="a21c6-114">Версия mscordbi.dll или mscordaccore.dll не совпадает с версией целевого объекта CoreCLR.dll.</span><span class="sxs-lookup"><span data-stu-id="a21c6-114">Either mscordbi.dll or mscordaccore.dll is not the same version as the target CoreCLR.dll.</span></span>  
  
 <span data-ttu-id="a21c6-115">`E_FAIL`(или другие `E_` коды возврата) </span><span class="sxs-lookup"><span data-stu-id="a21c6-115">`E_FAIL` (or other `E_` return codes)</span></span>\
 <span data-ttu-id="a21c6-116">Не удалось вернуть [Интерфейс ICorDebug](icordebug-interface.md).</span><span class="sxs-lookup"><span data-stu-id="a21c6-116">Unable to return an [ICorDebug interface](icordebug-interface.md).</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="a21c6-117">Remarks</span><span class="sxs-lookup"><span data-stu-id="a21c6-117">Remarks</span></span>

 <span data-ttu-id="a21c6-118">Возвращаемый интерфейс предоставляет средства для подключения к среде CLR в целевом процессе и отладки управляемого кода, который выполняется в этой среде CLR.</span><span class="sxs-lookup"><span data-stu-id="a21c6-118">The interface that is returned provides the facilities for attaching to a CLR in a target process and debugging the managed code that the CLR is running.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a21c6-119">Требования</span><span class="sxs-lookup"><span data-stu-id="a21c6-119">Requirements</span></span>

 <span data-ttu-id="a21c6-120">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="a21c6-120">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a21c6-121">**Заголовок:** dbgshim. h</span><span class="sxs-lookup"><span data-stu-id="a21c6-121">**Header:** dbgshim.h</span></span>  
  
 <span data-ttu-id="a21c6-122">**Библиотека:** dbgshim. dll</span><span class="sxs-lookup"><span data-stu-id="a21c6-122">**Library:** dbgshim.dll</span></span>  
  
 <span data-ttu-id="a21c6-123">**.NET Framework версии:** 3,5 SP1</span><span class="sxs-lookup"><span data-stu-id="a21c6-123">**.NET Framework Versions:** 3.5 SP1</span></span>
