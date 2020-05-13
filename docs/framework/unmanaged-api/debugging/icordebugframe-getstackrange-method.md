---
title: Метод ICorDebugFrame::GetStackRange
ms.date: 03/30/2017
api_name:
- ICorDebugFrame.GetStackRange
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugFrame::GetStackRange
helpviewer_keywords:
- GetStackRange method, ICorDebugFrame interface [.NET Framework debugging]
- ICorDebugFrame::GetStackRange method [.NET Framework debugging]
ms.assetid: fab037cb-fda6-40fb-9367-921e435dd5a0
topic_type:
- apiref
ms.openlocfilehash: cacdccf5c27cd1d115134d49e754b4ace2870b72
ms.sourcegitcommit: 488aced39b5f374bc0a139a4993616a54d15baf0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/12/2020
ms.locfileid: "83205163"
---
# <a name="icordebugframegetstackrange-method"></a><span data-ttu-id="5d5dd-102">Метод ICorDebugFrame::GetStackRange</span><span class="sxs-lookup"><span data-stu-id="5d5dd-102">ICorDebugFrame::GetStackRange Method</span></span>
<span data-ttu-id="5d5dd-103">Возвращает диапазон абсолютных адресов этого кадра стека.</span><span class="sxs-lookup"><span data-stu-id="5d5dd-103">Gets the absolute address range of this stack frame.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5d5dd-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="5d5dd-104">Syntax</span></span>  
  
```cpp  
HRESULT GetStackRange (  
    [out] CORDB_ADDRESS      *pStart,
    [out] CORDB_ADDRESS      *pEnd  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="5d5dd-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="5d5dd-105">Parameters</span></span>  
 `pStart`  
 <span data-ttu-id="5d5dd-106">заполняет Указатель на объект `CORDB_ADDRESS` , указывающий начальный адрес кадра стека, представленного этим `ICorDebugFrame` объектом.</span><span class="sxs-lookup"><span data-stu-id="5d5dd-106">[out] A pointer to a `CORDB_ADDRESS` that specifies the starting address of the stack frame represented by this `ICorDebugFrame` object.</span></span>  
  
 `pEnd`  
 <span data-ttu-id="5d5dd-107">заполняет Указатель на объект `CORDB_ADDRESS` , указывающий конечный адрес кадра стека, представленного этим `ICorDebugFrame` объектом.</span><span class="sxs-lookup"><span data-stu-id="5d5dd-107">[out] A pointer to a `CORDB_ADDRESS` that specifies the ending address of the stack frame represented by this `ICorDebugFrame` object.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="5d5dd-108">Remarks</span><span class="sxs-lookup"><span data-stu-id="5d5dd-108">Remarks</span></span>  
 <span data-ttu-id="5d5dd-109">Диапазон адресов стека полезен для пиеЦинг вместе чередующихся трассировок стека, собранных из нескольких ядер отладки.</span><span class="sxs-lookup"><span data-stu-id="5d5dd-109">The address range of the stack is useful for piecing together interleaved stack traces gathered from multiple debugging engines.</span></span> <span data-ttu-id="5d5dd-110">Числовой диапазон не предоставляет сведений о содержимом кадра стека.</span><span class="sxs-lookup"><span data-stu-id="5d5dd-110">The numeric range provides no information about the contents of the stack frame.</span></span> <span data-ttu-id="5d5dd-111">Он имеет смысл только для сравнения расположений в кадрах стека.</span><span class="sxs-lookup"><span data-stu-id="5d5dd-111">It is meaningful only for comparison of stack frame locations.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="5d5dd-112">Требования</span><span class="sxs-lookup"><span data-stu-id="5d5dd-112">Requirements</span></span>  
 <span data-ttu-id="5d5dd-113">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="5d5dd-113">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="5d5dd-114">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="5d5dd-114">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="5d5dd-115">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="5d5dd-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="5d5dd-116">**.NET Framework версии:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="5d5dd-116">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
