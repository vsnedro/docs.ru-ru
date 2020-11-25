---
title: Метод ISymUnmanagedReader::GetDocumentVersion
ms.date: 03/30/2017
api_name:
- ISymUnmanagedReader.GetDocumentVersion
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedReader::GetDocumentVersion
helpviewer_keywords:
- GetDocumentVersion method [.NET Framework debugging]
- ISymUnmanagedReader::GetDocumentVersion method [.NET Framework debugging]
ms.assetid: a51f1f64-e084-44c5-830c-2222da5a6bbf
topic_type:
- apiref
ms.openlocfilehash: fc38c167b47ea72c7bc7ad81074f9cb1a0d217d8
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/24/2020
ms.locfileid: "95707572"
---
# <a name="isymunmanagedreadergetdocumentversion-method"></a>Метод ISymUnmanagedReader::GetDocumentVersion

Возвращает указанную версию указанного документа. Версия документа начинается с 1 и увеличивается каждый раз при обновлении документа с помощью метода [UpdateSymbolStore](isymunmanagedreader-updatesymbolstore-method.md) . Если `pbCurrent` параметр имеет значение `true` , это последняя версия документа.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
HRESULT GetDocumentVersion (  
    [in]  ISymUnmanagedDocument *pDoc,  
    [out] int* version,  
    [out] BOOL* pbCurrent);  
```  
  
## <a name="parameters"></a>Параметры  

 `pDoc`  
 окне Указанный документ.  
  
 `version`  
 заполняет Указатель на переменную, которая получает версию указанного документа.  
  
 `pbCurrent`  
 заполняет Указатель на переменную, которая получает, `true` если это последняя версия документа, или `false` если это не последняя версия.  
  
## <a name="return-value"></a>Возвращаемое значение  

 S_OK, если метод выполнен. в противном случае E_FAIL или другой код ошибки.  
  
## <a name="requirements"></a>Требования  

 **Заголовок:** Корсим. idl, Корсим. h  
  
## <a name="see-also"></a>См. также раздел

- [Интерфейс ISymUnmanagedReader](isymunmanagedreader-interface.md)
