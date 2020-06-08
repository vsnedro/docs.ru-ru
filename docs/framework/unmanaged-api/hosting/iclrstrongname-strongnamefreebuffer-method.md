---
title: Метод ICLRStrongName::StrongNameFreeBuffer
ms.date: 03/30/2017
api_name:
- ICLRStrongName.StrongNameFreeBuffer
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRStrongName::StrongNameFreeBuffer
helpviewer_keywords:
- StrongNameFreeBuffer method, ICLRStrongName interface [.NET Framework hosting]
- ICLRStrongName::StrongNameFreeBuffer method [.NET Framework hosting]
ms.assetid: 6148c508-bd1d-4a37-85c3-06ecb09cc857
topic_type:
- apiref
ms.openlocfilehash: 7aed3e6877bfcd83754d462cdba81ccc229d002f
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/08/2020
ms.locfileid: "84504008"
---
# <a name="iclrstrongnamestrongnamefreebuffer-method"></a>Метод ICLRStrongName::StrongNameFreeBuffer
Освобождает память, выделенную с помощью предыдущего вызова метода строгого имени, такого как [метод iclrstrongname:: StrongNameGetPublicKey](iclrstrongname-strongnamegetpublickey-method.md), [метод iclrstrongname:: StrongNameTokenFromPublicKey](iclrstrongname-strongnametokenfrompublickey-method.md)или [метод iclrstrongname:: StrongNameSignatureGeneration](iclrstrongname-strongnamesignaturegeneration-method.md).  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
HRESULT StrongNameFreeBuffer (
   [in] BYTE   *pbMemory  
);  
```  
  
## <a name="parameters"></a>Параметры  
 `pbMemory`  
 окне Указатель на память для освобождения.  
  
## <a name="return-value"></a>Возвращаемое значение  
 `S_OK`значение, если метод успешно выполнен; в противном случае — значение HRESULT, указывающее на сбой (см. раздел [Общие значения HRESULT](/windows/win32/seccrypto/common-hresult-values) для списка).  
  
## <a name="requirements"></a>Требования  
 **Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).  
  
 **Заголовок:** Метахост. h  
  
 **Библиотека:** Включается в качестве ресурса в библиотеку MSCorEE. dll  
  
 **.NET Framework версии:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a>См. также

- [Интерфейс ICLRStrongName](iclrstrongname-interface.md)
