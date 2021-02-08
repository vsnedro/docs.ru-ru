---
description: 'Дополнительные сведения о методе: IMetaDataAssemblyImport:: GetAssemblyRefProps'
title: Метод IMetaDataAssemblyImport::GetAssemblyRefProps
ms.date: 03/30/2017
api_name:
- IMetaDataAssemblyImport.GetAssemblyRefProps
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataAssemblyImport::GetAssemblyRefProps
helpviewer_keywords:
- IMetaDataAssemblyImport::GetAssemblyRefProps method [.NET Framework metadata]
- GetAssemblyRefProps method [.NET Framework metadata]
ms.assetid: 5c6b7fb4-cbca-4479-b650-ab9a99732ea0
topic_type:
- apiref
ms.openlocfilehash: f7011806920ba37ca84b1a48f12da3a5557fa464
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2021
ms.locfileid: "99784136"
---
# <a name="imetadataassemblyimportgetassemblyrefprops-method"></a>Метод IMetaDataAssemblyImport::GetAssemblyRefProps

Возвращает набор свойств для ссылки на сборку с указанной сигнатурой метаданных.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
HRESULT GetAssemblyRefProps (  
    [in]  mdAssemblyRef        mdar,
    [out] const void          **ppbPublicKeyOrToken,
    [out] ULONG                *pcbPublicKeyOrToken,
    [out] LPWSTR               szName,
    [in]  ULONG                cchName,
    [out] ULONG                *pchName,
    [out] ASSEMBLYMETADATA     *pMetaData,
    [out] const void           **ppbHashValue,
    [out] ULONG                *pcbHashValue,
    [out] DWORD                *pdwAssemblyRefFlags  
);  
```  
  
## <a name="parameters"></a>Параметры  

 `mdar`  
 окне `mdAssemblyRef` Токен метаданных, представляющий ссылку на сборку, для которой необходимо получить свойства.  
  
 `ppbPublicKeyOrToken`  
 заполняет Указатель на открытый ключ или маркер метаданных.  
  
 `pcbPublicKeyOrToken`  
 заполняет Число байтов в возвращенном открытом ключе или токене.  
  
 `szName`  
 заполняет Простое имя сборки.  
  
 `cchName`  
 окне Размер (в расширенных символах) для `szName` .  
  
 `pchName`  
 заполняет Указатель на число расширенных символов, фактически возвращаемых в `szName` .  
  
 `pMetaData`  
 заполняет Указатель на структуру ASSEMBLYMETADATA, содержащую метаданные сборки.  
  
 `ppbHashValue`  
 заполняет Указатель на хэш-значение. Это хэш с использованием алгоритма SHA-1 `PublicKey` Свойства сборки, на которую указывает ссылка, если не задан флаг арффуллоригинатор перечисления [ассемблиреффлагс](assemblyrefflags-enumeration.md) .  
  
 `pcbHashValue`  
 заполняет Число расширенных символов в возвращенном хэш-значении.  
  
 `pdwAssemblyRefFlags`  
 заполняет Указатель на флаги, описывающие метаданные, примененные к сборке. Значение Flags является сочетанием одного или нескольких значений [корассемблифлагс](corassemblyflags-enumeration.md) .  
  
## <a name="return-value"></a>Возвращаемое значение  

 Этот метод возвращает S_OK, если он выполнен. в противном случае возвращается один из кодов ошибок, определенных в файле заголовка Winerror. h.  
  
## <a name="requirements"></a>Требования  

 **Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).  
  
 **Заголовок:** COR. h  
  
 **Библиотека:** Используется в качестве ресурса в MsCorEE.dll  
  
 **Платформа .NET Framework версии:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>См. также

- [Интерфейс IMetaDataAssemblyImport](imetadataassemblyimport-interface.md)
