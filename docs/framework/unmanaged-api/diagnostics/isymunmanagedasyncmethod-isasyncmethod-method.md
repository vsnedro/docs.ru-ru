---
description: 'Дополнительные сведения о методе: Исимунманажедасинкмесод:: Исасинкмесод'
title: Метод ISymUnmanagedAsyncMethod::IsAsyncMethod
ms.date: 03/30/2017
ms.assetid: 670a7653-dac6-4171-98ee-d669e3adf4b2
ms.openlocfilehash: 4b151f5367bac5fd92cc8237492cad6dacfb8e88
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2021
ms.locfileid: "99790260"
---
# <a name="isymunmanagedasyncmethodisasyncmethod-method"></a>Метод ISymUnmanagedAsyncMethod::IsAsyncMethod

Проверяет, имеет ли метод асинхронную информацию.  
  
 Если этот метод возвращает значение `FALSE` , то он недопустим для вызова любых других методов в этом интерфейсе. `E_UNEXPECTED`В этом случае они будут возвращаться.  
  
## <a name="syntax"></a>Синтаксис  
  
```idl  
HRESULT IsAsyncMethod(    [out, retval] BOOL* pRetVal);  
```  
  
## <a name="parameters"></a>Параметры  
  
|Параметр|Описание|  
|---------------|-----------------|  
|`pRetVal`||  
  
## <a name="return-value"></a>Возвращаемое значение  

 Возвращает `HRESULT`.  
  
## <a name="requirements"></a>Требования  

 **Заголовок:** Корсим. idl, Корсим. h  
  
## <a name="see-also"></a>См. также

- [Интерфейс ISymUnmanagedAsyncMethod](isymunmanagedasyncmethod-interface.md)
