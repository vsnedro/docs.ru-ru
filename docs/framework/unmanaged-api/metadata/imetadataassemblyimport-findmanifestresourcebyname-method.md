---
description: 'Дополнительные сведения о методе: IMetaDataAssemblyImport:: Финдманифестресаурцебинаме'
title: Метод IMetaDataAssemblyImport::FindManifestResourceByName
ms.date: 03/30/2017
api_name:
- IMetaDataAssemblyImport.FindManifestResourceByName
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataAssemblyImport::FindManifestResourceByName
helpviewer_keywords:
- FindManifestResourceByName method [.NET Framework metadata]
- IMetaDataAssemblyImport::FindManifestResourceByName method [.NET Framework metadata]
ms.assetid: 7b72fa11-3866-402b-bdea-2b966b77cfe0
topic_type:
- apiref
ms.openlocfilehash: 1d1312277675a1f2bf213221ab8d9d2a584733a4
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2021
ms.locfileid: "99784175"
---
# <a name="imetadataassemblyimportfindmanifestresourcebyname-method"></a>Метод IMetaDataAssemblyImport::FindManifestResourceByName

Возвращает указатель на ресурс манифеста с указанным именем.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp
HRESULT FindManifestResourceByName (  
    [in]  LPCWSTR                szName,
    [out] mdManifestResource     *ptkManifestResource  
);
```  
  
## <a name="parameters"></a>Параметры  

 `szName`  
 [in] Имя ресурса.  
  
 `ptkManifestResource`  
 заполняет Массив, используемый для хранения `mdManifestResource` маркеров метаданных, каждый из которых представляет ресурс манифеста.  
  
## <a name="remarks"></a>Remarks  

 `FindManifestResourceByName`Метод использует стандартные правила, используемые средой CLR для разрешения ссылок.  
  
## <a name="requirements"></a>Требования  

 **Платформа:** См. раздел [требования к системе](../../get-started/system-requirements.md).  
  
 **Заголовок:** COR. h  
  
 **Библиотека:** Используется в качестве ресурса в MsCorEE.dll  
  
 **Платформа .NET Framework версии:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>См. также

- [Интерфейс IMetaDataAssemblyImport](imetadataassemblyimport-interface.md)
- [Обнаружение сборок в среде выполнения](../../deployment/how-the-runtime-locates-assemblies.md)
