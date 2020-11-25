---
title: Метод ISymUnmanagedMethod::GetSourceStartEnd
ms.date: 03/30/2017
api_name:
- ISymUnmanagedMethod.GetSourceStartEnd
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedMethod::GetSourceStartEnd
helpviewer_keywords:
- GetSourceStartEnd method [.NET Framework debugging]
- ISymUnmanagedMethod::GetSourceStartEnd method [.NET Framework debugging]
ms.assetid: 2a420900-01f1-4461-8777-3a34a6dc1426
topic_type:
- apiref
ms.openlocfilehash: f53afa5f87f1502f287b25e3d9756f9a54ad6869
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/24/2020
ms.locfileid: "95699291"
---
# <a name="isymunmanagedmethodgetsourcestartend-method"></a>Метод ISymUnmanagedMethod::GetSourceStartEnd

Возвращает начальную и конечную позиции документа для источника данного метода. Первой позицией массива является начало, а вторая — конец.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
HRESULT GetSourceStartEnd(  
    [in]  ISymUnmanagedDocument  *docs[2],  
    [in]  ULONG32                lines[2],  
    [in]  ULONG32                columns[2],  
    [out] BOOL                   *pRetVal);  
```  
  
## <a name="parameters"></a>Параметры  

 `docs`  
 окне Начальный и конечный документы источника.  
  
 `lines`  
 окне Начальная и конечная строки соответствующих исходных документов.  
  
 `columns`  
 окне Начальные и конечные столбцы в соответствующих исходных документах.  
  
 `pRetVal`  
 [out] `true` значение, если позиции определены; в противном случае — `false` .  
  
## <a name="return-value"></a>Возвращаемое значение  

 S_OK, если метод выполнен. в противном случае E_FAIL или другой код ошибки.  
  
## <a name="requirements"></a>Требования  

 **Заголовок:** Корсим. idl, Корсим. h  
  
## <a name="see-also"></a>См. также раздел

- [Интерфейс ISymUnmanagedMethod](isymunmanagedmethod-interface.md)
