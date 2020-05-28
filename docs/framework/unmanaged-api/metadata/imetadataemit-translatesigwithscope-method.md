---
title: Метод IMetaDataEmit::TranslateSigWithScope
ms.date: 03/30/2017
api_name:
- IMetaDataEmit.TranslateSigWithScope
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataEmit::TranslateSigWithScope
helpviewer_keywords:
- TranslateSigWithScope method [.NET Framework metadata]
- IMetaDataEmit::TranslateSigWithScope method [.NET Framework metadata]
ms.assetid: 47915d33-b7bf-409e-b484-4ee1df15de22
topic_type:
- apiref
ms.openlocfilehash: 7ef6dbc46806febc6fba89b39a8b894377225c23
ms.sourcegitcommit: 03fec33630b46e78d5e81e91b40518f32c4bd7b5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/27/2020
ms.locfileid: "84003988"
---
# <a name="imetadataemittranslatesigwithscope-method"></a>Метод IMetaDataEmit::TranslateSigWithScope
Импортирует сборку в текущую область и получает новую сигнатуру метаданных для Объединенной области.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
HRESULT TranslateSigWithScope (
    [in]  IMetaDataAssemblyImport   *pAssemImport,
    [in]  const void                *pbHashValue,
    [in]  ULONG                     cbHashValue,
    [in]  IMetaDataImport           *import,
    [in]  PCCOR_SIGNATURE           pbSigBlob,
    [in]  ULONG                     cbSigBlob,  
    [in]  IMetaDataAssemblyEmit     *pAssemEmit,
    [in]  IMetaDataEmit             *emit,
    [out] PCOR_SIGNATURE            pvTranslatedSig,
    [in]  ULONG                     cbTranslatedSigMax,
    [out] ULONG                     *pcbTranslatedSig
);  
```  
  
## <a name="parameters"></a>Параметры  
 `pAssemImport`  
 окне Интерфейс для импортируемой сборки (где определена сигнатура).  
  
 `pbHashValue`  
 окне Хэш-объект хэша для сборки.  
  
 `cbHashValue`  
 окне Число байтов в `pbHashValue` .  
  
 `import`  
 окне Интерфейс для области действия метаданных импорта.  
  
 `pbSigBlob`  
 окне Импортируемая подпись.  
  
 `cbSigBlob`  
 окне Размер (в байтах) `pbSigBlob` .  
  
 `pAssemEmit`  
 окне Интерфейс для экспорта сборки.  
  
 `emit`  
 окне Интерфейс для области экспорта метаданных.  
  
 `pvTranslatedSig`  
 заполняет Буфер для хранения переведенного большого двоичного объекта сигнатуры.  
  
 `cbTranslatedSigMax`  
 окне Емкость (в байтах) `pvTranslatedSig` .  
  
 `pcbTranslatedSig`  
 заполняет Число фактических байтов в переведенной сигнатуре.  
  
## <a name="requirements"></a>Требования  
 **Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).  
  
 **Заголовок:** COR. h  
  
 **Библиотека:** Используется в качестве ресурса в MSCorEE. dll  
  
 **.NET Framework версии:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>См. также статью

- [Интерфейс IMetaDataAssemblyEmit](imetadataassemblyemit-interface.md)
- [Интерфейс IMetaDataAssemblyImport](imetadataassemblyimport-interface.md)
- [Интерфейс IMetaDataEmit](imetadataemit-interface.md)
- [Интерфейс IMetaDataEmit2](imetadataemit2-interface.md)
- [Интерфейс IMetaDataImport](imetadataimport-interface.md)
