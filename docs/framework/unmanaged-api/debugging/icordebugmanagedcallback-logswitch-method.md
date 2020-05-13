---
title: Метод ICorDebugManagedCallback::LogSwitch
ms.date: 03/30/2017
api_name:
- ICorDebugManagedCallback.LogSwitch
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugManagedCallback::LogSwitch
helpviewer_keywords:
- LogSwitch method [.NET Framework debugging]
- ICorDebugManagedCallback::LogSwitch method [.NET Framework debugging]
ms.assetid: 0ac59d27-783f-4a87-b7a8-baa3ccc54582
topic_type:
- apiref
ms.openlocfilehash: f095bc0272e0e6f16467b9758d5e392d371139dd
ms.sourcegitcommit: 488aced39b5f374bc0a139a4993616a54d15baf0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/12/2020
ms.locfileid: "83212689"
---
# <a name="icordebugmanagedcallbacklogswitch-method"></a><span data-ttu-id="956f9-102">Метод ICorDebugManagedCallback::LogSwitch</span><span class="sxs-lookup"><span data-stu-id="956f9-102">ICorDebugManagedCallback::LogSwitch Method</span></span>
<span data-ttu-id="956f9-103">Уведомляет отладчик о том, что управляемый поток среды CLR вызвал метод в <xref:System.Diagnostics.Switch> классе для создания, изменения или удаления переключателя отладки или трассировки.</span><span class="sxs-lookup"><span data-stu-id="956f9-103">Notifies the debugger that a common language runtime (CLR) managed thread has called a method in the <xref:System.Diagnostics.Switch> class to create, modify, or delete a debugging/tracing switch.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="956f9-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="956f9-104">Syntax</span></span>  
  
```cpp  
HRESULT LogSwitch (  
    [in] ICorDebugAppDomain  *pAppDomain,  
    [in] ICorDebugThread     *pThread,  
    [in] LONG                 lLevel,  
    [in] ULONG                ulReason,  
    [in] WCHAR               *pLogSwitchName,  
    [in] WCHAR               *pParentName);  
```  
  
## <a name="parameters"></a><span data-ttu-id="956f9-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="956f9-105">Parameters</span></span>  
 `PAppDomain`  
 <span data-ttu-id="956f9-106">окне Указатель на объект ICorDebugAppDomain, представляющий домен приложения, содержащий управляемый поток, который создал, изменил или удалил параметр отладки/трассировки.</span><span class="sxs-lookup"><span data-stu-id="956f9-106">[in] A pointer to an ICorDebugAppDomain object that represents the application domain containing the managed thread that created, modified, or deleted a debugging/tracing switch.</span></span>  
  
 `pThread`  
 <span data-ttu-id="956f9-107">окне Указатель на объект ICorDebugThread, представляющий управляемый поток.</span><span class="sxs-lookup"><span data-stu-id="956f9-107">[in] A pointer to an ICorDebugThread object that represents the managed thread.</span></span>  
  
 `lLevel`  
 <span data-ttu-id="956f9-108">окне Значение, указывающее степень серьезности описательного сообщения, записанного в журнал событий.</span><span class="sxs-lookup"><span data-stu-id="956f9-108">[in] A value that indicates the severity level of the descriptive message that was written to the event log.</span></span>  
  
 `ulReason`  
 <span data-ttu-id="956f9-109">окне Значение перечисления [логсвитчкаллреасон](logswitchcallreason-enumeration.md) , указывающее операцию, выполняемую с переключателем "Отладка/трассировка".</span><span class="sxs-lookup"><span data-stu-id="956f9-109">[in] A value of the [LogSwitchCallReason](logswitchcallreason-enumeration.md) enumeration that indicates the operation performed on the debugging/tracing switch.</span></span>  
  
 `pLogSwitchName`  
 <span data-ttu-id="956f9-110">окне Указатель на имя переключателя отладки/трассировки.</span><span class="sxs-lookup"><span data-stu-id="956f9-110">[in] A pointer to the name of the debugging/tracing switch.</span></span>  
  
 `pParentName`  
 <span data-ttu-id="956f9-111">окне Указатель на имя родителя переключателя "Отладка/трассировка".</span><span class="sxs-lookup"><span data-stu-id="956f9-111">[in] A pointer to the name of the parent of the debugging/tracing switch.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="956f9-112">Требования</span><span class="sxs-lookup"><span data-stu-id="956f9-112">Requirements</span></span>  
 <span data-ttu-id="956f9-113">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="956f9-113">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="956f9-114">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="956f9-114">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="956f9-115">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="956f9-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="956f9-116">**.NET Framework версии:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="956f9-116">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="956f9-117">См. также</span><span class="sxs-lookup"><span data-stu-id="956f9-117">See also</span></span>

- [<span data-ttu-id="956f9-118">Интерфейс ICorDebugManagedCallback</span><span class="sxs-lookup"><span data-stu-id="956f9-118">ICorDebugManagedCallback Interface</span></span>](icordebugmanagedcallback-interface.md)
