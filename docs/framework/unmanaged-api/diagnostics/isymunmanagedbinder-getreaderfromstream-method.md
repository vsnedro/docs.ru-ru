---
description: 'Дополнительные сведения о методе: ISymUnmanagedBinder:: Жетреадерфромстреам'
title: Метод ISymUnmanagedBinder::GetReaderFromStream
ms.date: 03/30/2017
api_name:
- ISymUnmanagedBinder.GetReaderFromStream
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedBinder::GetReaderFromStream
helpviewer_keywords:
- ISymUnmanagedBinder::GetReaderFromStream method [.NET Framework debugging]
- GetReaderFromStream method [.NET Framework debugging]
ms.assetid: aa38efd4-de7e-4482-a5d3-adc152093460
topic_type:
- apiref
ms.openlocfilehash: da238ed8e450250be427ae27c4492c1e091f7997
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2021
ms.locfileid: "99689993"
---
# <a name="isymunmanagedbindergetreaderfromstream-method"></a>Метод ISymUnmanagedBinder::GetReaderFromStream

При наличии интерфейса метаданных и потока, содержащего хранилище символов, возвращает правильную структуру [ISymUnmanagedReader](isymunmanagedreader-interface.md) , которая будет считывать отладочные символы из заданного хранилища символов.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
HRESULT GetReaderFromStream(  
    [in]  IUnknown  *importer,  
    [in]  IStream   *pstream,  
    [out,retval] ISymUnmanagedReader **pRetVal);  
```  
  
## <a name="parameters"></a>Параметры  

 `importer`  
 окне Указатель на интерфейс импорта метаданных.  
  
 `pstream`  
 окне Указатель на поток, содержащий хранилище символов.  
  
 `pRetVal`  
 заполняет Указатель, которому присваивается возвращаемый интерфейс [ISymUnmanagedReader](isymunmanagedreader-interface.md) .  
  
## <a name="return-value"></a>Возвращаемое значение  

 S_OK, если метод выполнен. в противном случае E_FAIL или другой код ошибки.  
  
## <a name="requirements"></a>Требования  

 **Заголовок:** Корсим. idl, Корсим. h  
  
## <a name="see-also"></a>См. также

- [Интерфейс ISymUnmanagedBinder](isymunmanagedbinder-interface.md)
