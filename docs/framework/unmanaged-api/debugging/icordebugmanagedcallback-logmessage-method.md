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
ms.openlocfilehash: 92b2a7f7f1dd98f0d847119a6431e3816c16d5da
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/24/2020
ms.locfileid: "95679576"
---
# <a name="icordebugmanagedcallbacklogmessage-method"></a><span data-ttu-id="36c9e-102">Метод ICorDebugManagedCallback::LogMessage</span><span class="sxs-lookup"><span data-stu-id="36c9e-102">ICorDebugManagedCallback::LogMessage Method</span></span>

<span data-ttu-id="36c9e-103">Уведомляет отладчик о том, что управляемый поток среды CLR вызвал метод в <xref:System.Diagnostics.EventLog> классе для записи события в журнал.</span><span class="sxs-lookup"><span data-stu-id="36c9e-103">Notifies the debugger that a common language runtime (CLR) managed thread has called a method in the <xref:System.Diagnostics.EventLog> class to log an event.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="36c9e-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="36c9e-104">Syntax</span></span>  
  
```cpp  
HRESULT LogMessage (  
    [in] ICorDebugAppDomain  *pAppDomain,  
    [in] ICorDebugThread     *pThread,  
    [in] LONG                 lLevel,  
    [in] WCHAR               *pLogSwitchName,  
    [in] WCHAR               *pMessage  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="36c9e-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="36c9e-105">Parameters</span></span>  

 `pAppDomain`  
 <span data-ttu-id="36c9e-106">окне Указатель на объект ICorDebugAppDomain, представляющий домен приложения, содержащий управляемый поток, который зарегистрировал событие.</span><span class="sxs-lookup"><span data-stu-id="36c9e-106">[in] A pointer to an ICorDebugAppDomain object that represents the application domain containing the managed thread that logged the event.</span></span>  
  
 `pThread`  
 <span data-ttu-id="36c9e-107">окне Указатель на объект ICorDebugThread, представляющий управляемый поток.</span><span class="sxs-lookup"><span data-stu-id="36c9e-107">[in] A pointer to an ICorDebugThread object that represents the managed thread.</span></span>  
  
 `lLevel`  
 <span data-ttu-id="36c9e-108">окне Значение перечисления [логгинглевеленум](logginglevelenum-enumeration.md) , указывающее степень серьезности описательного сообщения, записанного в журнал событий.</span><span class="sxs-lookup"><span data-stu-id="36c9e-108">[in] A value of the [LoggingLevelEnum](logginglevelenum-enumeration.md) enumeration that indicates the severity level of the descriptive message that was written to the event log.</span></span>  
  
 `pLogSwitchName`  
 <span data-ttu-id="36c9e-109">окне Указатель на имя переключателя трассировки.</span><span class="sxs-lookup"><span data-stu-id="36c9e-109">[in] A pointer to the name of the tracing switch.</span></span>  
  
 `pMessage`  
 <span data-ttu-id="36c9e-110">окне Указатель на сообщение, записанное в журнал событий.</span><span class="sxs-lookup"><span data-stu-id="36c9e-110">[in] A pointer to the message that was written to the event log.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="36c9e-111">Требования</span><span class="sxs-lookup"><span data-stu-id="36c9e-111">Requirements</span></span>  

 <span data-ttu-id="36c9e-112">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="36c9e-112">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="36c9e-113">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="36c9e-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="36c9e-114">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="36c9e-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="36c9e-115">**.NET Framework версии:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="36c9e-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="36c9e-116">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="36c9e-116">See also</span></span>

- [<span data-ttu-id="36c9e-117">Интерфейс ICorDebugManagedCallback</span><span class="sxs-lookup"><span data-stu-id="36c9e-117">ICorDebugManagedCallback Interface</span></span>](icordebugmanagedcallback-interface.md)
