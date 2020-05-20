---
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
ms.openlocfilehash: 950fb3b9c51ae2c9470b5aadd31c877d7aa6b6f6
ms.sourcegitcommit: 27db07ffb26f76912feefba7b884313547410db5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/19/2020
ms.locfileid: "83615063"
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
 окне Язык документа. Этот параметр необязателен.  
  
 `languageVendor`  
 окне Удостоверение поставщика для языка документа. Этот параметр необязателен.  
  
 `documentType`  
 окне Тип документа. Этот параметр необязателен.  
  
 `pRetVal`  
 заполняет Указатель на возвращаемый интерфейс.  
  
## <a name="return-value"></a>Возвращаемое значение  
 S_OK, если метод выполнен. в противном случае E_FAIL или другой код ошибки.  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** Корсим. idl, Корсим. h  
  
## <a name="see-also"></a>Дополнительно

- [Интерфейс ISymUnmanagedReader](isymunmanagedreader-interface.md)
