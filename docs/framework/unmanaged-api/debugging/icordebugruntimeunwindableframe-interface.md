---
title: Интерфейс ICorDebugRuntimeUnwindableFrame
ms.date: 03/30/2017
api_name:
- ICorDebugUnwindableFrame
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugUnwindableFrame
helpviewer_keywords:
- ICorDebugUnwindableFrame interface [.NET Framework debugging]
ms.assetid: cd6a3982-6ed3-4909-808d-a66055e813e0
topic_type:
- apiref
ms.openlocfilehash: 6619b8888588341f23a93b83865cd2e75cc9b3db
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/24/2020
ms.locfileid: "95712018"
---
# <a name="icordebugruntimeunwindableframe-interface"></a>Интерфейс ICorDebugRuntimeUnwindableFrame

Предоставляет поддержку для неуправляемых методов, которым требуется среда CLR для раскручивания кадра.  
  
## <a name="remarks"></a>Комментарии  

 `ICorDebugRuntimeUnwindableFrame` — Это специализированная версия интерфейса ICorDebugFrame. Он используется неуправляемыми методами, требующими от среды выполнения очистки кадра в текущем стеке. Существующие правила очистки не работают, так как они не используют JIT-скомпилированный код. Когда отладчик видит неотображаемый кадр, он должен использовать метод [икордебугстакквалк:: Next](icordebugstackwalk-next-method.md) для его очистки, но должен выполнить проверку. Когда отладчик получает объект `ICorDebugRuntimeUnwindableFrame` , он может вызвать метод [икордебугстакквалк:: oncontext](icordebugstackwalk-getcontext-method.md) для получения контекста кадра.  
  
## <a name="requirements"></a>Требования  

 **Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).  
  
 **Заголовок:** CorDebug.idl, CorDebug.h  
  
 **Библиотека:** CorGuids.lib  
  
 **.NET Framework версии:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a>См. также раздел

- [Интерфейсы отладки](debugging-interfaces.md)
- [Отладка](index.md)
