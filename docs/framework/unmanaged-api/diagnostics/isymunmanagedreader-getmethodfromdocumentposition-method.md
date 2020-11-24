---
title: Метод ISymUnmanagedReader::GetMethodFromDocumentPosition
ms.date: 03/30/2017
api_name:
- ISymUnmanagedReader.GetMethodFromDocumentPosition
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedReader::GetMethodFromDocumentPosition
helpviewer_keywords:
- GetMethodFromDocumentPosition method [.NET Framework debugging]
- ISymUnmanagedReader::GetMethodFromDocumentPosition method [.NET Framework debugging]
ms.assetid: 55773dbc-9053-46e3-8a3c-86caa9d91fb4
topic_type:
- apiref
ms.openlocfilehash: 417644e5d0c7af802d5266bd1825efa83c181597
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/24/2020
ms.locfileid: "95689606"
---
# <a name="isymunmanagedreadergetmethodfromdocumentposition-method"></a>Метод ISymUnmanagedReader::GetMethodFromDocumentPosition

Возвращает метод, содержащий точку останова в заданной позиции в документе.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
HRESULT GetMethodFromDocumentPosition (  
    [in]  ISymUnmanagedDocument*  document,  
    [in]  ULONG32  line,  
    [in]  ULONG32  column,  
    [out, retval] ISymUnmanagedMethod**  pRetVal);  
```  
  
## <a name="parameters"></a>Параметры  

 `document`  
 окне Указанный документ.  
  
 `line`  
 окне Строка указанного документа.  
  
 `column`  
 окне Столбец указанного документа.  
  
 `pRetVal`  
 заполняет Указатель на адрес объекта [интерфейса ISymUnmanagedMethod](isymunmanagedmethod-interface.md) , который представляет метод, содержащий точку останова.  
  
## <a name="return-value"></a>Возвращаемое значение  

 S_OK, если метод выполнен. в противном случае E_FAIL или другой код ошибки.  
  
## <a name="requirements"></a>Требования  

 **Заголовок:** Корсим. idl, Корсим. h  
  
## <a name="see-also"></a>См. также раздел

- [Интерфейс ISymUnmanagedReader](isymunmanagedreader-interface.md)
