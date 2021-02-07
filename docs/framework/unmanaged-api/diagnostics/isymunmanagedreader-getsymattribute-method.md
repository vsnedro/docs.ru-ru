---
description: 'Дополнительные сведения о методе: ISymUnmanagedReader:: GetSymAttribute'
title: Метод ISymUnmanagedReader::GetSymAttribute
ms.date: 03/30/2017
api_name:
- ISymUnmanagedReader.GetSymAttribute
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedReader::GetSymAttribute
helpviewer_keywords:
- GetSymAttribute method [.NET Framework debugging]
- ISymUnmanagedReader::GetSymAttribute method [.NET Framework debugging]
ms.assetid: c675ce7e-76e7-45ff-8273-3b6489a2767c
topic_type:
- apiref
ms.openlocfilehash: cd1c453e9f2ef68799fc5eccf1288a7665c5cfdf
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2021
ms.locfileid: "99763973"
---
# <a name="isymunmanagedreadergetsymattribute-method"></a>Метод ISymUnmanagedReader::GetSymAttribute

Возвращает настраиваемый атрибут на основе его имени. В отличие от пользовательских атрибутов метаданных эти пользовательские атрибуты хранятся в хранилище символов.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
HRESULT GetSymAttribute (  
    [in]  mdToken  parent,  
    [in]  WCHAR    *name,  
    [in]  ULONG32  cBuffer,  
    [out] ULONG32  *pcBuffer,  
    [out, size_is (cBuffer),  
        length_is (*pcBuffer)] BYTE buffer[]);  
```  
  
## <a name="parameters"></a>Параметры  

 `parent`  
 окне Токен метаданных для объекта, для которого запрашивается атрибут.  
  
 `name`  
 окне Указатель на переменную, которая указывает извлекаемый атрибут.  
  
 `cBuffer`  
 [in] Размер массива `buffer`.  
  
 `pcBuffer`  
 заполняет Указатель на переменную, которая получает длину данных атрибута.  
  
 `buffer`  
 заполняет Указатель на переменную, которая получает данные атрибута.  
  
## <a name="return-value"></a>Возвращаемое значение  

 S_OK, если метод выполнен. в противном случае E_FAIL или другой код ошибки.  
  
## <a name="requirements"></a>Требования  

 **Заголовок:** Корсим. idl, Корсим. h  
  
## <a name="see-also"></a>См. также

- [Интерфейс ISymUnmanagedReader](isymunmanagedreader-interface.md)
