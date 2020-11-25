---
title: Метод ISymENCUnmanagedMethod::GetDocumentsForMethod
ms.date: 03/30/2017
api_name:
- ISymENCUnmanagedMethod.GetDocumentsForMethod
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymENCUnmanagedMethod::GetDocumentsForMethod
helpviewer_keywords:
- GetDocumentsForMethod method [.NET Framework debugging]
- ISymENCUnmanagedMethod::GetDocumentsForMethod method [.NET Framework debugging]
ms.assetid: bd6ccde5-d578-48d8-abed-b474fbd48d13
topic_type:
- apiref
ms.openlocfilehash: d9fe18225dc27e93d4e97940cba878e4d73b4ed2
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/24/2020
ms.locfileid: "95730530"
---
# <a name="isymencunmanagedmethodgetdocumentsformethod-method"></a>Метод ISymENCUnmanagedMethod::GetDocumentsForMethod

Возвращает документы, в которых у этого метода есть строки.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
HRESULT GetDocumentsForMethod(  
    [in]  ULONG32  cDocs,  
    [out] ULONG32  *pcDocs,
    [in, size_is(cDocs)] ISymUnmanagedDocument* documents[]);  
```  
  
## <a name="parameters"></a>Параметры  

 `cDocs`  
 окне Длина буфера, на который указывает `pcDocs` .  
  
 `pcDocs`  
 заполняет Указатель на объект `ULONG32` , который получает размер (в символах) буфера, необходимого для хранения документов.  
  
 `documents`  
 окне Буфер, содержащий документы.  
  
## <a name="return-value"></a>Возвращаемое значение  

 S_OK, если метод выполнен. в противном случае — код ошибки.  
  
## <a name="requirements"></a>Требования  

 **Заголовок:** Корсим. idl, Корсим. h  
  
## <a name="see-also"></a>См. также раздел

- [Интерфейс ISymENCUnmanagedMethod](isymencunmanagedmethod-interface.md)
