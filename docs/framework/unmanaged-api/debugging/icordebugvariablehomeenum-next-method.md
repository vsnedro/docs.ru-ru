---
description: 'Дополнительные сведения о методе: ICorDebugVariableHomeEnum:: Next'
title: 'Метод ICorDebugVariableHomeEnum:: Next'
ms.date: 03/30/2017
api_name:
- ICorDebugVariableHomeEnum.Next
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugVariableHomeEnum::Next
helpviewer_keywords:
- ICorDebugVariableHomeEnum::Next method [.NET Framework debugging]
- Next method, ICorDebugVariableHomeEnum interface [.NET Framework debugging]
ms.assetid: eb9ea96c-5b58-4655-8104-094fc8b393b8
topic_type:
- apiref
ms.openlocfilehash: 0aa0174e67bceaa724ddfeadc2560d12e112b859
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2021
ms.locfileid: "99790611"
---
# <a name="icordebugvariablehomeenumnext-method"></a>Метод ICorDebugVariableHomeEnum:: Next

Возвращает указанное число экземпляров [ICorDebugVariableHome](icordebugvariablehome-interface.md) , содержащих сведения о локальных переменных и аргументах в функции.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
HRESULT Next(  
    [in] ULONG celt,  
    [out, size_is(celt), length_is(*pceltFetched)] ICorDebugVariableHome *homes[],  
    [out] ULONG *pceltFetched  
);  
```  
  
## <a name="parameters"></a>Параметры  

 `celt`  
 [in] Количество объектов, которые должны быть получены.  
  
 `homes`  
 Массив указателей, каждый из которых указывает на объект [ICorDebugVariableHome](icordebugvariablehome-interface.md) , предоставляющий сведения о локальной переменной или аргументе функции.  
  
 `pceltFetched`  
 заполняет Число экземпляров, фактически возвращаемых в объектах.  
  
## <a name="return-value"></a>Возвращаемое значение  

 Метод возвращает следующие значения.  
  
|HRESULT|Описание|  
|-------------|-----------------|  
|`S_OK`|Метод завершился успешно.|  
|`S_FALSE`|Фактическое число получаемых экземпляров, как показано в `pceltFetched` , меньше числа запрошенных экземпляров.|  
  
## <a name="remarks"></a>Remarks  

 Метод [ICorDebugVariableHomeEnum:: Next](icordebugvariablehomeenum-next-method.md) извлекает максимум  `celt` объектов, начиная с текущей позиции перечислителя. При возврате из метода `pceltFetched` содержит фактическое число извлеченных объектов.  
  
## <a name="requirements"></a>Требования  

 **Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).  
  
 **Заголовок:** CorDebug.idl, CorDebug.h  
  
 **Библиотека:** CorGuids.lib  
  
 **Платформа .NET Framework версии:**[!INCLUDE[net_current_v462plus](../../../../includes/net-current-v462plus-md.md)]  
  
## <a name="see-also"></a>См. также

- [Интерфейс ICorDebugVariableHomeEnum](icordebugvariablehomeenum-interface.md)
- [Интерфейс ICorDebugVariableHome](icordebugvariablehome-interface.md)
