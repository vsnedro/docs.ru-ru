---
description: 'Дополнительные сведения о методе: ISymENCUnmanagedMethod:: GetLineFromOffset'
title: Метод ISymENCUnmanagedMethod::GetLineFromOffset
ms.date: 03/30/2017
api_name:
- ISymENCUnmanagedMethod.GetLineFromOffset
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymENCUnmanagedMethod::GetLineFromOffset
helpviewer_keywords:
- GetLineFromOffset method [.NET Framework debugging]
- ISymENCUnmanagedMethod::GetLineFromOffset method [.NET Framework debugging]
ms.assetid: cc09bad2-fb34-4d13-a521-6ec7b1a1d915
topic_type:
- apiref
ms.openlocfilehash: 18fe942b509340c89a4c3044e02bf8e9d952f91d
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2021
ms.locfileid: "99737965"
---
# <a name="isymencunmanagedmethodgetlinefromoffset-method"></a>Метод ISymENCUnmanagedMethod::GetLineFromOffset

Возвращает сведения о строке, связанные со смещением. Если параметр offset ( `dwOffset` ) не является точкой последовательности, этот метод получает сведения о строке, связанные с предыдущим смещением.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
HRESULT GetLineFromOffset(  
     [in]  ULONG32   dwOffset,  
     [out] ULONG32*  pline,  
     [out] ULONG32*  pcolumn,  
     [out] ULONG32*  pendLine,  
     [out] ULONG32*  pendColumn,  
     [out] ULONG32*  pdwStartOffset);  
```  
  
## <a name="parameters"></a>Параметры  

 `dwOffset`  
 окне Значение типа `ULONG32` , содержащее смещение.  
  
 `pline`  
 заполняет Указатель на объект `ULONG32` , получающий строку.  
  
 `pcolumn`  
 заполняет Указатель на объект `ULONG32` , который получает столбец.  
  
 `pendLine`  
 заполняет Указатель на объект `ULONG32` , который получает конечную строку.  
  
 `pendColumn`  
 заполняет Указатель на объект `ULONG32` , который получает конечный столбец.  
  
 `pdwStartOffset`  
 заполняет Указатель на объект `ULONG32` , который получает связанную точку последовательности.  
  
## <a name="return-value"></a>Возвращаемое значение  

 S_OK, если метод выполнен. в противном случае E_FAIL или другой код ошибки.  
  
## <a name="requirements"></a>Требования  

 **Заголовок:** Корсим. idl, Корсим. h  
  
## <a name="see-also"></a>См. также

- [Интерфейс ISymENCUnmanagedMethod](isymencunmanagedmethod-interface.md)
