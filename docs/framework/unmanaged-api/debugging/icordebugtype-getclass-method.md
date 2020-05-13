---
title: Метод ICorDebugType::GetClass
ms.date: 03/30/2017
api_name:
- ICorDebugType.GetClass
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugType::GetClass
helpviewer_keywords:
- ICorDebugType::GetClass method [.NET Framework debugging]
- GetClass method, ICorDebugType interface [.NET Framework debugging]
ms.assetid: 2644f48b-db3c-429f-ae62-76f1c98a1af5
topic_type:
- apiref
ms.openlocfilehash: 878a57514af34730049864f17f4853c1237904c2
ms.sourcegitcommit: d6bd7903d7d46698e9d89d3725f3bb4876891aa3
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/13/2020
ms.locfileid: "83379960"
---
# <a name="icordebugtypegetclass-method"></a><span data-ttu-id="3a7f2-102">Метод ICorDebugType::GetClass</span><span class="sxs-lookup"><span data-stu-id="3a7f2-102">ICorDebugType::GetClass Method</span></span>
<span data-ttu-id="3a7f2-103">Возвращает указатель интерфейса на объект ICorDebugClass, представляющий универсальный тип, экземпляр которого не был создан.</span><span class="sxs-lookup"><span data-stu-id="3a7f2-103">Gets an interface pointer to an ICorDebugClass that represents the uninstantiated generic type.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3a7f2-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="3a7f2-104">Syntax</span></span>  
  
```cpp  
HRESULT GetClass (  
    [out] ICorDebugClass   **ppClass  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="3a7f2-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="3a7f2-105">Parameters</span></span>  
 `ppClass`  
 <span data-ttu-id="3a7f2-106">заполняет Указатель на адрес `ICorDebugClass` интерфейса, представляющий универсальный тип, экземпляр которого не был создан.</span><span class="sxs-lookup"><span data-stu-id="3a7f2-106">[out] A pointer to the address of an `ICorDebugClass` interface that represents the uninstantiated generic type.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="3a7f2-107">Remarks</span><span class="sxs-lookup"><span data-stu-id="3a7f2-107">Remarks</span></span>  
 <span data-ttu-id="3a7f2-108">`GetClass`может вызываться только при определенных условиях.</span><span class="sxs-lookup"><span data-stu-id="3a7f2-108">`GetClass` can be called only under certain conditions.</span></span> <span data-ttu-id="3a7f2-109">Вызовите метод [ICorDebugType:: GetType](icordebugtype-gettype-method.md) перед вызовом метода `GetClass` .</span><span class="sxs-lookup"><span data-stu-id="3a7f2-109">Call [ICorDebugType::GetType](icordebugtype-gettype-method.md) before calling `GetClass`.</span></span> <span data-ttu-id="3a7f2-110">Если `ICorDebugType::GetType` возвращает значение корелементтипе, которое равно ELEMENT_TYPE_CLASS или ELEMENT_TYPE_VALUETYPE, `GetClass` можно вызвать метод, чтобы получить неэкземплярный тип для универсального типа.</span><span class="sxs-lookup"><span data-stu-id="3a7f2-110">If `ICorDebugType::GetType` returns a CorElementType value that is ELEMENT_TYPE_CLASS or ELEMENT_TYPE_VALUETYPE, `GetClass` can be called to get the uninstantiated type for a generic type.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="3a7f2-111">Требования</span><span class="sxs-lookup"><span data-stu-id="3a7f2-111">Requirements</span></span>  
 <span data-ttu-id="3a7f2-112">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="3a7f2-112">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="3a7f2-113">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="3a7f2-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="3a7f2-114">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="3a7f2-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="3a7f2-115">**.NET Framework версии:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="3a7f2-115">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>
