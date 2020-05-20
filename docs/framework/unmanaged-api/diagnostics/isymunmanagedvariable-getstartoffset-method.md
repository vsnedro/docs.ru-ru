---
title: Метод ISymUnmanagedVariable::GetStartOffset
ms.date: 03/30/2017
api_name:
- ISymUnmanagedVariable.GetStartOffset
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedVariable::GetStartOffset
helpviewer_keywords:
- GetStartOffset method, ISymUnmanagedVariable interface [.NET Framework debugging]
- ISymUnmanagedVariable::GetStartOffset method [.NET Framework debugging]
ms.assetid: 63021fc1-9c2d-4788-811f-fe8ca077206a
topic_type:
- apiref
ms.openlocfilehash: f2996349fd2bf1765a3de5b67d3296a25b1eaa5e
ms.sourcegitcommit: 27db07ffb26f76912feefba7b884313547410db5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/19/2020
ms.locfileid: "83610370"
---
# <a name="isymunmanagedvariablegetstartoffset-method"></a>Метод ISymUnmanagedVariable::GetStartOffset
Возвращает начальное смещение этой переменной в родительском элементе. Если это локальная переменная в области, начальное смещение будет находиться в пределах смещений, определенных для области.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
HRESULT GetStartOffset(  
    [out, retval] ULONG32* pRetVal);  
```  
  
## <a name="parameters"></a>Параметры  
 `pRetVal`  
 заполняет Указатель на объект `ULONG32` , который получает начальное смещение.  
  
## <a name="return-value"></a>Возвращаемое значение  
 S_OK, если метод выполнен. в противном случае E_FAIL или другой код ошибки.  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** Корсим. idl, Корсим. h  
  
## <a name="see-also"></a>Дополнительно

- [Интерфейс ISymUnmanagedVariable](isymunmanagedvariable-interface.md)
- [Метод GetEndOffset](isymunmanagedvariable-getendoffset-method.md)
