---
description: 'Дополнительные сведения: IMetaDataEmit::D метод Ефинефиелд'
title: Метод IMetaDataEmit::DefineField
ms.date: 03/30/2017
api_name:
- IMetaDataEmit.DefineField
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataEmit::DefineField
helpviewer_keywords:
- IMetaDataEmit::DefineField method [.NET Framework metadata]
- DefineField method, IMetaDataEmit interface [.NET Framework metadata
ms.assetid: 6b5be4fc-2e86-499c-8b09-833160bca767
topic_type:
- apiref
ms.openlocfilehash: 7636b1521de721cc183305e8a0763ff0a61f331b
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2021
ms.locfileid: "99753450"
---
# <a name="imetadataemitdefinefield-method"></a>Метод IMetaDataEmit::DefineField

Создает определение для поля с указанной сигнатурой метаданных и получает маркер для этого определения поля.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
HRESULT DefineField (
    [in]  mdTypeDef   td,
    [in]  LPCWSTR     szName,
    [in]  DWORD       dwFieldFlags,
    [in]  PCCOR_SIGNATURE pvSigBlob,
    [in]  ULONG       cbSigBlob,
    [in]  DWORD       dwCPlusTypeFlag,
    [in]  void const  *pValue,
    [in]  ULONG       cchValue,
    [out] mdFieldDef  *pmd
);  
```  
  
## <a name="parameters"></a>Параметры  

 `td`  
 окне `mdTypeDef` Токен для включающего класса или интерфейса.  
  
 `szName`  
 окне Имя поля в Юникоде.  
  
 `dwFieldFlags`  
 окне Атрибуты поля. Это битовая маска `CorFieldAttr` значений.  
  
 `pvSigBlob`  
 окне Подпись поля в виде большого двоичного объекта.  
  
 `cbSigBlob`  
 окне Число байтов в `pvSigBlob` .  
  
 `dwCPlusTypeFlag`  
 окне `ELEMENT_TYPE_` *\** Значение для постоянного значения. Это `CorElementType` значение. Если для поля не определено постоянное значение, используйте `ELEMENT_TYPE_END` .  
  
 `pValue`  
 окне Постоянное значение для поля.  
  
 `cchValue`  
 окне Размер символов (в Юникоде) `pValue` .  
  
 `pmd`  
 заполняет `mdFieldDef` Назначенный маркер.  
  
## <a name="requirements"></a>Требования  

 **Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).  
  
 **Заголовок:** COR. h  
  
 **Библиотека:** Используется в качестве ресурса в MSCorEE.dll  
  
 **Платформа .NET Framework версии:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>См. также

- [Интерфейс IMetaDataEmit](imetadataemit-interface.md)
- [Интерфейс IMetaDataEmit2](imetadataemit2-interface.md)
