---
title: Метод ICorDebugILFrame4::GetCodeEx
ms.date: 03/30/2017
dev_langs:
- cpp
api_name:
- ICorDebugILFrame4.GetLocalVariableEx
api_location:
- mscordbi.dll
api_type:
- COM
ms.assetid: aeda0e42-29ee-4ca8-9f21-ac4641677a62
topic_type:
- apiref
ms.openlocfilehash: a88bb02626dc125c494e4bbe68bfe6ed8bfd3b7b
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/24/2020
ms.locfileid: "95719649"
---
# <a name="icordebugilframe4getcodeex-method"></a>Метод ICorDebugILFrame4::GetCodeEx

[Поддерживается в .NET Framework 4.5.2 и более поздних версиях.]  
  
 Получает указатель на код, который выполняется этим кадром стека.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp
HRESULT GetCodeEx(  
   [in] ILCodeKind flags,
   [out] ICorDebugCode **ppCode  
);  
```  
  
## <a name="parameters"></a>Параметры  

 `flags`  
 окне Элемент перечисления [ILCodeKind](ilcodekind-enumeration.md) , указывающий, включается ли в кадр промежуточный язык (IL), определенный в запросе ReJIT профилировщика.  
  
 `ppCode`  
 заполняет Указатель на адрес объекта ICorDebugCode, который представляет код, который исполняется этим кадром стека.  
  
## <a name="remarks"></a>Комментарии  

 Этот метод аналогичен методу [ICorDebugFrame::-Code](icordebugframe-getcode-method.md) , за исключением того, что он дополнительно получает доступ к коду, определенному в запросе ReJIT профилировщика. Вызов этого метода со `flags` значением `ILCODE_ORIGINAL_IL` эквивалентен вызову метода " [.](icordebugframe-getcode-method.md)" Если метод инструментирован, его Il будет недоступен. `ILCODE_REJIT_IL` позволяет отладчику получить доступ к промежуточному языку, определенному запросом ReJIT профилировщика. Если IL не инструментирован, `ppCode` имеет **значение NULL** и метод возвращает `S_OK` .  
  
## <a name="requirements"></a>Требования  

 **Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).  
  
 **Заголовок:** CorDebug.idl, CorDebug.h  
  
 **Библиотека:** CorGuids.lib  
  
 **.NET Framework версии:**[!INCLUDE[net_current_v452plus](../../../../includes/net-current-v452plus-md.md)]  
  
## <a name="see-also"></a>См. также раздел

- [Интерфейс ICorDebugILFrame4](icordebugilframe4-interface.md)
- [Интерфейсы отладки](debugging-interfaces.md)
- [ReJIT: руководство по How-To](/archive/blogs/davbr/rejit-a-how-to-guide)
