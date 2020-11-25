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
ms.openlocfilehash: 6d58efa5629bb02158a275dec61c0313bca821a1
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/24/2020
ms.locfileid: "95720766"
---
# <a name="icordebugcode4enumeratevariablehomes-method"></a><span data-ttu-id="6d1c0-102">Метод ICorDebugCode4:: Енумератевариаблехомес</span><span class="sxs-lookup"><span data-stu-id="6d1c0-102">ICorDebugCode4::EnumerateVariableHomes Method</span></span>

<span data-ttu-id="6d1c0-103">Возвращает перечислитель для локальных переменных и аргументов в функции.</span><span class="sxs-lookup"><span data-stu-id="6d1c0-103">Gets an enumerator to the local variables and arguments in a function.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6d1c0-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="6d1c0-104">Syntax</span></span>  
  
```cpp  
HRESULT EnumerateVariableHomes(  
    [out] ICorDebugVariableHomeEnum **ppEnum  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="6d1c0-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="6d1c0-105">Parameters</span></span>  

 `ppEnum`  
 <span data-ttu-id="6d1c0-106">Указатель на адрес объекта интерфейса [ICorDebugVariableHomeEnum](icordebugvariablehomeenum-interface.md) , который является перечислителем для локальных переменных и аргументов в функции.</span><span class="sxs-lookup"><span data-stu-id="6d1c0-106">A pointer to the address of an [ICorDebugVariableHomeEnum](icordebugvariablehomeenum-interface.md) interface object that is an enumerator for the local variables and arguments in a function.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="6d1c0-107">Комментарии</span><span class="sxs-lookup"><span data-stu-id="6d1c0-107">Remarks</span></span>  

 <span data-ttu-id="6d1c0-108">Объект интерфейса [ICorDebugVariableHomeEnum](icordebugvariablehomeenum-interface.md) является стандартным перечислителем, производным от интерфейса "ICorDebugEnum", который позволяет перечислить объекты [ICorDebugVariableHome](icordebugvariablehome-interface.md) .</span><span class="sxs-lookup"><span data-stu-id="6d1c0-108">The [ICorDebugVariableHomeEnum](icordebugvariablehomeenum-interface.md) interface object is a standard enumerator derived from the "ICorDebugEnum" interface that allows you to enumerate [ICorDebugVariableHome](icordebugvariablehome-interface.md) objects.</span></span> <span data-ttu-id="6d1c0-109">Коллекция может содержать несколько объектов [ICorDebugVariableHome](icordebugvariablehome-interface.md) для одного и того же индекса слота или аргумента, если они имеют разные расположения в разных точках функции.</span><span class="sxs-lookup"><span data-stu-id="6d1c0-109">The collection may include multiple [ICorDebugVariableHome](icordebugvariablehome-interface.md) objects for the same slot or      argument index if they have different homes at different points in the      function.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="6d1c0-110">Требования</span><span class="sxs-lookup"><span data-stu-id="6d1c0-110">Requirements</span></span>  

 <span data-ttu-id="6d1c0-111">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="6d1c0-111">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="6d1c0-112">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="6d1c0-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="6d1c0-113">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="6d1c0-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="6d1c0-114">**.NET Framework версии:**[!INCLUDE[net_current_v462plus](../../../../includes/net-current-v462plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="6d1c0-114">**.NET Framework Versions:** [!INCLUDE[net_current_v462plus](../../../../includes/net-current-v462plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6d1c0-115">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="6d1c0-115">See also</span></span>

- [<span data-ttu-id="6d1c0-116">Интерфейс ICorDebugCode4</span><span class="sxs-lookup"><span data-stu-id="6d1c0-116">ICorDebugCode4 Interface</span></span>](icordebugcode4-interface.md)
- [<span data-ttu-id="6d1c0-117">Интерфейсы отладки</span><span class="sxs-lookup"><span data-stu-id="6d1c0-117">Debugging Interfaces</span></span>](debugging-interfaces.md)
