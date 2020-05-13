---
title: Метод ICorDebugType::EnumerateTypeParameters
ms.date: 03/30/2017
api_name:
- ICorDebugType.EnumerateTypeParameters
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugType::EnumerateTypeParameters
helpviewer_keywords:
- EnumerateTypeParameters method, ICorDebugType interface [.NET Framework debugging]
- ICorDebugType::EnumerateTypeParameters method [.NET Framework debugging]
ms.assetid: 1ee1f6e6-1bd7-4ebb-83b8-ff9a08ca03de
topic_type:
- apiref
ms.openlocfilehash: dc6bf4f02c49788e640c6e230f864e3ca8e71b0d
ms.sourcegitcommit: d6bd7903d7d46698e9d89d3725f3bb4876891aa3
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/13/2020
ms.locfileid: "83380005"
---
# <a name="icordebugtypeenumeratetypeparameters-method"></a>Метод ICorDebugType::EnumerateTypeParameters
Возвращает указатель интерфейса на ICorDebugTypeEnum, содержащий <xref:System.Type> Параметры класса, на который ссылается этот объект ICorDebugType.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
HRESULT EnumerateTypeParameters (  
    [out] ICorDebugTypeEnum   **ppTyParEnum  
);  
```  
  
## <a name="parameters"></a>Параметры  
 `ppTyParEnum`  
 заполняет Указатель на адрес объекта `ICorDebugTypeEnum` , который содержит параметры типа.  
  
## <a name="remarks"></a>Remarks  
 Можно использовать, `EnumerateTypeParameters` Если значение корелементтипе, возвращаемое методом [ICorDebugType:: GetType](icordebugtype-gettype-method.md) , равно ELEMENT_TYPE_CLASS, ELEMENT_TYPE_VALUETYPE, ELEMENT_TYPE_ARRAY, ELEMENT_TYPE_SZARRAY, ELEMENT_TYPE_BYREF, ELEMENT_TYPE_PTR или ELEMENT_TYPE_FNPTR. Количество параметров и их порядок зависит от типа:  
  
- ELEMENT_TYPE_CLASS или ELEMENT_TYPE_VALUETYPE: количество параметров типа, содержащихся в, `ICorDebugTypeEnum` которые возвращает этот метод, будет зависеть от числа формальных параметров типа для соответствующего класса. Например, если тип — `class Dict<String,int32>` , то `EnumerateTypeParameters` возвратит объект `ICorDebugTypeEnum` , содержащий объекты, представляющие `String` и `int32` в последовательности.  
  
- ELEMENT_TYPE_FNPTR: количество параметров типа, содержащихся в, `ICorDebugTypeEnum` будет больше, чем число аргументов, принимаемых функцией. Первый параметр типа, содержащийся в, `ICorDebugTypeEnum` является типом возвращаемого значения для функции, а последующие параметры типа — параметрами функции.  
  
- ELEMENT_TYPE_ARRAY, ELEMENT_TYPE_SZARRAY, ELEMENT_TYPE_BYREF или ELEMENT_TYPE_PTR: будет возвращен один параметр типа. Например, если тип является массивом типа, таким как `int32[]` , `EnumerateTypeParameters` возвращает объект `ICorDebugTypeEnum` , содержащий объект, представляющий `int32` .  
  
## <a name="requirements"></a>Требования  
 **Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).  
  
 **Заголовок:** CorDebug.idl, CorDebug.h  
  
 **Библиотека:** CorGuids.lib  
  
 **.NET Framework версии:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]
