---
description: 'Дополнительные сведения: IMetaDataEmit::D метод Ефинепроперти'
title: Метод IMetaDataEmit::DefineProperty
ms.date: 03/30/2017
api_name:
- IMetaDataEmit.DefineProperty
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataEmit::DefineProperty
helpviewer_keywords:
- IMetaDataEmit::DefineProperty method [.NET Framework metadata]
- DefineProperty method [.NET Framework metadata]
ms.assetid: 5c4c1dc2-d40d-4173-bbe6-7058fb21c98f
topic_type:
- apiref
ms.openlocfilehash: c0c0b6009f8674a5edebf1c982e277f4ca5b185b
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2021
ms.locfileid: "99784037"
---
# <a name="imetadataemitdefineproperty-method"></a>Метод IMetaDataEmit::DefineProperty

Создает определение свойства для указанного типа с указанными `get` `set` методами доступа и и получает маркер для этого определения свойства.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
HRESULT DefineProperty (
    [in]  mdTypeDef          td,
    [in]  LPCWSTR            szProperty,
    [in]  DWORD              dwPropFlags,
    [in]  PCCOR_SIGNATURE    pvSig,
    [in]  ULONG              cbSig,
    [in]  DWORD              dwCPlusTypeFlag,
    [in]  void const         *pValue,
    [in]  ULONG              cchValue,
    [in]  mdMethodDef        mdSetter,
    [in]  mdMethodDef        mdGetter,
    [in]  mdMethodDef        rmdOtherMethods[],
    [out] mdProperty         *pmdProp
);  
```  
  
## <a name="parameters"></a>Параметры  

 `td`  
 окне Токен для класса или интерфейса, для которого определяется свойство.  
  
 `szProperty`  
 [in] Имя свойства.  
  
 `dwPropFlags`  
 окне Флаги свойств.  
  
 `pvSig`  
 окне Сигнатура свойства.  
  
 `cbSig`  
 окне Число байтов в `pvSig` .  
  
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
 окне Массив других методов, связанных со свойством. Завершите массив с помощью `mdTokenNil` .  
  
 `pmdProp`  
 заполняет `mdProperty` Назначенный маркер.  
  
## <a name="requirements"></a>Требования  

 **Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).  
  
 **Заголовок:** COR. h  
  
 **Библиотека:** Используется в качестве ресурса в MSCorEE.dll  
  
 **Платформа .NET Framework версии:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>См. также

- [Интерфейс IMetaDataEmit](imetadataemit-interface.md)
- [Интерфейс IMetaDataEmit2](imetadataemit2-interface.md)
