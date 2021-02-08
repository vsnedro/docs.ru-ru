---
description: 'Дополнительные сведения о: интерфейс ICorDebugType2'
title: Интерфейс ICorDebugType2
ms.date: 03/30/2017
api_name:
- ICorDebugType2
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugType2
helpviewer_keywords:
- ICorDebugType2 interface
ms.assetid: 376fb03f-f1ef-4107-baa4-4d9d55884862
topic_type:
- apiref
ms.openlocfilehash: 8691cf294e835bef0f5a0ac694110f73577fb5d3
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2021
ms.locfileid: "99800873"
---
# <a name="icordebugtype2-interface"></a>Интерфейс ICorDebugType2

Расширяет интерфейс ICorDebugType для получения идентификатора типа базового типа или сложного (определяемого пользователем) типа.  
  
## <a name="methods"></a>Методы  
  
|Метод||  
|------------|-|  
|[Метод GetTypeID](icordebugtype2-gettypeid-method.md)|Возвращает [COR_TYPEID](cor-typeid-structure.md) для этого типа.|  
  
## <a name="remarks"></a>Remarks  

 Этот интерфейс является логическим расширением интерфейса ICorDebugType.  
  
> [!NOTE]
> Этот интерфейс не поддерживает удаленные вызовы между компьютерами или между процессами.  
  
## <a name="example"></a>Пример  

 В следующем фрагменте кода показано использование метода [ICorDebugType2:: typeid](icordebugtype2-gettypeid-method.md) .  
  
```cpp  
// (error checking omitted for brevity)  
// given an ICorDebugType *pType  
  
ICorDebugType2 *pType2 = NULL;  
pType->QueryInterface(IID_ICorDebugType2, &pType);  
  
COR_TYPEID id;  
pType2->GetTypeID(&id);  
  
// now we can use existing APIs to get information about this COR_TYPEID  
```  
  
## <a name="requirements"></a>Требования  

 **Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).  
  
 **Заголовок:** CorDebug.idl, CorDebug.h  
  
 **Библиотека:** CorGuids.lib  
  
 **Платформа .NET Framework версии:**[!INCLUDE[net_current_v462plus](../../../../includes/net-current-v462plus-md.md)]  
  
## <a name="see-also"></a>См. также

- [Интерфейсы отладки](debugging-interfaces.md)
