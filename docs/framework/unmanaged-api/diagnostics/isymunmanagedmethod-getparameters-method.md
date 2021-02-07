---
description: 'Дополнительные сведения о методе: ISymUnmanagedMethod:: Parameters'
title: Метод ISymUnmanagedMethod::GetParameters
ms.date: 03/30/2017
api_name:
- ISymUnmanagedMethod.GetParameters
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedMethod::GetParameters
helpviewer_keywords:
- ISymUnmanagedMethod::GetParameters method [.NET Framework debugging]
- GetParameters method [.NET Framework debugging]
ms.assetid: 3a8074f1-facc-4a3f-bb9b-d6574fc2fc74
topic_type:
- apiref
ms.openlocfilehash: c8860a4d42019aaacef01879b175fd45ea837f2b
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2021
ms.locfileid: "99721376"
---
# <a name="isymunmanagedmethodgetparameters-method"></a>Метод ISymUnmanagedMethod::GetParameters

Возвращает параметры для этого метода. Параметры возвращаются в том порядке, в котором они определены в сигнатуре метода.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
HRESULT GetParameters(  
    [in]  ULONG32  cParams,  
    [out] ULONG32  *pcParams,  
    [out, size_is(cParams),  
        length_is(*pcParams)] ISymUnmanagedVariable*  params[]);  
```  
  
## <a name="parameters"></a>Параметры  

 `cParams`  
 [in] Размер массива `params`.  
  
 `pcParams`  
 окне Указатель на объект `ULONG32` , который получает размер буфера, который требуется для хранения параметров.  
  
 `params`  
 заполняет Указатель на буфер, который получает параметры.  
  
## <a name="return-value"></a>Возвращаемое значение  

 S_OK, если метод выполнен. в противном случае E_FAIL или другой код ошибки.  
  
## <a name="requirements"></a>Требования  

 **Заголовок:** Корсим. idl, Корсим. h  
  
## <a name="see-also"></a>См. также

- [Интерфейс ISymUnmanagedMethod](isymunmanagedmethod-interface.md)
