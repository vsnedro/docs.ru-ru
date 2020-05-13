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
ms.openlocfilehash: 4883c208468db0096bed3ff8cf4a8ed50a5d7cc6
ms.sourcegitcommit: d6bd7903d7d46698e9d89d3725f3bb4876891aa3
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/13/2020
ms.locfileid: "83379231"
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
  
## <a name="remarks"></a>Remarks  
 Отладка в смешанном режиме (управляемый и машинный код) не поддерживается в Windows 95, Windows 98 или Windows ME, а также на платформах, отличных от x86 (например, IA-64 и AMD64).  
  
## <a name="requirements"></a>Требования  
 **Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).  
  
 **Заголовок:** CorDebug. idl  
  
 **Библиотека:** : коргуидс. lib  
  
 **.NET Framework версии:** 3,5 SP1  
  
## <a name="see-also"></a>См. также

- [Интерфейс ICorDebugRemote](icordebugremote-interface.md)
- [Интерфейс ICorDebug](icordebug-interface.md)
- [Интерфейсы отладки](debugging-interfaces.md)
