---
title: Метод ISymUnmanagedBinder3::GetReaderFromCallback
ms.date: 03/30/2017
api_name:
- ISymUnmanagedBinder3.GetReaderFromCallback
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedBinder3::GetReaderFromCallback
helpviewer_keywords:
- GetReaderFromCallback method [.NET Framework debugging]
- ISymUnmanagedBinder3::GetReaderFromCallback method [.NET Framework debugging]
ms.assetid: 4ef83bd2-3d8e-499e-8a12-d9d6fd6ced30
topic_type:
- apiref
ms.openlocfilehash: d48c2bdd55e487038048f432c5586d49f393118c
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/24/2020
ms.locfileid: "95706948"
---
# <a name="isymunmanagedbinder3getreaderfromcallback-method"></a>Метод ISymUnmanagedBinder3::GetReaderFromCallback

Позволяет пользователю реализовать или предоставить через обратный вызов либо `IID_IDiaReadExeAtRVACallback` `IID_IDiaReadExeAtOffsetCallback` для получения сведений о каталоге отладки из памяти.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
HRESULT GetReaderFromCallback(  
    [in]  IUnknown     *importer,  
    [in]  const WCHAR  *fileName,  
    [in]  const WCHAR  *searchPath,  
    [in]  ULONG32      searchPolicy,  
    [in]  IUnknown     *callback,  
    [out,retval] ISymUnmanagedReader  **pRetVal);  
```  
  
## <a name="parameters"></a>Параметры  

 `importer`  
 окне Указатель на интерфейс импорта метаданных.  
  
 `fileName`  
 окне Указатель на имя файла.  
  
 `searchPath`  
 окне Указатель на путь поиска.  
  
 `searchPolicy`  
 окне Значение перечисления [корсимсеарчполициаттрибутес](corsymsearchpolicyattributes-enumeration.md) , указывающее политику, используемую при поиске средства чтения символов.  
  
 `callback`  
 окне Указатель на функцию обратного вызова.  
  
 `pRetVal`  
 заполняет Указатель, которому присваивается возвращаемый интерфейс [ISymUnmanagedReader](isymunmanagedreader-interface.md) .  
  
## <a name="return-value"></a>Возвращаемое значение  

 S_OK, если метод выполнен. в противном случае E_FAIL или другой код ошибки.  
  
## <a name="requirements"></a>Требования  

 **Заголовок:** Корсим. idl  
  
## <a name="see-also"></a>См. также раздел

- [Интерфейс ISymUnmanagedBinder3](isymunmanagedbinder3-interface.md)
