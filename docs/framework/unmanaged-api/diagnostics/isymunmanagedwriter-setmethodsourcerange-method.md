---
title: Метод ISymUnmanagedWriter::SetMethodSourceRange
ms.date: 03/30/2017
api_name:
- ISymUnmanagedWriter.SetMethodSourceRange
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedWriter::SetMethodSourceRange
helpviewer_keywords:
- SetMethodSourceRange method [.NET Framework debugging]
- ISymUnmanagedWriter::SetMethodSourceRange method [.NET Framework debugging]
ms.assetid: c698b86e-ace7-4b21-9549-f52d6a034959
topic_type:
- apiref
ms.openlocfilehash: 4ba3f31ae6d6b67d7beaa2f709bf6174b721136d
ms.sourcegitcommit: 27db07ffb26f76912feefba7b884313547410db5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/19/2020
ms.locfileid: "83609525"
---
# <a name="isymunmanagedwritersetmethodsourcerange-method"></a>Метод ISymUnmanagedWriter::SetMethodSourceRange
Указывает истинные начало и конец метода в исходном файле. Этот метод используется для указания экстента метода независимо от точек следования, которые существуют в методе.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
HRESULT SetMethodSourceRange(  
    [in] ISymUnmanagedDocumentWriter  *startDoc,  
    [in] ULONG32                      startLine,  
    [in] ULONG32                      startColumn,  
    [in] ISymUnmanagedDocumentWriter  *endDoc,  
    [in] ULONG32                      endLine,  
    [in] ULONG32                      endColumn);  
```  
  
## <a name="parameters"></a>Параметры  
 `startDoc`  
 окне Указатель на документ, содержащий начальную точку.  
  
 `startLine`  
 окне Номер начальной строки.  
  
 `startColumn`  
 окне Начальный столбец.  
  
 `endDoc`  
 окне Указатель на документ, содержащий конечную точку.  
  
 `endLine`  
 окне Номер конечной строки.  
  
 `endColumn`  
 окне Номер конечного столбца.  
  
## <a name="return-value"></a>Возвращаемое значение  
 S_OK, если метод выполнен. в противном случае E_FAIL или другой код ошибки.  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** Корсим. idl, Корсим. h  
  
## <a name="see-also"></a>Дополнительно

- [Интерфейс ISymUnmanagedWriter](isymunmanagedwriter-interface.md)
