---
title: Метод IMetaDataEmit::DefineParam
ms.date: 03/30/2017
api_name:
- IMetaDataEmit.DefineParam
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataEmit::DefineParam
helpviewer_keywords:
- IMetaDataEmit::DefineParam method [.NET Framework metadata]
- DefineParam method [.NET Framework metadata]
ms.assetid: d86a3d14-4796-4909-9591-dfafe3de5ce4
topic_type:
- apiref
ms.openlocfilehash: a58e03875ec021b41479085fa9e27a4321ae965e
ms.sourcegitcommit: 03fec33630b46e78d5e81e91b40518f32c4bd7b5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/27/2020
ms.locfileid: "84004378"
---
# <a name="imetadataemitdefineparam-method"></a>Метод IMetaDataEmit::DefineParam
Создает определение параметра с указанной сигнатурой для метода, на который ссылается указанный токен, и получает маркер для этого определения параметра.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
HRESULT DefineParam (  
    [in]  mdMethodDef md,
    [in]  ULONG       ulParamSeq,
    [in]  LPCWSTR     szName,
    [in]  DWORD       dwParamFlags,
    [in]  DWORD       dwCPlusTypeFlag,
    [in]  void const  *pValue,  
    [in]  ULONG       cchValue,
    [out] mdParamDef  *ppd
);  
```  
  
## <a name="parameters"></a>Параметры  
 `md`  
 окне Токен для метода, параметр которого определяется.  
  
 `ulParamSeq`  
 окне Порядковый номер параметра.  
  
 `szName`  
 окне Имя параметра в Юникоде.  
  
 `dwParamFlags`  
 окне Флаги для параметра. Это битовая маска `CorParamAttr` значений.  
  
 `dwCPlusTypeFlag`  
 [входные] `ELEMENT_TYPE_` *\** для постоянного значения.  
  
 `pValue`  
 окне Постоянное значение для параметра.  
  
 `cchValue`  
 окне Размер (в символах Юникода) `pValue` .  
  
 `ppd`  
 заполняет `mdParamDef`Назначенный маркер.  
  
## <a name="remarks"></a>Примечания  
 Значения последовательности в `ulParamSeq` аргументе начинаются с 1 для параметров. Возвращаемое значение имеет порядковый номер 0.  
  
## <a name="requirements"></a>Требования  
 **Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).  
  
 **Заголовок:** COR. h  
  
 **Библиотека:** Используется в качестве ресурса в MSCorEE. dll  
  
 **.NET Framework версии:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>См. также статью

- [Интерфейс IMetaDataEmit](imetadataemit-interface.md)
- [Интерфейс IMetaDataEmit2](imetadataemit2-interface.md)
