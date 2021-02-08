---
description: 'Дополнительные сведения: метод ISymUnmanagedReader:: WebMethod'
title: Метод ISymUnmanagedReader::GetDocuments
ms.date: 03/30/2017
api_name:
- ISymUnmanagedReader.GetDocuments
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedReader::GetDocuments
helpviewer_keywords:
- GetDocuments method [.NET Framework debugging]
- ISymUnmanagedReader::GetDocuments method [.NET Framework debugging]
ms.assetid: e3b73a3f-d089-4101-a9a9-5e0765d05b61
topic_type:
- apiref
ms.openlocfilehash: 8ee2a2d8e83fcbe2f5b39960fa99e11de2ab4cd2
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2021
ms.locfileid: "99800218"
---
# <a name="isymunmanagedreadergetdocuments-method"></a>Метод ISymUnmanagedReader::GetDocuments

Возвращает массив всех документов, определенных в хранилище символов.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
HRESULT GetDocuments (  
    [in]  ULONG32  cDocs,  
    [out] ULONG32  *pcDocs,  
    [out, size_is (cDocs),  
        length_is (*pcDocs)] ISymUnmanagedDocument *pDocs[]);  
```  
  
## <a name="parameters"></a>Параметры  

 `cDocs`  
 [in] Размер массива `pDocs`.  
  
 `pcDocs`  
 заполняет Указатель на переменную, которая получает длину массива.  
  
 `pDocs`  
 заполняет Указатель на переменную, которая получает массив документов.  
  
## <a name="return-value"></a>Возвращаемое значение  

 S_OK, если метод выполнен. в противном случае E_FAIL или другой код ошибки.  
  
## <a name="requirements"></a>Требования  

 **Заголовок:** Корсим. idl, Корсим. h  
  
## <a name="see-also"></a>См. также

- [Интерфейс ISymUnmanagedReader](isymunmanagedreader-interface.md)
