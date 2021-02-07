---
description: 'Дополнительные сведения о методе: ICorDebugClass2:: GetParameterizedType'
title: Метод ICorDebugClass2::GetParameterizedType
ms.date: 03/30/2017
api_name:
- ICorDebugClass2.GetParameterizedType
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugClass2::GetParameterizedType
helpviewer_keywords:
- GetParameterizedType method [.NET Framework debugging]
- ICorDebugClass2::GetParameterizedType method [.NET Framework debugging]
ms.assetid: 94b591c4-9302-4af2-a510-089496afb036
topic_type:
- apiref
ms.openlocfilehash: 4810e10e88af9256a466579ee607c0ef314d984b
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2021
ms.locfileid: "99765042"
---
# <a name="icordebugclass2getparameterizedtype-method"></a>Метод ICorDebugClass2::GetParameterizedType

Возвращает объявление типа для этого класса.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
HRESULT GetParameterizedType (  
    [in] CorElementType                      elementType,  
    [in] ULONG32                             nTypeArgs,  
    [in, size_is(nTypeArgs)] ICorDebugType  *ppTypeArgs[],  
    [out] ICorDebugType                    **ppType  
);  
```  
  
## <a name="parameters"></a>Параметры  

 `elementType`  
 окне Значение перечисления Корелементтипе, указывающее тип элемента для этого класса: задайте для этого параметра значение ELEMENT_TYPE_VALUETYPE, если этот ICorDebugClass2 представляет тип значения. Присвойте этому параметру значение ELEMENT_TYPE_CLASS, если оно `ICorDebugClass2` представляет сложный тип.  
  
 `nTypeArgs`  
 окне Число параметров типа, если тип является универсальным. Количество параметров типа (если таковое имеется) должно совпадать с числом, необходимым для класса.  
  
 `ppTypeArgs`  
 окне Массив указателей, каждый из которых указывает на объект ICorDebugType, представляющий параметр типа. Если класс не является универсальным, это значение равно null.  
  
 `ppType`  
 заполняет Указатель на адрес `ICorDebugType` объекта, который представляет объявление типа. Этот объект эквивалентен <xref:System.Type> объекту в управляемом коде.  
  
## <a name="remarks"></a>Remarks  

 Если класс не является универсальным, то есть если он не имеет параметров типа, `GetParameterizedType` просто получает объект типа среды выполнения, соответствующий классу. `elementType`Для параметра необходимо задать правильный тип элемента для класса: ELEMENT_TYPE_VALUETYPE, если класс является типом значения; в противном случае — ELEMENT_TYPE_CLASS.  
  
 Если класс принимает параметры типа (например, `ArrayList<T>` ), можно использовать `GetParameterizedType` для создания объекта типа для экземпляра такого типа, как `ArrayList<int>` .  
  
## <a name="background-information"></a>Основные сведения  

 В платформа .NET Framework версиях 1,0 и 1,1 каждый тип в метаданных можно напрямую сопоставить с типом в выполняемом процессе. Таким словами, тип метаданных и тип среды выполнения имеют одно представление в выполняющемся процессе. Однако один универсальный тип в метаданных может быть сопоставлен с множеством различных экземпляров типа в выполняющемся процессе. Например, тип метаданных `SortedList<K,V>` может сопоставляться с `SortedList<String, EmployeeRecord>` , `SortedList<Int32, String>` , `SortedList<String,Array<Int32>>` и т. д. Таким образом, необходим способ для управления созданием экземпляров типа.  
  
 В платформа .NET Framework версии 2,0 появился `ICorDebugType` интерфейс. Для универсального типа `ICorDebugClass` объект или представляет тип, не являющийся `ICorDebugClass2` экземпляром ( `SortedList<K,V>` ), а `ICorDebugType` объект представляет различные экземпляры типов. При наличии `ICorDebugClass` `ICorDebugClass2` объекта или можно создать `ICorDebugType` объект для любого экземпляра, вызвав `ICorDebugClass2::GetParameterizedType` метод. Можно также создать `ICorDebugType` объект для простого типа, например Int32, или для неуниверсального типа.  
  
 Введение `ICorDebugType` объекта, представляющего представление времени выполнения типа, оказывает воздействие на весь интерфейс API. Функции, которые ранее принимали `ICorDebugClass` `ICorDebugClass2` объект или или даже `CorElementType` значение, обобщены для получения `ICorDebugType` объекта.  
  
## <a name="requirements"></a>Требования  

 **Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).  
  
 **Заголовок:** CorDebug.idl, CorDebug.h  
  
 **Библиотека:** CorGuids.lib  
  
 **Платформа .NET Framework версии:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]
