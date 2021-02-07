---
description: 'Дополнительные сведения о методе: ISymUnmanagedNamespace:: WebMethod'
title: Метод ISymUnmanagedNamespace::GetVariables
ms.date: 03/30/2017
api_name:
- ISymUnmanagedNamespace.GetVariables
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedNamespace::GetVariables
helpviewer_keywords:
- ISymUnmanagedNamespace::GetVariables method [.NET Framework debugging]
- GetVariables method, ISymUnmanagedNamespace interface [.NET Framework debugging]
ms.assetid: ea7c1617-f3ce-4220-8288-f2b50eaf0f0f
topic_type:
- apiref
ms.openlocfilehash: 63316bf3ba1e4736d542be3362076c3ae6e95def
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2021
ms.locfileid: "99721207"
---
# <a name="isymunmanagednamespacegetvariables-method"></a>Метод ISymUnmanagedNamespace::GetVariables

Возвращает все переменные, определенные в глобальной области видимости в этом пространстве имен.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp
HRESULT GetVariables(  
    [in]  ULONG32  cVars,  
    [out] ULONG32  *pcVars,  
    [out, size_is(cVars), length_is(*pcVars)]  
        ISymUnmanagedVariable *pVars[]);  
```  
  
## <a name="parameters"></a>Параметры  

 `cVars`  
 окне Значение типа `ULONG32` , указывающее размер `pVars` массива.  
  
 `pcVars`  
 заполняет Указатель на объект `ULONG32` , который получает размер буфера, необходимого для хранения пространств имен.  
  
 `pVars`  
 заполняет Указатель на буфер, содержащий пространства имен.  
  
## <a name="return-value"></a>Возвращаемое значение  

 S_OK, если метод выполнен. в противном случае E_FAIL или другой код ошибки.  
  
## <a name="requirements"></a>Требования  

 **Заголовок:** Корсим. idl, Корсим. h  
  
## <a name="see-also"></a>См. также

- [Интерфейс ISymUnmanagedNamespace](isymunmanagednamespace-interface.md)
