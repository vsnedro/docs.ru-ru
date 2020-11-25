---
title: Метод ISymUnmanagedScope::GetChildren
ms.date: 03/30/2017
api_name:
- ISymUnmanagedScope.GetChildren
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedScope::GetChildren
helpviewer_keywords:
- ISymUnmanagedScope::GetChildren method [.NET Framework debugging]
- GetChildren method [.NET Framework debugging]
ms.assetid: 0bed524e-cc48-4bf0-b9fa-25d665e63ddb
topic_type:
- apiref
ms.openlocfilehash: 8f3c83a7a89553ba600f3e0e368eec0ddd0350e9
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/24/2020
ms.locfileid: "95727613"
---
# <a name="isymunmanagedscopegetchildren-method"></a>Метод ISymUnmanagedScope::GetChildren

Возвращает дочерние элементы этой области.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
HRESULT GetChildren(  
    [in]  ULONG32  cChildren,  
    [out] ULONG32  *pcChildren,  
    [out, size_is(cChildren),  
        length_is(*pcChildren)] ISymUnmanagedScope* children[]);  
```  
  
## <a name="parameters"></a>Параметры  

 `cChildren`  
 окне Значение типа `ULONG32` , указывающее размер `children` массива.  
  
 `pcChildren`  
 заполняет Указатель на объект `ULONG32` , который получает размер буфера, необходимого для хранения дочерних элементов.  
  
 `children`  
 заполняет Возвращаемый массив дочерних элементов.  
  
## <a name="return-value"></a>Возвращаемое значение  

 S_OK, если метод выполнен. в противном случае E_FAIL или другой код ошибки.  
  
## <a name="requirements"></a>Требования  

 **Заголовок:** Корсим. idl, Корсим. h  
  
## <a name="see-also"></a>См. также раздел

- [Интерфейс ISymUnmanagedScope](isymunmanagedscope-interface.md)
- [Метод GetParent](isymunmanagedscope-getparent-method.md)
