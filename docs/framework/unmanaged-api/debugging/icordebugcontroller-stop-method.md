---
description: 'Дополнительные сведения о методе: ICorDebugController:: останавливаться'
title: Метод ICorDebugController::Stop
ms.date: 03/30/2017
api_name:
- ICorDebugController.Stop
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugController::Stop
helpviewer_keywords:
- Stop method, ICorDebugController interface [.NET Framework debugging]
- ICorDebugController::Stop method [.NET Framework debugging]
ms.assetid: c34e79be-a7fb-479e-8dec-d126a4c330e5
topic_type:
- apiref
ms.openlocfilehash: 613fd81a03114580ae3d826a94d855023895b694
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2021
ms.locfileid: "99764610"
---
# <a name="icordebugcontrollerstop-method"></a>Метод ICorDebugController::Stop

Выполняет совместную работу во всех потоках, где выполняется управляемый код в процессе.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
HRESULT Stop (  
    [in] DWORD dwTimeoutIgnored  
);  
```  
  
## <a name="parameters"></a>Параметры  

 `dwTimeoutIgnored`  
 Не используется.  
  
## <a name="remarks"></a>Remarks  

 `Stop` выполняет совместную работу всех потоков, выполняющих управляемый код в процессе. Во время сеанса отладки, доступного только для управляемого кода, неуправляемые потоки могут продолжать выполняться (но будут заблокированы при попытке вызвать управляемый код). Во время сеанса отладки взаимодействия неуправляемые потоки также будут остановлены. `dwTimeoutIgnored`Значение в настоящее время игнорируется и обрабатывается как БЕСконечное (-1). Если совместная остановка завершается сбоем из-за взаимоблокировки, все потоки приостанавливаются и возвращается E_TIMEOUT.  
  
> [!NOTE]
> `Stop` — единственный синхронный метод в API отладки. Когда `Stop` функция возвращает S_OK, процесс останавливается. Обратный вызов не предоставляется для уведомления прослушивателей об ошибке. Отладчик должен вызвать [ICorDebugController:: Continue](icordebugcontroller-continue-method.md) , чтобы разрешить возобновление процесса.  
  
 Отладчик поддерживает счетчик "останавливается". Когда счетчик переходит в нулевое значение, контроллер возобновляется. Каждый вызов `Stop` или каждый отправленный обратный вызов увеличивает счетчик. Каждый вызов `ICorDebugController::Continue` уменьшает значение счетчика.  
  
## <a name="requirements"></a>Требования  

 **Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).  
  
 **Заголовок:** CorDebug.idl, CorDebug.h  
  
 **Библиотека:** CorGuids.lib  
  
 **Платформа .NET Framework версии:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>См. также
