---
description: Дополнительные сведения о перечислении Кордебугрекордформат
title: Перечисление CorDebugRecordFormat
ms.date: 03/30/2017
api_name:
- CorDebugRecordFormat
api_location:
- mscordbi.dll
api_type:
- COM
ms.assetid: d680c1c0-16ab-4ccc-9444-39cf8e0e05ee
topic_type:
- apiref
ms.openlocfilehash: 856522497a8f858abdb39ac232fb3034d4d91dfc
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2021
ms.locfileid: "99801570"
---
# <a name="cordebugrecordformat-enumeration"></a>Перечисление CorDebugRecordFormat

Описывает формат данных в массиве байтов, который содержит информацию о событии отладки собственного исключения.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
typedef enum CorDebugRecordFormat {  
    FORMAT_WINDOWS_EXCEPTIONRECORD32 = 1,  
    FORMAT_WINDOWS_EXCEPTIONRECORD64 = 2,  
} CorDebugRecordFormat;  
```  
  
## <a name="members"></a>Члены  
  
|Член|Описание|  
|------------|-----------------|  
|`FORMAT_WINDOWS_EXCEPTIONRECORD32`|Данные представляют собой 32-разрядную запись Windows-исключения.|  
|`FORMAT_WINDOWS_EXCEPTIONRECORD64`|Данные представляют собой 64-разрядную запись Windows-исключения.|  
  
## <a name="remarks"></a>Remarks  

 Член `CorDebugRecordFormat` перечисления передается в метод [DecodeEvent](icordebugprocess6-decodeevent-method.md) для указания формата массива байтов в его `pRecord` аргументе.  
  
> [!NOTE]
> Это перечисление предназначено для использования только в сценариях отладки .NET Native.  
  
## <a name="requirements"></a>Требования  

 **Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).  
  
 **Заголовок:** CorDebug.idl, CorDebug.h  
  
 **Библиотека:** CorGuids.lib  
  
 **Платформа .NET Framework версии:**[!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]  
  
## <a name="see-also"></a>См. также

- [Перечисления отладки](debugging-enumerations.md)
