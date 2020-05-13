---
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
ms.openlocfilehash: 660bc13e8109994f59444c0adebbc97f54de0b43
ms.sourcegitcommit: 488aced39b5f374bc0a139a4993616a54d15baf0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/12/2020
ms.locfileid: "83207594"
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
 окне `mdFieldDef`Токен, ссылающийся на метаданные, описывающие поле.  
  
 `ppValue`  
 заполняет Указатель на объект "ICorDebugValue", представляющий значение указанного поля.  
  
## <a name="remarks"></a>Remarks  
 Класс, указанный в `pClass` параметре, должен находиться в иерархии класса значения объекта, а поле должно быть полем этого класса.  
  
 `GetFieldValue`Метод по-прежнему будет выполняться для универсальных объектов и универсальных классов. Например, если Мидиктионари \< V> наследуется из \< строки словаря, V>, а значение объекта имеет тип мидиктионари \< Int32>, передача `ICorDebugClass` объекта для словаря \< K, V> успешно получит поле \< строки словаря,> Int32.  
  
## <a name="requirements"></a>Требования  
 **Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).  
  
 **Заголовок:** CorDebug.idl, CorDebug.h  
  
 **Библиотека:** CorGuids.lib  
  
 **.NET Framework версии:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>См. также
