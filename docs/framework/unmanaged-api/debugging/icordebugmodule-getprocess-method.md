---
title: Метод ICorDebugModule::GetProcess
ms.date: 03/30/2017
api_name:
- ICorDebugModule.GetProcess
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugModule::GetProcess
helpviewer_keywords:
- GetProcess method, ICorDebugModule interface [.NET Framework debugging]
- ICorDebugModule::GetProcess method [.NET Framework debugging]
ms.assetid: 5e13446c-0271-446c-924a-9072c0e6eeae
topic_type:
- apiref
ms.openlocfilehash: 8f4b9e73e0d716561dd64bc0df702d835e0eee06
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/24/2020
ms.locfileid: "95709964"
---
# <a name="icordebugmodulegetprocess-method"></a><span data-ttu-id="40247-102">Метод ICorDebugModule::GetProcess</span><span class="sxs-lookup"><span data-stu-id="40247-102">ICorDebugModule::GetProcess Method</span></span>

<span data-ttu-id="40247-103">Возвращает содержащий процесс этого модуля.</span><span class="sxs-lookup"><span data-stu-id="40247-103">Gets the containing process of this module.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="40247-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="40247-104">Syntax</span></span>  
  
```cpp  
HRESULT GetProcess (  
    [out] ICorDebugProcess **ppProcess  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="40247-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="40247-105">Parameters</span></span>  

 `ppProcess`  
 <span data-ttu-id="40247-106">заполняет Указатель на адрес объекта ICorDebugProcess, который представляет процесс, содержащий этот модуль.</span><span class="sxs-lookup"><span data-stu-id="40247-106">[out] A pointer to the address of an ICorDebugProcess object that represents the process containing this module.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="40247-107">Требования</span><span class="sxs-lookup"><span data-stu-id="40247-107">Requirements</span></span>  

 <span data-ttu-id="40247-108">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="40247-108">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="40247-109">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="40247-109">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="40247-110">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="40247-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="40247-111">**.NET Framework версии:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="40247-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
