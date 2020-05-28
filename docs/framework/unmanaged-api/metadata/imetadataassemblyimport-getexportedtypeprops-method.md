---
title: Метод IMetaDataAssemblyImport::GetExportedTypeProps
ms.date: 03/30/2017
api_name:
- IMetaDataAssemblyImport.GetExportedTypeProps
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataAssemblyImport::GetExportedTypeProps
helpviewer_keywords:
- GetExportedTypeProps method [.NET Framework metadata]
- IMetaDataAssemblyImport::GetExportedTypeProps method [.NET Framework metadata]
ms.assetid: 25ca7623-5a55-4f09-b44a-36b03d142278
topic_type:
- apiref
ms.openlocfilehash: 944941c2356cae93ecc85f1714b4b29aefcb50ad
ms.sourcegitcommit: 03fec33630b46e78d5e81e91b40518f32c4bd7b5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/27/2020
ms.locfileid: "84008408"
---
# <a name="imetadataassemblyimportgetexportedtypeprops-method"></a>Метод IMetaDataAssemblyImport::GetExportedTypeProps
Возвращает набор свойств экспортированного типа с указанной сигнатурой метаданных.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
HRESULT GetExportedTypeProps (  
    [in]  mdExportedType    mdct,
    [out] LPWSTR            szName,
    [in]  ULONG             cchName,
    [out] ULONG             *pchName,
    [out] mdToken           *ptkImplementation,
    [out] mdTypeDef         *ptkTypeDef,
    [out] DWORD             *pdwExportedTypeFlags  
);  
```  
  
## <a name="parameters"></a>Параметры  
 `mdct`  
 окне `mdExportedType`Токен метаданных, представляющий экспортированный тип.  
  
 `szName`  
 заполняет Имя экспортированного типа.  
  
 `cchName`  
 окне Размер (в расширенных символах) `szName` .  
  
 `pchName`  
 заполняет Число расширенных символов, фактически возвращаемых в`szName`  
  
 `ptkImplementation`  
 заполняет `mdFile` `mdAssemblyRef` Маркер метаданных, или `mdExportedType` , который содержит или разрешает доступ к свойствам экспортированного типа.  
  
 `ptkTypeDef`  
 заполняет Указатель на `mdTypeDef` маркер, представляющий тип в файле.  
  
 `pdwExportedTypeFlags`  
 заполняет Указатель на флаги, описывающие метаданные, применяемые к экспортируемому типу. Значение Flags может быть одним или несколькими [кортипеаттр](cortypeattr-enumeration.md) значениями.  
  
## <a name="requirements"></a>Требования  
 **Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).  
  
 **Заголовок:** COR. h  
  
 **Библиотека:** Используется в качестве ресурса в MsCorEE. dll  
  
 **.NET Framework версии:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>См. также статью

- [Интерфейс IMetaDataAssemblyImport](imetadataassemblyimport-interface.md)
