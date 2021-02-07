---
description: 'Дополнительные сведения о методе: ICorDebugObjectValue:: GetFieldValue'
title: Метод ICorDebugObjectValue::GetFieldValue
ms.date: 03/30/2017
api_name:
- ICorDebugObjectValue.GetFieldValue
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugObjectValue::GetFieldValue
helpviewer_keywords:
- ICorDebugObjectValue::GetFieldValue method [.NET Framework debugging]
- GetFieldValue method [.NET Framework debugging]
ms.assetid: c96770b0-3e09-47bb-bd29-20353b043459
topic_type:
- apiref
ms.openlocfilehash: 38dac36747b286ab16ae3310b6b59695480a6ff1
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2021
ms.locfileid: "99722195"
---
# <a name="icordebugobjectvaluegetfieldvalue-method"></a>Метод ICorDebugObjectValue::GetFieldValue

Возвращает значение указанного поля указанного класса для данного значения объекта.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
HRESULT GetFieldValue (  
    [in]  ICorDebugClass     *pClass,  
    [in]  mdFieldDef         fieldDef,  
    [out] ICorDebugValue     **ppValue  
);  
```  
  
## <a name="parameters"></a>Параметры  

 `pClass`  
 окне Указатель на объект "ICorDebugClass", представляющий класс, для которого необходимо получить значение поля.  
  
 `fieldDef`  
 окне `mdFieldDef` Токен, ссылающийся на метаданные, описывающие поле.  
  
 `ppValue`  
 заполняет Указатель на объект "ICorDebugValue", представляющий значение указанного поля.  
  
## <a name="remarks"></a>Remarks  

 Класс, указанный в `pClass` параметре, должен находиться в иерархии класса значения объекта, а поле должно быть полем этого класса.  
  
 `GetFieldValue`Метод по-прежнему будет выполняться для универсальных объектов и универсальных классов. Например, если Мидиктионари \<V> наследуется от Dictionary \<string,V> , а значение объекта имеет тип мидиктионари \<int32> , передача `ICorDebugClass` объекта для словаря \<K,V> успешно получит поле Dictionary \<string,int32> .  
  
## <a name="requirements"></a>Требования  

 **Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).  
  
 **Заголовок:** CorDebug.idl, CorDebug.h  
  
 **Библиотека:** CorGuids.lib  
  
 **Платформа .NET Framework версии:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>См. также
