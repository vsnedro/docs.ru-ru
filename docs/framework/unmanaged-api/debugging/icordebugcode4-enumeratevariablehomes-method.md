---
title: 'Метод ICorDebugCode4:: Енумератевариаблехомес'
ms.date: 03/30/2017
api_name:
- ICorDebugCode4.EnumerateVariableHomes
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugCode4::EnumerateVariableHomes
helpviewer_keywords:
- EnumerateVariableHomes method [.NET Framework debugging]
- ICorDebugCode4::EnumerateVariableHomes method [.NET Framework debugging]
ms.assetid: 802c01ff-8b80-4733-b6dd-03ab6ff7fa11
topic_type:
- apiref
ms.openlocfilehash: 5f731b1459542c3f5378790b21f2ea576e89ad97
ms.sourcegitcommit: 957c49696eaf048c284ef8f9f8ffeb562357ad95
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/07/2020
ms.locfileid: "82893339"
---
# <a name="icordebugcode4enumeratevariablehomes-method"></a><span data-ttu-id="2ee1e-102">Метод ICorDebugCode4:: Енумератевариаблехомес</span><span class="sxs-lookup"><span data-stu-id="2ee1e-102">ICorDebugCode4::EnumerateVariableHomes Method</span></span>
<span data-ttu-id="2ee1e-103">Возвращает перечислитель для локальных переменных и аргументов в функции.</span><span class="sxs-lookup"><span data-stu-id="2ee1e-103">Gets an enumerator to the local variables and arguments in a function.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2ee1e-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="2ee1e-104">Syntax</span></span>  
  
```cpp  
HRESULT EnumerateVariableHomes(  
    [out] ICorDebugVariableHomeEnum **ppEnum  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="2ee1e-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="2ee1e-105">Parameters</span></span>  
 `ppEnum`  
 <span data-ttu-id="2ee1e-106">Указатель на адрес объекта интерфейса [ICorDebugVariableHomeEnum](icordebugvariablehomeenum-interface.md) , который является перечислителем для локальных переменных и аргументов в функции.</span><span class="sxs-lookup"><span data-stu-id="2ee1e-106">A pointer to the address of an [ICorDebugVariableHomeEnum](icordebugvariablehomeenum-interface.md) interface object that is an enumerator for the local variables and arguments in a function.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="2ee1e-107">Remarks</span><span class="sxs-lookup"><span data-stu-id="2ee1e-107">Remarks</span></span>  
 <span data-ttu-id="2ee1e-108">Объект интерфейса [ICorDebugVariableHomeEnum](icordebugvariablehomeenum-interface.md) является стандартным перечислителем, производным от интерфейса "ICorDebugEnum", который позволяет перечислить объекты [ICorDebugVariableHome](icordebugvariablehome-interface.md) .</span><span class="sxs-lookup"><span data-stu-id="2ee1e-108">The [ICorDebugVariableHomeEnum](icordebugvariablehomeenum-interface.md) interface object is a standard enumerator derived from the "ICorDebugEnum" interface that allows you to enumerate [ICorDebugVariableHome](icordebugvariablehome-interface.md) objects.</span></span> <span data-ttu-id="2ee1e-109">Коллекция может содержать несколько объектов [ICorDebugVariableHome](icordebugvariablehome-interface.md) для одного и того же индекса слота или аргумента, если они имеют разные расположения в разных точках функции.</span><span class="sxs-lookup"><span data-stu-id="2ee1e-109">The collection may include multiple [ICorDebugVariableHome](icordebugvariablehome-interface.md) objects for the same slot or      argument index if they have different homes at different points in the      function.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="2ee1e-110">Требования</span><span class="sxs-lookup"><span data-stu-id="2ee1e-110">Requirements</span></span>  
 <span data-ttu-id="2ee1e-111">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="2ee1e-111">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="2ee1e-112">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="2ee1e-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="2ee1e-113">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="2ee1e-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="2ee1e-114">**.NET Framework версии:**[!INCLUDE[net_current_v462plus](../../../../includes/net-current-v462plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="2ee1e-114">**.NET Framework Versions:** [!INCLUDE[net_current_v462plus](../../../../includes/net-current-v462plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2ee1e-115">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="2ee1e-115">See also</span></span>

- [<span data-ttu-id="2ee1e-116">Интерфейс ICorDebugCode4</span><span class="sxs-lookup"><span data-stu-id="2ee1e-116">ICorDebugCode4 Interface</span></span>](icordebugcode4-interface.md)
- [<span data-ttu-id="2ee1e-117">Интерфейсы отладки</span><span class="sxs-lookup"><span data-stu-id="2ee1e-117">Debugging Interfaces</span></span>](debugging-interfaces.md)
