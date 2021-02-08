---
description: 'Дополнительные сведения о методе: ISymUnmanagedDispose::D естрой'
title: Метод ISymUnmanagedDispose::Destroy
ms.date: 03/30/2017
api_name:
- ISymUnmanagedDispose.Destroy
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedDispose::Destroy
helpviewer_keywords:
- ISymUnmanagedDispose::Destroy method [.NET Framework debugging]
- Destroy method [.NET Framework debugging]
ms.assetid: a854ab9f-d2ba-470e-867f-808c1e7bd07a
topic_type:
- apiref
ms.openlocfilehash: 3c13f90e08f2ba0dd7c70acc3321913b14195f1c
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2021
ms.locfileid: "99790208"
---
# <a name="isymunmanageddisposedestroy-method"></a>Метод ISymUnmanagedDispose::Destroy

Заставляет базовый объект освобождать все внутренние ссылки и возвращать ошибку при любом последующем вызове метода.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
HRESULT Destroy();  
```  
  
## <a name="return-value"></a>Возвращаемое значение  

 S_OK, если метод выполнен. в противном случае E_FAIL или другой код ошибки.  
  
## <a name="requirements"></a>Требования  

 **Заголовок:** Корсим. idl, Корсим. h  
  
## <a name="see-also"></a>См. также

- [Интерфейс ISymUnmanagedDispose](isymunmanageddispose-interface.md)
