---
title: Метод ISymUnmanagedWriter::OpenNamespace
ms.date: 03/30/2017
api_name:
- ISymUnmanagedWriter.OpenNamespace
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedWriter::OpenNamespace
helpviewer_keywords:
- ISymUnmanagedWriter::OpenNamespace method [.NET Framework debugging]
- OpenNamespace method [.NET Framework debugging]
ms.assetid: 426f4e4f-e60d-4ad1-b546-a10e3c55c283
topic_type:
- apiref
ms.openlocfilehash: 2f64f9f4bde3119f9f089becec5a36d69ed43596
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/24/2020
ms.locfileid: "95730065"
---
# <a name="isymunmanagedwriteropennamespace-method"></a>Метод ISymUnmanagedWriter::OpenNamespace

Открывает новое пространство имен. Вызовите этот метод перед определением методов или переменных, которые занимают пространство имен. Пространства имен могут быть вложенными.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
HRESULT OpenNamespace(  
    [in] const WCHAR *name);  
```  
  
## <a name="parameters"></a>Параметры  

 `name`  
 окне Указатель на имя нового пространства имен.  
  
## <a name="return-value"></a>Возвращаемое значение  

 S_OK, если метод выполнен. в противном случае E_FAIL или другой код ошибки.  
  
## <a name="requirements"></a>Требования  

 **Заголовок:** Корсим. idl, Корсим. h  
  
## <a name="see-also"></a>См. также раздел

- [Интерфейс ISymUnmanagedWriter](isymunmanagedwriter-interface.md)
- [Метод CloseNamespace](isymunmanagedwriter-closenamespace-method.md)
