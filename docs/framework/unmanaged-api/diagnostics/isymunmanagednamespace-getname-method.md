---
description: 'Дополнительные сведения о методе: ISymUnmanagedNamespace:: Name'
title: Метод ISymUnmanagedNamespace::GetName
ms.date: 03/30/2017
api_name:
- ISymUnmanagedNamespace.GetName
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedNamespace::GetName
helpviewer_keywords:
- ISymUnmanagedNamespace::GetName method [.NET Framework debugging]
- GetName method, ISymUnmanagedNamespace interface [.NET Framework debugging]
ms.assetid: 657bf91d-005a-4ea4-9298-04d1291c0bc3
topic_type:
- apiref
ms.openlocfilehash: f4d366363cd089995f98039389f59077e949fb79
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2021
ms.locfileid: "99721220"
---
# <a name="isymunmanagednamespacegetname-method"></a>Метод ISymUnmanagedNamespace::GetName

Возвращает имя этого пространства имен.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
HRESULT GetName(  
    [in]  ULONG32  cchName,  
    [out] ULONG32  *pcchName,  
    [out, size_is(cchName),  
        length_is(*pcchName)] WCHAR szName[]);  
```  
  
## <a name="parameters"></a>Параметры  

 `cchName`  
 окне Значение типа `ULONG32` , указывающее размер `szName` буфера.  
  
 `pcchName`  
 заполняет Указатель на объект `ULONG32` , который получает размер (в символах) буфера, необходимого для хранения имени пространства имен, включая завершение значения NULL.  
  
 `szName`  
 заполняет Указатель на буфер, содержащий имя пространства имен.  
  
## <a name="return-value"></a>Возвращаемое значение  

 S_OK, если метод выполнен. в противном случае E_FAIL или другой код ошибки.  
  
## <a name="requirements"></a>Требования  

 **Заголовок:** Корсим. idl, Корсим. h  
  
## <a name="see-also"></a>См. также

- [Интерфейс ISymUnmanagedNamespace](isymunmanagednamespace-interface.md)
