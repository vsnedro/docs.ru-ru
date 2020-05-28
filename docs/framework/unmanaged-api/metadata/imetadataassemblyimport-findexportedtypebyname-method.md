---
title: Метод IMetaDataAssemblyImport::FindExportedTypeByName
ms.date: 03/30/2017
api_name:
- IMetaDataAssemblyImport.FindExportedTypeByName
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataAssemblyImport::FindExportedTypeByName
helpviewer_keywords:
- FindExportedTypeByName method [.NET Framework metadata]
- IMetaDataAssemblyImport::FindExportedTypeByName method [.NET Framework metadata]
ms.assetid: 46264b2c-574d-4dde-aafc-77187a104fdd
topic_type:
- apiref
ms.openlocfilehash: ac6de9a16fad6ba9d14f3960ddd28c42c111f254
ms.sourcegitcommit: 03fec33630b46e78d5e81e91b40518f32c4bd7b5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/27/2020
ms.locfileid: "84009396"
---
# <a name="imetadataassemblyimportfindexportedtypebyname-method"></a>Метод IMetaDataAssemblyImport::FindExportedTypeByName
Возвращает указатель на экспортированный тип по заданному имени и включающему его типу.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
HRESULT FindExportedTypeByName (  
    [in]  LPCWSTR           szName,
    [in]  mdToken           mdtExportedType,
    [out] mdExportedType    *ptkExportedType  
);  
```  
  
## <a name="parameters"></a>Параметры  
 `szName`  
 окне Имя экспортированного типа.  
  
 `mdtExportedType`  
 окне Токен метаданных для включающего класса экспортируемого типа. Это значение равно, `mdExportedTypeNil` Если запрошенный экспортированный тип не является вложенным типом.  
  
 `ptkExportedType`  
 заполняет Указатель на `mdExportedType` маркер, представляющий экспортированный тип.  
  
## <a name="remarks"></a>Примечания  
 `FindExportedTypeByName`Метод использует стандартные правила, используемые средой CLR для разрешения ссылок.  
  
## <a name="requirements"></a>Требования  
 **Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).  
  
 **Заголовок:** COR. h  
  
 **Библиотека:** Используется в качестве ресурса в MsCorEE. dll  
  
 **.NET Framework версии:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>См. также статью

- [Интерфейс IMetaDataAssemblyImport](imetadataassemblyimport-interface.md)
- [Обнаружение сборок в среде выполнения](../../deployment/how-the-runtime-locates-assemblies.md)
