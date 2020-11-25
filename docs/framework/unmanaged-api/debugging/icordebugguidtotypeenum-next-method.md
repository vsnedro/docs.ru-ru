---
title: Метод ICorDebugGuidToTypeEnum::Next
ms.date: 03/30/2017
api_name:
- ICorDebugGuidToTypeEnum.Next
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugGuidToTypeEnum::Next
helpviewer_keywords:
- ICorDebugGuidToTypeEnum::Next method [.NET Framework debugging]
- Next method, ICorDebugGuidToTypeEnum interface [.NET Framework debugging]
ms.assetid: c9937666-8e18-484d-9fe0-b9ac95199530
topic_type:
- apiref
ms.openlocfilehash: 68f548705213da7d715ae569116abae0cd24129d
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/24/2020
ms.locfileid: "95705661"
---
# <a name="icordebugguidtotypeenumnext-method"></a>Метод ICorDebugGuidToTypeEnum::Next

Возвращает указанное число экземпляров [кордебуггуидтотипемаппинг](cordebugguidtotypemapping-structure.md) , которые сопоставляют идентификаторы GUID со сведениями о типе.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
HRESULT Next(  
    [in] ULONG celt,  
    [out, size_is(celt), length_is(*pceltFetched] CorDebugGuidToTypeMapping values[  ],  
    [out] ULONG *pceltFetched  
);  
```  
  
## <a name="parameters"></a>Параметры  

 `celt`  
 окне Число получаемых объектов сопоставления GUID и типа.  
  
 `values`  
 заполняет Массив указателей, каждый из которых указывает на объект [кордебуггуидтотипемаппинг](cordebugguidtotypemapping-structure.md) , который сопоставляет идентификатор GUID среда выполнения Windows с соответствующим объектом ICorDebugType.  
  
 `pceltFetched`  
 заполняет Указатель на число объектов [кордебуггуидтотипемаппинг](cordebugguidtotypemapping-structure.md) , фактически возвращаемых в `values` .  
  
## <a name="remarks"></a>Remarks  
  
## <a name="requirements"></a>Требования  

 **Платформы:** среда выполнения Windows  
  
 **Заголовок:** CorDebug.idl, CorDebug.h  
  
 **Библиотека:** CorGuids.lib  
  
 **.NET Framework версии:**[!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]  
  
## <a name="see-also"></a>См. также раздел

- [Интерфейс ICorDebugGuidToTypeEnum](icordebugguidtotypeenum-interface.md)
- [Интерфейсы отладки](debugging-interfaces.md)
