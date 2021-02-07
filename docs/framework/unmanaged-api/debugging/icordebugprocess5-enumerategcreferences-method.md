---
description: 'Дополнительные сведения о методе: метод ICorDebugProcess5:: Енумератегкреференцес'
title: Метод ICorDebugProcess5::EnumerateGCReferences
ms.date: 03/30/2017
api_name:
- ICorDebugProcess5.EnumerateGCReferences
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugProcess5::EnumerateGCReferences
helpviewer_keywords:
- EnumerateGCReferences method, ICorDebugProcess5 interface [.NET Framework debugging]
- ICorDebugProcess5::EnumerateGCReferences method [.NET Framework debugging]
ms.assetid: 86c397c3-81d8-463e-a248-3cbe06c44d9d
topic_type:
- apiref
ms.openlocfilehash: 5145fd072b083ed107b874fe99403984915233ec
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2021
ms.locfileid: "99746416"
---
# <a name="icordebugprocess5enumerategcreferences-method"></a>Метод ICorDebugProcess5::EnumerateGCReferences

Возвращает перечислитель для всех объектов, которые должны быть собраны в процессе сборки мусора.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
HRESULT EnumerateGCReferences(  
    [in] Bool enumerateWeakReferences,
    [out] ICorDebugGCReferenceEnum **ppEnum  
);  
```  
  
## <a name="parameters"></a>Параметры  

 `enumerateWeakReferences`  
 окне Логическое значение, указывающее, будут ли также перечисляться слабые ссылки. Если `enumerateWeakReferences` имеет значение `true` , `ppEnum` перечислитель включает как строгие ссылки, так и слабые ссылки. Если `enumerateWeakReferences` имеет значение `false` , перечислитель включает только строгие ссылки.  
  
 `ppEnum`  
 заполняет Указатель на адрес [ICorDebugGCReferenceEnum](icordebuggcreferenceenum-interface.md) , который является перечислителем для объектов, которые должны быть собраны в мусор.  
  
## <a name="remarks"></a>Remarks  

 Этот метод предоставляет способ определения полной цепочки корневых объектов для любого управляемого объекта в процессе и может использоваться для определения причины, по которой объект остается в рабочем состоянии.  
  
## <a name="requirements"></a>Требования  

 **Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).  
  
 **Заголовок:** CorDebug.idl, CorDebug.h  
  
 **Библиотека:** CorGuids.lib  
  
 **Платформа .NET Framework версии:**[!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]  
  
## <a name="see-also"></a>См. также

- [Интерфейс ICorDebugProcess5](icordebugprocess5-interface.md)
- [Интерфейсы отладки](debugging-interfaces.md)
