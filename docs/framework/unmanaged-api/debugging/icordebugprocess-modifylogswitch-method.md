---
title: Метод ICorDebugProcess::ModifyLogSwitch
ms.date: 03/30/2017
api_name:
- ICorDebugProcess.ModifyLogSwitch
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugProcess::ModifyLogSwitch
helpviewer_keywords:
- ICorDebugProcess::ModifyLogSwitch method [.NET Framework debugging]
- ModifyLogSwitch method [.NET Framework debugging]
ms.assetid: 5fd30875-555e-4e96-877b-5dd266cde7c4
topic_type:
- apiref
ms.openlocfilehash: c9375854b45432eafb6cc706a1a62f5424e0fee8
ms.sourcegitcommit: 488aced39b5f374bc0a139a4993616a54d15baf0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/12/2020
ms.locfileid: "83210492"
---
# <a name="icordebugprocessmodifylogswitch-method"></a><span data-ttu-id="38013-102">Метод ICorDebugProcess::ModifyLogSwitch</span><span class="sxs-lookup"><span data-stu-id="38013-102">ICorDebugProcess::ModifyLogSwitch Method</span></span>
<span data-ttu-id="38013-103">Задает уровень серьезности указанного переключателя журнала.</span><span class="sxs-lookup"><span data-stu-id="38013-103">Sets the severity level of the specified log switch.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="38013-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="38013-104">Syntax</span></span>  
  
```cpp  
HRESULT ModifyLogSwitch(  
    [in] WCHAR *pLogSwitchName,  
    [in] LONG  lLevel);  
```  
  
## <a name="parameters"></a><span data-ttu-id="38013-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="38013-105">Parameters</span></span>  
 `pLogSwitchName`  
 <span data-ttu-id="38013-106">окне Указатель на строку, указывающую имя переключателя журнала.</span><span class="sxs-lookup"><span data-stu-id="38013-106">[in] A pointer to a string that specifies the name of the log switch.</span></span>  
  
 `lLevel`  
 <span data-ttu-id="38013-107">окне Уровень серьезности, заданный для указанного переключателя журнала.</span><span class="sxs-lookup"><span data-stu-id="38013-107">[in] The severity level to be set for the specified log switch.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="38013-108">Remarks</span><span class="sxs-lookup"><span data-stu-id="38013-108">Remarks</span></span>  
 <span data-ttu-id="38013-109">Этот метод допустим только после выполнения обратного вызова [ICorDebugManagedCallback:: CreateProcess](icordebugmanagedcallback-createprocess-method.md) .</span><span class="sxs-lookup"><span data-stu-id="38013-109">This method is valid only after the [ICorDebugManagedCallback::CreateProcess](icordebugmanagedcallback-createprocess-method.md) callback has occurred.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="38013-110">Требования</span><span class="sxs-lookup"><span data-stu-id="38013-110">Requirements</span></span>  
 <span data-ttu-id="38013-111">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="38013-111">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="38013-112">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="38013-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="38013-113">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="38013-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="38013-114">**.NET Framework версии:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="38013-114">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>
