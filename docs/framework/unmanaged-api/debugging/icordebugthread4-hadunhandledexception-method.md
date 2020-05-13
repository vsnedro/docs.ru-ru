---
title: Метод ICorDebugThread4::HadUnhandledException
ms.date: 03/30/2017
api_name:
- ICorDebugThread4.HadUnhandledException Method
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugThread4::HadUnhandledException
helpviewer_keywords:
- ICorDebugThread4::HadUnhandledException method [.NET Framework debugging]
- HadUnhandledException method [.NET Framework debugging]
ms.assetid: 05558daa-39e2-4c38-aeaf-e2aec4a09468
topic_type:
- apiref
ms.openlocfilehash: 4d954057c519263da49f8aaeeeef6ab9402b6956
ms.sourcegitcommit: d6bd7903d7d46698e9d89d3725f3bb4876891aa3
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/13/2020
ms.locfileid: "83378376"
---
# <a name="icordebugthread4hadunhandledexception-method"></a><span data-ttu-id="3acbc-102">Метод ICorDebugThread4::HadUnhandledException</span><span class="sxs-lookup"><span data-stu-id="3acbc-102">ICorDebugThread4::HadUnhandledException Method</span></span>
<span data-ttu-id="3acbc-103">Указывает, имел ли когда-либо поток необработанное исключение.</span><span class="sxs-lookup"><span data-stu-id="3acbc-103">Indicates whether the thread has ever had an unhandled exception.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3acbc-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="3acbc-104">Syntax</span></span>  
  
```cpp  
HRESULT GetBlockingObjects (  
    [out] ICorDebugBlockingObjectEnum **ppBlockingObjectEnum  
    );  
```  
  
## <a name="parameters"></a><span data-ttu-id="3acbc-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="3acbc-105">Parameters</span></span>  
 `ppBlockingObjectEnum`  
 <span data-ttu-id="3acbc-106">заполняет Указатель на адрес упорядоченного перечисления структур [CorDebugBlockingObject](cordebugblockingobject-structure.md) .</span><span class="sxs-lookup"><span data-stu-id="3acbc-106">[out] A pointer to the address of an ordered enumeration of [CorDebugBlockingObject](cordebugblockingobject-structure.md) structures.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="3acbc-107">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="3acbc-107">Return Value</span></span>  
 <span data-ttu-id="3acbc-108">Этот метод возвращает следующие конкретные результаты HRESULT, а также ошибки HRESULT, которые указывают на сбой метода.</span><span class="sxs-lookup"><span data-stu-id="3acbc-108">This method returns the following specific HRESULTs as well as HRESULT errors that indicate method failure.</span></span>  
  
|<span data-ttu-id="3acbc-109">HRESULT</span><span class="sxs-lookup"><span data-stu-id="3acbc-109">HRESULT</span></span>|<span data-ttu-id="3acbc-110">Описание</span><span class="sxs-lookup"><span data-stu-id="3acbc-110">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="3acbc-111">S_OK</span><span class="sxs-lookup"><span data-stu-id="3acbc-111">S_OK</span></span>|<span data-ttu-id="3acbc-112">В потоке возникло необработанное исключение с момента его создания.</span><span class="sxs-lookup"><span data-stu-id="3acbc-112">The thread has had an unhandled exception since its creation.</span></span>|  
|<span data-ttu-id="3acbc-113">S_FALSE</span><span class="sxs-lookup"><span data-stu-id="3acbc-113">S_FALSE</span></span>|<span data-ttu-id="3acbc-114">В потоке никогда не было необработанного исключения.</span><span class="sxs-lookup"><span data-stu-id="3acbc-114">The thread has never had an unhandled exception.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="3acbc-115">Remarks</span><span class="sxs-lookup"><span data-stu-id="3acbc-115">Remarks</span></span>  
 <span data-ttu-id="3acbc-116">Этот метод указывает, имел ли у потока когда-либо необработанное исключение.</span><span class="sxs-lookup"><span data-stu-id="3acbc-116">This method indicates whether the thread has ever had an unhandled exception.</span></span> <span data-ttu-id="3acbc-117">К моменту запуска обратного вызова необработанного исключения или инициализации собственного JIT-присоединения этот метод гарантированно возвращает S_OK.</span><span class="sxs-lookup"><span data-stu-id="3acbc-117">By the time the unhandled exception callback is triggered or native JIT-attach is initiated, this method is guaranteed to return S_OK.</span></span> <span data-ttu-id="3acbc-118">Нет никакой гарантии, что метод [ICorDebugThread. жеткуррентексцептион](icordebugthread-getcurrentexception-method.md) будет возвращать необработанное исключение; Тем не менее, если процесс еще не был продолжен после получения обратного вызова необработанного исключения или собственного JIT-присоединения.</span><span class="sxs-lookup"><span data-stu-id="3acbc-118">There is no guarantee that the [ICorDebugThread.GetCurrentException](icordebugthread-getcurrentexception-method.md) method will return the unhandled exception; however, it will if the process has not yet been continued after getting the unhandled exception callback or upon native JIT-attach.</span></span> <span data-ttu-id="3acbc-119">Кроме того, во время выполнения собственного JIT-присоединения можно (хотя маловероятно) иметь более одного потока с необработанным исключением.</span><span class="sxs-lookup"><span data-stu-id="3acbc-119">Furthermore, it is possible (although unlikely) to have more than one thread with an unhandled exception at the time native JIT-attach is triggered.</span></span> <span data-ttu-id="3acbc-120">В этом случае нет способа определить, какое исключение активировало JIT-присоединение.</span><span class="sxs-lookup"><span data-stu-id="3acbc-120">In such a case there is no way to determine which exception triggered the JIT-attach.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="3acbc-121">Требования</span><span class="sxs-lookup"><span data-stu-id="3acbc-121">Requirements</span></span>  
 <span data-ttu-id="3acbc-122">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="3acbc-122">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="3acbc-123">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="3acbc-123">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="3acbc-124">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="3acbc-124">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="3acbc-125">**.NET Framework версии:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="3acbc-125">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3acbc-126">См. также</span><span class="sxs-lookup"><span data-stu-id="3acbc-126">See also</span></span>

- [<span data-ttu-id="3acbc-127">Интерфейс ICorDebugThread4</span><span class="sxs-lookup"><span data-stu-id="3acbc-127">ICorDebugThread4 Interface</span></span>](icordebugthread4-interface.md)
- [<span data-ttu-id="3acbc-128">Интерфейсы отладки</span><span class="sxs-lookup"><span data-stu-id="3acbc-128">Debugging Interfaces</span></span>](debugging-interfaces.md)
- [<span data-ttu-id="3acbc-129">Отладка</span><span class="sxs-lookup"><span data-stu-id="3acbc-129">Debugging</span></span>](index.md)
