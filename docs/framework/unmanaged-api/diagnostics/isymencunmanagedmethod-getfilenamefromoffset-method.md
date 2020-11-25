---
title: Метод ISymENCUnmanagedMethod::GetFileNameFromOffset
ms.date: 03/30/2017
api_name:
- ISymENCUnmanagedMethod.GetFileNameFromOffset
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymENCUnmanagedMethod::GetFileNameFromOffset
helpviewer_keywords:
- GetFileNameFromOffset method [.NET Framework debugging]
- ISymENCUnmanagedMethod::GetFileNameFromOffset method [.NET Framework debugging]
ms.assetid: 00e2e194-12f5-436e-a997-2b9d3e844d4f
topic_type:
- apiref
ms.openlocfilehash: ad9631039c8d032e7ffdba1e6098b66398f82277
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/24/2020
ms.locfileid: "95707390"
---
# <a name="isymencunmanagedmethodgetfilenamefromoffset-method"></a>Метод ISymENCUnmanagedMethod::GetFileNameFromOffset

Возвращает имя файла для строки, связанной со смещением.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
HRESULT GetFileNameFromOffset(  
    [in]  ULONG32  dwOffset,  
    [in]  ULONG32  cchName,  
    [out] ULONG32  *pcchName,  
    [out, size_is(cchName),  
       length_is(*pcchName)] WCHAR szName[]);  
```  
  
## <a name="parameters"></a>Параметры  

 `dwOffset`  
 окне Значение типа `ULONG32` , содержащее смещение.  
  
 `cchName`  
 окне Значение типа `ULONG32` , указывающее размер `szName` буфера.  
  
 `pcchName`  
 заполняет Указатель на объект `ULONG32` , который получает размер (в символах) буфера, необходимого для хранения имен файлов.  
  
 `szName`  
 заполняет Буфер, содержащий имена файлов.  
  
## <a name="return-value"></a>Возвращаемое значение  

 S_OK, если метод выполнен. в противном случае E_FAIL или другой код ошибки.  
  
## <a name="requirements"></a>Требования  

 **Заголовок:** Корсим. idl, Корсим. h  
  
## <a name="see-also"></a>См. также раздел

- [Интерфейс ISymENCUnmanagedMethod](isymencunmanagedmethod-interface.md)
