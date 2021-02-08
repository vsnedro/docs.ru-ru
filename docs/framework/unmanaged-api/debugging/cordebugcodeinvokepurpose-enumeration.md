---
description: Дополнительные сведения о перечислении Кордебугкодеинвокепурпосе
title: Перечисление CorDebugCodeInvokePurpose
ms.date: 03/30/2017
api_name:
- CorDebugInvokePurpose
api_location:
- mscordbi.dll
api_type:
- COM
ms.assetid: 31833a2d-a0d6-48a1-b05f-995ca307a08f
topic_type:
- apiref
ms.openlocfilehash: 1402343cc15e451975567564e6ce353900454bf4
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2021
ms.locfileid: "99801726"
---
# <a name="cordebugcodeinvokepurpose-enumeration"></a>Перечисление CorDebugCodeInvokePurpose

Описывает, почему экспортируемая функция вызывает управляемый код.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
typedef enum CorDebugCodeInvokePurpose  
{  
    CODE_INVOKE_PURPOSE_NONE,  
    CODE_INVOKE_PURPOSE_NATIVE_TO_MANAGED_TRANSITION,
    CODE_INVOKE_PURPOSE_CLASS_INIT,  
    CODE_INVOKE_PURPOSE_INTERFACE_DISPATCH,  
} CorDebugCodeInvokePurpose;  
```  
  
## <a name="members"></a>Члены  
  
|Член|Описание|  
|------------|-----------------|  
|`CODE_INVOKE_PURPOSE_NONE`|Отсутствует или неизвестно.|  
|`CODE_INVOKE_PURPOSE_NATIVE_TO_MANAGED_TRANSITION`|Управляемый код будет выполнять любую управляемую точку входа, например, обратный p-invoke. Любые дополнительные цели неизвестны среде выполнения.|  
|`CODE_INVOKE_PURPOSE_CLASS_INIT`|Управляемый код будет выполнять статический конструктор.|  
|`CODE_INVOKE_PURPOSE_INTERFACE_DISPATCH`|Управляемый код будет выполнять реализацию некоторого метода интерфейса, который был вызван.|  
  
## <a name="remarks"></a>Remarks  

 Это перечисление используется методом [ICorDebugProcess6:: жетекспортстепинфо](icordebugprocess6-getexportstepinfo-method.md) для предоставления сведений о пошаговом выполнении управляемого кода.  
  
> [!NOTE]
> Это перечисление предназначено для использования только в сценариях отладки .NET Native.  
  
## <a name="requirements"></a>Требования  

 **Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).  
  
 **Заголовок:** CorDebug.idl, CorDebug.h  
  
 **Библиотека:** CorGuids.lib  
  
 **Платформа .NET Framework версии:**[!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]  
  
## <a name="see-also"></a>См. также

- [Перечисления отладки](debugging-enumerations.md)
- [Отладка](index.md)
