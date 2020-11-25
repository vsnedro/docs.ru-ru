---
title: Метод ICorDebugILCode::GetEHClauses
ms.date: 03/30/2017
dev_langs:
- cpp
api_name:
- ICorDebugILCode.GetEHClauses
api_location:
- mscordbi.dll
api_type:
- COM
ms.assetid: cf7a0e00-06ae-47a5-8037-598b26196802
topic_type:
- apiref
ms.openlocfilehash: 38936a57944e9a0920c374f473c4cbe8e8d70abb
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/24/2020
ms.locfileid: "95728671"
---
# <a name="icordebugilcodegetehclauses-method"></a>Метод ICorDebugILCode::GetEHClauses

[Поддерживается в .NET Framework 4.5.2 и более поздних версиях.]  
  
 Возвращает указатель на список предложений обработки исключений, определенных для этого промежуточного языка.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp
HRESULT GetEHClauses(  
   [in] ULONG32 cClauses,  
   [out] ULONG32 * pcClauses,  
   [out, size_is(cClauses), length_is(*pcClauses)] CorDebugEHClause clauses[]);  
```  
  
## <a name="parameters"></a>Параметры  

 `cClauses`  
 [в] Емкость хранилища массива `clauses`. Дополнительные сведения см. в разделе "Примечания".  
  
 `pcClauses`  
 [из] Количество предложений, информация о которых записывается в массив `clauses`.  
  
 предложения  
 заполняет Массив объектов [кордебужехклаусе](cordebugehclause-structure.md) , содержащих сведения о предложениях обработки исключений, определенных для этого IL.  
  
## <a name="remarks"></a>Комментарии  

 Если значение `cClauses` равно 0 и `pcClauses` не равно **null**, то параметру присваивается `pcClauses` число доступных предложений обработки исключений. Если значение `cClauses` не равно 0, оно обозначает емкость хранилища массива `clauses`. Когда метод возвращает не пустое значение, `clauses` содержит максимум элементов `cClauses`, а значению `pcClauses` присваивается количество предложений, записанных в массив `clauses` на данный момент.  
  
## <a name="requirements"></a>Требования  

 **Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).  
  
 **Заголовок:** CorDebug.idl, CorDebug.h  
  
 **Библиотека:** CorGuids.lib  
  
 **.NET Framework версии:**[!INCLUDE[net_current_v452plus](../../../../includes/net-current-v452plus-md.md)]  
  
## <a name="see-also"></a>См. также раздел

- [Интерфейс ICorDebugILCode](icordebugilcode-interface.md)
- [Структура CorDebugEHClause](cordebugehclause-structure.md)
- [Интерфейсы отладки](debugging-interfaces.md)
