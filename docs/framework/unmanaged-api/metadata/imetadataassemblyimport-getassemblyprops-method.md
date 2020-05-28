---
title: Метод IMetaDataAssemblyImport::GetAssemblyProps
ms.date: 03/30/2017
api_name:
- IMetaDataAssemblyImport.GetAssemblyProps
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataAssemblyImport::GetAssemblyProps
helpviewer_keywords:
- GetAssemblyProps method [.NET Framework metadata]
- IMetaDataAssemblyImport::GetAssemblyProps method [.NET Framework metadata]
ms.assetid: 0eaa4aa9-9441-444a-920c-e4b2a2db899e
topic_type:
- apiref
ms.openlocfilehash: a90deaf3e9ddf326c6fca558cbb4681fc40e022d
ms.sourcegitcommit: 03fec33630b46e78d5e81e91b40518f32c4bd7b5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/27/2020
ms.locfileid: "84009058"
---
# <a name="imetadataassemblyimportgetassemblyprops-method"></a>Метод IMetaDataAssemblyImport::GetAssemblyProps
Возвращает набор свойств для сборки с указанной сигнатурой метаданных.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
HRESULT GetAssemblyProps (  
    [in]  mdAssembly          mda,  
    [out] const void          **ppbPublicKey,
    [out] ULONG               *pcbPublicKey,  
    [out] ULONG               *pulHashAlgId,  
    [out] LPWSTR              szName,  
    [in] ULONG                cchName,  
    [out] ULONG               *pchName,  
    [out] ASSEMBLYMETADATA    *pMetaData,  
    [out] DWORD               *pdwAssemblyFlags  
);  
```  
  
## <a name="parameters"></a>Параметры  
 `mda`  
 [in]. `mdAssembly`Токен метаданных, представляющий сборку, для которой необходимо получить свойства.  
  
 `ppbPublicKey`  
 заполняет Указатель на открытый ключ или маркер метаданных.  
  
 `pcbPublicKey`  
 заполняет Число байтов в возвращенном открытом ключе.  
  
 `pulHashAlgId`  
 заполняет Указатель на алгоритм, используемый для хэширования файлов в сборке.  
  
 `szName`  
 заполняет Простое имя сборки.  
  
 `cchName`  
 окне Размер (в расширенных символах) для `szName` .  
  
 `pchName`  
 заполняет Число расширенных символов, фактически возвращаемых в `szName` .  
  
 `pMetaData`  
 заполняет Указатель на структуру ASSEMBLYMETADATA, содержащую метаданные сборки.  
  
 `pdwAssemblyFlags`  
 заполняет Флаги, описывающие метаданные, применяемые к сборке. Это значение представляет собой сочетание одного или нескольких значений [корассемблифлагс](corassemblyflags-enumeration.md) .  
  
## <a name="requirements"></a>Требования  
 **Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).  
  
 **Заголовок:** COR. h  
  
 **Библиотека:** Используется в качестве ресурса в MsCorEE. dll  
  
 **.NET Framework версии:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>См. также статью

- [Интерфейс IMetaDataAssemblyImport](imetadataassemblyimport-interface.md)
