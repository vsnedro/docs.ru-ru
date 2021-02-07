---
description: 'Дополнительные сведения о методе: Икордебугблоккингобжектенум:: Next'
title: Метод ICorDebugBlockingObjectEnum::Next
ms.date: 03/30/2017
api_name:
- ICorDebugBlockingObjectEnum.Next Method
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugBlockingObjectEnum::Next
helpviewer_keywords:
- Next method, ICorDebugBlockingObjectEnum interface [.NET Framework debugging]
- ICorDebugBlockingObjectEnum::Next method [.NET Framework debugging]
ms.assetid: 0121753f-ebea-48d0-aeb2-ed7fda76dc60
topic_type:
- apiref
ms.openlocfilehash: 66999ebf333c7115790b56afc1dc1d1ab7c47d69
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2021
ms.locfileid: "99711821"
---
# <a name="icordebugblockingobjectenumnext-method"></a>Метод ICorDebugBlockingObjectEnum::Next

Возвращает указанное число объектов [CorDebugBlockingObject](cordebugblockingobject-structure.md) из перечисления, начиная с текущей позиции.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
HRESULT Next([in] ULONG  celt,  
             [out, size_is(celt), length_is(*pceltFetched)]  
                           CorDebugBlockingObject values[],  
             [out] ULONG *pceltFetched;  
```  
  
## <a name="parameters"></a>Параметры  

 `celt`  
 окне Число извлекаемых объектов.  
  
 `values`  
 заполняет Массив указателей на объекты [CorDebugBlockingObject](cordebugblockingobject-structure.md) .  
  
 `pceltFetched`  
 заполняет Указатель на количество полученных объектов.  
  
## <a name="return-value"></a>Возвращаемое значение  

 Этот метод возвращает следующие специфичные результаты HRESULT.  
  
|HRESULT|Описание:|  
|-------------|-----------------|  
|S_OK|Метод завершился успешно.|  
|S_FALSE|Значение параметра `pceltFetched` не равно `celt`.|  
  
## <a name="remarks"></a>Remarks  

 Этот метод работает, как типичный перечислитель COM.  
  
 Значения входного массива должны иметь размер не ниже `celt` . Массив будет заполнен либо следующими `celt` значениями в перечислении, либо со всеми оставшимися значениями, если они меньше `celt` , чем осталось. При возврате из этого метода `pceltFetched` будет заполнено количество полученных значений. Если `values` содержит недопустимые указатели или указывает на буфер, который меньше `celt` , или если `pceltFetched` является недопустимым указателем, результат не определен.  
  
> [!NOTE]
> Хотя структуру [CorDebugBlockingObject](cordebugblockingobject-structure.md) не нужно освобождать, интерфейс "ICorDebugValue" внутри него должен быть освобожден.  
  
## <a name="requirements"></a>Требования  

 **Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).  
  
 **Заголовок:** CorDebug.idl, CorDebug.h  
  
 **Библиотека:** CorGuids.lib  
  
 **Платформа .NET Framework версии:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a>См. также

- [Интерфейс ICorDebugDataTarget](icordebugdatatarget-interface.md)
- [Интерфейсы отладки](debugging-interfaces.md)
- [Отладка](index.md)
