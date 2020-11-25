---
title: Метод ISymUnmanagedWriter::DefineGlobalVariable
ms.date: 03/30/2017
api_name:
- ISymUnmanagedWriter.DefineGlobalVariable
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedWriter::DefineGlobalVariable
helpviewer_keywords:
- ISymUnmanagedWriter::DefineGlobalVariable method [.NET Framework debugging]
- DefineGlobalVariable method [.NET Framework debugging]
ms.assetid: 843c904a-8176-4d8f-bd47-b4d4c29f4c5c
topic_type:
- apiref
ms.openlocfilehash: bc389b7247a6b1d6ce16cb3cf350f1672213b2e2
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/24/2020
ms.locfileid: "95716425"
---
# <a name="isymunmanagedwriterdefineglobalvariable-method"></a>Метод ISymUnmanagedWriter::DefineGlobalVariable

Определяет одну глобальную переменную.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
HRESULT DefineGlobalVariable(  
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

 `name`  
 окне Указатель на объект `WCHAR` , который определяет имя глобальной переменной.  
  
 `attributes`  
 окне Атрибуты глобальных переменных.  
  
 `cSig`  
 окне Значение типа `ULONG32` , указывающее размер буфера (в символах) `signature` .  
  
 `signature`  
 окне Сигнатура глобальной переменной.  
  
 `addrKind`  
 окне Тип адреса.  
  
 `addr1`  
 окне Первый адрес для спецификации параметра.  
  
 `addr2`  
 окне Второй адрес для спецификации параметра.  
  
 `addr3`  
 окне Третий адрес для спецификации параметра.  
  
## <a name="return-value"></a>Возвращаемое значение  

 S_OK, если метод выполнен. в противном случае E_FAIL или другой код ошибки.  
  
## <a name="requirements"></a>Требования  

 **Заголовок:** Корсим. idl, Корсим. h  
  
## <a name="see-also"></a>См. также раздел

- [Интерфейс ISymUnmanagedWriter](isymunmanagedwriter-interface.md)
- [Метод DefineLocalVariable](isymunmanagedwriter-definelocalvariable-method.md)
- [Метод DefineGlobalVariable2](isymunmanagedwriter2-defineglobalvariable2-method.md)
