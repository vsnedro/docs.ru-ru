---
description: 'Дополнительные сведения о методе: IMetaDataAssemblyImport:: GetFileProps'
title: Метод IMetaDataAssemblyImport::GetFileProps
ms.date: 03/30/2017
api_name:
- IMetaDataAssemblyImport.GetFileProps
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataAssemblyImport::GetFileProps
helpviewer_keywords:
- GetFileProps method [.NET Framework metadata]
- IMetaDataAssemblyImport::GetFileProps method [.NET Framework metadata]
ms.assetid: c5e6216f-ae3d-4697-9688-66b69c1251ec
topic_type:
- apiref
ms.openlocfilehash: 6814fee7edf5478a1ce2cf2b81d8f16fa62cd3f3
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2021
ms.locfileid: "99784110"
---
# <a name="imetadataassemblyimportgetfileprops-method"></a>Метод IMetaDataAssemblyImport::GetFileProps

Возвращает свойства файла с указанной сигнатурой метаданных.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
HRESULT GetFileProps (  
    [in]  mdFile      mdf,
    [out] LPWSTR      szName,
    [in]  ULONG       cchName,
    [out] ULONG       *pchName,
    [out] const void  **ppbHashValue,
    [out] ULONG       *pcbHashValue,
    [out] DWORD       *pdwFileFlags  
);  
```  
  
## <a name="parameters"></a>Параметры  

 `mdf`  
 окне `mdFile` Токен метаданных, представляющий файл, для которого необходимо получить свойства.  
  
 `szName`  
 заполняет Простое имя файла.  
  
 `cchName`  
 окне Размер (в расширенных символах) для `szName` .  
  
 `pchName`  
 заполняет Число расширенных символов, фактически возвращаемых в `szName` .  
  
 `ppbHashValue`  
 заполняет Указатель на хэш-значение. Это хэш-код с использованием алгоритма SHA-1 файла.  
  
 `pcbHashValue`  
 заполняет Число расширенных символов в возвращенном хэш-значении.  
  
 `pdwFileFlags`  
 заполняет Указатель на флаги, описывающие метаданные, примененные к файлу. Значение Flags является сочетанием одного или нескольких значений [корфилефлагс](corfileflags-enumeration.md) .  
  
## <a name="requirements"></a>Требования  

 **Платформа:** См. раздел [требования к системе](../../get-started/system-requirements.md).  
  
 **Заголовок:** COR. h  
  
 **Библиотека:** Используется в качестве ресурса в MsCorEE.dll  
  
 **Платформа .NET Framework версии:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>См. также

- [Интерфейс IMetaDataAssemblyImport](imetadataassemblyimport-interface.md)
