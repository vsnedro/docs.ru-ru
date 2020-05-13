---
title: Метод ICorDebugFunction::GetClass
ms.date: 03/30/2017
api_name:
- ICorDebugFunction.GetClass
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugFunction::GetClass
helpviewer_keywords:
- GetClass method, ICorDebugFunction interface [.NET Framework debugging]
- ICorDebugFunction::GetClass method [.NET Framework debugging]
ms.assetid: 27967230-144f-40d3-9e23-961d0241abd9
topic_type:
- apiref
ms.openlocfilehash: 7a089831c39c36b0f8a0c7746e95a96e4ddfc5d9
ms.sourcegitcommit: 488aced39b5f374bc0a139a4993616a54d15baf0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/12/2020
ms.locfileid: "83209400"
---
# <a name="icordebugfunctiongetclass-method"></a><span data-ttu-id="11ddf-102">Метод ICorDebugFunction::GetClass</span><span class="sxs-lookup"><span data-stu-id="11ddf-102">ICorDebugFunction::GetClass Method</span></span>
<span data-ttu-id="11ddf-103">Возвращает объект ICorDebugClass, представляющий класс, членом которого является эта функция.</span><span class="sxs-lookup"><span data-stu-id="11ddf-103">Gets an ICorDebugClass object that represents the class this function is a member of.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="11ddf-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="11ddf-104">Syntax</span></span>  
  
```cpp  
HRESULT GetClass (  
    [out] ICorDebugClass **ppClass  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="11ddf-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="11ddf-105">Parameters</span></span>  
 `ppClass`  
 <span data-ttu-id="11ddf-106">заполняет Указатель на адрес `ICorDebugClass` объекта, представляющий класс, или значение null, если эта функция не является членом класса.</span><span class="sxs-lookup"><span data-stu-id="11ddf-106">[out] A pointer to the address of the `ICorDebugClass` object that represents the class, or null, if this function is not a member of a class.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="11ddf-107">Требования</span><span class="sxs-lookup"><span data-stu-id="11ddf-107">Requirements</span></span>  
 <span data-ttu-id="11ddf-108">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="11ddf-108">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="11ddf-109">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="11ddf-109">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="11ddf-110">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="11ddf-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="11ddf-111">**.NET Framework версии:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="11ddf-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
