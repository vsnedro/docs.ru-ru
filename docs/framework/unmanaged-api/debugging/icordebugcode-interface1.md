---
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
ms.openlocfilehash: 3736627e7f42ad9db6699c31a0a618e993eef770
ms.sourcegitcommit: 957c49696eaf048c284ef8f9f8ffeb562357ad95
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/07/2020
ms.locfileid: "82893472"
---
# <a name="icordebugcode-interface"></a>Интерфейс ICorDebugCode

Представляет сегмент кода на языке MSIL или сегмент машинного кода.  
  
## <a name="methods"></a>Методы  
  
|Метод|Описание|  
|------------|-----------------|  
|[Метод CreateBreakpoint](icordebugcode-createbreakpoint-method.md)|Создает точку останова по указанному смещению.|  
|[Метод GetAddress](icordebugcode-getaddress-method.md)|Возвращает относительный виртуальный адрес (RVA) сегмента кода, который представляет `ICorDebugCode` этот объект.|  
|[Метод GetCode](icordebugcode-getcode-method.md)|Возвращает весь код для указанной функции, отформатированный для дизассемблирования. Этот метод не рекомендуется к использованию. Вместо этого используйте [ICorDebugCode2:: жеткодечункс](icordebugcode2-getcodechunks-method.md) .|  
|[Метод GetEnCRemapSequencePoints](icordebugcode-getencremapsequencepoints-method.md)|Не реализовано.|  
|[Метод GetFunction](icordebugcode-getfunction-method.md)|Возвращает "ICorDebugFunction", связанный с этим `ICorDebugCode`.|  
|[Метод GetILToNativeMapping](icordebugcode-getiltonativemapping-method.md)|Возвращает массив экземпляров "COR_DEBUG_IL_TO_NATIVE_MAP", которые представляют сопоставления от смещений MSIL до собственных смещений.|  
|[Метод GetSize](icordebugcode-getsize-method.md)|Возвращает размер двоичного кода, представленного этим `ICorDebugCode`объектом, в байтах.|  
|[Метод GetVersionNumber](icordebugcode-getversionnumber-method.md)|Возвращает номер, отсчитываемый от единицы, определяющий версию кода, который представляет данный `ICorDebugCode` объект.|  
|[Метод IsIL](icordebugcode-isil-method.md)|Возвращает значение, указывающее, компилируется `ICorDebugCode` ли это в MSIL.|  
  
## <a name="remarks"></a>Remarks  
 `ICorDebugCode`может представлять язык MSIL или машинный код. Объект "ICorDebugFunction", представляющий код MSIL, может быть связан с нулем или `ICorDebugCode` с одним объектом. Объект "ICorDebugFunction", представляющий машинный код, может иметь любое количество `ICorDebugCode` связанных с ним объектов.  
  
> [!NOTE]
> Этот интерфейс не поддерживает удаленные вызовы между компьютерами или между процессами.  
  
## <a name="requirements"></a>Требования  
 **Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).  
  
 **Заголовок:** CorDebug.idl, CorDebug.h  
  
 **Библиотека:** CorGuids.lib  
  
 **.NET Framework версии:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>См. также раздел

- [Интерфейс ICorDebugCode3](icordebugcode3-interface.md)
- [Интерфейсы отладки](debugging-interfaces.md)
