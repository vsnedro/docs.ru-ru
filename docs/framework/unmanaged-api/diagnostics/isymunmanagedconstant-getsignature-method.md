---
description: 'Дополнительные сведения о методе: ISymUnmanagedConstant:: Signature'
title: Метод ISymUnmanagedConstant::GetSignature
ms.date: 03/30/2017
api_name:
- ISymUnmanagedConstant.GetSignature
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedConstant::GetSignature
helpviewer_keywords:
- GetSignature method, ISymUnmanagedConstant interface [.NET Framework debugging]
- ISymUnmanagedConstant::GetSignature method [.NET Framework debugging]
ms.assetid: 3eb41151-a228-43e3-ba8f-e6dd3ceb8542
topic_type:
- apiref
ms.openlocfilehash: d28051c9d0e2675e980926fe63ffa7c4d13ef13a
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2021
ms.locfileid: "99689798"
---
# <a name="isymunmanagedconstantgetsignature-method"></a>Метод ISymUnmanagedConstant::GetSignature

Возвращает сигнатуру константы.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
HRESULT GetSignature(  
    [in]  ULONG32  cSig,  
    [out] ULONG32  *pcSig,  
    [out, size_is(cSig),  
        length_is(*pcSig)] BYTE sig[]);  
```  
  
## <a name="parameters"></a>Параметры  

 `cSig`  
 окне Длина буфера, `pcSig` на который указывает параметр.  
  
 `pcSig`  
 заполняет Указатель на объект `ULONG32` , который получает размер (в символах) буфера, необходимого для хранения подписи.  
  
 `sig`  
 заполняет Буфер, в котором хранится подпись.  
  
## <a name="return-value"></a>Возвращаемое значение  

 S_OK, если метод выполнен. в противном случае E_FAIL или другой код ошибки.  
  
## <a name="requirements"></a>Требования  

 **Заголовок:** Корсим. idl, Корсим. h  
  
## <a name="see-also"></a>См. также

- [Интерфейс ISymUnmanagedConstant](isymunmanagedconstant-interface.md)
- [Метод GetName](isymunmanagedconstant-getname-method.md)
- [Метод GetValue](isymunmanagedconstant-getvalue-method.md)
