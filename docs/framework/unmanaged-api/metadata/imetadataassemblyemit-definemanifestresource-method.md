---
title: Метод IMetaDataAssemblyEmit::DefineManifestResource
ms.date: 03/30/2017
api_name:
- IMetaDataAssemblyEmit.DefineManifestResource
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataAssemblyEmit::DefineManifestResource
helpviewer_keywords:
- DefineManifestResource method [.NET Framework metadata]
- IMetaDataAssemblyEmit::DefineManifestResource method [.NET Framework metadata]
ms.assetid: 27f6d295-0fe9-4cda-b77e-6e7d5c53df09
topic_type:
- apiref
ms.openlocfilehash: 026f5efe195cdb34999b65c5f47de6f68d30e11a
ms.sourcegitcommit: 03fec33630b46e78d5e81e91b40518f32c4bd7b5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/27/2020
ms.locfileid: "84008135"
---
# <a name="imetadataassemblyemitdefinemanifestresource-method"></a>Метод IMetaDataAssemblyEmit::DefineManifestResource
Создает структуру `ManifestResource`, содержащую метаданные для указанного ресурса манифеста, и возвращает связанный токен метаданных.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
HRESULT DefineManifestResource (  
    [in] LPCWSTR                szName,
    [in] mdToken                tkImplementation,
    [in] DWORD                  dwOffset,
    [in] DWORD                  dwResourceFlags,  
    [out] mdManifestResource    *pmdmr  
);  
```  
  
## <a name="parameters"></a>Параметры  
 `szName`  
 [in] Имя ресурса.  
  
 `tkImplementation`  
 окне Маркер метаданных типа `mdtFile` или `mdtAssemblyRef` , сопоставляемый с поставщиком ресурсов. Значение NULL указывает, что файл, в котором внедрены метаданные, является поставщиком ресурсов.  
  
 `dwOffset`  
 окне Смещение в начале ресурса в файле. Для ресурсов в отдельных файлах это значение всегда будет равно нулю. Если ресурс внедряется в PE-файл, это смещение большого двоичного объекта ресурса, которое начинается в расположении, указанном в файле заголовка COR. h.  
  
 `dwResourceFlags`  
 окне Побитовое сочетание значений флагов, задающих настройки свойств для определения ресурса.  
  
 `pmdmr`  
 заполняет Указатель на возвращаемый маркер метаданных.  
  
## <a name="remarks"></a>Примечания  
 `ManifestResource`Для каждого ресурса, реализованного в каждом файле сборки, должна быть определена одна структура метаданных.  
  
## <a name="requirements"></a>Требования  
 **Платформа:** См. раздел [требования к системе](../../get-started/system-requirements.md).  
  
 **Заголовок:** COR. h  
  
 **Библиотека:** Используется в качестве ресурса в MsCorEE. dll  
  
 **.NET Framework версии:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>См. также статью

- [Интерфейс IMetaDataAssemblyEmit](imetadataassemblyemit-interface.md)
