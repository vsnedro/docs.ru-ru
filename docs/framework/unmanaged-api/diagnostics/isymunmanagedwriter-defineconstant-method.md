---
description: 'Дополнительные сведения о методе: ISymUnmanagedWriter::D Ефинеконстант'
title: Метод ISymUnmanagedWriter::DefineConstant
ms.date: 03/30/2017
api_name:
- ISymUnmanagedWriter.DefineConstant
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedWriter::DefineConstant
helpviewer_keywords:
- DefineConstant method [.NET Framework debugging]
- ISymUnmanagedWriter::DefineConstant method [.NET Framework debugging]
ms.assetid: 9e986986-2223-4d5f-b040-85d716146924
topic_type:
- apiref
ms.openlocfilehash: 4c3fd3986d42061272406150422f037236c4b9bf
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2021
ms.locfileid: "99762530"
---
# <a name="isymunmanagedwriterdefineconstant-method"></a>Метод ISymUnmanagedWriter::DefineConstant

Определяет имя для постоянного значения.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
HRESULT DefineConstant(  
    [in] const WCHAR *name,  
    [in] VARIANT value,  
    [in] ULONG32 cSig,  
    [in, size_is(cSig)] unsigned char signature[]);  
```  
  
## <a name="parameters"></a>Параметры  

 `name`  
 окне Указатель на объект `WCHAR` , который определяет имя константы.  
  
 `value`  
 окне Значение константы.  
  
 `cSig`  
 [in] Размер массива `signature`.  
  
 `signature`  
 окне Сигнатура типа для константы.  
  
## <a name="return-value"></a>Возвращаемое значение  

 S_OK, если метод выполнен. в противном случае E_FAIL или другой код ошибки.  
  
## <a name="requirements"></a>Требования  

 **Заголовок:** Корсим. idl, Корсим. h  
  
## <a name="see-also"></a>См. также

- [Интерфейс ISymUnmanagedWriter](isymunmanagedwriter-interface.md)
- [Метод DefineConstant2](isymunmanagedwriter2-defineconstant2-method.md)
