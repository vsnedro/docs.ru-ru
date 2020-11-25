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
ms.openlocfilehash: cbcee923ecbb1106bb129f05d2e602a0fd17258d
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/24/2020
ms.locfileid: "95732493"
---
# <a name="icordebugreferencevaluedereference-method"></a><span data-ttu-id="c3813-102">Метод ICorDebugReferenceValue::Dereference</span><span class="sxs-lookup"><span data-stu-id="c3813-102">ICorDebugReferenceValue::Dereference Method</span></span>

<span data-ttu-id="c3813-103">Возвращает объект, на который указывает ссылка.</span><span class="sxs-lookup"><span data-stu-id="c3813-103">Gets the object that is referenced.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c3813-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="c3813-104">Syntax</span></span>  
  
```cpp  
HRESULT Dereference (  
    [out] ICorDebugValue  **ppValue  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="c3813-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="c3813-105">Parameters</span></span>  

 `ppValue`  
 <span data-ttu-id="c3813-106">заполняет Указатель на адрес ICorDebugValue, представляющий объект, на который указывает объект ICorDebugReferenceValue.</span><span class="sxs-lookup"><span data-stu-id="c3813-106">[out] A pointer to the address of an ICorDebugValue that represents the object to which this ICorDebugReferenceValue object points.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="c3813-107">Комментарии</span><span class="sxs-lookup"><span data-stu-id="c3813-107">Remarks</span></span>  

 <span data-ttu-id="c3813-108">`ICorDebugValue`Объект допустим только в том случае, если его ссылка еще не была отключена.</span><span class="sxs-lookup"><span data-stu-id="c3813-108">The `ICorDebugValue` object is valid only while its reference has not yet been disabled.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c3813-109">Требования</span><span class="sxs-lookup"><span data-stu-id="c3813-109">Requirements</span></span>  

 <span data-ttu-id="c3813-110">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="c3813-110">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c3813-111">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="c3813-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="c3813-112">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="c3813-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="c3813-113">**.NET Framework версии:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c3813-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
