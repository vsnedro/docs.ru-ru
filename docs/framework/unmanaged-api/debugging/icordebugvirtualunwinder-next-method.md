---
title: Метод ICorDebugVirtualUnwinder::Next
ms.date: 03/30/2017
ms.assetid: 790e0426-e5cd-49fd-a792-f8c8635d72fe
ms.openlocfilehash: bfc827a1503b0367a442e3f3ca0915bd2aaeb01e
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/24/2020
ms.locfileid: "95725954"
---
# <a name="icordebugvirtualunwindernext-method"></a>Метод ICorDebugVirtualUnwinder::Next

Переходит в контекст вызывающего объекта.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
HRESULT Next();  
```  
  
## <a name="parameters"></a>Параметры  

 Нет.  
  
## <a name="return-value"></a>Возвращаемое значение  

 Значение `S_OK`, если очистка произошла успешно, или значение `CORDBG_S_AT_END_OF_STACK`, если не удалось завершить очистку, поскольку больше нет фреймов.  
  
 Если возвращается значение HRESULT, указывающее на ошибку, API ICorDebug будут возвращать `CORDBG_E_DATA_TARGET_ERROR`.  
  
## <a name="remarks"></a>Комментарии  

 Обходчик стека должен проверять, что он продвигается вперед, поэтому в конечном итоге вызов `Next` вернет значение HRESULT, указывающее на ошибку, или значение `CORDBG_S_AT_END_OF_STACK`. Неопределенный возврат `S_OK` может привести к бесконечному циклу.  
  
> [!NOTE]
> Этот метод доступен только в машинном коде .NET.  
  
## <a name="requirements"></a>Требования  

 **Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).  
  
 **Заголовок:** CorDebug.idl, CorDebug.h  
  
 **Библиотека:** CorGuids.lib  
  
 **.NET Framework версии:**[!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]  
  
## <a name="see-also"></a>См. также раздел

- [Интерфейс ICorDebugMemoryBuffer](icordebugmemorybuffer-interface.md)
- [Интерфейсы отладки](debugging-interfaces.md)
