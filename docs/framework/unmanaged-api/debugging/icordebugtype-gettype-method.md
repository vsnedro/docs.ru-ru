---
title: Метод ICorDebugType::GetType
ms.date: 03/30/2017
api_name:
- ICorDebugType.GetType
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugType::GetType
helpviewer_keywords:
- ICorDebugType::GetType method [.NET Framework debugging]
- GetType method, ICorDebugType interface [.NET Framework debugging]
ms.assetid: d6e64534-4d47-4ad0-a340-7590e07e2b4a
topic_type:
- apiref
ms.openlocfilehash: ac42c6254182ea775377a448a54d527b234c97dc
ms.sourcegitcommit: d6bd7903d7d46698e9d89d3725f3bb4876891aa3
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/13/2020
ms.locfileid: "83379922"
---
# <a name="icordebugtypegettype-method"></a><span data-ttu-id="f3f0f-102">Метод ICorDebugType::GetType</span><span class="sxs-lookup"><span data-stu-id="f3f0f-102">ICorDebugType::GetType Method</span></span>
<span data-ttu-id="f3f0f-103">Возвращает значение Корелементтипе, описывающее собственный тип общеязыковой среды выполнения (CLR), <xref:System.Type> представленной этим объектом ICorDebugType.</span><span class="sxs-lookup"><span data-stu-id="f3f0f-103">Gets a CorElementType value that describes the native type of the common language runtime (CLR) <xref:System.Type> represented by this ICorDebugType.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f3f0f-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="f3f0f-104">Syntax</span></span>  
  
```cpp  
HRESULT GetType (  
    [out] CorElementType   *ty  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="f3f0f-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="f3f0f-105">Parameters</span></span>  
 `ty`  
 <span data-ttu-id="f3f0f-106">заполняет Указатель на значение `CorElementType` перечисления, указывающее среду CLR <xref:System.Type> , которую представляет этот объект `ICorDebugType` .</span><span class="sxs-lookup"><span data-stu-id="f3f0f-106">[out] A pointer to a value of the `CorElementType` enumeration that indicates the CLR <xref:System.Type> that this `ICorDebugType` represents.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="f3f0f-107">Remarks</span><span class="sxs-lookup"><span data-stu-id="f3f0f-107">Remarks</span></span>  
 <span data-ttu-id="f3f0f-108">Если значение параметра `ty` — ELEMENT_TYPE_CLASS или ELEMENT_TYPE_VALUETYPE, можно вызвать метод [ICorDebugType:: coclass](icordebugtype-getclass-method.md) , чтобы получить тип без экземпляров для универсального типа; в противном случае не вызывайте `ICorDebugType::GetClass` .</span><span class="sxs-lookup"><span data-stu-id="f3f0f-108">If the value of `ty` is either ELEMENT_TYPE_CLASS or ELEMENT_TYPE_VALUETYPE, the [ICorDebugType::GetClass](icordebugtype-getclass-method.md) method may be called to get the uninstantiated type for a generic type; otherwise, do not call `ICorDebugType::GetClass`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f3f0f-109">Требования</span><span class="sxs-lookup"><span data-stu-id="f3f0f-109">Requirements</span></span>  
 <span data-ttu-id="f3f0f-110">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="f3f0f-110">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f3f0f-111">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="f3f0f-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="f3f0f-112">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="f3f0f-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="f3f0f-113">**.NET Framework версии:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f3f0f-113">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>
