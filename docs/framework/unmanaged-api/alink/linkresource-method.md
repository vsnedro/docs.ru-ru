---
title: Метод LinkResource
ms.date: 03/30/2017
api_name:
- IALink.LinkResource
api_location:
- alink.dll
api_type:
- COM
f1_keywords:
- LinkResource
helpviewer_keywords:
- LinkResource method
ms.assetid: c404acb3-4c59-4100-9a4c-483cbdb1d736
topic_type:
- apiref
ms.openlocfilehash: 4f2f13976dfd4e5601bf8b54bed7b851884fbb9d
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/24/2020
ms.locfileid: "95690451"
---
# <a name="linkresource-method"></a>Метод LinkResource

Ссылки в ресурсе.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
HRESULT LinkResource(  
    mdAssembly  AssemblyID,  
    LPCWSTR     pszFileName,  
    LPCWSTR     pszNewLocation,  
    LPCWSTR     pszResourceName,  
    DWORD       dwFlags  
) PURE;  
```  
  
## <a name="parameters"></a>Параметры  

 `AssemblyID`  
 Идентификатор сборки.  
  
 `pszFileName`  
 Имя файла.  
  
 `pszNewLocation`  
 Необязательное новое имя файла. Если значение не равно NULL, `pszFileName` будет скопировано в псзневлокатион.  
  
 `pszResourceName`  
 Имя ресурса.  
  
 `dwFlags`  
 Флаги специальных возможностей, такие как `mrPublic` и `mrPrivate` . Этот параметр может быть передан [методу DefineManifestResource](../metadata/imetadataassemblyemit-definemanifestresource-method.md).  
  
## <a name="return-value"></a>Возвращаемое значение  

 Возвращает S_OK, если метод завершается с ошибкой.  
  
## <a name="requirements"></a>Требования  

 Требуется ALink. h.  
  
## <a name="see-also"></a>См. также раздел

- [Интерфейс IALink](ialink-interface.md)
- [Интерфейс IALink2](ialink2-interface.md)
- [API ALink](index.md)
