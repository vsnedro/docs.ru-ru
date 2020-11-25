---
title: Метод ISymUnmanagedWriter::CloseScope
ms.date: 03/30/2017
api_name:
- ISymUnmanagedWriter.CloseScope
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedWriter::CloseScope
helpviewer_keywords:
- CloseScope method [.NET Framework debugging]
- ISymUnmanagedWriter::CloseScope method [.NET Framework debugging]
ms.assetid: 6dade525-7770-4cb4-bafd-4bb995ad0d87
topic_type:
- apiref
ms.openlocfilehash: 561a6348b9976789b02961fadb37d9127f5a6a13
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/24/2020
ms.locfileid: "95713045"
---
# <a name="isymunmanagedwriterclosescope-method"></a>Метод ISymUnmanagedWriter::CloseScope

Закрывает текущую лексическую область видимости.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
HRESULT CloseScope(  
    [in] ULONG32 endOffset);  
```  
  
## <a name="parameters"></a>Параметры  

 `endOffset`  
 окне Смещение от начала метода точки в конце последней инструкции в лексической области в байтах.  
  
## <a name="return-value"></a>Возвращаемое значение  

 S_OK, если метод выполнен. в противном случае E_FAIL или другой код ошибки.  
  
## <a name="remarks"></a>Комментарии  

 После закрытия области в ней больше нельзя определять переменные.  
  
 [ISymUnmanagedWriter:: OpenScope](isymunmanagedwriter-openscope-method.md) возвращает непрозрачный идентификатор области, который можно использовать с [ISymUnmanagedWriter:: сетскоперанже](isymunmanagedwriter-setscoperange-method.md) , чтобы определить начальное и конечное смещение области. В этом случае смещения, переданные методам `ISymUnmanagedWriter::OpenScope` и `ISymUnmanagedWriter::CloseScope`, пропускаются. Идентификаторы областей допустимы только в текущем методе.  
  
## <a name="requirements"></a>Требования  

 **Заголовок:** Корсим. idl, Корсим. h  
  
## <a name="see-also"></a>См. также раздел

- [Интерфейс ISymUnmanagedWriter](isymunmanagedwriter-interface.md)
