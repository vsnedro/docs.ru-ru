---
description: 'Дополнительные сведения о методе: ISymENCUnmanagedMethod:: GetFileNameFromOffset'
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
ms.openlocfilehash: 1322e55f115958a2f4b2634dfa25eff127167d54
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2021
ms.locfileid: "99738004"
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
  
## <a name="see-also"></a>См. также

- [Интерфейс ISymENCUnmanagedMethod](isymencunmanagedmethod-interface.md)
