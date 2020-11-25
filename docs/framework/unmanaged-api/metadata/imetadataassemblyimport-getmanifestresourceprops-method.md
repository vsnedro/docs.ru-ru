---
title: Метод IMetaDataAssemblyImport::GetManifestResourceProps
ms.date: 03/30/2017
api_name:
- IMetaDataAssemblyImport.GetManifestResourceProps
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataAssemblyImport::GetManifestResourceProps
helpviewer_keywords:
- GetManifestResourceProps method [.NET Framework metadata]
- IMetaDataAssemblyImport::GetManifestResourceProps method [.NET Framework metadata]
ms.assetid: 00be4789-ac63-4397-b2ec-1629a5c5a585
topic_type:
- apiref
ms.openlocfilehash: 585a9e39f529294841cd11389f03d763968a0f5e
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/24/2020
ms.locfileid: "95723822"
---
# <a name="imetadataassemblyimportgetmanifestresourceprops-method"></a>Метод IMetaDataAssemblyImport::GetManifestResourceProps

Возвращает набор свойств ресурса манифеста с указанной сигнатурой метаданных.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
HRESULT GetManifestResourceProps (  
    [in]  mdManifestResource   mdmr,
    [out] LPWSTR               szName,
    [in]  ULONG                cchName,
    [out] ULONG                *pchName,
    [out] mdToken              *ptkImplementation,
    [out] DWORD                *pdwOffset,
    [out] DWORD                *pdwResourceFlags  
);  
```  
  
## <a name="parameters"></a>Параметры  

 `mdmr`  
 окне `mdManifestResource` Токен, представляющий ресурс, для которого необходимо получить свойства.  
  
 `szName`  
 заполняет Имя ресурса.  
  
 `cchName`  
 окне Размер (в расширенных символах) для `szName` .  
  
 `pchName`  
 заполняет Указатель на число расширенных символов, фактически возвращаемых в `szName` .  
  
 `ptkImplementation`  
 заполняет Указатель на `mdFile` маркер или `mdAssemblyRef` маркер, представляющий файл или сборку соответственно, который содержит ресурс.  
  
 `pdwOffset`  
 заполняет Указатель на значение, указывающее смещение к началу ресурса в файле.  
  
 `pdwResourceFlags`  
 заполняет Указатель на флаги, описывающие метаданные, применяемые к ресурсу. Значение Flags является сочетанием одного или нескольких значений [корманифестресаурцефлагс](cormanifestresourceflags-enumeration.md) .  
  
## <a name="requirements"></a>Требования  

 **Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).  
  
 **Заголовок:** COR. h  
  
 **Библиотека:** Используется в качестве ресурса в MsCorEE.dll  
  
 **.NET Framework версии:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>См. также раздел

- [Интерфейс IMetaDataAssemblyImport](imetadataassemblyimport-interface.md)
