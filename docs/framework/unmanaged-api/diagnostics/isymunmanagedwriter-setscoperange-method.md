---
title: Метод ISymUnmanagedWriter::SetScopeRange
ms.date: 03/30/2017
api_name:
- ISymUnmanagedWriter.SetScopeRange
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedWriter::SetScopeRange
helpviewer_keywords:
- SetScopeRange method [.NET Framework debugging]
- ISymUnmanagedWriter::SetScopeRange method [.NET Framework debugging]
ms.assetid: d4d98676-444b-46ca-bfe6-0d827385cd22
topic_type:
- apiref
ms.openlocfilehash: 06dff4847ec3d15f446f1c89219b10eddb8eec4f
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/24/2020
ms.locfileid: "95683528"
---
# <a name="isymunmanagedwritersetscoperange-method"></a>Метод ISymUnmanagedWriter::SetScopeRange

Определяет диапазон смещений для заданной лексической области видимости. Область становится новой текущей областью и помещается в стек областей. Области должны образовывать иерархию. Не допускается перекрытие одноуровневых элементов.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
HRESULT OpenScope(  
    [in] ULONG32  scopeID,  
    [in] ULONG32  startOffset,  
    [in] ULONG32  endOffset);  
```  
  
## <a name="parameters"></a>Параметры  

 `scopeId`  
 окне Идентификатор области.  
  
 `startOffset`  
 окне Смещение первой инструкции в лексической области от начала метода (в байтах).  
  
 `endOffset`  
 окне Смещение (в байтах) последней инструкции в лексической области от начала метода.  
  
## <a name="return-value"></a>Возвращаемое значение  

 S_OK, если метод выполнен. в противном случае E_FAIL или другой код ошибки.  
  
## <a name="remarks"></a>Комментарии  

 [ISymUnmanagedWriter:: OpenScope](isymunmanagedwriter-openscope-method.md) возвращает непрозрачный идентификатор области, который можно использовать с `ISymUnmanagedWriter::SetScopeRange` для определения начального и конечного смещения области в более позднее время. В этом случае смещения, передаваемые в `ISymUnmanagedWriter::OpenScope` и [ISymUnmanagedWriter:: CloseScope](isymunmanagedwriter-closescope-method.md) , игнорируются. Идентификаторы областей допустимы только в текущем методе.  
  
## <a name="requirements"></a>Требования  

 **Заголовок:** Корсим. idl, Корсим. h  
  
## <a name="see-also"></a>См. также раздел

- [Интерфейс ISymUnmanagedWriter](isymunmanagedwriter-interface.md)
