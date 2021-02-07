---
description: 'Дополнительные сведения о методе: Исимунманажедскопе:: Жетендоффсет'
title: Метод ISymUnmanagedScope::GetEndOffset
ms.date: 03/30/2017
api_name:
- ISymUnmanagedScope.GetEndOffset
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedScope::GetEndOffset
helpviewer_keywords:
- ISymUnmanagedScope::GetEndOffset method [.NET Framework debugging]
- GetEndOffset method, ISymUnmanagedScope interface [.NET Framework debugging]
ms.assetid: 1d0b15c9-8059-435f-9fce-346a08b9bd36
topic_type:
- apiref
ms.openlocfilehash: ac95b98bb87fbf3dc3b42b5a2e5413f76dfffa34
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2021
ms.locfileid: "99763481"
---
# <a name="isymunmanagedscopegetendoffset-method"></a>Метод ISymUnmanagedScope::GetEndOffset

Возвращает конечное смещение для данной области.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
HRESULT GetEndOffset(  
    [out, retval] ULONG32* pRetVal);  
```  
  
## <a name="parameters"></a>Параметры  

 `pRetVal`  
 заполняет Указатель на объект `ULONG32` , который получает конечное смещение.  
  
## <a name="return-value"></a>Возвращаемое значение  

 S_OK, если метод выполнен. в противном случае E_FAIL или другой код ошибки.  
  
## <a name="requirements"></a>Требования  

 **Заголовок:** Корсим. idl, Корсим. h  
  
## <a name="see-also"></a>См. также

- [Интерфейс ISymUnmanagedScope](isymunmanagedscope-interface.md)
- [Метод GetStartOffset](isymunmanagedscope-getstartoffset-method.md)
