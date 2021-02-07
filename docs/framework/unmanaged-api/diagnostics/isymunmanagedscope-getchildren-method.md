---
description: 'Дополнительные сведения о методе: Исимунманажедскопе:: Children'
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
ms.openlocfilehash: 55d72c98d34fcb30a479611895228fbc1b9f7f55
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2021
ms.locfileid: "99763505"
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
  
## <a name="see-also"></a>См. также

- [Интерфейс ISymUnmanagedScope](isymunmanagedscope-interface.md)
- [Метод GetParent](isymunmanagedscope-getparent-method.md)
