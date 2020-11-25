---
title: Метод IMetaDataEmit::DefineImportType
ms.date: 03/30/2017
api_name:
- IMetaDataEmit.DefineImportType
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataEmit::DefineImportType
helpviewer_keywords:
- DefineImportType method [.NET Framework metadata]
- IMetaDataEmit::DefineImportType method [.NET Framework metadata]
ms.assetid: 37fd27af-8062-4904-ace4-51bb78ec600a
topic_type:
- apiref
ms.openlocfilehash: 94ce4443be210fdfeb1bab197c3e603255e1cc4c
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/24/2020
ms.locfileid: "95723250"
---
# <a name="imetadataemitdefineimporttype-method"></a>Метод IMetaDataEmit::DefineImportType

Создает ссылку на указанный тип, определенный вне текущей области, и определяет маркер для этой ссылки.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
HRESULT DefineImportType (
    [in]  IMetaDataAssemblyImport  *pAssemImport,
    [in]  const void               *pbHashValue,
    [in]  ULONG                    cbHashValue,
    [in]  IMetaDataImport          *pImport,
    [in]  mdTypeDef                tdImport,
    [in]  IMetaDataAssemblyEmit    *pAssemEmit,
    [out] mdTypeRef                *ptr  
);  
```  
  
## <a name="parameters"></a>Параметры  

 `pAssemImport`  
 окне Интерфейс [IMetaDataAssemblyImport](imetadataassemblyimport-interface.md) , представляющий сборку, из которой импортируется целевой тип.  
  
 `pbHashValue`  
 окне Массив, содержащий хэш для сборки, заданной параметром `pAssemImport` .  
  
 `cbHashValue`  
 [in] Число байтов в массиве `pbHashValue`.  
  
 `pImport`  
 окне Интерфейс [IMetaDataImport](imetadataimport-interface.md) , представляющий область метаданных, из которой импортируется целевой тип.  
  
 `tdImport`  
 окне `mdTypeDef` Токен, указывающий тип целевого объекта.  
  
 `pAssemEmit`  
 окне Интерфейс [IMetaDataAssemblyEmit](imetadataassemblyemit-interface.md) , представляющий сборку, в которую импортируется целевой тип.  
  
 `ptr`  
 заполняет `mdTypeRef` Токен, определенный в текущей области для ссылки на тип.  
  
## <a name="remarks"></a>Комментарии  

 Перед вызовом метода [IMetaDataEmit::D ефинеимпортмембер](imetadataemit-defineimportmember-method.md) можно использовать `DefineImportType` метод для создания ссылки на тип в текущей области для родительского класса члена или родительского интерфейса.  
  
## <a name="requirements"></a>Требования  

 **Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).  
  
 **Заголовок:** COR. h  
  
 **Библиотека:** Используется в качестве ресурса в MSCorEE.dll  
  
 **.NET Framework версии:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>См. также раздел

- [Интерфейс IMetaDataEmit](imetadataemit-interface.md)
- [Интерфейс IMetaDataEmit2](imetadataemit2-interface.md)
