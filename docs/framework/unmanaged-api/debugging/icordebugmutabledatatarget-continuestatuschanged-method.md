---
description: 'Дополнительные сведения о методе: Икордебугмутабледататаржет:: Континуестатусчанжед'
title: Метод ICorDebugMutableDataTarget::ContinueStatusChanged
ms.date: 03/30/2017
ms.assetid: 5a66d3f4-dd16-4d62-9dcc-0eab7041d894
ms.openlocfilehash: 6655d6f1a115b4879c73e356faa8e8785a110078
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2021
ms.locfileid: "99722507"
---
# <a name="icordebugmutabledatatargetcontinuestatuschanged-method"></a>Метод ICorDebugMutableDataTarget::ContinueStatusChanged

Изменяет состояние продолжения для незавершенных событий отладки в указанном потоке.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
HRESULT ContinueStatusChanged(  
   [in] DWORD dwThreadId,  
   [in] CORDB_CONTINUE_STATUS continueStatus);  
```  
  
## <a name="parameters"></a>Параметры  

 `dwThreadId`  
 Идентификатор потока, определяемый операционной системой.  
  
 `continueStatus`  
 Значение [COREDB_CONTINUE_STATUS](../common-data-types-unmanaged-api-reference.md), которое представляет новое запрошенное состояние продолжения.  
  
## <a name="remarks"></a>Remarks  

 Отладчик вызывает метод `ContinueStatusChanged` при вызове метода ICorDebug, требующего, чтобы способ обработки текущего события отладки потенциально отличался от способа, которым оно обычно обрабатывается. Например, если имеется незавершенное исключение и отладчик запрашивает операцию, которая будет отменять это исключение (например, [ICorDebugILFrame::SetIP](icordebugilframe-setip-method.md) или `FuncEval`), этот API используется для запроса отмены исключения.  
  
## <a name="requirements"></a>Требования  

 **Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).  
  
 **Заголовок:** CorDebug.idl, CorDebug.h  
  
 **Библиотека:** CorGuids.lib  
  
 **Платформа .NET Framework версии:**[!INCLUDE[net_current_v46plus](../../../../includes/net-current-v46plus-md.md)]  
  
## <a name="see-also"></a>См. также

- [Интерфейс ICorDebugMutableDataTarget](icordebugmutabledatatarget-interface.md)
- [Интерфейсы отладки](debugging-interfaces.md)
