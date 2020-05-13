---
title: Метод ICorDebugManagedCallback::LogMessage
ms.date: 03/30/2017
api_name:
- ICorDebugManagedCallback.LogMessage
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugManagedCallback::LogMessage
helpviewer_keywords:
- ICorDebugManagedCallback::LogMessage method [.NET Framework debugging]
- LogMessage method [.NET Framework debugging]
ms.assetid: d218554a-bf42-4d88-833d-ede30de67a53
topic_type:
- apiref
ms.openlocfilehash: c60af0ccfb143e68be3b987b0caf92fe3d992b4d
ms.sourcegitcommit: 488aced39b5f374bc0a139a4993616a54d15baf0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/12/2020
ms.locfileid: "83212715"
---
# <a name="icordebugmanagedcallbacklogmessage-method"></a><span data-ttu-id="fc434-102">Метод ICorDebugManagedCallback::LogMessage</span><span class="sxs-lookup"><span data-stu-id="fc434-102">ICorDebugManagedCallback::LogMessage Method</span></span>
<span data-ttu-id="fc434-103">Уведомляет отладчик о том, что управляемый поток среды CLR вызвал метод в <xref:System.Diagnostics.EventLog> классе для записи события в журнал.</span><span class="sxs-lookup"><span data-stu-id="fc434-103">Notifies the debugger that a common language runtime (CLR) managed thread has called a method in the <xref:System.Diagnostics.EventLog> class to log an event.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="fc434-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="fc434-104">Syntax</span></span>  
  
```cpp  
HRESULT LogMessage (  
    [in] ICorDebugAppDomain  *pAppDomain,  
    [in] ICorDebugThread     *pThread,  
    [in] LONG                 lLevel,  
    [in] WCHAR               *pLogSwitchName,  
    [in] WCHAR               *pMessage  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="fc434-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="fc434-105">Parameters</span></span>  
 `pAppDomain`  
 <span data-ttu-id="fc434-106">окне Указатель на объект ICorDebugAppDomain, представляющий домен приложения, содержащий управляемый поток, который зарегистрировал событие.</span><span class="sxs-lookup"><span data-stu-id="fc434-106">[in] A pointer to an ICorDebugAppDomain object that represents the application domain containing the managed thread that logged the event.</span></span>  
  
 `pThread`  
 <span data-ttu-id="fc434-107">окне Указатель на объект ICorDebugThread, представляющий управляемый поток.</span><span class="sxs-lookup"><span data-stu-id="fc434-107">[in] A pointer to an ICorDebugThread object that represents the managed thread.</span></span>  
  
 `lLevel`  
 <span data-ttu-id="fc434-108">окне Значение перечисления [логгинглевеленум](logginglevelenum-enumeration.md) , указывающее степень серьезности описательного сообщения, записанного в журнал событий.</span><span class="sxs-lookup"><span data-stu-id="fc434-108">[in] A value of the [LoggingLevelEnum](logginglevelenum-enumeration.md) enumeration that indicates the severity level of the descriptive message that was written to the event log.</span></span>  
  
 `pLogSwitchName`  
 <span data-ttu-id="fc434-109">окне Указатель на имя переключателя трассировки.</span><span class="sxs-lookup"><span data-stu-id="fc434-109">[in] A pointer to the name of the tracing switch.</span></span>  
  
 `pMessage`  
 <span data-ttu-id="fc434-110">окне Указатель на сообщение, записанное в журнал событий.</span><span class="sxs-lookup"><span data-stu-id="fc434-110">[in] A pointer to the message that was written to the event log.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="fc434-111">Требования</span><span class="sxs-lookup"><span data-stu-id="fc434-111">Requirements</span></span>  
 <span data-ttu-id="fc434-112">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="fc434-112">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="fc434-113">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="fc434-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="fc434-114">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="fc434-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="fc434-115">**.NET Framework версии:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="fc434-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fc434-116">См. также</span><span class="sxs-lookup"><span data-stu-id="fc434-116">See also</span></span>

- [<span data-ttu-id="fc434-117">Интерфейс ICorDebugManagedCallback</span><span class="sxs-lookup"><span data-stu-id="fc434-117">ICorDebugManagedCallback Interface</span></span>](icordebugmanagedcallback-interface.md)
