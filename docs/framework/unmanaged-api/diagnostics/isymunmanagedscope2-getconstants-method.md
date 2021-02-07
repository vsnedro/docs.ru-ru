---
description: "Дополнительные сведения: метод ISymUnmanagedScope2:: ' Constant '"
title: Метод ISymUnmanagedScope2::GetConstants
ms.date: 03/30/2017
api_name:
- ISymUnmanagedScope2.GetConstants
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedScope2::GetConstants
helpviewer_keywords:
- ISymUnmanagedScope2::GetConstants method [.NET Framework debugging]
- GetConstants method [.NET Framework debugging]
ms.assetid: f241b620-9ec5-42fd-92ef-3b22329db72a
topic_type:
- apiref
ms.openlocfilehash: 025bb9ddd0501f2309b2c0a3f7af20eb961604cb
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2021
ms.locfileid: "99763219"
---
# <a name="isymunmanagedscope2getconstants-method"></a>Метод ISymUnmanagedScope2::GetConstants

Возвращает локальные константы, определенные в этой области.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
HRESULT GetConstants(  
     [in]  ULONG32  cConstants,  
     [out] ULONG32  *pcConstants,  
     [out, size_is(cConstants),  
         length_is(*pcConstants)] ISymUnmanagedConstant*
             constants[]);  
```  
  
## <a name="parameters"></a>Параметры  

 `cConstants`  
 окне Длина буфера, `pcConstants` на который указывает параметр.  
  
 `pcConstants`  
 заполняет Указатель на объект `ULONG32` , который получает размер буфера (в символах), необходимого для хранения констант.  
  
 `constants`  
 заполняет Буфер, в котором хранятся константы.  
  
## <a name="return-value"></a>Возвращаемое значение  

 S_OK, если метод выполнен. в противном случае E_FAIL или другой код ошибки.  
  
## <a name="requirements"></a>Требования  

 **Заголовок:** Корсим. idl, Корсим. h  
  
## <a name="see-also"></a>См. также

- [Интерфейс ISymUnmanagedScope2](isymunmanagedscope2-interface.md)
