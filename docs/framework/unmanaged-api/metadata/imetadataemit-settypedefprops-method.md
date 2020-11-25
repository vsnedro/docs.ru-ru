---
title: Метод IMetaDataEmit::SetTypeDefProps
ms.date: 03/30/2017
api_name:
- IMetaDataEmit.SetTypeDefProps
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataEmit::SetTypeDefProps
helpviewer_keywords:
- SetTypeDefProps method [.NET Framework metadata]
- IMetaDataEmit::SetTypeDefProps method [.NET Framework metadata]
ms.assetid: 480d596a-759f-4d29-ac1a-3dbff8f3544d
topic_type:
- apiref
ms.openlocfilehash: 2f572f66f16ff701350fde3b05be822b9e8c78b4
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/24/2020
ms.locfileid: "95706837"
---
# <a name="imetadataemitsettypedefprops-method"></a>Метод IMetaDataEmit::SetTypeDefProps

Задает функции типа, определенного при предыдущем вызове метода [IMetaDataEmit::D ефинетипедеф](imetadataemit-definetypedef-method.md).  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
HRESULT SetTypeDefProps (  
    [in]  mdTypeDef   td,
    [in]  DWORD       dwTypeDefFlags,
    [in]  mdToken     tkExtends,
    [in]  mdToken     rtkImplements[]
);  
```  
  
## <a name="parameters"></a>Параметры  

 `td`  
 окне `mdTypeDef` Маркер, полученный из исходного вызова [IMetaDataEmit::D ефинетипедеф](imetadataemit-definetypedef-method.md).  
  
 `dwTypeDefFlags`  
 [входные] `TypeDef` атрибута. Это битовая маска `CorTypeAttr` значений.  
  
 `tkExtends`  
 окне `mdToken` Класс базового класса. Получено из предыдущего вызова [IMetaDataEmit::D ефинеимпорттипе](imetadataemit-defineimporttype-method.md)или `null` .  
  
 `rtkImplements[]`  
 окне Массив токенов для интерфейсов, реализуемых этим типом. Эти `mdTypeRef` токены получаются с помощью [IMetaDataEmit::D ефинеимпорттипе](imetadataemit-defineimporttype-method.md). Последним элементом массива должен быть `mdTokenNil` .  
  
## <a name="requirements"></a>Требования  

 **Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).  
  
 **Заголовок:** COR. h  
  
 **Библиотека:** Используется в качестве ресурса в MSCorEE.dll  
  
 **.NET Framework версии:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>См. также раздел

- [Интерфейс IMetaDataEmit](imetadataemit-interface.md)
- [Интерфейс IMetaDataEmit2](imetadataemit2-interface.md)
