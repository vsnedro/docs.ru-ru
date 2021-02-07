---
description: 'Дополнительные сведения о методе: ISymUnmanagedWriter3:: OpenMethod2'
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
ms.openlocfilehash: 7e76be03598599a6498ed45bc3799c6d6f21e088
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2021
ms.locfileid: "99761698"
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
  
## <a name="see-also"></a>См. также

- [Интерфейс ISymUnmanagedWriter3](isymunmanagedwriter3-interface.md)
- [Метод OpenMethod](isymunmanagedwriter-openmethod-method.md)
