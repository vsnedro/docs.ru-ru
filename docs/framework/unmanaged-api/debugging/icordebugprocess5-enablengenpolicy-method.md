---
description: 'Дополнительные сведения о методе: метод ICorDebugProcess5:: EnableNGENPolicy'
title: Метод ICorDebugProcess5::EnableNGENPolicy
ms.date: 03/30/2017
api_name:
- ICorDebugProcess5::EnableNGenPolicy
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugProcess5::EnableNGENPolicy
helpviewer_keywords:
- ICorDebugProcess5::EnableNGENPolicy method [.NET Framework debugging]
- EnableNGENPolicy method, ICorDebugProcess5 interface [.NET Framework debugging]
ms.assetid: 3b8e15ca-3c72-4685-a937-da4c739cb9e9
topic_type:
- apiref
ms.openlocfilehash: 0f3194893665bfe9fff802a293aaafed8254f2e3
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2021
ms.locfileid: "99649927"
---
# <a name="icordebugprocess5enablengenpolicy-method"></a>Метод ICorDebugProcess5::EnableNGENPolicy

Задает значение, определяющее, как приложение загружает образы в машинном кодах при выполнении в управляемом отладчике.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
HRESULT EnableNGENPolicy(  
    [in] CorDebugNGENPolicy ePolicy  
);  
```  
  
## <a name="parameters"></a>Параметры  

 `ePolicy`  
 окне Константа [кордебугнженполици](cordebugngenpolicy-enumeration.md) , определяющая, как приложение загружает образы в машинном кодах при работе в управляемом отладчике.  
  
## <a name="remarks"></a>Remarks  

 Если политика успешно установлена, метод возвращает значение `S_OK` . Если `ePolicy` находится вне диапазона перечисляемых значений, определенных параметром [кордебугнженполици](cordebugngenpolicy-enumeration.md), метод возвращает значение, `E_INVALIDARG` и вызов метода не оказывает никакого влияния. Если не удается обновить политику генератора образов в машинном кодах (Ngen.exe), метод возвращает `E_FAIL` .  
  
 `ICorDebugProcess5::EnableNGenPolicy`Метод может быть вызван в любой момент времени существования процесса. Политика действует для всех модулей, загруженных после установки политики.  
  
## <a name="requirements"></a>Требования  

 **Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).  
  
 **Заголовок:** CorDebug.idl, CorDebug.h  
  
 **Библиотека:** CorGuids.lib  
  
 **Платформа .NET Framework версии:**[!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]  
  
## <a name="see-also"></a>См. также

- [Интерфейс ICorDebugProcess5](icordebugprocess5-interface.md)
- [Интерфейсы отладки](debugging-interfaces.md)
- [Отладка](index.md)
