---
description: 'Дополнительные сведения о: структура Кордебужексцептионобжектстаккфраме'
title: Структура CorDebugExceptionObjectStackFrame
ms.date: 03/30/2017
api_name:
- CorDebugExceptionObjectStackFrame
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- CorDebugExceptionObjectStackFrame
helpviewer_keywords:
- CorDebugExceptionObjectStackFrame structure [.NET Framework debugging]
ms.assetid: 542cdd81-5ae7-4361-b0ef-1ae4775df258
topic_type:
- apiref
ms.openlocfilehash: abeb5a9f6385c494745a34c6f37d6fbc1376ad7b
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2021
ms.locfileid: "99662160"
---
# <a name="cordebugexceptionobjectstackframe-structure"></a>Структура CorDebugExceptionObjectStackFrame

Представляет сведения о кадре стека из объекта исключения.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
typedef struct CorDebugExceptionObjectStackFrame {  
    ICorDebugModule* pModule;  
    CORDB_ADDRESS ip;  
    mdMethodDef methodDef;  
    BOOL isLastForeignExceptionFrame;  
} CorDebugExceptionObjectStackFrame;  
```  
  
## <a name="members"></a>Члены  
  
|Член|Описание|  
|------------|-----------------|  
|`pModule`|Указатель на объект ICorDebugModule для текущего кадра.|  
|`ip`|Значение указателя инструкций (EIP/RIP) для текущего кадра.|  
|`methodDef`|Токен метода для текущего кадра.|  
|`isLastForeignExceptionFrame`|Значение, указывающее, является ли кадр последним кадром во внешнем исключении.|  
  
## <a name="remarks"></a>Remarks  

 Вызывающая сторона должна освободить указатель на объект ICorDebugModule, когда он больше не используется.  
  
## <a name="requirements"></a>Требования  

 **Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).  
  
 **Заголовок:** CorDebug.idl, CorDebug.h  
  
 **Библиотека:** CorGuids.lib  
  
 **Платформа .NET Framework версии:**[!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]  
  
## <a name="see-also"></a>См. также

- [Структуры отладки](debugging-structures.md)
- [Отладка](index.md)
