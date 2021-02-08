---
description: 'Дополнительные сведения: IMetaDataEmit::D метод Ефинепарам'
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
ms.openlocfilehash: 300de3183b329773a8e6813d6b92c6d049d63195
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2021
ms.locfileid: "99784097"
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
 заполняет `mdParamDef` Назначенный маркер.  
  
## <a name="remarks"></a>Remarks  

 Значения последовательности в `ulParamSeq` аргументе начинаются с 1 для параметров. Возвращаемое значение имеет порядковый номер 0.  
  
## <a name="requirements"></a>Требования  

 **Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).  
  
 **Заголовок:** COR. h  
  
 **Библиотека:** Используется в качестве ресурса в MSCorEE.dll  
  
 **Платформа .NET Framework версии:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>См. также

- [Интерфейс IMetaDataEmit](imetadataemit-interface.md)
- [Интерфейс IMetaDataEmit2](imetadataemit2-interface.md)
