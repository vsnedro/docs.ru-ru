---
description: 'Дополнительные сведения о методе: ISymENCUnmanagedMethod:: GetDocumentsForMethodCount'
title: Метод ISymENCUnmanagedMethod::GetDocumentsForMethodCount
ms.date: 03/30/2017
api_name:
- ISymENCUnmanagedMethod.GetDocumentsForMethodCount
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymENCUnmanagedMethod::GetDocumentsForMethodCount
helpviewer_keywords:
- GetDocumentsForMethodCount method [.NET Framework debugging]
- ISymENCUnmanagedMethod::GetDocumentsForMethodCount method [.NET Framework debugging]
ms.assetid: cc1a823a-3ff3-4a33-b641-96edc93d2b17
topic_type:
- apiref
ms.openlocfilehash: 0594771c544ad1de32531e92f30fe96f245b5699
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2021
ms.locfileid: "99738017"
---
# <a name="isymencunmanagedmethodgetdocumentsformethodcount-method"></a>Метод ISymENCUnmanagedMethod::GetDocumentsForMethodCount

Возвращает число документов, в которых у этого метода есть строки.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
HRESULT GetDocumentsForMethodCount(  
    [out, retval] ULONG32* pRetVal);  
```  
  
## <a name="parameters"></a>Параметры  

 `pRetVal`  
 заполняет Указатель на объект `ULONG32` , который получает размер буфера, необходимого для хранения документов.  
  
## <a name="return-value"></a>Возвращаемое значение  

 S_OK, если метод выполнен. в противном случае E_FAIL или другой код ошибки.  
  
## <a name="requirements"></a>Требования  

 **Заголовок:** Корсим. idl, Корсим. h  
  
## <a name="see-also"></a>См. также

- [Интерфейс ISymENCUnmanagedMethod](isymencunmanagedmethod-interface.md)
