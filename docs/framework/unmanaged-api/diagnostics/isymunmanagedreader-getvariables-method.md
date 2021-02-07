---
description: 'Дополнительные сведения о методе: ISymUnmanagedReader:: WebMethod'
title: Метод ISymUnmanagedReader::GetVariables
ms.date: 03/30/2017
api_name:
- ISymUnmanagedReader.GetVariables
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedReader::GetVariables
helpviewer_keywords:
- ISymUnmanagedReader::GetVariables method [.NET Framework debugging]
- GetVariables method, ISymUnmanagedReader interface [.NET Framework debugging]
ms.assetid: 16dc49cb-2c60-4ac8-9c35-020e9afba3f8
topic_type:
- apiref
ms.openlocfilehash: 93208e6c5c65c4c770c533b7ea72de513451d97d
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2021
ms.locfileid: "99763908"
---
# <a name="isymunmanagedreadergetvariables-method"></a>Метод ISymUnmanagedReader::GetVariables

Возвращает нелокальную переменную с учетом ее родителя и имени.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
HRESULT GetVariables (  
    [in]  mdToken  parent,  
    [in]  ULONG32  cVars,  
    [out] ULONG32  *pcVars,  
    [out, size_is (cVars),  
        length_is (*pcVars)] ISymUnmanagedVariable *pVars[]);  
```  
  
## <a name="parameters"></a>Параметры  

 `parent`  
 окне Родительский объект переменной.  
  
 `cVars`  
 [in] Размер массива `pVars`.  
  
 `pcVars`  
 заполняет Указатель на переменную, которая получает количество переменных, возвращаемых в `pVars` .  
  
 `pVars`  
 заполняет Указатель на переменную, которая получает переменные.  
  
## <a name="return-value"></a>Возвращаемое значение  

 S_OK, если метод выполнен. в противном случае E_FAIL или другой код ошибки.  
  
## <a name="requirements"></a>Требования  

 **Заголовок:** Корсим. idl, Корсим. h  
  
## <a name="see-also"></a>См. также

- [Интерфейс ISymUnmanagedReader](isymunmanagedreader-interface.md)
