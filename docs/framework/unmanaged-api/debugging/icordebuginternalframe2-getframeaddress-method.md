---
title: Метод ICorDebugInternalFrame2::GetFrameAddress
ms.date: 03/30/2017
api_name:
- ICorDebugInternalFrame2.GetFrameAddress Method
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugInternalFrame2::GetFrameAddress
helpviewer_keywords:
- GetFrameAddress method [.NET Framework debugging]
- ICorDebugInternalFrame2::GetFrameAddress method [.NET Framework debugging]
ms.assetid: 4ee8d058-ffc8-4967-9133-a5adfef4e518
topic_type:
- apiref
ms.openlocfilehash: 05a9ab58acb3bf5829fd231ae6d8bcc96ae06da6
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/24/2020
ms.locfileid: "95724875"
---
# <a name="icordebuginternalframe2getframeaddress-method"></a>Метод ICorDebugInternalFrame2::GetFrameAddress

Возвращает адрес стека внутреннего кадра.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
HRESULT GetFrameAddress([out] CORDB_ADDRESS *pAddress);  
```  
  
## <a name="parameters"></a>Параметры  

 `pAddress`  
 заполняет Указатель на объект `CORDB_ADDRESS` для внутреннего кадра.  
  
## <a name="return-value"></a>Возвращаемое значение  

 Этот метод возвращает следующие конкретные результаты HRESULT, а также ошибки HRESULT, которые указывают на сбой метода.  
  
|HRESULT|Описание:|  
|-------------|-----------------|  
|S_OK|Адрес внутреннего кадра успешно возвращен.|  
|E_FAIL|Не удалось вернуть адрес внутреннего кадра.|  
|E_INVALIDARG|`pAddress` имеет значение `null`.|  
  
## <a name="remarks"></a>Комментарии  

 Значение, возвращаемое в, `pAddress` можно использовать для определения расположения внутреннего кадра относительно других кадров в стеке. Даже на компьютерах на базе IA-64 внутренний кадр находится только в стеке и не имеет соответствующего указателя на резервное хранилище.  
  
## <a name="requirements"></a>Требования  

 **Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).  
  
 **Заголовок:** CorDebug.idl, CorDebug.h  
  
 **Библиотека:** CorGuids.lib  
  
 **.NET Framework версии:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a>См. также раздел

- [Интерфейс ICorDebugInternalFrame2](icordebuginternalframe2-interface.md)
- [Интерфейсы отладки](debugging-interfaces.md)
- [Отладка](index.md)
