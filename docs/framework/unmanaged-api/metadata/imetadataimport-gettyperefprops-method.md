---
description: 'Дополнительные сведения: метод IMetaDataImport:: GetTypeRefProps'
title: Метод IMetaDataImport::GetTypeRefProps
ms.date: 03/30/2017
api_name:
- IMetaDataImport.GetTypeRefProps
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataImport::GetTypeRefProps
helpviewer_keywords:
- IMetaDataImport::GetTypeRefProps method [.NET Framework metadata]
- GetTypeRefProps method [.NET Framework metadata]
ms.assetid: 01837955-ce1e-4068-b338-fd473bd77d1d
topic_type:
- apiref
ms.openlocfilehash: 8d4741ca2d04aaa4af48fee2cf6485de3403a525
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2021
ms.locfileid: "99789129"
---
# <a name="imetadataimportgettyperefprops-method"></a>Метод IMetaDataImport::GetTypeRefProps

Возвращает метаданные, связанные с <xref:System.Type> объектом, на который ссылается указанный токен TypeRef.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
HRESULT GetTypeRefProps (  
   [in]  mdTypeRef   tr,  
   [out] mdToken     *ptkResolutionScope,  
   [out] LPWSTR      szName,  
   [in]  ULONG       cchName,  
   [out] ULONG       *pchName  
);  
```  
  
## <a name="parameters"></a>Параметры  

 `tr`  
 окне Токен TypeRef, представляющий тип, для которого возвращаются метаданные.  
  
 `ptkResolutionScope`  
 заполняет Указатель на область, в которой создана ссылка. Это значение является токеном AssemblyRef или ModuleRef.  
  
 `szName`  
 заполняет Буфер, содержащий имя типа.  
  
 `cchName`  
 окне Запрошенный размер в расширенных символах `szName` .  
  
 `pchName`  
 заполняет Возвращаемый размер в расширенных символах `szName` .  
  
## <a name="requirements"></a>Требования  

 **Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).  
  
 **Заголовок:** COR. h  
  
 **Библиотека:** Включается в качестве ресурса в MsCorEE.dll  
  
 **Платформа .NET Framework версии:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>См. также

- [Интерфейс IMetaDataImport](imetadataimport-interface.md)
- [Интерфейс IMetaDataImport2](imetadataimport2-interface.md)
