---
title: Метод ICorDebugThread::GetCurrentException
ms.date: 03/30/2017
api_name:
- ICorDebugThread.GetCurrentException
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugThread::GetCurrentException
helpviewer_keywords:
- ICorDebugThread::GetCurrentException method [.NET Framework debugging]
- GetCurrentException method [.NET Framework debugging]
ms.assetid: 331ed465-a195-4359-8584-b82c6098b29b
topic_type:
- apiref
ms.openlocfilehash: c21be7b062b7e2d4129bafabae004351442ab853
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/24/2020
ms.locfileid: "95728060"
---
# <a name="icordebugthreadgetcurrentexception-method"></a><span data-ttu-id="8ec63-102">Метод ICorDebugThread::GetCurrentException</span><span class="sxs-lookup"><span data-stu-id="8ec63-102">ICorDebugThread::GetCurrentException Method</span></span>

<span data-ttu-id="8ec63-103">Возвращает указатель интерфейса на объект ICorDebugValue, представляющий исключение, которое в данный момент вызывается управляемым кодом.</span><span class="sxs-lookup"><span data-stu-id="8ec63-103">Gets an interface pointer to an ICorDebugValue object that represents an exception that is currently being thrown by managed code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8ec63-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="8ec63-104">Syntax</span></span>  
  
```cpp  
HRESULT GetCurrentException (  
    [out] ICorDebugValue **ppExceptionObject  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="8ec63-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="8ec63-105">Parameters</span></span>  

 `ppExceptionObject`  
 <span data-ttu-id="8ec63-106">заполняет Указатель на адрес `ICorDebugValue` объекта, представляющий исключение, которое в данный момент вызывается управляемым кодом.</span><span class="sxs-lookup"><span data-stu-id="8ec63-106">[out] A pointer to the address of an `ICorDebugValue` object that represents the exception that is currently being thrown by managed code.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="8ec63-107">Комментарии</span><span class="sxs-lookup"><span data-stu-id="8ec63-107">Remarks</span></span>  

 <span data-ttu-id="8ec63-108">Объект исключения будет существовать с момента возникновения исключения до конца `catch` блока.</span><span class="sxs-lookup"><span data-stu-id="8ec63-108">The exception object will exist from the time the exception is thrown until the end of the `catch` block.</span></span> <span data-ttu-id="8ec63-109">Вычисление функции, выполняемое методами ICorDebugEval, очистит объект исключения при установке и восстановит его по завершении.</span><span class="sxs-lookup"><span data-stu-id="8ec63-109">A function evaluation, which is performed by the ICorDebugEval methods, will clear out the exception object on setup and restore it on completion.</span></span>  
  
 <span data-ttu-id="8ec63-110">Исключения могут быть вложенными (например, если исключение создается в фильтре или в вычислении функции), поэтому в одном потоке может быть несколько необработанных исключений.</span><span class="sxs-lookup"><span data-stu-id="8ec63-110">Exceptions can be nested (for example, if an exception is thrown in a filter or in a function evaluation), so there may be multiple outstanding exceptions on a single thread.</span></span> <span data-ttu-id="8ec63-111">`GetCurrentException` Возвращает последнее исключение.</span><span class="sxs-lookup"><span data-stu-id="8ec63-111">`GetCurrentException` returns the most current exception.</span></span>  
  
 <span data-ttu-id="8ec63-112">Объект и тип исключения могут меняться в течение всего времени существования исключения.</span><span class="sxs-lookup"><span data-stu-id="8ec63-112">The exception object and type may change throughout the life of the exception.</span></span> <span data-ttu-id="8ec63-113">Например, после возникновения исключения типа x среда CLR может закончится нехваткой памяти и повысить ее до исключения нехватки памяти.</span><span class="sxs-lookup"><span data-stu-id="8ec63-113">For example, after an exception of type x is thrown, the common language runtime (CLR) may run out of memory and promote it to an out-of-memory exception.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="8ec63-114">Требования</span><span class="sxs-lookup"><span data-stu-id="8ec63-114">Requirements</span></span>  

 <span data-ttu-id="8ec63-115">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="8ec63-115">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="8ec63-116">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="8ec63-116">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="8ec63-117">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="8ec63-117">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="8ec63-118">**.NET Framework версии:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="8ec63-118">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
