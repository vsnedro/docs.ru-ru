---
description: 'См. Дополнительные сведения о методе ISymUnmanagedMethod:: Range.'
title: Метод ISymUnmanagedMethod::GetRanges
ms.date: 03/30/2017
api_name:
- ISymUnmanagedMethod.GetRanges
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedMethod::GetRanges
helpviewer_keywords:
- ISymUnmanagedMethod::GetRanges method [.NET Framework debugging]
- GetRanges method [.NET Framework debugging]
ms.assetid: a85283d8-379c-417a-9736-ddeeef9bcf50
topic_type:
- apiref
ms.openlocfilehash: e6a1da285c0574ef5910e8e727c3bcc5cb9e5d35
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2021
ms.locfileid: "99790104"
---
# <a name="isymunmanagedmethodgetranges-method"></a>Метод ISymUnmanagedMethod::GetRanges

При наличии позиции в документе возвращает массив пар начального и конечного смещения, соответствующих диапазонам промежуточного языка MSIL, которые находятся в этом методе. Массив является массивом целых чисел и имеет формат [начало, конец, начало, конец]. Число пар диапазонов — это длина массива, деленная на 2.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
HRESULT GetRanges(  
    [in]  ISymUnmanagedDocument* document,  
    [in]  ULONG32                line,  
    [in]  ULONG32                column,  
    [in]  ULONG32                cRanges,  
    [out] ULONG32                *pcRanges,  
    [out, size_is(cRanges),  
        length_is(*pcRanges)] ULONG32 ranges[]);  
```  
  
## <a name="parameters"></a>Параметры  

 `document`  
 окне Документ, для которого запрашивается смещение.  
  
 `line`  
 окне Строка документа, соответствующая диапазонам.  
  
 `column`  
 окне Столбец документа, соответствующий диапазонам.  
  
 `cRanges`  
 [in] Размер массива `ranges`.  
  
 `pcRanges`  
 заполняет Указатель на объект `ULONG32` , который получает размер буфера, необходимого для хранения диапазонов.  
  
 `ranges`  
 заполняет Указатель на буфер, который получает диапазоны.  
  
## <a name="return-value"></a>Возвращаемое значение  

 S_OK, если метод выполнен. в противном случае E_FAIL или другой код ошибки.  
  
## <a name="requirements"></a>Требования  

 **Заголовок:** Корсим. idl, Корсим. h  
  
## <a name="see-also"></a>См. также

- [Интерфейс ISymUnmanagedMethod](isymunmanagedmethod-interface.md)
