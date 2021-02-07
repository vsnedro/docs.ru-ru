---
description: 'Дополнительные сведения о методе: IMetaDataAssemblyEmit::D Ефинефиле'
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
ms.openlocfilehash: 825ef44c2b0a5f312b4c5f9c851d62e75709c7ff
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2021
ms.locfileid: "99671056"
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
  
## <a name="remarks"></a>Remarks  

 Одна `File` структура метаданных должна быть определена для каждого файла, который был частью этой сборки на момент построения этой сборки, за исключением файла, содержащего метаданные.  
  
## <a name="requirements"></a>Требования  

 **Платформа:** См. раздел [требования к системе](../../get-started/system-requirements.md).  
  
 **Заголовок:** COR. h  
  
 **Библиотека:** Используется в качестве ресурса в MsCorEE.dll  
  
 **Платформа .NET Framework версии:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>См. также

- [Интерфейс IMetaDataAssemblyEmit](imetadataassemblyemit-interface.md)
