---
title: Метод ICorDebugType::GetStaticFieldValue
ms.date: 03/30/2017
api_name:
- ICorDebugType.GetStaticFieldValue
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugType::GetStaticFieldValue
helpviewer_keywords:
- GetStaticFieldValue method, ICorDebugType interface [.NET Framework debugging]
- ICorDebugType::GetStaticFieldValue method [.NET Framework debugging]
ms.assetid: 62eb5d55-53ee-4fb3-8d47-7b6c96808f9e
topic_type:
- apiref
ms.openlocfilehash: 281b9f46194e93220f47ef8aadbf29ce03084582
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/24/2020
ms.locfileid: "95711953"
---
# <a name="icordebugtypegetstaticfieldvalue-method"></a>Метод ICorDebugType::GetStaticFieldValue

Возвращает указатель интерфейса на объект ICorDebugValue, содержащий значение статического поля, на которое ссылается заданный токен поля в указанном кадре стека.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
HRESULT GetStaticFieldValue (  
    [in]  mdFieldDef        fieldDef,  
    [in]  ICorDebugFrame    *pFrame,  
    [out] ICorDebugValue    **ppValue  
);  
```  
  
## <a name="parameters"></a>Параметры  

 `fieldDef`  
 окне `mdFieldDef` Токен, указывающий статическое поле.  
  
 `pFrame`  
 окне Указатель на объект ICorDebugFrame, представляющий кадр стека.  
  
 `ppValue`  
 заполняет Указатель на адрес объекта `ICorDebugValue` , который содержит значение статического поля.  
  
## <a name="remarks"></a>Комментарии  

 `GetStaticFieldValue`Метод может использоваться только в том случае, если тип имеет значение ELEMENT_TYPE_CLASS или ELEMENT_TYPE_VALUETYPE, как указано в методе [ICorDebugType:: GetType](icordebugtype-gettype-method.md) .  
  
 Для неуниверсальных типов операция, выполняемая, `GetStaticFieldValue` идентична вызову [ICorDebugClass:: GetStaticFieldValue](icordebugclass-getstaticfieldvalue-method.md) для объекта ICorDebugClass, возвращаемого командлетом [ICorDebugType::](icordebugtype-getclass-method.md)GetObject.  
  
 Для универсальных типов значение статического поля будет относиться к определенному экземпляру. Кроме того, если статическое поле может быть связано с потоком, контекстом или доменом приложения, то кадр стека поможет отладчику определить правильное значение.  
  
## <a name="remarks"></a>Комментарии  

 `GetStaticFieldValue` может использоваться, только если вызов `ICorDebugType::GetType` возвращает значение ELEMENT_TYPE_CLASS или ELEMENT_TYPE_VALUETYPE.  
  
## <a name="requirements"></a>Требования  

 **Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).  
  
 **Заголовок:** CorDebug.idl, CorDebug.h  
  
 **Библиотека:** CorGuids.lib  
  
 **.NET Framework версии:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]
