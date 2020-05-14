---
title: Метод ICorDebugVariableSymbol::GetValue
ms.date: 03/30/2017
ms.assetid: 90abece1-392e-4ade-94a1-30c75b0f7074
ms.openlocfilehash: f217f7226d53a27363f66eb90a340fd3604a0217
ms.sourcegitcommit: 046a9c22487551360e20ec39fc21eef99820a254
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/14/2020
ms.locfileid: "83396520"
---
# <a name="icordebugvariablesymbolgetvalue-method"></a>Метод ICorDebugVariableSymbol::GetValue
Возвращает значение переменной в виде массива байтов.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
HRESULT GetValue(  
   [in] ULONG32 offset,  
   [in] ULONG32 cbContext,  
   [in, size_is(cbContext)] BYTE context[],  
   [in] ULONG32 cbValue,  
   [out] ULONG32 *pcbValue,  
   [out, size_is(cbValue), length_is(*pcbValue)] BYTE pValue[]  
);  
```  
  
## <a name="parameters"></a>Параметры  
 `offset`  
 [in] Начальное смещение в переменной, с которого следует читать значение. Этот параметр используется при чтении полей членов в объекте.  
  
 `cbContext`  
 [in] Размер аргумента `context` в байтах.  
  
 `context`  
 [in] Контекст потока, используемый для чтения значения.  
  
 `cbValue`  
 [in] Размер буфера `pValue` в байтах.  
  
 `pcbValue`  
 [out] Число байтов, фактически записанных в буфер `pValue`.  
  
 `pValue`  
 [out] Массив байтов, содержащий значение переменной.  
  
## <a name="remarks"></a>Remarks  
  
> [!NOTE]
> Этот метод доступен только в машинном коде .NET.  
  
## <a name="requirements"></a>Требования  
 **Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).  
  
 **Заголовок:** CorDebug.idl, CorDebug.h  
  
 **Библиотека:** CorGuids.lib  
  
 **.NET Framework версии:**[!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]  
  
## <a name="see-also"></a>См. также статью

- [Интерфейс ICorDebugVariableSymbol](icordebugvariablesymbol-interface.md)
- [Интерфейсы отладки](debugging-interfaces.md)
