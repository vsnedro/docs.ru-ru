---
description: 'Дополнительные сведения о методе: ISymUnmanagedReader:: \ Document'
title: Метод ISymUnmanagedReader::GetDocument
ms.date: 03/30/2017
api_name:
- ISymUnmanagedReader.GetDocument
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedReader::GetDocument
helpviewer_keywords:
- ISymUnmanagedReader::GetDocument method [.NET Framework debugging]
- GetDocument method [.NET Framework debugging]
ms.assetid: bb203853-6a6d-4027-b9e9-603a7f28b9d3
topic_type:
- apiref
ms.openlocfilehash: 7f2f31467cfd00de68737224a2c1af5b1e78efed
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2021
ms.locfileid: "99764103"
---
# <a name="isymunmanagedreadergetdocument-method"></a>Метод ISymUnmanagedReader::GetDocument

Находит документ. Язык документа, поставщик и тип являются необязательными.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
HRESULT GetDocument (  
    [in]  WCHAR  *url,  
    [in]  GUID   language,  
    [in]  GUID   languageVendor,  
    [in]  GUID   documentType,  
    [out, retval] ISymUnmanagedDocument** pRetVal);  
```  
  
## <a name="parameters"></a>Параметры  

 `url`  
 окне URL-адрес, определяющий документ.  
  
 `language`  
 окне Язык документа. Этот параметр является необязательным.  
  
 `languageVendor`  
 окне Удостоверение поставщика для языка документа. Этот параметр является необязательным.  
  
 `documentType`  
 окне Тип документа. Этот параметр является необязательным.  
  
 `pRetVal`  
 заполняет Указатель на возвращаемый интерфейс.  
  
## <a name="return-value"></a>Возвращаемое значение  

 S_OK, если метод выполнен. в противном случае E_FAIL или другой код ошибки.  
  
## <a name="requirements"></a>Требования  

 **Заголовок:** Корсим. idl, Корсим. h  
  
## <a name="see-also"></a>См. также

- [Интерфейс ISymUnmanagedReader](isymunmanagedreader-interface.md)
