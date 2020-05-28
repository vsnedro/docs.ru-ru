---
title: Метод IMetaDataAssemblyEmit::DefineFile
ms.date: 03/30/2017
api_name:
- IMetaDataAssemblyEmit.DefineFile
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataAssemblyEmit::DefineFile
helpviewer_keywords:
- IMetaDataAssemblyEmit::DefineFile method [.NET Framework metadata]
- DefineFile method [.NET Framework metadata]
ms.assetid: c065aadf-c1ca-4981-bde6-597042cb29c4
topic_type:
- apiref
ms.openlocfilehash: 61d81c94e3a9c092b5d45791962635c761e8da8a
ms.sourcegitcommit: 03fec33630b46e78d5e81e91b40518f32c4bd7b5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/27/2020
ms.locfileid: "84008148"
---
# <a name="imetadataassemblyemitdefinefile-method"></a>Метод IMetaDataAssemblyEmit::DefineFile
Создает структуру метаданных `File`, содержащую метаданные для сборки, на которую ссылается данная сборка, и возвращает связанный токен метаданных.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
HRESULT DefineFile (  
    [in]  LPCWSTR        szName,
    [in]  const void     *pbHashValue,
    [in]  ULONG          cbHashValue,  
    [in]  DWORD          dwFileFlags,  
    [out] mdFile         *pmdf  
);  
```  
  
## <a name="parameters"></a>Параметры  
 `szName`  
 окне Имя файла, который будет использоваться.  
  
 `pbHashValue`  
 окне Указатель на хэш-данные, связанные со сборкой.  
  
 `cbHashValue`  
 окне Размер в байтах для `pbHashValue` .  
  
 `dwFileFlags`  
 окне Побитовое сочетание `FileFlags` значений, задающих настройки свойств.  
  
 `pmdf`  
 заполняет Указатель на возвращаемый `File` токен.  
  
## <a name="remarks"></a>Примечания  
 Одна `File` структура метаданных должна быть определена для каждого файла, который был частью этой сборки на момент построения этой сборки, за исключением файла, содержащего метаданные.  
  
## <a name="requirements"></a>Требования  
 **Платформа:** См. раздел [требования к системе](../../get-started/system-requirements.md).  
  
 **Заголовок:** COR. h  
  
 **Библиотека:** Используется в качестве ресурса в MsCorEE. dll  
  
 **.NET Framework версии:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>См. также статью

- [Интерфейс IMetaDataAssemblyEmit](imetadataassemblyemit-interface.md)
