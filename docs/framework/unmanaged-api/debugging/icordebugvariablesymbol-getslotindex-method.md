---
title: Метод ICorDebugVariableSymbol::GetSlotIndex
ms.date: 03/30/2017
ms.assetid: 09c19f5f-afc4-4e0c-bffe-cd7147bc7a43
ms.openlocfilehash: fc42517cb95dfc14c472b5bb9111ebd70639cee7
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/24/2020
ms.locfileid: "95725993"
---
# <a name="icordebugvariablesymbolgetslotindex-method"></a>Метод ICorDebugVariableSymbol::GetSlotIndex

Возвращает управляемый индекс слота локальной переменной.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
HRESULT GetSlotIndex(  
   [out] ULONG32 *pSlotIndex  
);  
```  
  
## <a name="parameters"></a>Параметры  

 `pSlotIndex`  
 [выходной] Указатель на индекс слота локальной переменной.  
  
## <a name="return-value"></a>Возвращаемое значение  

 `S_OK` в случае успешного выполнения. `E_FAIL`, если переменная является аргументом функции.  
  
## <a name="remarks"></a>Комментарии  

 Управляемый индекс слота можно использовать для получения информации о метаданных переменной.  
  
> [!NOTE]
> Этот метод доступен только в машинном коде .NET.  
  
## <a name="requirements"></a>Требования  

 **Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).  
  
 **Заголовок:** CorDebug.idl, CorDebug.h  
  
 **Библиотека:** CorGuids.lib  
  
 **.NET Framework версии:**[!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]  
  
## <a name="see-also"></a>См. также раздел

- [Интерфейс ICorDebugVariableSymbol](icordebugvariablesymbol-interface.md)
- [Интерфейсы отладки](debugging-interfaces.md)
