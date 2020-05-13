---
title: Метод ICorDebugType::GetType
ms.date: 03/30/2017
api_name:
- ICorDebugType.GetType
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugType::GetType
helpviewer_keywords:
- ICorDebugType::GetType method [.NET Framework debugging]
- GetType method, ICorDebugType interface [.NET Framework debugging]
ms.assetid: d6e64534-4d47-4ad0-a340-7590e07e2b4a
topic_type:
- apiref
ms.openlocfilehash: ac42c6254182ea775377a448a54d527b234c97dc
ms.sourcegitcommit: d6bd7903d7d46698e9d89d3725f3bb4876891aa3
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/13/2020
ms.locfileid: "83379922"
---
# <a name="icordebugtypegettype-method"></a>Метод ICorDebugType::GetType
Возвращает значение Корелементтипе, описывающее собственный тип общеязыковой среды выполнения (CLR), <xref:System.Type> представленной этим объектом ICorDebugType.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
HRESULT GetType (  
    [out] CorElementType   *ty  
);  
```  
  
## <a name="parameters"></a>Параметры  
 `ty`  
 заполняет Указатель на значение `CorElementType` перечисления, указывающее среду CLR <xref:System.Type> , которую представляет этот объект `ICorDebugType` .  
  
## <a name="remarks"></a>Remarks  
 Если значение параметра `ty` — ELEMENT_TYPE_CLASS или ELEMENT_TYPE_VALUETYPE, можно вызвать метод [ICorDebugType:: coclass](icordebugtype-getclass-method.md) , чтобы получить тип без экземпляров для универсального типа; в противном случае не вызывайте `ICorDebugType::GetClass` .  
  
## <a name="requirements"></a>Требования  
 **Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).  
  
 **Заголовок:** CorDebug.idl, CorDebug.h  
  
 **Библиотека:** CorGuids.lib  
  
 **.NET Framework версии:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]
