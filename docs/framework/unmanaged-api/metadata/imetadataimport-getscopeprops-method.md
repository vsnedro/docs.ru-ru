---
description: 'Дополнительные сведения: метод IMetaDataImport:: Жетскопепропс'
title: Метод IMetaDataImport::GetScopeProps
ms.date: 03/30/2017
api_name:
- IMetaDataImport.GetScopeProps
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataImport::GetScopeProps
helpviewer_keywords:
- IMetaDataImport::GetScopeProps method [.NET Framework metadata]
- GetScopeProps method [.NET Framework metadata]
ms.assetid: c8ba42d2-d9fa-43cb-bbc0-f33e1e592cb6
topic_type:
- apiref
ms.openlocfilehash: 2ed7c08cc876f467a46fe38c7c27719e5608e623
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2021
ms.locfileid: "99789155"
---
# <a name="imetadataimportgetscopeprops-method"></a>Метод IMetaDataImport::GetScopeProps

Возвращает имя и при необходимости идентификатор версии сборки или модуля в текущей области метаданных.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
HRESULT GetScopeProps (  
   [out] LPWSTR           szName,  
   [in]  ULONG            cchName,  
   [out] ULONG            *pchName,  
   [out, optional] GUID   *pmvid  
);  
```  
  
## <a name="parameters"></a>Параметры  

 `szName`  
 заполняет Буфер для имени сборки или модуля.  
  
 `cchName`  
 окне Размер в расширенных символах `szName` .  
  
 `pchName`  
 заполняет Число расширенных символов, возвращаемых в `szName` .  
  
 `pmvid`  
 [out, необязательно] Указатель на идентификатор GUID, однозначно определяющий версию сборки или модуля.  
  
## <a name="remarks"></a>Remarks  

 Для задания этих свойств используется метод [IMetaDataEmit:: сетмодулепропс](imetadataemit-setmoduleprops-method.md) .  
  
## <a name="requirements"></a>Требования  

 **Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).  
  
 **Заголовок:** COR. h  
  
 **Библиотека:** Включается в качестве ресурса в MsCorEE.dll  
  
 **Платформа .NET Framework версии:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>См. также

- [Интерфейс IMetaDataImport](imetadataimport-interface.md)
- [Интерфейс IMetaDataImport2](imetadataimport2-interface.md)
