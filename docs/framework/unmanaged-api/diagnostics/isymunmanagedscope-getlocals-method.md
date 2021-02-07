---
description: 'Дополнительные сведения о методе Исимунманажедскопе:: Localization.'
title: Метод ISymUnmanagedScope::GetLocals
ms.date: 03/30/2017
api_name:
- ISymUnmanagedScope.GetLocals
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedScope::GetLocals
helpviewer_keywords:
- GetLocals method [.NET Framework debugging]
- ISymUnmanagedScope::GetLocals method [.NET Framework debugging]
ms.assetid: 17c45f15-8c44-44da-b070-f902077b36e4
topic_type:
- apiref
ms.openlocfilehash: 6b20d8a79e826be0bd191d46e794f8dad45c4810
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2021
ms.locfileid: "99763414"
---
# <a name="isymunmanagedscopegetlocals-method"></a>Метод ISymUnmanagedScope::GetLocals

Возвращает локальные переменные, определенные в этой области.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
HRESULT GetLocals(  
    [in]  ULONG32  cLocals,  
    [out] ULONG32  *pcLocals,  
    [out, size_is(cLocals),  
        length_is(*pcLocals)] ISymUnmanagedVariable* locals[]);  
```  
  
## <a name="parameters"></a>Параметры  

 `cLocals`  
 окне Значение типа `ULONG32` , указывающее размер `locals` массива.  
  
 `pcLocals`  
 заполняет Указатель на объект `ULONG32` , который получает размер буфера, необходимого для хранения локальных переменных.  
  
 `locals`  
 заполняет Массив, который получает локальные переменные.  
  
## <a name="return-value"></a>Возвращаемое значение  

 S_OK, если метод выполнен. в противном случае E_FAIL или другой код ошибки.  
  
## <a name="requirements"></a>Требования  

 **Заголовок:** Корсим. idl, Корсим. h  
  
## <a name="see-also"></a>См. также

- [Интерфейс ISymUnmanagedScope](isymunmanagedscope-interface.md)
