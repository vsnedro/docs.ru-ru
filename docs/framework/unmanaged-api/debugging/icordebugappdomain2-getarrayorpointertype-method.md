---
description: 'Дополнительные сведения о методе: ICorDebugAppDomain2:: Жетаррайорпоинтертипе'
title: Метод ICorDebugAppDomain2::GetArrayOrPointerType
ms.date: 03/30/2017
api_name:
- ICorDebugAppDomain2.GetArrayOrPointerType
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugAppDomain2::GetArrayOrPointerType
helpviewer_keywords:
- GetArrayOrPointerType method [.NET Framework debugging]
- ICorDebugAppDomain2::GetArrayOrPointerType method [.NET Framework debugging]
ms.assetid: 97e493f5-3a62-4ec7-b42f-4af57bf71f57
topic_type:
- apiref
ms.openlocfilehash: e42d105e807bdb8c81f2d6f8ef6c2f65a4081d98
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2021
ms.locfileid: "99754229"
---
# <a name="icordebugappdomain2getarrayorpointertype-method"></a>Метод ICorDebugAppDomain2::GetArrayOrPointerType

Возвращает массив указанного типа или указатель или ссылку на указанный тип.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
HRESULT GetArrayOrPointerType (  
    [in]  CorElementType    elementType,  
    [in]  ULONG32           nRank,  
    [in]  ICorDebugType     *pTypeArg,  
    [out] ICorDebugType     **ppType  
);  
```  
  
## <a name="parameters"></a>Параметры  

 `elementType`  
 окне Значение перечисления Корелементтипе, которое указывает базовый собственный тип (массив, указатель или ссылка), который необходимо создать.  
  
 `nRank`  
 окне Ранг (то есть количество измерений) массива. Это значение должно быть равно 0 `elementType` , если указывает тип указателя или ссылки.  
  
 `pTypeArg`  
 окне Указатель на объект ICorDebugType, представляющий тип создаваемого массива, указателя или ссылки.  
  
 `ppType`  
 заполняет Указатель на адрес `ICorDebugType` объекта, представляющий сконструированный массив, тип указателя или ссылочный тип.  
  
## <a name="remarks"></a>Remarks  

 Значение *ElementType* должно быть одним из следующих:  
  
- ELEMENT_TYPE_PTR  
  
- ELEMENT_TYPE_BYREF  
  
- ELEMENT_TYPE_ARRAY или ELEMENT_TYPE_SZARRAY  
  
 Если значение *ElementType* равно ELEMENT_TYPE_PTR или ELEMENT_TYPE_BYREF, *нранк* должно быть равно нулю.  
  
## <a name="requirements"></a>Требования  

 **Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).  
  
 **Заголовок:** CorDebug.idl, CorDebug.h  
  
 **Библиотека:** CorGuids.lib  
  
 **Платформа .NET Framework версии:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]
