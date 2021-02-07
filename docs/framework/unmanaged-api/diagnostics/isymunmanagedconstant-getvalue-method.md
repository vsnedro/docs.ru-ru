---
description: 'Дополнительные сведения о методе: ISymUnmanagedConstant:: GetValue'
title: Метод ISymUnmanagedConstant::GetValue
ms.date: 03/30/2017
api_name:
- ISymUnmanagedConstant.GetValue
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedConstant::GetValue
helpviewer_keywords:
- GetValue method, ISymUnmanagedConstant interface [.NET Framework debugging]
- ISymUnmanagedConstant::GetValue method [.NET Framework debugging]
ms.assetid: 0036fc10-e768-47a8-b9cf-bf47faf8d194
topic_type:
- apiref
ms.openlocfilehash: 05818028deb804bf2a2426285b5185b01776199d
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2021
ms.locfileid: "99689694"
---
# <a name="isymunmanagedconstantgetvalue-method"></a>Метод ISymUnmanagedConstant::GetValue

 Возвращает значение константы.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
HRESULT GetValue(  
    [out]  VARIANT* pValue  
);  
```  
  
## <a name="parameters"></a>Параметры  

 `pValue`  
 заполняет Указатель на переменную, которая получает значение.  
  
## <a name="return-value"></a>Возвращаемое значение  

 S_OK, если метод выполнен. в противном случае E_FAIL или другой код ошибки.  
  
## <a name="requirements"></a>Требования  

 **Заголовок:** Корсим. idl, Корсим. h  
  
## <a name="see-also"></a>См. также

- [Интерфейс ISymUnmanagedConstant](isymunmanagedconstant-interface.md)
- [Метод GetName](isymunmanagedconstant-getname-method.md)
- [Метод GetSignature](isymunmanagedconstant-getsignature-method.md)
