---
title: Метод ICorDebugThread4::GetBlockingObjects
ms.date: 03/30/2017
api_name:
- ICorDebugThread4.GetBlockingObjects Method
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugThread4::GetBlockingObjects
helpviewer_keywords:
- GetBlockingObjects method [.NET Framework debugging]
- ICorDebugThread4::GetBlockingObjects method [.NET Framework debugging]
ms.assetid: a7e6c54e-7be9-4e52-bbb4-95f52458e8e4
topic_type:
- apiref
ms.openlocfilehash: 366b5124cc66a4e9a1c3bd4e77f604f15ba8d8a8
ms.sourcegitcommit: d6bd7903d7d46698e9d89d3725f3bb4876891aa3
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/13/2020
ms.locfileid: "83379673"
---
# <a name="icordebugthread4getblockingobjects-method"></a><span data-ttu-id="d1d79-102">Метод ICorDebugThread4::GetBlockingObjects</span><span class="sxs-lookup"><span data-stu-id="d1d79-102">ICorDebugThread4::GetBlockingObjects Method</span></span>
<span data-ttu-id="d1d79-103">Предоставляет упорядоченное перечисление структур [CorDebugBlockingObject](cordebugblockingobject-structure.md) , которые предоставляют сведения о блокировке потока.</span><span class="sxs-lookup"><span data-stu-id="d1d79-103">Provides an ordered enumeration of [CorDebugBlockingObject](cordebugblockingobject-structure.md) structures that provide thread blocking information.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d1d79-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="d1d79-104">Syntax</span></span>  
  
```cpp  
HRESULT GetBlockingObjects (  
    [out] ICorDebugBlockingObjectEnum **ppBlockingObjectEnum  
```  
  
## <a name="parameters"></a><span data-ttu-id="d1d79-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="d1d79-105">Parameters</span></span>  
 `ppBlockingObjectEnum`  
 <span data-ttu-id="d1d79-106">заполняет Указатель на упорядоченное перечисление структур [CorDebugBlockingObject](cordebugblockingobject-structure.md) .</span><span class="sxs-lookup"><span data-stu-id="d1d79-106">[out] A pointer to an ordered enumeration of [CorDebugBlockingObject](cordebugblockingobject-structure.md) structures.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="d1d79-107">Remarks</span><span class="sxs-lookup"><span data-stu-id="d1d79-107">Remarks</span></span>  
 <span data-ttu-id="d1d79-108">Первый элемент в возвращенном перечислении соответствует первой структуре, блокирующей поток.</span><span class="sxs-lookup"><span data-stu-id="d1d79-108">The first element in the returned enumeration corresponds to the first structure that is blocking the thread.</span></span> <span data-ttu-id="d1d79-109">Второй элемент соответствует блокирующему элементу, который обнаруживается при выполнении асинхронного вызова процедуры (APC) при блокировке в первом и т. д.</span><span class="sxs-lookup"><span data-stu-id="d1d79-109">The second element corresponds to a blocking item that is encountered while running an asynchronous procedure call (APC) when blocked on the first, and so on.</span></span>  
  
 <span data-ttu-id="d1d79-110">Перечисление допустимо только в течение текущего синхронизированного состояния.</span><span class="sxs-lookup"><span data-stu-id="d1d79-110">The enumeration is valid only for the duration of the current synchronized state.</span></span>  
  
 <span data-ttu-id="d1d79-111">Этот метод должен вызываться, когда отлаживаемый объект находится в синхронизированном состоянии.</span><span class="sxs-lookup"><span data-stu-id="d1d79-111">This method must be called while the debuggee is in a synchronized state.</span></span>  
  
 <span data-ttu-id="d1d79-112">Если не `ppBlockingObjectEnum` является допустимым указателем, результат не определен.</span><span class="sxs-lookup"><span data-stu-id="d1d79-112">If `ppBlockingObjectEnum` is not a valid pointer, the result is undefined.</span></span>  
  
 <span data-ttu-id="d1d79-113">Если поток заблокирован и ошибка не может быть определена, метод возвращает значение HRESULT, указывающее на ошибку; в противном случае возвращается S_OK.</span><span class="sxs-lookup"><span data-stu-id="d1d79-113">If a thread is blocked and the error cannot be determined, the method returns an HRESULT that indicates failure; otherwise, it returns S_OK.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d1d79-114">Требования</span><span class="sxs-lookup"><span data-stu-id="d1d79-114">Requirements</span></span>  
 <span data-ttu-id="d1d79-115">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="d1d79-115">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d1d79-116">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="d1d79-116">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="d1d79-117">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="d1d79-117">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="d1d79-118">**.NET Framework версии:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d1d79-118">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d1d79-119">См. также</span><span class="sxs-lookup"><span data-stu-id="d1d79-119">See also</span></span>

- [<span data-ttu-id="d1d79-120">Интерфейс ICorDebugThread4</span><span class="sxs-lookup"><span data-stu-id="d1d79-120">ICorDebugThread4 Interface</span></span>](icordebugthread4-interface.md)
- [<span data-ttu-id="d1d79-121">Интерфейсы отладки</span><span class="sxs-lookup"><span data-stu-id="d1d79-121">Debugging Interfaces</span></span>](debugging-interfaces.md)
- [<span data-ttu-id="d1d79-122">Отладка</span><span class="sxs-lookup"><span data-stu-id="d1d79-122">Debugging</span></span>](index.md)
