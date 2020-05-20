---
title: Метод ISymUnmanagedWriter3::OpenMethod2
ms.date: 03/30/2017
api_name:
- ISymUnmanagedWriter3.OpenMethod2
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedWriter3::OpenMethod2
helpviewer_keywords:
- ISymUnmanagedWriter3::OpenMethod2 method [.NET Framework debugging]
- OpenMethod2 method [.NET Framework debugging]
ms.assetid: 025e358c-448f-4423-a2f2-57acf437c8a5
topic_type:
- apiref
ms.openlocfilehash: e88a844a7f79f14c717a5966b345588b3b3b9f81
ms.sourcegitcommit: 27db07ffb26f76912feefba7b884313547410db5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/19/2020
ms.locfileid: "83609421"
---
# <a name="isymunmanagedwriter3openmethod2-method"></a>Метод ISymUnmanagedWriter3::OpenMethod2
Открывает метод и предоставляет его фактическое смещение раздела в изображении.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
HRESULT OpenMethod2(
    [in] mdMethodDef method,  
    [in] ULONG32 isect,  
    [in] ULONG32 offset);  
```  
  
## <a name="parameters"></a>Параметры  
 `method`  
 окне Токен метаданных для открываемого метода.  
  
 `isect`  
 окне Смещение раздела в изображении.  
  
 `offset`  
 окне Смещение в изображении.  
  
## <a name="return-value"></a>Возвращаемое значение  
 S_OK, если метод выполнен. в противном случае E_FAIL или другой код ошибки.  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** Корсим. idl, Корсим. h  
  
## <a name="see-also"></a>Дополнительно

- [Интерфейс ISymUnmanagedWriter3](isymunmanagedwriter3-interface.md)
- [Метод OpenMethod](isymunmanagedwriter-openmethod-method.md)
