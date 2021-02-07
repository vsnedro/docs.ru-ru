---
description: 'Дополнительные сведения о методе: ISymUnmanagedReader2:: Жетмесодсиндокумент'
title: Метод ISymUnmanagedReader2::GetMethodsInDocument
ms.date: 03/30/2017
api_name:
- ISymUnmanagedReader2.GetMethodsInDocument
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedReader2::GetMethodsInDocument
helpviewer_keywords:
- ISymUnmanagedReader2::GetMethodsInDocument method [.NET Framework debugging]
- GetMethodsInDocument method [.NET Framework debugging]
ms.assetid: c7ae84d6-81e8-4cb7-a1f9-d48b6cde5d79
topic_type:
- apiref
ms.openlocfilehash: 1f75594a479edbf2e0160c9d3543384c0cbf68a0
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2021
ms.locfileid: "99763687"
---
# <a name="isymunmanagedreader2getmethodsindocument-method"></a>Метод ISymUnmanagedReader2::GetMethodsInDocument

Возвращает каждый метод, имеющий сведения о строке в указанном документе.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
HRESULT GetMethodsInDocument(  
    [in]  ISymUnmanagedDocument *document,  
    [in]  ULONG32 cMethod,  
    [out] ULONG32* pcMethod,  
    [out, size_is(cMethod),  
        length_is(*pcMethod)] ISymUnmanagedMethod* pRetVal[]);  
```  
  
## <a name="parameters"></a>Параметры  

 `document`  
 окне Указатель на документ.  
  
 `cMethod`  
 окне Значение типа `ULONG32` , указывающее размер  `pRetVal` массива.  
  
 `pcMethod`  
 заполняет Указатель на объект `ULONG32` , который получает размер буфера, необходимого для хранения методов.  
  
 `pRetVal`  
 заполняет Указатель на буфер, который получает методы.  
  
## <a name="return-value"></a>Возвращаемое значение  

 S_OK, если метод выполнен. в противном случае E_FAIL или другой код ошибки.  
  
## <a name="requirements"></a>Требования  

 **Заголовок:** Корсим. idl, Корсим. h  
  
## <a name="see-also"></a>См. также

- [Интерфейс ISymUnmanagedReader2](isymunmanagedreader2-interface.md)
