---
title: Метод IMetaDataEmit::SetParamProps
ms.date: 03/30/2017
api_name:
- IMetaDataEmit.SetParamProps
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataEmit::SetParamProps
helpviewer_keywords:
- IMetaDataEmit::SetParamProps method [.NET Framework metadata]
- SetParamProps method [.NET Framework metadata]
ms.assetid: a95a3908-9f87-4084-937e-8e01ef03ad63
topic_type:
- apiref
ms.openlocfilehash: b710f966f519e2702607b7e186fff5986110d391
ms.sourcegitcommit: 03fec33630b46e78d5e81e91b40518f32c4bd7b5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/27/2020
ms.locfileid: "84007823"
---
# <a name="imetadataemitsetparamprops-method"></a>Метод IMetaDataEmit::SetParamProps
Задает или изменяет функции параметра метода, который был определен при предыдущем вызове [IMetaDataEmit::D ефинепарам](imetadataemit-defineparam-method.md).  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
HRESULT SetParamProps (
    [in]  mdParamDef  pd,
    [in]  LPCWSTR     szName,
    [in]  DWORD       dwParamFlags,
    [in]  DWORD       dwCPlusTypeFlag,
    [in]  void const  *pValue,
    [in]  ULONG       cchValue
);  
```  
  
## <a name="parameters"></a>Параметры  
 `pd`  
 окне Токен для целевого параметра.  
  
 `szName`  
 окне Имя параметра в Юникоде.  
  
 `dwParamFlags`  
 окне Флаги для параметра.  
  
 `dwCPlusTypeFlag`  
 окне ELEMENT_TYPE_ * для постоянного значения.  
  
 `pValue`  
 окне Постоянное значение для параметра.  
  
 `cchValue`  
 окне Размер символов (в Юникоде) `pValue` .  
  
## <a name="requirements"></a>Требования  
 **Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).  
  
 **Заголовок:** COR. h  
  
 **Библиотека:** Используется в качестве ресурса в MSCorEE. dll  
  
 **.NET Framework версии:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>См. также статью

- [Интерфейс IMetaDataEmit](imetadataemit-interface.md)
- [Интерфейс IMetaDataEmit2](imetadataemit2-interface.md)
