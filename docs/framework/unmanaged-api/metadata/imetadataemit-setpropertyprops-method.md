---
title: Метод IMetaDataEmit::SetPropertyProps
ms.date: 03/30/2017
api_name:
- IMetaDataEmit.SetPropertyProps
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataEmit::SetPropertyProps
helpviewer_keywords:
- SetPropertyProps method [.NET Framework metadata]
- IMetaDataEmit::SetPropertyProps method [.NET Framework metadata]
ms.assetid: e2501fc8-b2bc-4dcc-9205-e3acd5a53ffe
topic_type:
- apiref
ms.openlocfilehash: b5af877c26c20bf64a27618bf24a7bce5b410419
ms.sourcegitcommit: 03fec33630b46e78d5e81e91b40518f32c4bd7b5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/27/2020
ms.locfileid: "84007784"
---
# <a name="imetadataemitsetpropertyprops-method"></a>Метод IMetaDataEmit::SetPropertyProps
Задает функции, хранимые в метаданных для свойства, определенного при предыдущем вызове [метода DefineProperty](imetadataemit-defineproperty-method.md).  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
HRESULT SetPropertyProps (
    [in]  mdProperty      pr,
    [in]  DWORD           dwPropFlags,
    [in]  DWORD           dwCPlusTypeFlag,
    [in]  void const      *pValue,
    [in]  ULONG           cchValue,
    [in]  mdMethodDef     mdSetter,
    [in]  mdMethodDef     mdGetter,
    [in]  mdMethodDef     rmdOtherMethods[]
);  
```  
  
## <a name="parameters"></a>Параметры  
 `pr`  
 окне Токен изменяемого свойства  
  
 `dwPropFlags`  
 окне Флаги свойств.  
  
 `dwCPlusTypeFlag`  
 окне Тип значения свойства по умолчанию.  
  
 `pValue`  
 окне Значение по умолчанию для свойства.  
  
 `cchValue`  
 окне Число символов Юникода в `pValue` .  
  
 `mdSetter`  
 окне Метод, который задает значение свойства.  
  
 `mdGetter`  
 окне Метод, который получает значение свойства.  
  
 `rmdOtherMethods[]`  
 окне Массив других методов, связанных со свойством. Завершите этот массив `mdTokenNil` токеном.  
  
## <a name="requirements"></a>Требования  
 **Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).  
  
 **Заголовок:** COR. h  
  
 **Библиотека:** Используется в качестве ресурса в MSCorEE. dll  
  
 **.NET Framework версии:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>См. также статью

- [Интерфейс IMetaDataEmit](imetadataemit-interface.md)
- [Интерфейс IMetaDataEmit2](imetadataemit2-interface.md)
