---
title: Метод ICorDebugRegisterSet::GetRegistersAvailable
ms.date: 03/30/2017
api_name:
- ICorDebugRegisterSet.GetRegistersAvailable
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugRegisterSet::GetRegistersAvailable
helpviewer_keywords:
- ICorDebugRegisterSet::GetRegistersAvailable method [.NET Framework debugging]
- GetRegistersAvailable method, ICorDebugRegisterSet interface [.NET Framework debugging]
ms.assetid: 4ba08ffa-55a2-4662-9d6d-4738f1db60c9
topic_type:
- apiref
ms.openlocfilehash: d28c130e55cbebf29348752780c03b03c1b8f358
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/24/2020
ms.locfileid: "95716997"
---
# <a name="icordebugregistersetgetregistersavailable-method"></a>Метод ICorDebugRegisterSet::GetRegistersAvailable

Возвращает битовую маску, указывающую, какие регистры в этом [ICorDebugRegisterSet](icordebugregisterset-interface.md) в настоящее время доступны.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
HRESULT GetRegistersAvailable (  
    [out] ULONG64   *pAvailable  
);  
```  
  
## <a name="parameters"></a>Параметры  

 `pAvailable`  
 заполняет Битовая маска, указывающая, какие регистры доступны в настоящее время.  
  
## <a name="remarks"></a>Комментарии  

 Регистр может быть недоступен, если его значение не может быть определено для данной ситуации.  
  
 Возвращаемая маска содержит бит для каждого регистра (1 << индекс регистра). Значение бита равно 1, если регистр доступен, или 0, если он недоступен.  
  
## <a name="requirements"></a>Требования  

 **Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).  
  
 **Заголовок:** CorDebug.idl, CorDebug.h  
  
 **Библиотека:** CorGuids.lib  
  
 **.NET Framework версии:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>См. также раздел

- [Интерфейс ICorDebugRegisterSet](icordebugregisterset-interface.md)
- [Интерфейс ICorDebugRegisterSet2](icordebugregisterset2-interface.md)
