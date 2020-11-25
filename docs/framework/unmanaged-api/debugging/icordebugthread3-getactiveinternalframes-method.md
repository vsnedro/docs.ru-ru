---
title: Метод ICorDebugThread3::GetActiveInternalFrames
ms.date: 03/30/2017
api_name:
- ICorDebugThread3.GetActiveInternalFrames Method
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugThread3::GetActiveInternalFrames
helpviewer_keywords:
- ICorDebugThread3::GetActiveInternalFrames method [.NET Framework debugging]
- GetActiveInternalFrames method [.NET Framework debugging]
ms.assetid: d69796b4-5b6d-457c-85f6-2cf42e8a8773
topic_type:
- apiref
ms.openlocfilehash: 2ca3bf94298b45e404c930ffe52e101085ee482d
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/24/2020
ms.locfileid: "95726214"
---
# <a name="icordebugthread3getactiveinternalframes-method"></a>Метод ICorDebugThread3::GetActiveInternalFrames

Возвращает массив внутренних кадров (объектов[ICorDebugInternalFrame2](icordebuginternalframe2-interface.md) ) в стеке.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp
HRESULT GetActiveInternalFrames  
      (  
      [in] ULONG32 cInternalFrames,  
      [out] ULONG32 *pcInternalFrames,  
      [in, out,size_is(cInternalFrames), length_is(*pcInternalFrames)]  
            ICorDebugInternalFrame2 * ppInternalFrames[]  
      );  
```  
  
## <a name="parameters"></a>Параметры  

 `cInternalFrames`  
 окне Число внутренних кадров, ожидаемых в `ppInternalFrames` .  
  
 `pcInternalFrames`  
 заполняет Указатель на объект `ULONG32` , который содержит количество внутренних кадров в стеке.  
  
 `ppInternalFrames`  
 [вход, выход] Указатель на адрес массива внутренних кадров в стеке.  
  
## <a name="return-value"></a>Возвращаемое значение  

 Этот метод возвращает следующие конкретные результаты HRESULT, а также ошибки HRESULT, которые указывают на сбой метода.  
  
|HRESULT|Описание:|  
|-------------|-----------------|  
|S_OK|Объект [ICorDebugInternalFrame2](icordebuginternalframe2-interface.md) успешно создан.|  
|E_INVALIDARG|`cInternalFrames` не равен нулю `ppInternalFrames` , имеет значение `null` , или `pcInternalFrames` имеет значение `null` .|  
|HRESULT_FROM_WIN32(ERROR_INSUFFICIENT_BUFFER)|`ppInternalFrames` меньше, чем число внутренних кадров.|  
  
## <a name="exceptions"></a>Исключения  
  
## <a name="remarks"></a>Remarks  

 Внутренние кадры — это структуры данных, помещаемые в стек средой выполнения для хранения временных данных.  
  
 При первом вызове `GetActiveInternalFrames` следует присвоить `cInternalFrames` параметру значение 0 (ноль), а `ppInternalFrames` параметр — значению NULL. При `GetActiveInternalFrames` первом возвращении `pcInternalFrames` содержит количество внутренних кадров в стеке.  
  
 `GetActiveInternalFrames` Затем следует вызвать второй раз. Необходимо передать соответствующее значение Count ( `pcInternalFrames` ) в `cInternalFrames` параметре и указать указатель на массив соответствующего размера в `ppInternalFrames` .  
  
 Используйте метод [икордебугстакквалк:: noframes](icordebugthread3-getactiveinternalframes-method.md) для возврата фактических кадров стека.  
  
## <a name="requirements"></a>Требования  

 **Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).  
  
 **Заголовок:** CorDebug.idl, CorDebug.h  
  
 **Библиотека:** CorGuids.lib  
  
 **.NET Framework версии:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a>См. также раздел

- [Интерфейсы отладки](debugging-interfaces.md)
- [Отладка](index.md)
