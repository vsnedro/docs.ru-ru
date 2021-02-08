---
description: 'Дополнительные сведения о методе: Икордебуглоадедмодуле:: GetBaseAddress'
title: Метод ICorDebugLoadedModule::GetBaseAddress
ms.date: 03/30/2017
ms.assetid: 7c036772-d58a-47f1-a5fa-31779898ef0d
ms.openlocfilehash: 2852131d543cfb9593cf4ff607d1f752226c2880
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2021
ms.locfileid: "99801271"
---
# <a name="icordebugloadedmodulegetbaseaddress-method"></a>Метод ICorDebugLoadedModule::GetBaseAddress

Получает базовый адрес загруженного модуля.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
HRESULT GetBaseAddress(  
   [out] CORDB_ADDRESS *pAddress  
);  
```  
  
## <a name="parameters"></a>Параметры  

 `pAddress`  
 [out] Указатель на базовый адрес загруженного модуля.  
  
## <a name="remarks"></a>Remarks  
  
> [!NOTE]
> Этот метод доступен только в машинном коде .NET.  
  
## <a name="requirements"></a>Требования  

 **Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).  
  
 **Заголовок:** CorDebug.idl, CorDebug.h  
  
 **Библиотека:** CorGuids.lib  
  
 **Платформа .NET Framework версии:**[!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]  
  
## <a name="see-also"></a>См. также

- [Интерфейс ICorDebugLoadedModule](icordebugloadedmodule-interface.md)
- [Интерфейсы отладки](debugging-interfaces.md)
