---
description: 'Дополнительные сведения о методе: ISymUnmanagedWriter::D Ефинефиелд'
title: Метод ISymUnmanagedWriter::DefineField
ms.date: 03/30/2017
api_name:
- ISymUnmanagedWriter.DefineField
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedWriter::DefineField
helpviewer_keywords:
- ISymUnmanagedWriter::DefineField method [.NET Framework debugging]
- DefineField method, ISymUnmanagedWriter interface [.NET Framework debugging]
ms.assetid: c6a1f797-dbf4-40f5-ab99-d9b4bfb26148
topic_type:
- apiref
ms.openlocfilehash: f5bb47d4691780d94baf50cc9ceb3c14b1fa16ec
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2021
ms.locfileid: "99762400"
---
# <a name="isymunmanagedwriterdefinefield-method"></a>Метод ISymUnmanagedWriter::DefineField

Определяет одну переменную, не находящиеся в методе. Этот метод используется для определенных полей в классах, битовых полях и т. д.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
HRESULT DefineField(  
    [in] mdTypeDef    parent,  
    [in] const WCHAR  *name,  
    [in] ULONG32      attributes,  
    [in] ULONG32      cSig,  
    [in, size_is(cSig)] unsigned char signature[],  
    [in] ULONG32      addrKind,  
    [in] ULONG32      addr1,  
    [in] ULONG32      addr2,  
    [in] ULONG32      addr3);  
```  
  
## <a name="parameters"></a>Параметры  

 `parent`  
 окне Тип метаданных или токен метода.  
  
 `name`  
 окне Имя поля.  
  
 `attributes`  
 окне Атрибуты поля.  
  
 `cSig`  
 окне Объект `ULONG32` , который представляет собой размер (в символах) буфера, необходимого для хранения подписи поля.  
  
 `signature`  
 окне Массив подписей полей.  
  
 `addrKind`  
 окне Тип адреса.  
  
 `addr1`  
 окне Первый адрес для спецификации поля.  
  
 `addr2`  
 окне Второй адрес для спецификации поля.  
  
 `addr3`  
 окне Третий адрес для спецификации поля.  
  
## <a name="return-value"></a>Возвращаемое значение  

 S_OK, если метод выполнен. в противном случае E_FAIL или другой код ошибки.  
  
## <a name="requirements"></a>Требования  

 **Заголовок:** Корсим. idl, Корсим. h  
  
## <a name="see-also"></a>См. также

- [Интерфейс ISymUnmanagedWriter](isymunmanagedwriter-interface.md)
