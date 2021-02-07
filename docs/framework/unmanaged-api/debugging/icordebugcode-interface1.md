---
description: Дополнительные сведения о интерфейсе ICorDebugCode
title: Интерфейс ICorDebugCode
ms.date: 03/30/2017
api_name:
- ICorDebugCode
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugCode
helpviewer_keywords:
- ICorDebugCode interface [.NET Framework debugging]
ms.assetid: 7bd14fb6-8b54-4484-a891-e3c21859c019
topic_type:
- apiref
ms.openlocfilehash: ce67c48501783bbe00152f0ba2c224e6e7dde6d7
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2021
ms.locfileid: "99711158"
---
# <a name="icordebugcode-interface"></a>Интерфейс ICorDebugCode

Представляет сегмент кода на языке MSIL или сегмент машинного кода.  
  
## <a name="methods"></a>Методы  
  
|Метод|Описание|  
|------------|-----------------|  
|[Метод CreateBreakpoint](icordebugcode-createbreakpoint-method.md)|Создает точку останова по указанному смещению.|  
|[Метод GetAddress](icordebugcode-getaddress-method.md)|Возвращает относительный виртуальный адрес (RVA) сегмента кода, который представляет этот объект `ICorDebugCode` .|  
|[Метод GetCode](icordebugcode-getcode-method.md)|Возвращает весь код для указанной функции, отформатированный для дизассемблирования. Этот метод не рекомендуется к использованию. Вместо этого используйте [ICorDebugCode2:: жеткодечункс](icordebugcode2-getcodechunks-method.md) .|  
|[Метод GetEnCRemapSequencePoints](icordebugcode-getencremapsequencepoints-method.md)|Не реализован.|  
|[Метод GetFunction](icordebugcode-getfunction-method.md)|Возвращает "ICorDebugFunction", связанный с этим `ICorDebugCode` .|  
|[Метод GetILToNativeMapping](icordebugcode-getiltonativemapping-method.md)|Возвращает массив экземпляров "COR_DEBUG_IL_TO_NATIVE_MAP", которые представляют сопоставления от смещений MSIL до собственных смещений.|  
|[Метод GetSize](icordebugcode-getsize-method.md)|Возвращает размер двоичного кода, представленного этим объектом, в байтах `ICorDebugCode` .|  
|[Метод GetVersionNumber](icordebugcode-getversionnumber-method.md)|Возвращает номер, отсчитываемый от единицы, определяющий версию кода, который представляет данный объект `ICorDebugCode` .|  
|[Метод IsIL](icordebugcode-isil-method.md)|Возвращает значение, указывающее, `ICorDebugCode` компилируется ли это в MSIL.|  
  
## <a name="remarks"></a>Remarks  

 `ICorDebugCode` может представлять язык MSIL или машинный код. Объект "ICorDebugFunction", представляющий код MSIL, может быть связан с нулем или `ICorDebugCode` с одним объектом. Объект "ICorDebugFunction", представляющий машинный код, может иметь любое количество `ICorDebugCode` связанных с ним объектов.  
  
> [!NOTE]
> Этот интерфейс не поддерживает удаленные вызовы между компьютерами или между процессами.  
  
## <a name="requirements"></a>Требования  

 **Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).  
  
 **Заголовок:** CorDebug.idl, CorDebug.h  
  
 **Библиотека:** CorGuids.lib  
  
 **Платформа .NET Framework версии:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>См. также

- [Интерфейс ICorDebugCode3](icordebugcode3-interface.md)
- [Интерфейсы отладки](debugging-interfaces.md)
