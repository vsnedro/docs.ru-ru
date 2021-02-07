---
description: 'Дополнительные сведения о методе: ISymUnmanagedNamespace:: namespace'
title: Метод ISymUnmanagedNamespace::GetNamespaces
ms.date: 03/30/2017
api_name:
- ISymUnmanagedNamespace.GetNamespaces
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedNamespace::GetNamespaces
helpviewer_keywords:
- ISymUnmanagedNamespace::GetNamespaces method [.NET Framework debugging]
- GetNamespaces method, ISymUnmanagedNamespace interface [.NET Framework debugging]
ms.assetid: 0ea9d9af-8709-4a46-872b-f54d9e840088
topic_type:
- apiref
ms.openlocfilehash: f17b16e2a3a7001d16c86dd6dc95241c1b0785e6
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2021
ms.locfileid: "99709910"
---
# <a name="isymunmanagednamespacegetnamespaces-method"></a>Метод ISymUnmanagedNamespace::GetNamespaces

Возвращает дочерние элементы этого пространства имен.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
HRESULT GetNamespaces(  
    [in]  ULONG32  cNameSpaces,  
    [out] ULONG32  *pcNameSpaces,  
    [out, size_is(cNameSpaces), length_is(*pcNameSpaces)]  
        ISymUnmanagedNamespace* namespaces[]);  
```  
  
## <a name="parameters"></a>Параметры  

 `cNameSpaces`  
 окне Значение типа `ULONG32` , указывающее размер `namespaces` массива.  
  
 `pcNameSpaces`  
 заполняет Указатель на объект `ULONG32` , который получает размер буфера (в символах), необходимого для хранения пространств имен.  
  
 `namespaces`  
 заполняет Указатель на буфер, содержащий пространства имен.  
  
## <a name="return-value"></a>Возвращаемое значение  

 S_OK, если метод выполнен. в противном случае E_FAIL или другой код ошибки.  
  
## <a name="requirements"></a>Требования  

 **Заголовок:** Корсим. idl, Корсим. h  
  
## <a name="see-also"></a>См. также

- [Интерфейс ISymUnmanagedNamespace](isymunmanagednamespace-interface.md)
