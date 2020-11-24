---
title: Метод ISymUnmanagedWriter::RemapToken
ms.date: 03/30/2017
api_name:
- ISymUnmanagedWriter.RemapToken
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedWriter::RemapToken
helpviewer_keywords:
- ISymUnmanagedWriter::RemapToken method [.NET Framework debugging]
- RemapToken method [.NET Framework debugging]
ms.assetid: bca92682-ee1e-467f-8fb0-d8d4617f82fe
topic_type:
- apiref
ms.openlocfilehash: 8799815f7c6c6aefc7081f3583e6fd174cd478f7
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/24/2020
ms.locfileid: "95683561"
---
# <a name="isymunmanagedwriterremaptoken-method"></a>Метод ISymUnmanagedWriter::RemapToken

Уведомляет средство записи символов о том, что маркер метаданных был повторно сопоставлен при выдаче метаданных. Если средство записи символов сохранило Старый токен в хранилище символов, оно должно либо обновить сохраненный токен новым значением, либо сохранить карту для соответствующего средства чтения символов для сопоставления на этапе чтения.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
HRESULT RemapToken(  
    [in] mdToken  oldToken,  
    [in] mdToken  newToken);  
```  
  
## <a name="parameters"></a>Параметры  

 `oldToken`  
 окне Токен метаданных, который был повторно сопоставлен.  
  
 `newToken`  
 окне Новый токен метаданных, с которым `oldToken` было выполнено повторное сопоставление.  
  
## <a name="return-value"></a>Возвращаемое значение  

 S_OK, если метод выполнен. в противном случае E_FAIL или другой код ошибки.  
  
## <a name="requirements"></a>Требования  

 **Заголовок:** Корсим. idl, Корсим. h  
  
## <a name="see-also"></a>См. также раздел

- [Интерфейс ISymUnmanagedWriter](isymunmanagedwriter-interface.md)
