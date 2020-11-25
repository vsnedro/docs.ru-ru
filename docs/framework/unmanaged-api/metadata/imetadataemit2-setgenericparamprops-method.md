---
title: Метод IMetaDataEmit2::SetGenericParamProps
ms.date: 03/30/2017
api_name:
- IMetaDataEmit2.SetGenericParamProps
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataEmit2::SetGenericParamProps
helpviewer_keywords:
- IMetaDataEmit2::SetGenericParamProps method [.NET Framework metadata]
- SetGenericParamProps method [.NET Framework metadata]
ms.assetid: cd93a48d-1fed-4706-bec6-a05dc3b64fbd
topic_type:
- apiref
ms.openlocfilehash: 8858e692d66f7b34a66334bd4e8b906dd12962ba
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/24/2020
ms.locfileid: "95701995"
---
# <a name="imetadataemit2setgenericparamprops-method"></a>Метод IMetaDataEmit2::SetGenericParamProps

Задает значения свойств для определения универсального параметра, на которое ссылается указанный токен.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
HRESULT SetGenericParamProps (  
    [in] mdGenericParam   gp,
    [in] DWORD            dwParamFlags,
    [in] LPCWSTR          szName,
    [in] DWORD            reserved,
    [in] mdToken          rtkConstraints[]  
);  
```  
  
## <a name="parameters"></a>Параметры  

 `gp`  
 окне Токен для определения универсального параметра, для которого задаются значения.  
  
 `dwParamFlags`  
 окне Значение перечисления [корженерикпараматтр](corgenericparamattr-enumeration.md) , описывающее тип универсального параметра.  
  
 `szName`  
 [в] Необязательно. Имя параметра, для которого задаются значения.  
  
 `reserved`  
 окне Зарезервировано для будущего расширения.  
  
 `rtkConstraints`  
 [в] Необязательно. Массив ограничений типа, заканчивающийся нулем. Элементы массива должны быть `mdTypeDef` `mdTypeRef` `mdTypeSpec` маркером метаданных, или.  
  
## <a name="requirements"></a>Требования  

 **Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).  
  
 **Заголовок:** COR. h  
  
 **Библиотека:** Используется в качестве ресурса в MsCorEE.dll  
  
 **.NET Framework версии:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>См. также раздел

- [Интерфейс IMetaDataEmit2](imetadataemit2-interface.md)
- [Интерфейс IMetaDataEmit](imetadataemit-interface.md)
