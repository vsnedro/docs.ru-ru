---
description: 'Дополнительные сведения о методе: ISymUnmanagedReader:: GetSymbolStoreFileName'
title: Метод ISymUnmanagedReader::GetSymbolStoreFileName
ms.date: 03/30/2017
api_name:
- ISymUnmanagedReader.GetSymbolStoreFileName
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedReader::GetSymbolStoreFileName
helpviewer_keywords:
- GetSymbolStoreFileName method [.NET Framework debugging]
- ISymUnmanagedReader::GetSymbolStoreFileName method [.NET Framework debugging]
ms.assetid: c84f4846-9bc8-44a4-9a76-e39106d6d8b2
topic_type:
- apiref
ms.openlocfilehash: 5cbb33a39cf2e93eab64d5f1f1fefc5ceba1d418
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2021
ms.locfileid: "99763947"
---
# <a name="isymunmanagedreadergetsymbolstorefilename-method"></a>Метод ISymUnmanagedReader::GetSymbolStoreFileName

Предоставляет имя файла на диске для хранилища символов.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
HRESULT GetSymbolStoreFileName (  
    [in]  ULONG32 cchName,  
    [out] ULONG32 *pcchName,  
    [out, size_is (cchName),  
        length_is (*pcchName)] WCHAR szName[]);  
```  
  
## <a name="parameters"></a>Параметры  

 `cchName`  
 окне Размер `szName` буфера.  
  
 `pcchName`  
 заполняет Указатель на переменную, которая получает длину имени, возвращаемого в `szName` , включая завершение значения NULL.  
  
 `szName`  
 заполняет Указатель на переменную, которая получает имя файла хранилища символов.  
  
## <a name="return-value"></a>Возвращаемое значение  

 S_OK, если метод выполнен. в противном случае E_FAIL или другой код ошибки.  
  
## <a name="requirements"></a>Требования  

 **Заголовок:** Корсим. idl, Корсим. h  
  
## <a name="see-also"></a>См. также

- [Интерфейс ISymUnmanagedReader](isymunmanagedreader-interface.md)
