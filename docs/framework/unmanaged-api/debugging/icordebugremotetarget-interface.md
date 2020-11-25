---
title: Интерфейс ICorDebugRemoteTarget
ms.date: 03/30/2017
api_name:
- ICorDebugRemoteTarget
api_location:
- CorDebug.dll
api_type:
- COM
f1_keywords:
- ICorDebugRemoteTarget
helpviewer_keywords:
- ICorDebugRemoteTarget interface [.NET Framework debugging]
ms.assetid: bd9936a6-cc24-4869-8761-0988664464e6
topic_type:
- apiref
ms.openlocfilehash: 4212597b5ba43f0e4767aa585ca28a011e73e07a
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/24/2020
ms.locfileid: "95711992"
---
# <a name="icordebugremotetarget-interface"></a>Интерфейс ICorDebugRemoteTarget

Предоставляет методы, позволяющие разработчикам выполнять отладку приложений на основе Silverlight в среде CLR.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
interface ICorDebugRemoteTarget  : IUnknown  
{  
    HRESULT GetHostName (  
        [in]  ULONG32                    cchHostName,  
        [out] ULONG32*                   pcchHostName,  
        [out, size_is(cchHostName),  
              length_is(*pcchHostName)]  
                  WCHAR szHostName[]  
        );  
};  
```  
  
## <a name="methods"></a>Методы  
  
|Метод|Описание|  
|------------|-----------------|  
|[Метод ICorDebugRemoteTarget::GetHostName](icordebugremotetarget-gethostname-method.md)|Возвращает имя узла или IP-адрес удаленного компьютера.|  
  
## <a name="remarks"></a>Комментарии  

 Отладка в смешанном режиме (управляемый и машинный код) не поддерживается в Windows 95, Windows 98 или Windows ME, а также на платформах, отличных от x86 (например, IA-64 и AMD64).  
  
## <a name="requirements"></a>Требования  

 **Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).  
  
 **Заголовок:** CorDebug. idl  
  
 **Библиотека:** : коргуидс. lib  
  
 **.NET Framework версии:** 3,5 SP1  
  
## <a name="see-also"></a>См. также раздел

- [Интерфейс ICorDebugRemote](icordebugremote-interface.md)
- [Интерфейс ICorDebug](icordebug-interface.md)
- [Интерфейсы отладки](debugging-interfaces.md)
