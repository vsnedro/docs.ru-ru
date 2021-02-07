---
description: 'Дополнительные сведения о методе: ISymENCUnmanagedMethod:: Жетдокументсформесод'
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
ms.openlocfilehash: 01c7280abe437266618d96c6e195e61a4f830131
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2021
ms.locfileid: "99721545"
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
  
## <a name="see-also"></a>См. также

- [Интерфейс ISymENCUnmanagedMethod](isymencunmanagedmethod-interface.md)
