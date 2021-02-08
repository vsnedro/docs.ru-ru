---
description: 'Дополнительные сведения о методе: ICorDebugGCReferenceEnum:: Next'
title: Метод ICorDebugGCReferenceEnum::Next
ms.date: 03/30/2017
api_name:
- ICorDebugGCReferenceEnum.Next
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugGCReferenceEnum::Next
helpviewer_keywords:
- Next method, ICorDebugGCReferenceEnum interface [.NET Framework debugging]
- ICorDebugGCReferenceEnum::Next method [.NET Framework debugging]
ms.assetid: 91b1345c-a94f-4ef8-9696-3823d06c6d05
topic_type:
- apiref
ms.openlocfilehash: aec135fcb737a200d5a267529fa812c0852a24df
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2021
ms.locfileid: "99803702"
---
# <a name="icordebuggcreferenceenumnext-method"></a>Метод ICorDebugGCReferenceEnum::Next

Возвращает указанное число экземпляров [COR_GC_REFERENCE](cor-gc-reference-structure.md) , содержащих сведения об объектах, которые будут собираться сборщиком мусора.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
HRESULT Next(  
    [in] ULONG celt,    [out, size_is(celt), length_is(*pceltFetched)] COR_GC_REFERENCE roots[],
    [out] ULONG *pceltFetched  
);  
```  
  
## <a name="parameters"></a>Параметры  

 celt  
 окне Число извлекаемых корневых элементов.  
  
 корня  
 заполняет Массив указателей, каждый из которых указывает на объект [COR_GC_REFERENCE](cor-gc-reference-structure.md) , представляющий корень объекта, который должен быть собран сборщиком мусора.  
  
 pceltFetched  
 заполняет Указатель на число объектов [COR_GC_REFERENCE](cor-gc-reference-structure.md) , фактически возвращаемых в `roots` . Это значение может быть `null`, если параметр `celt` имеет значение 1.  
  
## <a name="remarks"></a>Remarks  
  
## <a name="requirements"></a>Требования  

 **Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).  
  
 **Заголовок:** CorDebug.idl, CorDebug.h  
  
 **Библиотека:** CorGuids.lib  
  
 **Платформа .NET Framework версии:**[!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]  
  
## <a name="see-also"></a>См. также

- [Интерфейс ICorDebugGCReferenceEnum](icordebuggcreferenceenum-interface.md)
- [Интерфейсы отладки](debugging-interfaces.md)
