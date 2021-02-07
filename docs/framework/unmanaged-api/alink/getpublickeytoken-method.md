---
description: Дополнительные сведения о методе Жетпубликкэйтокен
title: Метод GetPublicKeyToken
ms.date: 03/30/2017
api_name:
- IALink2.GetPublicKeyToken
api_location:
- alink.dll
api_type:
- COM
f1_keywords:
- GetPublicKeyToken
helpviewer_keywords:
- GetPublicKeyToken method
ms.assetid: 4a16374c-94b0-47b0-9fed-88c2b0cdccd4
topic_type:
- apiref
ms.openlocfilehash: b864c1dc61c7498ccca6aa04ef29b57a30e1a9ea
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2021
ms.locfileid: "99718425"
---
# <a name="getpublickeytoken-method"></a>Метод GetPublicKeyToken

Извлекает токен открытого ключа для данного ключа или контейнера ключей.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
HRESULT GetPublicKeyToken(  
    LPCWSTR pszKeyFile,  
    LPCWSTR pszKeyContainer,  
    void* pvPublicKeyToken,  
    DWORD* pcbPublicKeyToken  
) PURE;  
```  
  
## <a name="parameters"></a>Параметры  

 `pszKeyFile`  
 Имя файла ключа.  
  
 `pszKeyContainer`  
 Имя контейнера ключей.  
  
 `pvPublicKeyToken`  
 Адрес, по которому должен храниться токен ключа.  
  
 `pcbPublicKeyToken`  
 Задает размер буфера (в байтах), указанного в параметре `pvPublicKeyToken` . После возврата содержит фактическое число используемых байтов.  
  
## <a name="return-value"></a>Возвращаемое значение  

 Возвращает S_OK, если метод завершается с ошибкой.  
  
## <a name="requirements"></a>Требования  

 Требуется ALink. h.  
  
## <a name="see-also"></a>См. также

- [Интерфейс IALink2](ialink2-interface.md)
- [Интерфейс IALink](ialink-interface.md)
- [API ALink](index.md)
