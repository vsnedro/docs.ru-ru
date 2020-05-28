---
title: Метод IMetaDataEmit::DefineNestedType
ms.date: 03/30/2017
api_name:
- IMetaDataEmit.DefineNestedType
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataEmit::DefineNestedType
helpviewer_keywords:
- IMetaDataEmit::DefineNestedType method [.NET Framework metadata]
- DefineNestedType method [.NET Framework metadata]
ms.assetid: 1e994de6-4628-459c-b967-b34be1e9fe4f
topic_type:
- apiref
ms.openlocfilehash: 2b24c2ca6907dfdb63ad934ec30557c246db174c
ms.sourcegitcommit: 03fec33630b46e78d5e81e91b40518f32c4bd7b5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/27/2020
ms.locfileid: "84004360"
---
# <a name="imetadataemitdefinenestedtype-method"></a>Метод IMetaDataEmit::DefineNestedType
Создает сигнатуру метаданных определения типа, возвращает `mdTypeDef` маркер для этого типа и указывает, что определенный тип является членом типа, на который ссылается `tdEncloser` параметр.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
HRESULT DefineNestedType (
    [in]  LPCWSTR     szTypeDef,  
    [in]  DWORD       dwTypeDefFlags,
    [in]  mdToken     tkExtends,
    [in]  mdToken     rtkImplements[],
    [in]  mdTypeDef   tdEncloser,
    [out] mdTypeDef   *ptd  
);  
```  
  
## <a name="parameters"></a>Параметры  
 `szTypeDef`  
 окне Имя типа в Юникоде.  
  
 `dwTypeDefFlags`  
 [входные] `TypeDef` атрибута. Это битовая маска `CorTypeAttr` значений.  
  
 `tkExtends`  
 окне Маркер базового класса. Это либо маркер, либо `mdTypeDef` `mdTypeRef` .  
  
 `rtkImplements`[]  
 окне Массив токенов, задающих интерфейсы, реализуемые этим классом или интерфейсом.  
  
 `tdEncloser`  
 окне Токен включающего типа. Последний элемент массива должен быть `mdTokenNil` .  
  
 `ptd`  
 заполняет `mdTypeDef`Назначенный маркер.  
  
## <a name="requirements"></a>Требования  
 **Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).  
  
 **Заголовок:** COR. h  
  
 **Библиотека:** Используется в качестве ресурса в MSCorEE. dll  
  
 **.NET Framework версии:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>См. также статью

- [Интерфейс IMetaDataEmit](imetadataemit-interface.md)
- [Интерфейс IMetaDataEmit2](imetadataemit2-interface.md)
