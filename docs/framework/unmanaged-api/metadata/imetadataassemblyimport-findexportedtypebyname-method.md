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
ms.openlocfilehash: b1672d98d76241e5af4b6b60a38785f1278e15a8
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/24/2020
ms.locfileid: "95731596"
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
  
## <a name="remarks"></a>Комментарии  

 `FindExportedTypeByName`Метод использует стандартные правила, используемые средой CLR для разрешения ссылок.  
  
## <a name="requirements"></a>Требования  

 **Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).  
  
 **Заголовок:** COR. h  
  
 **Библиотека:** Используется в качестве ресурса в MsCorEE.dll  
  
 **.NET Framework версии:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>См. также раздел

- [Интерфейс IMetaDataAssemblyImport](imetadataassemblyimport-interface.md)
- [Обнаружение сборок в среде выполнения](../../deployment/how-the-runtime-locates-assemblies.md)
