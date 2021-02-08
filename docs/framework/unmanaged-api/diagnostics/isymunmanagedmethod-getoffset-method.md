---
description: 'Дополнительные сведения о методе: ISymUnmanagedMethod:: методом offset'
title: Метод ISymUnmanagedMethod::GetOffset
ms.date: 03/30/2017
api_name:
- ISymUnmanagedMethod.GetOffset
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedMethod::GetOffset
helpviewer_keywords:
- GetOffset method, ISymUnmanagedMethod interface [.NET Framework debugging]
- ISymUnmanagedMethod::GetOffset method [.NET Framework debugging]
ms.assetid: 8bf3cb62-89bf-4159-ad53-de606aba89e8
topic_type:
- apiref
ms.openlocfilehash: 3bc7154a47a38fd2cbadc62921f6e57f7901087e
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2021
ms.locfileid: "99790130"
---
# <a name="isymunmanagedmethodgetoffset-method"></a>Метод ISymUnmanagedMethod::GetOffset

Возвращает смещение в этом методе, соответствующее заданной позиции в документе.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
HRESULT GetOffset(  
    [in]  ISymUnmanagedDocument*  document,  
    [in]  ULONG32                 line,  
    [in]  ULONG32                 column,  
    [out, retval] ULONG32*        pRetVal);  
```  
  
## <a name="parameters"></a>Параметры  

 `document`  
 окне Указатель на документ, для которого запрашивается смещение.  
  
 `line`  
 окне Строка документа, для которой запрашивается смещение.  
  
 `column`  
 окне Столбец документа, для которого запрашивается смещение.  
  
 `pRetVal`  
 заполняет Указатель на объект `ULONG32` , который получает смещения.  
  
## <a name="return-value"></a>Возвращаемое значение  

 S_OK, если метод выполнен. в противном случае E_FAIL или другой код ошибки.  
  
## <a name="requirements"></a>Требования  

 **Заголовок:** Корсим. idl, Корсим. h  
  
## <a name="see-also"></a>См. также

- [Интерфейс ISymUnmanagedMethod](isymunmanagedmethod-interface.md)
