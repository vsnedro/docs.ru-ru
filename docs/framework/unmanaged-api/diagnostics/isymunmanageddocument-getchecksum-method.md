---
title: Метод ISymUnmanagedDocument::GetCheckSum
ms.date: 03/30/2017
api_name:
- ISymUnmanagedDocument.GetCheckSum
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedDocument::GetCheckSum
helpviewer_keywords:
- ISymUnmanagedDocument::GetCheckSum method [.NET Framework debugging]
- GetCheckSum method [.NET Framework debugging]
ms.assetid: 9bc881b3-e2ce-48a7-ad69-17eaaa304120
topic_type:
- apiref
ms.openlocfilehash: 4030da31400b7075952d146e5d6740306863e9ad
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/24/2020
ms.locfileid: "95721092"
---
# <a name="isymunmanageddocumentgetchecksum-method"></a>Метод ISymUnmanagedDocument::GetCheckSum

Возвращает контрольную сумму.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
HRESULT GetCheckSum(  
    [in]  ULONG32  cData,  
    [out] ULONG32  *pcData,  
    [out, size_is(cData), length_is(*pcData)] BYTE data[]);  
```  
  
## <a name="parameters"></a>Параметры  

 `cData`  
 окне Длина буфера, предоставленного `data` параметром  
  
 `pcData`  
 заполняет Размер и длина контрольной суммы в байтах.  
  
 `data`  
 заполняет Буфер, получающий контрольную сумму.  
  
## <a name="return-value"></a>Возвращаемое значение  

 S_OK, если метод выполнен. в противном случае — код ошибки.  
  
## <a name="see-also"></a>См. также раздел

- [Интерфейс ISymUnmanagedDocument](isymunmanageddocument-interface.md)
