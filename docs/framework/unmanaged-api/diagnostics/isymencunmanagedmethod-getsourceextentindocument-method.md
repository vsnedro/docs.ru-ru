---
title: Метод ISymENCUnmanagedMethod::GetSourceExtentInDocument
ms.date: 03/30/2017
api_name:
- ISymENCUnmanagedMethod.GetSourceExtentInDocument
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymENCUnmanagedMethod::GetSourceExtentInDocument
helpviewer_keywords:
- GetSourceExtentInDocument method [.NET Framework debugging]
- ISymENCUnmanagedMethod::GetSourceExtentInDocument method [.NET Framework debugging]
ms.assetid: 9c5566ab-4ec7-4b61-9753-839bb90ae78c
topic_type:
- apiref
ms.openlocfilehash: 2cd362279f5c5ff281b9674fe3d1e293ddbab5f1
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/24/2020
ms.locfileid: "95707299"
---
# <a name="isymencunmanagedmethodgetsourceextentindocument-method"></a>Метод ISymENCUnmanagedMethod::GetSourceExtentInDocument

Возвращает наименьшую начальную строку и самую новую конечную строку для метода в определенном документе.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
HRESULT GetSourceExtentInDocument(  
    [in]  ISymUnmanagedDocument *document,  
    [out] ULONG32* pstartLine,  
    [out] ULONG32* pendLine);  
```  
  
## <a name="parameters"></a>Параметры  

 `document`  
 окне Указатель на документ.  
  
 `pstartLine`  
 заполняет Указатель на объект `ULONG32` , получающий начальную строку.  
  
 `pendLine`  
 заполняет Указатель на объект `ULONG32` , который получает конечную строку.  
  
## <a name="return-value"></a>Возвращаемое значение  

 S_OK, если метод выполнен. в противном случае E_FAIL или другой код ошибки.  
  
## <a name="requirements"></a>Требования  

 **Заголовок:** Корсим. idl, Корсим. h  
  
## <a name="see-also"></a>См. также раздел

- [Интерфейс ISymENCUnmanagedMethod](isymencunmanagedmethod-interface.md)
