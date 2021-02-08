---
description: 'Дополнительные сведения о: интерфейс ICorDebugVariableHome'
title: Интерфейс ICorDebugVariableHome
ms.date: 03/30/2017
dev_langs:
- cpp
api_name:
- ICorDebugVariableHome
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugVariableHome
helpviewer_keywords:
- ICorDebugVariableHome interface [.NET Framework debugging]
ms.assetid: 76f2bf3b-759f-4eed-bce7-119415b25915
topic_type:
- apiref
ms.openlocfilehash: a1dcc959ba9aeffc0e511dcd2f5bb15f58445139
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2021
ms.locfileid: "99790637"
---
# <a name="icordebugvariablehome-interface"></a>Интерфейс ICorDebugVariableHome

Представляет локальную переменную или аргумент функции.  
  
## <a name="methods"></a>Методы  
  
|Метод|Описание|  
|------------|-----------------|  
|[Метод GetArgumentIndex](icordebugvariablehome-getargumentindex-method.md)|Возвращает индекс аргумента функции.|  
|[Метод GetCode](icordebugvariablehome-getcode-method.md)|Возвращает экземпляр "ICorDebugCode", который содержит этот `ICorDebugVariableHome` объект.|  
|[Метод GetLiveRange](icordebugvariablehome-getliverange-method.md)|Возвращает собственный диапазон, в котором эта переменная находится в режиме реального времени.|  
|[Метод GetLocationType](icordebugvariablehome-getlocationtype-method.md)|Возвращает тип собственного расположения переменной.|  
|[Метод GetOffset](icordebugvariablehome-getoffset-method.md)|Возвращает смещение от базового регистра для переменной.|  
|[Метод GetRegister](icordebugvariablehome-getregister-method.md)|Возвращает регистр, содержащий переменную с типом расположения `VLT_REGISTER` , и базовый регистр для переменной с типом расположения `VLT_REGISTER_RELATIVE` .|  
|[Метод GetSlotIndex](icordebugvariablehome-getslotindex-method.md)|Возвращает управляемый индекс в виде слота локальной переменной.|  
  
## <a name="example"></a>Пример  

 В следующем фрагменте кода используется объект [ICorDebugCode4](icordebugcode4-interface.md) с именем `pCode4` .  
  
```cpp  
ICorDebugCode4 *pCode4 = NULL;  
pCode->QueryInterface(IID_ICorDebugCode4, &pCode4);  
  
ICorDebugVariableEnum *pVarLocEnum = NULL;  
pCode4->EnumerateVariableHomes(&pVarLocEnum);  
  
// retrieve local variables and arguments  
ULONG celt = 0;  
pVarLocEnum->GetCount(&celt);  
ICorDebugVariableHome **homes = new ICorDebugVariableHome *[celt];  
ULONG celtFetched = 0;  
pVarLocEnum->Next(celt, homes, &celtFetched);  
  
for (int i = 0; i < celtFetched; i++)  
{  
    VariableLocationType locType = VLT_INVALID;  
    homes[i].GetLocationType(&locType);  
    switch (locType)  
    {  
    case VLT_REGISTER:  
        CorDebugRegister register = 0;  
        locals[i].GetRegister(&register);  
        // now we know which register it is in  
        break;  
    case VLT_REGISTER_RELATIVE:  
        CorDebugRegister baseRegister = 0;  
        LONG offset = 0;  
        locals[i].GetRegister(&register);  
        locals[i].GetOffset(&offset);  
        // now we know the register-relative offset  
        break;  
    case VLT_INVALID:  
        // handle case where we can't access the location  
        break;  
    }  
}  
```  
  
## <a name="requirements"></a>Требования  

 **Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).  
  
 **Заголовок:** CorDebug.idl, CorDebug.h  
  
 **Библиотека:** CorGuids.lib  
  
 **Платформа .NET Framework версии:**[!INCLUDE[net_current_v462plus](../../../../includes/net-current-v462plus-md.md)]  
  
## <a name="see-also"></a>См. также

- [Интерфейсы отладки](debugging-interfaces.md)
- [Интерфейс ICorDebugVariableHomeEnum](icordebugvariablehomeenum-interface.md)
