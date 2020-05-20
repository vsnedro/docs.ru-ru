---
title: Метод ISymUnmanagedVariable::GetAddressField2
ms.date: 03/30/2017
api_name:
- ISymUnmanagedVariable.GetAddressField2
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedVariable::GetAddressField2
helpviewer_keywords:
- GetAddressField2 method [.NET Framework debugging]
- ISymUnmanagedVariable::GetAddressField2 method [.NET Framework debugging]
ms.assetid: 1f25b294-72b6-4882-a49b-6c9d364b6008
topic_type:
- apiref
ms.openlocfilehash: 6256d052780b1c610e61267be2517954d722a42d
ms.sourcegitcommit: 27db07ffb26f76912feefba7b884313547410db5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/19/2020
ms.locfileid: "83610604"
---
# <a name="isymunmanagedvariablegetaddressfield2-method"></a>Метод ISymUnmanagedVariable::GetAddressField2
Получает второе поле адреса для этой переменной. Его значение зависит от типа адреса.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
HRESULT GetAddressField2(  
    [out, retval] ULONG32* pRetVal);  
```  
  
## <a name="parameters"></a>Параметры  
 `pRetVal`  
 заполняет Указатель на объект `ULONG32` , который получает второе поле адреса.  
  
## <a name="return-value"></a>Возвращаемое значение  
 S_OK, если метод выполнен. в противном случае E_FAIL или другой код ошибки.  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** Корсим. idl, Корсим. h  
  
## <a name="see-also"></a>Дополнительно

- [Интерфейс ISymUnmanagedVariable](isymunmanagedvariable-interface.md)
- [Метод GetAddressField1](isymunmanagedvariable-getaddressfield1-method.md)
- [Метод GetAddressField3](isymunmanagedvariable-getaddressfield3-method.md)
- [Метод GetAddressKind](isymunmanagedvariable-getaddresskind-method.md)
