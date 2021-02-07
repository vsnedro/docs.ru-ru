---
description: 'Дополнительные сведения: Метод IMetaDataEmit:: Транслатесигвисскопе'
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
ms.openlocfilehash: e5f4e522e993f2f391ca0c29e5fcc2cbb71775e8
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2021
ms.locfileid: "99720937"
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
  
 **Библиотека:** Используется в качестве ресурса в MSCorEE.dll  
  
 **Платформа .NET Framework версии:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>См. также

- [Интерфейс IMetaDataAssemblyEmit](imetadataassemblyemit-interface.md)
- [Интерфейс IMetaDataAssemblyImport](imetadataassemblyimport-interface.md)
- [Интерфейс IMetaDataEmit](imetadataemit-interface.md)
- [Интерфейс IMetaDataEmit2](imetadataemit2-interface.md)
- [Интерфейс IMetaDataImport](imetadataimport-interface.md)
