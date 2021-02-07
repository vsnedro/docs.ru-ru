---
description: 'Дополнительные сведения о методе: ISymUnmanagedWriter:: Сетмесодсаурцеранже'
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
ms.openlocfilehash: 2e2f0f664d8be30a8c3628100fafb3740d34f54f
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2021
ms.locfileid: "99762075"
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
  
## <a name="see-also"></a>См. также

- [Интерфейс ISymUnmanagedWriter](isymunmanagedwriter-interface.md)
