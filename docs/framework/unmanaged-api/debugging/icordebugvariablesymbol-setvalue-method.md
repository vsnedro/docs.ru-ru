---
description: 'Дополнительные сведения о методе: ICorDebugVariableSymbol:: SetValue'
title: Метод ICorDebugVariableSymbol::SetValue
ms.date: 03/30/2017
ms.assetid: 4609418d-71fa-44bc-9618-4d529d25cabb
ms.openlocfilehash: aa36712defcf44039f17fe846113c15814549e09
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2021
ms.locfileid: "99800855"
---
# <a name="icordebugvariablesymbolsetvalue-method"></a>Метод ICorDebugVariableSymbol::SetValue

Присваивает переменной значение массива байтов.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
HRESULT SetValue(  
   [in] ULONG32 offset,  
   [in] DWORD threadID,  
   [in] ULONG32 cbContext,  
   [in, size_is(cbContext)] BYTE context[],  
   [in] ULONG32 cbValue,  
   [in, size_is(cbValue)] BYTE pValue[]  
);  
```  
  
## <a name="parameters"></a>Параметры  

 `offset`  
 [in] Начальное смещение в переменной, с которого следует задавать значение. Этот параметр используется при записи в поля членов в объекте.  
  
 `threadID`  
 [in] Идентификатор потока, чей контекст должен быть обновлен в соответствии с новым значением.  
  
 `cbContext`  
 [in] Размер контекста потока в байтах.  
  
 `context`  
 [in] Контекст потока, используемый для записи значения.  
  
 `cbValue`  
 [in] Размер буфера `pValue` в байтах.  
  
 `pValue`  
 [in] Буфер, содержащий значение, которое требуется задать.  
  
## <a name="remarks"></a>Remarks  
  
> [!NOTE]
> Этот метод доступен только в машинном коде .NET.  
  
## <a name="requirements"></a>Требования  

 **Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).  
  
 **Заголовок:** CorDebug.idl, CorDebug.h  
  
 **Библиотека:** CorGuids.lib  
  
 **Платформа .NET Framework версии:**[!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]  
  
## <a name="see-also"></a>См. также

- [Интерфейс ICorDebugVariableSymbol](icordebugvariablesymbol-interface.md)
- [Интерфейсы отладки](debugging-interfaces.md)
