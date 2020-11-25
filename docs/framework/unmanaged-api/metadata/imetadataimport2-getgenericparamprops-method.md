---
title: Метод IMetaDataImport2::GetGenericParamProps
ms.date: 03/30/2017
api_name:
- IMetaDataImport2.GetGenericParamProps
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataImport2::GetGenericParamProps
helpviewer_keywords:
- IMetaDataImport2::GetGenericParamProps method [.NET Framework metadata]
- GetGenericParamProps method [.NET Framework metadata]
ms.assetid: dbb21e67-712b-49e7-a27c-a1e73ffd46c5
topic_type:
- apiref
ms.openlocfilehash: 16f69d571ffed87a2e848124ce16ac942d319c37
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/24/2020
ms.locfileid: "95702699"
---
# <a name="imetadataimport2getgenericparamprops-method"></a>Метод IMetaDataImport2::GetGenericParamProps

Возвращает метаданные, связанные с универсальным параметром, представленным указанным токеном.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
HRESULT GetGenericParamProps (  
   [in]  mdGenericParam  gp,  
   [out] ULONG           *pulParamSeq,  
   [out] DWORD           *pdwParamFlags,  
   [out] mdToken         *ptOwner,  
   [out] DWORD           *reserved,  
   [out] LPWSTR          wzName,  
   [in]  ULONG           cchName,  
   [out] ULONG           *pchName  
);  
```  
  
## <a name="parameters"></a>Параметры  

 `gp`  
 окне Токен, представляющий универсальный параметр, для которого возвращаются метаданные.  
  
 `pulParamSeq`  
 заполняет Порядковый номер `Type` параметра в родительском конструкторе или методе.  
  
 `pdwParamFlags`  
 заполняет Значение перечисления [корженерикпараматтр](corgenericparamattr-enumeration.md) , описывающее объект `Type` для универсального параметра.  
  
 `ptOwner`  
 заполняет Токен TypeDef или MethodDef, представляющий владельца параметра.  
  
 `reserved`  
 заполняет Зарезервировано для будущего расширения.  
  
 `wzName`  
 заполняет Имя универсального параметра.  
  
 `cchName`  
 окне Размер `wzName` буфера.  
  
 `pchName`  
 заполняет Возвращаемый размер имени в расширенных символах.  
  
## <a name="requirements"></a>Требования  

 **Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).  
  
 **Заголовок:** COR. h  
  
 **Библиотека:** Используется в качестве ресурса в MsCorEE.dll  
  
 **.NET Framework версии:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>См. также раздел

- [Интерфейс IMetaDataImport2](imetadataimport2-interface.md)
- [Интерфейс IMetaDataImport](imetadataimport-interface.md)
