---
title: Метод IMetaDataImport::GetNameFromToken
ms.date: 03/30/2017
api_name:
- IMetaDataImport.GetNameFromToken
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataImport::GetNameFromToken
helpviewer_keywords:
- GetNameFromToken method [.NET Framework metadata]
- IMetaDataImport::GetNameFromToken method [.NET Framework metadata]
ms.assetid: 32114ecf-8916-4ab2-a201-179c017344f1
topic_type:
- apiref
ms.openlocfilehash: 867fb0ee4bc1a093eb7fd46e25497d585c4d9b6b
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/24/2020
ms.locfileid: "95727501"
---
# <a name="imetadataimportgetnamefromtoken-method"></a>Метод IMetaDataImport::GetNameFromToken

Возвращает имя объекта, на который ссылается указанный токен метаданных, в формате UTF-8. Этот метод устарел.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
HRESULT GetNameFromToken (  
   [in] mdToken      tk,  
   [out] MDUTF8CSTR  *pszUtf8NamePtr  
);  
```  
  
## <a name="parameters"></a>Параметры  

 `tk`  
 окне Токен, представляющий объект, для которого возвращается имя.  
  
 `pszUtf8NamePtr`  
 заполняет Указатель на имя объекта UTF-8 в куче.  
  
## <a name="remarks"></a>Комментарии  

 `GetNameFromToken` устарел. В качестве альтернативы можно вызвать метод, чтобы получить свойства требуемого типа токена, например `GetFieldProps` для поля или `GetMethodProps` для метода.  
  
## <a name="requirements"></a>Требования  

 **Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).  
  
 **Заголовок:** COR. h  
  
 **Библиотека:** Включается в качестве ресурса в MsCorEE.dll  
  
 **.NET Framework версии:** 1,0  
  
## <a name="see-also"></a>См. также раздел

- [Интерфейс IMetaDataImport](imetadataimport-interface.md)
- [Интерфейс IMetaDataImport2](imetadataimport2-interface.md)
