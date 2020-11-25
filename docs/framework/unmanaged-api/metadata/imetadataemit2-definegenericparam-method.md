---
title: Метод IMetaDataEmit2::DefineGenericParam
ms.date: 03/30/2017
api_name:
- IMetaDataEmit2.DefineGenericParam
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataEmit2::DefineGenericParam
helpviewer_keywords:
- IMetaDataEmit2::DefineGenericParam method [.NET Framework metadata]
- DefineGenericParam method [.NET Framework metadata]
ms.assetid: 47b2a3b6-907d-43dc-858d-1ae7dca1316a
topic_type:
- apiref
ms.openlocfilehash: c9ff918121e7bb4ee972e674207810358b3f36f2
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/24/2020
ms.locfileid: "95712915"
---
# <a name="imetadataemit2definegenericparam-method"></a>Метод IMetaDataEmit2::DefineGenericParam

Создает определение для параметра универсального типа и получает маркер для этого параметра универсального типа.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
HRESULT DefineGenericParam (
    [in]  mdToken         tk,
    [in]  ULONG           ulParamSeq,
    [in]  DWORD           dwParamFlags,
    [in]  LPCWSTR         szname,
    [in]  DWORD           reserved,
    [in]  mdToken         rtkConstraints[],
    [out] mdGenericParam  *pgp  
);  
```  
  
## <a name="parameters"></a>Параметры  

 `tk`  
 окне `mdTypeDef` Токен или `mdMethodDef` , представляющий метод или конструктор, для которого необходимо определить универсальный параметр.  
  
 `ulParamSeq`  
 окне Индекс универсального параметра.  
  
 `dwParamFlags`  
 окне Значение перечисления [корженерикпараматтр](corgenericparamattr-enumeration.md) , описывающее тип универсального параметра.  
  
 `szname`  
 окне Имя параметра.  
  
 `reserved`  
 окне Этот параметр зарезервирован для расширения в будущем.  
  
 `rtkConstraints`  
 окне Массив ограничений типа, заканчивающийся нулем. Элементы массива должны быть `mdTypeDef` `mdTypeRef` `mdTypeSpec` маркером метаданных, или.  
  
 `pgp`  
 заполняет Токен, представляющий универсальный параметр.  
  
## <a name="requirements"></a>Требования  

 **Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).  
  
 **Заголовок:** COR. h  
  
 **Библиотека:** Используется в качестве ресурса в MsCorEE.dll  
  
 **.NET Framework версии:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>См. также раздел

- [Интерфейс IMetaDataEmit2](imetadataemit2-interface.md)
- [Интерфейс IMetaDataEmit](imetadataemit-interface.md)
