---
title: Метод IMetaDataImport::FindTypeDefByName
ms.date: 03/30/2017
api_name:
- IMetaDataImport.FindTypeDefByName
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataImport::FindTypeDefByName
helpviewer_keywords:
- FindTypeDefByName method [.NET Framework metadata]
- IMetaDataImport::FindTypeDefByName method [.NET Framework metadata]
ms.assetid: f4c2cd88-ac28-4bad-9ab1-2cf9d2de41e6
topic_type:
- apiref
ms.openlocfilehash: df1516a916b2b48080e4f94937fba063926330ba
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/24/2020
ms.locfileid: "95711303"
---
# <a name="imetadataimportfindtypedefbyname-method"></a>Метод IMetaDataImport::FindTypeDefByName

Возвращает указатель на маркер метаданных TypeDef для <xref:System.Type> с указанным именем.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
HRESULT FindTypeDefByName  
   [in]  LPCWSTR       szTypeDef,  
   [in]  mdToken       tkEnclosingClass,  
   [out] mdTypeDef     *ptd  
);  
```  
  
## <a name="parameters"></a>Параметры  

 `szTypeDef`  
 окне Имя типа, для которого требуется получить маркер TypeDef.  
  
 `tkEnclosingClass`  
 окне Токен TypeDef или TypeRef, представляющий включающий класс. Если искомый тип не является вложенным классом, присвойте этому параметру значение NULL.  
  
 `ptd`  
 заполняет Указатель на соответствующий маркер TypeDef.  
  
## <a name="requirements"></a>Требования  

 **Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).  
  
 **Заголовок:** COR. h  
  
 **Библиотека:** Включается в качестве ресурса в MsCorEE.dll  
  
 **.NET Framework версии:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>См. также раздел

- [Интерфейс IMetaDataImport](imetadataimport-interface.md)
- [Интерфейс IMetaDataImport2](imetadataimport2-interface.md)
