---
title: Метод ICorDebugModule3::CreateReaderForInMemorySymbols
ms.date: 03/30/2017
api_name:
- ICorDebugModule3.CreateReaderForInMemorySymbols
api_location:
- CorDebug.dll
api_type:
- COM
f1_keywords:
- ICorDebugModule3::CreateReaderForInMemorySymbols
helpviewer_keywords:
- CreateReaderForInMemorySymbols method, ICorDebugModule3 interface [.NET Framework debugging]
- ICorDebugModule3::CreateReaderForInMemorySymbols method [.NET Framework debugging]
ms.assetid: af317171-d66d-4114-89eb-063554c74940
topic_type:
- apiref
ms.openlocfilehash: 44f4c59f95c28f9982d67875584e2f9803c0ed3b
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/24/2020
ms.locfileid: "95709574"
---
# <a name="icordebugmodule3createreaderforinmemorysymbols-method"></a>Метод ICorDebugModule3::CreateReaderForInMemorySymbols

Создает средство чтения символов отладки для динамического модуля.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
HRESULT CreateReaderForInMemorySymbols (  
      [in] REFIID riid,  
      [out][iid_is(riid)] void **    ppObj  
```  
  
## <a name="parameters"></a>Параметры  

 riid  
 окне Идентификатор IID возвращаемого COM-интерфейса. Как правило, это [Интерфейс ISymUnmanagedReader](../diagnostics/isymunmanagedreader-interface.md).  
  
 ппобж  
 заполняет Указатель на указатель на возвращенный интерфейс.  
  
## <a name="return-value"></a>Возвращаемое значение  

 S_OK  
 Модуль чтения успешно создан.  
  
 CORDBG_E_MODULE_LOADED_FROM_DISK  
 Модуль не является ни в памяти, ни динамическим модулем.  
  
 CORDBG_E_SYMBOLS_NOT_AVAILABLE  
 Символы не были предоставлены приложением или пока недоступны.  
  
 E_FAIL (или другие коды возврата E_)  
 Не удалось создать модуль чтения.  
  
## <a name="remarks"></a>Комментарии  

 Этот метод можно также использовать для создания объекта средства чтения символов для модулей, не являющихся динамическими, но только после того, как символы будут первыми доступны (обозначены обратным вызовом [метода UpdateModuleSymbols](icordebugmanagedcallback-updatemodulesymbols-method.md) ).  
  
 Этот метод возвращает новый экземпляр модуля чтения при каждом вызове (например, [ккомптрбасе:: CoCreateInstance](/cpp/atl/reference/ccomptrbase-class#cocreateinstance)). Поэтому отладчик должен кэшировать результат и запросить новый экземпляр только в том случае, если базовые данные могли измениться (то есть при получении обратного вызова [метода loadClass](icordebugmanagedcallback-loadclass-method.md) ).  
  
 Динамические модули не имеют доступных символов, пока не будет загружен первый тип (как указано в обратном вызове [метода loadClass](icordebugmanagedcallback-loadclass-method.md) ).  
  
## <a name="requirements"></a>Требования  

 **Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).  
  
 **Заголовок:** CorDebug.idl, CorDebug.h  
  
 **Библиотека:** CorGuids.lib  
  
 **.NET Framework версии:** 4,5, 4, 3,5 SP1  
  
## <a name="see-also"></a>См. также раздел

- [Интерфейс ICorDebugRemoteTarget](icordebugremotetarget-interface.md)
- [Интерфейс ICorDebug](icordebug-interface.md)

- [Интерфейсы отладки](debugging-interfaces.md)
