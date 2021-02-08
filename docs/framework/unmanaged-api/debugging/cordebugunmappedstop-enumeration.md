---
description: Дополнительные сведения о перечислении Кордебугунмаппедстоп
title: Перечисление CorDebugUnmappedStop
ms.date: 03/30/2017
api_name:
- CorDebugUnmappedStop
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- CorDebugUnmappedStop
helpviewer_keywords:
- CorDebugUnmappedStop enumeration [.NET Framework debugging]
ms.assetid: a684f7d7-d0c2-4690-b721-639e613f11f8
topic_type:
- apiref
ms.openlocfilehash: 9c4f70c5de451689f98a1c08627fd6df5128fdbd
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2021
ms.locfileid: "99801531"
---
# <a name="cordebugunmappedstop-enumeration"></a>Перечисление CorDebugUnmappedStop

Указывает тип несопоставимого кода, который может привести к прерыванию выполнения кода пошаговым средством.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
typedef enum CorDebugUnmappedStop {  
    STOP_NONE               = 0x0,  
    STOP_PROLOG             = 0x01,  
    STOP_EPILOG             = 0x02,  
    STOP_NO_MAPPING_INFO    = 0x04,  
    STOP_OTHER_UNMAPPED     = 0x08,  
    STOP_UNMANAGED          = 0x10,  
    STOP_ALL                = 0xffff,  
} CorDebugUnmappedStop;  
```  
  
## <a name="members"></a>Члены  
  
|Член|Описание|  
|------------|-----------------|  
|`STOP_NONE`|Не останавливайте в любом типе несопоставленного кода.|  
|`STOP_PROLOG`|Останавливает в коде пролога.|  
|`STOP_EPILOG`|Прерывать в коде эпилога.|  
|`STOP_NO_MAPPING_INFO`|Прерывать в коде, не имеющем сведений о сопоставлении.|  
|`STOP_OTHER_UNMAPPED`|Прерывать в несопоставленном коде, который не помещается ни в прологе, ни в том, ни в какую информацию, ни в неуправляемой категории.|  
|`STOP_UNMANAGED`|Останавливает в неуправляемом коде. Это значение допустимо только при отладке взаимодействия.|  
|`STOP_ALL`|Останавливаются во всех типах несопоставленного кода.|  
  
## <a name="remarks"></a>Remarks  

 Используйте метод [ICorDebugStepper:: сетунмаппедстопмаск](icordebugstepper-setunmappedstopmask-method.md) , чтобы задать флаги, указывающие Несопоставленный код, в котором будет останавливаться средство Организации.  
  
## <a name="requirements"></a>Требования  

 **Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).  
  
 **Заголовок:** CorDebug.idl, CorDebug.h  
  
 **Библиотека:** CorGuids.lib  
  
 **Платформа .NET Framework версии:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>См. также

- [Перечисления отладки](debugging-enumerations.md)
