---
description: 'Дополнительные сведения о методе: Икордебугилкоде:: GetEHClauses'
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
ms.openlocfilehash: e790f0f1f69a38d3a1be9e98eacfc5e37be0fd05
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2021
ms.locfileid: "99660665"
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
  
## <a name="remarks"></a>Remarks  

 Если значение `cClauses` равно 0 и `pcClauses` не равно **null**, то параметру присваивается `pcClauses` число доступных предложений обработки исключений. Если значение `cClauses` не равно 0, оно обозначает емкость хранилища массива `clauses`. Когда метод возвращает не пустое значение, `clauses` содержит максимум элементов `cClauses`, а значению `pcClauses` присваивается количество предложений, записанных в массив `clauses` на данный момент.  
  
## <a name="requirements"></a>Требования  

 **Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).  
  
 **Заголовок:** CorDebug.idl, CorDebug.h  
  
 **Библиотека:** CorGuids.lib  
  
 **Платформа .NET Framework версии:**[!INCLUDE[net_current_v452plus](../../../../includes/net-current-v452plus-md.md)]  
  
## <a name="see-also"></a>См. также

- [Интерфейс ICorDebugILCode](icordebugilcode-interface.md)
- [Структура CorDebugEHClause](cordebugehclause-structure.md)
- [Интерфейсы отладки](debugging-interfaces.md)
