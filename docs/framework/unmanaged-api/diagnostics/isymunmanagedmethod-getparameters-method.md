---
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
ms.openlocfilehash: 031e9d9434bc655ba8947a2bb6aba56a150e9002
ms.sourcegitcommit: 27db07ffb26f76912feefba7b884313547410db5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/19/2020
ms.locfileid: "83614465"
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
  
## <a name="see-also"></a>См. также статью

- [Интерфейс ISymUnmanagedMethod](isymunmanagedmethod-interface.md)
