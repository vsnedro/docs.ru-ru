---
description: 'Дополнительные сведения о методе: ISymUnmanagedENCUpdate:: Жетлокалвариаблекаунт'
title: Метод ISymUnmanagedENCUpdate::GetLocalVariableCount
ms.date: 03/30/2017
api_name:
- ISymUnmanagedENCUpdate.GetLocalVariableCount
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedENCUpdate::GetLocalVariableCount
helpviewer_keywords:
- ISymUnmanagedENCUpdate::GetLocalVariableCount method [.NET Framework debugging]
- GetLocalVariableCount method [.NET Framework debugging]
ms.assetid: 9777d8bb-4abc-4be8-aa7c-34f853eceb9c
topic_type:
- apiref
ms.openlocfilehash: ab75ba0b0dda5722aebdbdc8b9a242cc90b0ac11
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2021
ms.locfileid: "99790156"
---
# <a name="isymunmanagedencupdategetlocalvariablecount-method"></a>Метод ISymUnmanagedENCUpdate::GetLocalVariableCount

Возвращает число локальных переменных.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
HRESULT GetLocalVariableCount(  
    [in]  mdMethodDef  mdMethodToken,  
    [out] ULONG        *pcLocals);  
```  
  
## <a name="parameters"></a>Параметры  

 `mdMethodToken`  
 окне Маркер метаданных методов.  
  
 `pcLocals`  
 заполняет Указатель на объект `ULONG32` , который получает размер буфера (в символах), необходимого для хранения числа локальных переменных.  
  
## <a name="return-value"></a>Возвращаемое значение  

 S_OK, если метод выполнен. в противном случае E_FAIL или другой код ошибки.  
  
## <a name="requirements"></a>Требования  

 **Заголовок:** Корсим. idl, Корсим. h  
  
## <a name="see-also"></a>См. также

- [Интерфейс ISymUnmanagedENCUpdate](isymunmanagedencupdate-interface.md)
