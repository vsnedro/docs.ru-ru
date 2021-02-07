---
description: 'Дополнительные сведения о методе: ISymUnmanagedENCUpdate:: Getlocalvariables-'
title: Метод ISymUnmanagedENCUpdate::GetLocalVariables
ms.date: 03/30/2017
api_name:
- ISymUnmanagedENCUpdate.GetLocalVariables
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedENCUpdate::GetLocalVariables
helpviewer_keywords:
- ISymUnmanagedENCUpdate::GetLocalVariables method [.NET Framework debugging]
- GetLocalVariables method [.NET Framework debugging]
ms.assetid: 5c8840be-ffea-447f-9c8d-178f1eaf8d06
topic_type:
- apiref
ms.openlocfilehash: bc034603dd6a09ea78dad789e11ea951d65e839b
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2021
ms.locfileid: "99721467"
---
# <a name="isymunmanagedencupdategetlocalvariables-method"></a>Метод ISymUnmanagedENCUpdate::GetLocalVariables

Возвращает локальные переменные.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
HRESULT GetLocalVariables(  
    [in]  mdMethodDef  mdMethodToken,  
    [in]  ULONG        cLocals,  
    [out, size_is(cLocals), length_is(*pceltFetched)]  
        ISymUnmanagedVariable *rgLocals[],  
    [out] ULONG        *pceltFetched);  
```  
  
## <a name="parameters"></a>Параметры  

 `mdMethodToken`  
 окне Маркер метаданных метода.  
  
 `cLocals`  
 окне Значение типа `ULONG` , указывающее размер `rgLocals` параметра.  
  
 `rgLocals`  
 заполняет Возвращаемый массив экземпляров [ISymUnmanagedVariable](isymunmanagedvariable-interface.md) .  
  
 `pceltFetched`  
 заполняет Указатель на объект `ULONG` , который получает размер `rgLocals` буфера, необходимого для хранения локальных переменных.  
  
## <a name="return-value"></a>Возвращаемое значение  

 S_OK, если метод выполнен. в противном случае E_FAIL или другой код ошибки.  
  
## <a name="requirements"></a>Требования  

 **Заголовок:** Корсим. idl, Корсим. h  
  
## <a name="see-also"></a>См. также

- [Интерфейс ISymUnmanagedENCUpdate](isymunmanagedencupdate-interface.md)
