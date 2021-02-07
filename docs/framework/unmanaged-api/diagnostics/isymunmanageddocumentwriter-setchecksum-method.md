---
description: 'Дополнительные сведения о методе: ISymUnmanagedDocumentWriter:: Сетчекксум'
title: Метод ISymUnmanagedDocumentWriter::SetCheckSum
ms.date: 03/30/2017
api_name:
- ISymUnmanagedDocumentWriter.SetCheckSum
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedDocumentWriter::SetCheckSum
helpviewer_keywords:
- ISymUnmanagedDocumentWriter::SetCheckSum method [.NET Framework debugging]
- SetCheckSum method [.NET Framework debugging]
ms.assetid: c7e99879-421f-43ce-b193-34733cf30085
topic_type:
- apiref
ms.openlocfilehash: ac2ba9654f3610dca333cf0e06c20696cf31bd1f
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2021
ms.locfileid: "99710092"
---
# <a name="isymunmanageddocumentwritersetchecksum-method"></a>Метод ISymUnmanagedDocumentWriter::SetCheckSum

Задает сведения о контрольной сумме.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
HRESULT SetCheckSum(  
    [in]  GUID     algorithmId,  
    [in]  ULONG32  checkSumSize,  
    [in, size_is(checkSumSize)]  BYTE checkSum[]);  
```  
  
## <a name="parameters"></a>Параметры  

 `algorithmId`  
 окне Идентификатор GUID, представляющий идентификатор алгоритма.  
  
 `checkSumSize`  
 окне Значение типа `ULONG32` , указывающее размер буфера (в байтах) `checkSum` .  
  
 `checkSum`  
 окне Буфер, в котором хранятся сведения о контрольной сумме.  
  
## <a name="return-value"></a>Возвращаемое значение  

 S_OK, если метод выполнен. в противном случае E_FAIL или другой код ошибки.  
  
## <a name="requirements"></a>Требования  

 **Заголовок:** Корсим. idl, Корсим. h  
  
## <a name="see-also"></a>См. также

- [Интерфейс ISymUnmanagedDocumentWriter](isymunmanageddocumentwriter-interface.md)
