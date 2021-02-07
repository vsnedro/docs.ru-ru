---
description: Дополнительные сведения о перечислении Кордебугмдафлагс
title: Перечисление CorDebugMDAFlags
ms.date: 03/30/2017
api_name:
- CorDebugMDAFlags
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- CorDebugMDAFlags
helpviewer_keywords:
- CorDebugMDAFlags enumeration [.NET Framework debugging]
ms.assetid: 7c0c92fe-8bd2-477f-b307-aca0143732ca
topic_type:
- apiref
ms.openlocfilehash: d7e9178d76286b112035729e997b1f68e2a93fb3
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2021
ms.locfileid: "99661939"
---
# <a name="cordebugmdaflags-enumeration"></a>Перечисление CorDebugMDAFlags

Указывает состояние потока, по которому был вызван помощник по отладке управляемого кода.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
typedef enum CorDebugMDAFlags {  
    MDA_FLAG_SLIP = 0x2  
} CorDebugMDAFlags;  
```  
  
## <a name="members"></a>Члены  
  
|Член|Описание|  
|------------|-----------------|  
|`MDA_FLAG_SLIP`|Поток, в котором был запущен MDA, был в запаздывания с момента запуска MDA.|  
  
## <a name="remarks"></a>Remarks  

 Если стек вызовов больше не описывает место первоначального создания MDA, обсуждение считается *, что он* находится в недоступном месте. Это необычное обстоятельство, вызванное выполнением недействительной операции потока при выходе.  
  
## <a name="requirements"></a>Требования  

 **Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).  
  
 **Заголовок:** CorDebug.idl, CorDebug.h  
  
 **Библиотека:** CorGuids.lib  
  
 **Платформа .NET Framework версии:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>См. также

- [Перечисления отладки](debugging-enumerations.md)
