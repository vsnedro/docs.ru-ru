---
title: Метод ICorDebugModule::GetGlobalVariableValue
ms.date: 03/30/2017
api_name:
- ICorDebugModule.GetGlobalVariableValue
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugModule::GetGlobalVariableValue
helpviewer_keywords:
- ICorDebugModule::GetGlobalVariableValue method [.NET Framework debugging]
- GetGlobalVariableValue method [.NET Framework debugging]
ms.assetid: bbc0881c-6a59-41a0-b5ee-2f3d1b71684c
topic_type:
- apiref
ms.openlocfilehash: 7e32f3f4f6613d34e2b40946ed3eadb8eb0a7c1f
ms.sourcegitcommit: 488aced39b5f374bc0a139a4993616a54d15baf0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/12/2020
ms.locfileid: "83212574"
---
# <a name="icordebugmodulegetglobalvariablevalue-method"></a><span data-ttu-id="8c5fd-102">Метод ICorDebugModule::GetGlobalVariableValue</span><span class="sxs-lookup"><span data-stu-id="8c5fd-102">ICorDebugModule::GetGlobalVariableValue Method</span></span>
<span data-ttu-id="8c5fd-103">Возвращает значение указанной глобальной переменной.</span><span class="sxs-lookup"><span data-stu-id="8c5fd-103">Gets the value of the specified global variable.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8c5fd-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="8c5fd-104">Syntax</span></span>  
  
```cpp  
HRESULT GetGlobalVariableValue(  
    [in]  mdFieldDef      fieldDef,  
    [out] ICorDebugValue  **ppValue  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="8c5fd-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="8c5fd-105">Parameters</span></span>  
 `fieldDef`  
 <span data-ttu-id="8c5fd-106">окне `mdFieldDef`Токен, ссылающийся на метаданные, описывающие глобальную переменную.</span><span class="sxs-lookup"><span data-stu-id="8c5fd-106">[in] An `mdFieldDef` token that references the metadata describing the global variable.</span></span>  
  
 `ppValue`  
 <span data-ttu-id="8c5fd-107">заполняет Указатель на адрес объекта ICorDebugValue, представляющий значение указанной глобальной переменной.</span><span class="sxs-lookup"><span data-stu-id="8c5fd-107">[out] A pointer to the address of an ICorDebugValue object that represents the value of the specified global variable.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="8c5fd-108">Требования</span><span class="sxs-lookup"><span data-stu-id="8c5fd-108">Requirements</span></span>  
 <span data-ttu-id="8c5fd-109">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="8c5fd-109">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="8c5fd-110">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="8c5fd-110">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="8c5fd-111">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="8c5fd-111">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="8c5fd-112">**.NET Framework версии:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="8c5fd-112">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
