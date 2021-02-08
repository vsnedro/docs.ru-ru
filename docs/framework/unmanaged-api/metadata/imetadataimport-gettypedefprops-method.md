---
description: 'Дополнительные сведения: метод IMetaDataImport:: Жеттипедефпропс'
title: Метод IMetaDataImport::GetTypeDefProps
ms.date: 03/30/2017
api_name:
- IMetaDataImport.GetTypeDefProps
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataImport::GetTypeDefProps
helpviewer_keywords:
- GetTypeDefProps method [.NET Framework metadata]
- IMetaDataImport::GetTypeDefProps method [.NET Framework metadata]
ms.assetid: 00061a25-ba05-47a7-b984-fd916b06b149
topic_type:
- apiref
ms.openlocfilehash: da5c6117f636098ed0cfeddc541979d235729d63
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2021
ms.locfileid: "99799282"
---
# <a name="imetadataimportgettypedefprops-method"></a>Метод IMetaDataImport::GetTypeDefProps

Возвращает сведения о метаданных для, <xref:System.Type> представленного указанным маркером TypeDef.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
HRESULT GetTypeDefProps (  
   [in]  mdTypeDef   td,  
   [out] LPWSTR      szTypeDef,  
   [in]  ULONG       cchTypeDef,  
   [out] ULONG       *pchTypeDef,  
   [out] DWORD       *pdwTypeDefFlags,  
   [out] mdToken     *ptkExtends  
);  
```  
  
## <a name="parameters"></a>Параметры  

 `td`  
 окне Токен TypeDef, представляющий тип, для которого возвращаются метаданные.  
  
 `szTypeDef`  
 заполняет Буфер, содержащий имя типа.  
  
 `cchTypeDef`  
 окне Размер в расширенных символах `szTypeDef` .  
  
 `pchTypeDef`  
 заполняет Число расширенных символов, возвращаемых в `szTypeDef` .  
  
 `pdwTypeDefFlags`  
 заполняет Указатель на любые флаги, изменяющие определение типа. Это значение является битовой маской из перечисления [кортипеаттр](cortypeattr-enumeration.md) .  
  
 `ptkExtends`  
 заполняет Токен метаданных TypeDef или TypeRef, представляющий базовый тип запрошенного типа.  
  
## <a name="requirements"></a>Требования  

 **Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).  
  
 **Заголовок:** COR. h  
  
 **Библиотека:** Включается в качестве ресурса в MsCorEE.dll  
  
 **Платформа .NET Framework версии:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>См. также

- [Интерфейс IMetaDataImport](imetadataimport-interface.md)
- [Интерфейс IMetaDataImport2](imetadataimport2-interface.md)
