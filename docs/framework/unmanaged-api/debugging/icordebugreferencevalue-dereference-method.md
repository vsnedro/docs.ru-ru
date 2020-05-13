---
title: Метод ICorDebugReferenceValue::Dereference
ms.date: 03/30/2017
api_name:
- ICorDebugReferenceValue.Dereference
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugReferenceValue::Dereference
helpviewer_keywords:
- ICorDebugReferenceValue::Dereference method [.NET Framework debugging]
- Dereference method [.NET Framework debugging]
ms.assetid: 5ec8cf76-3deb-4ce6-9a49-77a4c35d80b9
topic_type:
- apiref
ms.openlocfilehash: 7c64823e1a5c519eb74b508af093afeb1132e608
ms.sourcegitcommit: 488aced39b5f374bc0a139a4993616a54d15baf0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/12/2020
ms.locfileid: "83210089"
---
# <a name="icordebugreferencevaluedereference-method"></a><span data-ttu-id="71d55-102">Метод ICorDebugReferenceValue::Dereference</span><span class="sxs-lookup"><span data-stu-id="71d55-102">ICorDebugReferenceValue::Dereference Method</span></span>
<span data-ttu-id="71d55-103">Возвращает объект, на который указывает ссылка.</span><span class="sxs-lookup"><span data-stu-id="71d55-103">Gets the object that is referenced.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="71d55-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="71d55-104">Syntax</span></span>  
  
```cpp  
HRESULT Dereference (  
    [out] ICorDebugValue  **ppValue  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="71d55-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="71d55-105">Parameters</span></span>  
 `ppValue`  
 <span data-ttu-id="71d55-106">заполняет Указатель на адрес ICorDebugValue, представляющий объект, на который указывает объект ICorDebugReferenceValue.</span><span class="sxs-lookup"><span data-stu-id="71d55-106">[out] A pointer to the address of an ICorDebugValue that represents the object to which this ICorDebugReferenceValue object points.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="71d55-107">Remarks</span><span class="sxs-lookup"><span data-stu-id="71d55-107">Remarks</span></span>  
 <span data-ttu-id="71d55-108">`ICorDebugValue`Объект допустим только в том случае, если его ссылка еще не была отключена.</span><span class="sxs-lookup"><span data-stu-id="71d55-108">The `ICorDebugValue` object is valid only while its reference has not yet been disabled.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="71d55-109">Требования</span><span class="sxs-lookup"><span data-stu-id="71d55-109">Requirements</span></span>  
 <span data-ttu-id="71d55-110">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="71d55-110">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="71d55-111">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="71d55-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="71d55-112">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="71d55-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="71d55-113">**.NET Framework версии:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="71d55-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
