---
title: Метод ICorDebugProcess6::GetCode
ms.date: 03/30/2017
ms.assetid: faa538c2-60c9-4064-b996-1b4c24ebd751
ms.openlocfilehash: cee1556fd7d803765b09a7cbd86ce2ff7be91cc9
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/24/2020
ms.locfileid: "95732636"
---
# <a name="icordebugprocess6getcode-method"></a>Метод ICorDebugProcess6::GetCode

Получает информацию об управляемом коде по адресу определенного кода.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
HRESULT GetCode(  
    [in] CORDB_ADDRESS codeAddress,
    [out] ICorDebugCode **ppCode);  
```  
  
## <a name="parameters"></a>Параметры  

 `codeAddress`  
 окне Значение [CORDB_ADDRESS](../common-data-types-unmanaged-api-reference.md) , указывающее начальный адрес сегмента управляемого кода.  
  
 `ppCode`  
 заполняет Указатель на адрес объекта ICorDebugCode, который представляет сегмент управляемого кода.  
  
## <a name="remarks"></a>Комментарии  
  
> [!NOTE]
> Этот метод доступен только в машинном коде .NET.  
  
## <a name="requirements"></a>Требования  

 **Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).  
  
 **Заголовок:** CorDebug.idl, CorDebug.h  
  
 **Библиотека:** CorGuids.lib  
  
 **.NET Framework версии:**[!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]  
  
## <a name="see-also"></a>См. также раздел

- [Интерфейс ICorDebugProcess6](icordebugprocess6-interface.md)
- [Интерфейсы отладки](debugging-interfaces.md)
