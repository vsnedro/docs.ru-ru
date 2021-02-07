---
description: 'См. Дополнительные сведения о методе ISymUnmanagedMethod:: методом with Token'
title: Метод ISymUnmanagedMethod::GetToken
ms.date: 03/30/2017
api_name:
- ISymUnmanagedMethod.GetToken
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedMethod::GetToken
helpviewer_keywords:
- ISymUnmanagedMethod::GetToken method [.NET Framework debugging]
- GetToken method, ISymUnmanagedMethod interface [.NET Framework debugging]
ms.assetid: 4effbe95-c36e-4a45-8b2a-ee21339415fb
topic_type:
- apiref
ms.openlocfilehash: fde9936a6e79b9d1fff5b38ee7242cf5bb71369d
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2021
ms.locfileid: "99721311"
---
# <a name="isymunmanagedmethodgettoken-method"></a>Метод ISymUnmanagedMethod::GetToken

Возвращает маркер метаданных для данного метода.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
HRESULT GetToken(  
   [out, retval]  mdMethodDef  *pToken);  
```  
  
## <a name="parameters"></a>Параметры  

 `pToken`  
 заполняет Указатель на объект `mdMethodDef` , который получает размер буфера (в символах), необходимого для хранения метаданных.  
  
## <a name="return-value"></a>Возвращаемое значение  

 S_OK, если метод выполнен. в противном случае E_FAIL или другой код ошибки.  
  
## <a name="requirements"></a>Требования  

 **Заголовок:** Корсим. idl, Корсим. h  
  
## <a name="see-also"></a>См. также

- [Интерфейс ISymUnmanagedMethod](isymunmanagedmethod-interface.md)
