---
title: Интерфейс ICorDebugModule3
ms.date: 03/30/2017
api_name:
- ICorDebugModule3
api_location:
- CorDebug.dll
api_type:
- COM
f1_keywords:
- ICorDebugModule3
helpviewer_keywords:
- ICorDebugModule3 interface [.NET Framework debugging]
ms.assetid: 0b69f945-263a-4e11-8512-89d27f6ea296
topic_type:
- apiref
ms.openlocfilehash: 543a1a3c79b6cf3eb799da5844f35286dfa91940
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/24/2020
ms.locfileid: "95709561"
---
# <a name="icordebugmodule3-interface"></a>Интерфейс ICorDebugModule3

Создает средство чтения символов для динамического модуля.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
interface ICorDebugModule3 : IUnknown  
{  
    HRESULT CreateReaderForInMemorySymbols  
      (  
      [in] REFIID riid,  
      [out][iid_is(riid)] void **  ppObj  
      );  
};  
```  
  
## <a name="methods"></a>Методы  
  
|Метод|Описание|  
|------------|-----------------|  
|[Метод ICorDebugModule3::CreateReaderForInMemorySymbols](icordebugmodule3-createreaderforinmemorysymbols-method.md)|Создает средство чтения символов (обычно [ISymUnmanagedReader Interface](../diagnostics/isymunmanagedreader-interface.md)) для динамического модуля.|  
  
## <a name="remarks"></a>Комментарии  

 Этот интерфейс логически расширяет интерфейсы "ICorDebugModule" и "ICorDebugModule2".  
  
> [!NOTE]
> Этот интерфейс не поддерживает удаленные вызовы между компьютерами или между процессами.  
  
## <a name="requirements"></a>Требования  

 **Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).  
  
 **Заголовок:** CorDebug.idl, CorDebug.h  
  
 **Библиотека:** CorGuids.lib  
  
 **.NET Framework версии:** 4,5, 4, 3,5 SP1
  
## <a name="see-also"></a>См. также раздел

- [Интерфейс ICorDebugRemoteTarget](icordebugremotetarget-interface.md)
- [Интерфейс ICorDebug](icordebug-interface.md)

- [Интерфейсы отладки](debugging-interfaces.md)
