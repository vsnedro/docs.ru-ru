---
title: Метод ICorDebugILFrame2::EnumerateTypeParameters
ms.date: 03/30/2017
api_name:
- ICorDebugILFrame2.EnumerateTypeParameters
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugILFrame2::EnumerateTypeParameters
helpviewer_keywords:
- EnumerateTypeParameters method, ICorDebugILFrame2 interface [.NET Framework debugging]
- ICorDebugILFrame2::EnumerateTypeParameters method [.NET Framework debugging]
ms.assetid: 722d0d74-e0df-491f-98c4-62d501dfaf6f
topic_type:
- apiref
ms.openlocfilehash: 73c17864047270302dbc115667eec4bf5ea1569d
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/24/2020
ms.locfileid: "95725052"
---
# <a name="icordebugilframe2enumeratetypeparameters-method"></a>Метод ICorDebugILFrame2::EnumerateTypeParameters

Возвращает объект ICorDebugTypeEnum, содержащий <xref:System.Type> Параметры в этом кадре.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
HRESULT EnumerateTypeParameters (  
    [out] ICorDebugTypeEnum    **ppTyParEnum  
);  
```  
  
## <a name="parameters"></a>Параметры  

 `ppTyParEnum`  
 Указатель на адрес объекта интерфейса ICorDebugTypeEnum, который допускает перечисление параметров типа.  
  
 Список параметров типа включает параметры типа класса (если они есть), за которыми следуют параметры типа метода (если они есть).  
  
## <a name="remarks"></a>Комментарии  

 Используйте метод [IMetaDataImport2:: EnumGenericParams](../metadata/imetadataimport2-enumgenericparams-method.md) , чтобы определить, сколько параметров типа класса и параметров типа метода содержит этот список.  
  
 Параметры типа доступны не всегда.  
  
## <a name="requirements"></a>Требования  

 **Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).  
  
 **Заголовок:** CorDebug.idl, CorDebug.h  
  
 **Библиотека:** CorGuids.lib  
  
 **.NET Framework версии:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]
