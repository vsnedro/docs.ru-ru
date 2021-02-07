---
description: 'Дополнительные сведения о методе: ISymUnmanagedReader:: Жетглобалвариаблес'
title: Метод ISymUnmanagedReader::GetGlobalVariables
ms.date: 03/30/2017
api_name:
- ISymUnmanagedReader.GetGlobalVariables
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedReader::GetGlobalVariables
helpviewer_keywords:
- GetGlobalVariables method [.NET Framework debugging]
- ISymUnmanagedReader::GetGlobalVariables method [.NET Framework debugging]
ms.assetid: a2dd5098-3e58-4be5-b7a2-e4160b3b505a
topic_type:
- apiref
ms.openlocfilehash: 2b017d2a5746942f701cf79d3d29f1eb571dceab
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2021
ms.locfileid: "99689655"
---
# <a name="isymunmanagedreadergetglobalvariables-method"></a>Метод ISymUnmanagedReader::GetGlobalVariables

Возвращает все глобальные переменные.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
HRESULT GetGlobalVariables(  
    [in]  ULONG32  cVars,  
    [out] ULONG32  *pcVars,  
    [out, size_is(cVars),  
        length_is(*pcVars)] ISymUnmanagedVariable *pVars[]);  
```  
  
## <a name="parameters"></a>Параметры  

 `cVars`  
 окне Длина буфера, на который указывает `pcVars` .  
  
 `pcVars`  
 заполняет Указатель на объект `ULONG32` , который получает размер буфера, необходимого для хранения переменных.  
  
 `pVars`  
 заполняет Буфер, содержащий переменные.  
  
## <a name="return-value"></a>Возвращаемое значение  

 S_OK, если метод выполнен. в противном случае E_FAIL или другой код ошибки.  
  
## <a name="requirements"></a>Требования  

 **Заголовок:** Корсим. idl, Корсим. h  
  
## <a name="see-also"></a>См. также

- [Интерфейс ISymUnmanagedReader](isymunmanagedreader-interface.md)
