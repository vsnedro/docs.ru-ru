---
description: 'Дополнительные сведения о методе: ICorDebugGuidToTypeEnum:: Next'
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
ms.openlocfilehash: 0ab05cc0689c76c0bb185205ea00c5ccebfcbe03
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2021
ms.locfileid: "99661003"
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
  
 **Платформа .NET Framework версии:**[!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]  
  
## <a name="see-also"></a>См. также

- [Интерфейс ICorDebugGuidToTypeEnum](icordebugguidtotypeenum-interface.md)
- [Интерфейсы отладки](debugging-interfaces.md)
