---
title: Метод ISymUnmanagedWriter::Close
ms.date: 03/30/2017
api_name:
- ISymUnmanagedWriter.Close
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedWriter::Close
helpviewer_keywords:
- Close method, ISymUnmanagedWriter interface [.NET Framework debugging]
- ISymUnmanagedWriter::Close method [.NET Framework debugging]
ms.assetid: 4cce59e1-80b9-4fc4-b3aa-126f1c5876bc
topic_type:
- apiref
ms.openlocfilehash: 0a7ecd475a8031fedb2c8474593b45045fcc6fb9
ms.sourcegitcommit: 27db07ffb26f76912feefba7b884313547410db5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/19/2020
ms.locfileid: "83610136"
---
# <a name="isymunmanagedwriterclose-method"></a>Метод ISymUnmanagedWriter::Close
Закрывает модуль записи символов после фиксации символов в хранилище символов.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
HRESULT Close();  
```  
  
## <a name="return-value"></a>Возвращаемое значение  
 S_OK, если метод выполнен. в противном случае E_FAIL или другой код ошибки.  
  
## <a name="remarks"></a>Комментарии  
 После этого вызова средство записи символов станет недействительным для последующих обновлений. Чтобы закрыть средство записи символов без фиксации символов, следует использовать метод [ISymUnmanagedWriter:: Abort](isymunmanagedwriter-abort-method.md) .  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** Корсим. idl, Корсим. h  
  
## <a name="see-also"></a>Дополнительно

- [Интерфейс ISymUnmanagedWriter](isymunmanagedwriter-interface.md)
