---
title: Интерфейс ICorDebugFunction2
ms.date: 03/30/2017
api_name:
- ICorDebugFunction2
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugFunction2
helpviewer_keywords:
- ICorDebugFunction2 interface [.NET Framework debugging]
ms.assetid: 2b936bef-9b75-48bf-859f-42e419c65f1c
topic_type:
- apiref
ms.openlocfilehash: d9e84a70d72db1338c80140ce3350774bfae4bca
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/24/2020
ms.locfileid: "95726279"
---
# <a name="icordebugfunction2-interface"></a>Интерфейс ICorDebugFunction2

Логически расширяет интерфейс ICorDebugFunction, чтобы обеспечить поддержку Только мой код пошаговой отладке, которая пропускает код, не являющийся пользовательским.  
  
## <a name="methods"></a>Методы  
  
|Метод|Описание|  
|------------|-----------------|  
|[Метод EnumerateNativeCode](icordebugfunction2-enumeratenativecode-method.md)|(Еще не реализовано.) Возвращает указатель интерфейса на Икордебугкодинум, содержащий операторы машинного кода в функции, на которую ссылается этот объект ICorDebugFunction2.|  
|[Метод GetJMCStatus](icordebugfunction2-getjmcstatus-method.md)|Возвращает значение, указывающее, помечена ли эта функция как пользовательский код.|  
|[Метод GetVersionNumber](icordebugfunction2-getversionnumber-method.md)|Возвращает версию функции "изменить и продолжить".|  
|[Метод SetJMCStatus](icordebugfunction2-setjmcstatus-method.md)|Помечает эту функцию для Только мой код пошагового выполнения.|  
  
## <a name="remarks"></a>Комментарии  
  
> [!NOTE]
> Этот интерфейс не поддерживает удаленные вызовы между компьютерами или между процессами.  
  
## <a name="requirements"></a>Требования  

 **Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).  
  
 **Заголовок:** CorDebug.idl, CorDebug.h  
  
 **Библиотека:** CorGuids.lib  
  
 **.NET Framework версии:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>См. также раздел

- [Интерфейсы отладки](debugging-interfaces.md)
