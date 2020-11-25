---
title: Метод ISymUnmanagedMethod::GetScopeFromOffset
ms.date: 03/30/2017
api_name:
- ISymUnmanagedMethod.GetScopeFromOffset
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedMethod::GetScopeFromOffset
helpviewer_keywords:
- GetScopeFromOffset method [.NET Framework debugging]
- ISymUnmanagedMethod::GetScopeFromOffset method [.NET Framework debugging]
ms.assetid: d14cf210-81f8-46e1-8b19-6ddec0ba8b11
topic_type:
- apiref
ms.openlocfilehash: cf2784ce0ac6e614e75a341660808b9fe03ada0e
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/24/2020
ms.locfileid: "95699447"
---
# <a name="isymunmanagedmethodgetscopefromoffset-method"></a>Метод ISymUnmanagedMethod::GetScopeFromOffset

Возвращает наиболее окружающую лексическую область внутри этого метода, которая заключает заданное смещение. Это можно использовать для запуска поиска локальных переменных.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
HRESULT GetScopeFromOffset(  
    [in]  ULONG32 offset,  
    [out, retval] ISymUnmanagedScope**  pRetVal);  
```  
  
## <a name="parameters"></a>Параметры  

 `offset`  
 окне Значение типа `ULONG` , содержащее смещение.  
  
 `pRetVal`  
 заполняет Указатель, которому присваивается возвращаемый интерфейс [исимунманажедскопе](isymunmanagedscope-interface.md) .  
  
## <a name="return-value"></a>Возвращаемое значение  

 S_OK, если метод выполнен. в противном случае E_FAIL или другой код ошибки.  
  
## <a name="requirements"></a>Требования  

 **Заголовок:** Корсим. idl, Корсим. h  
  
## <a name="see-also"></a>См. также раздел

- [Интерфейс ISymUnmanagedMethod](isymunmanagedmethod-interface.md)
