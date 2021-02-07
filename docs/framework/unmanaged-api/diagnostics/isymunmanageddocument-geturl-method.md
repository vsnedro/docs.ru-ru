---
description: 'Дополнительные сведения о методе: ISymUnmanagedDocument:: GetURL'
title: Метод ISymUnmanagedDocument::GetURL
ms.date: 03/30/2017
api_name:
- ISymUnmanagedDocument.GetURL
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedDocument::GetURL
helpviewer_keywords:
- GetURL method [.NET Framework debugging]
- ISymUnmanagedDocument::GetURL method [.NET Framework debugging]
ms.assetid: 60600178-c2b5-4cab-b3a5-f0f61acebaf1
topic_type:
- apiref
ms.openlocfilehash: b39b36054d80f9ad2f9dd076e2055ccbc6526973
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2021
ms.locfileid: "99710196"
---
# <a name="isymunmanageddocumentgeturl-method"></a>Метод ISymUnmanagedDocument::GetURL

Возвращает универсальный указатель ресурса (URL) для этого документа.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
HRESULT GetURL(  
    [in]  ULONG32  cchUrl,  
    [out] ULONG32  *pcchUrl,  
    [out, size_is(cchUrl), length_is(*pcchUrl)] WCHAR szUrl[]);  
```  
  
## <a name="parameters"></a>Параметры  

 `cchUrl`  
 окне Размер буфера (в символах) `szURL` .  
  
 `pcchUrl`  
 заполняет Указатель на переменную, которая получает размер URL-адреса, включая завершение, равное NULL.  
  
 `szUrl`  
 заполняет Буфер, содержащий URL-адрес.  
  
## <a name="return-value"></a>Возвращаемое значение  

 S_OK, если метод выполнен. в противном случае — код ошибки.  
  
## <a name="see-also"></a>См. также

- [Интерфейс ISymUnmanagedDocument](isymunmanageddocument-interface.md)
