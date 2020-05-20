---
title: Метод ISymUnmanagedWriter::DefineLocalVariable
ms.date: 03/30/2017
api_name:
- ISymUnmanagedWriter.DefineLocalVariable
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedWriter::DefineLocalVariable
helpviewer_keywords:
- ISymUnmanagedWriter::DefineLocalVariable method [.NET Framework debugging]
- DefineLocalVariable method [.NET Framework debugging]
ms.assetid: 6fab8a58-3883-490f-8b27-64042c90f104
topic_type:
- apiref
ms.openlocfilehash: 5730cdd910257d762230f5e54576d5e0a7ac1adb
ms.sourcegitcommit: 27db07ffb26f76912feefba7b884313547410db5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/19/2020
ms.locfileid: "83614829"
---
# <a name="isymunmanagedwriterdefinelocalvariable-method"></a>Метод ISymUnmanagedWriter::DefineLocalVariable
Определяет одну переменную в текущей лексической области видимости. Этот метод может вызываться несколько раз для переменной с тем же именем, которая имеет несколько домов в пределах области. Однако в этом случае значения `startOffset` `endOffset` параметров и не должны перекрываться.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
HRESULT DefineLocalVariable(  
    [in] const WCHAR  *name,  
    [in] ULONG32      attributes,  
    [in] ULONG32      cSig,  
    [in, size_is(cSig)] unsigned char signature[],  
    [in] ULONG32      addrKind,  
    [in] ULONG32      addr1,  
    [in] ULONG32      addr2,  
    [in] ULONG32      addr3,  
    [in] ULONG32      startOffset,  
    [in] ULONG32      endOffset);  
```  
  
## <a name="parameters"></a>Параметры  
 `name`  
 окне Указатель на объект `WCHAR` , который определяет имя локальной переменной.  
  
 `attributes`  
 окне Атрибуты локальной переменной.  
  
 `cSig`  
 окне Значение типа `ULONG32` , указывающее размер буфера (в байтах) `signature` .  
  
 `signature`  
 окне Сигнатура локальной переменной.  
  
 `addrKind`  
 окне Тип адреса.  
  
 `addr1`  
 окне Первый адрес для спецификации параметра.  
  
 `addr2`  
 окне Второй адрес для спецификации параметра.  
  
 `addr3`  
 окне Третий адрес для спецификации параметра.  
  
 `startOffset`  
 окне Начальное смещение для переменной. Этот параметр необязателен. Если значение равно 0, этот параметр не учитывается, и переменная определяется всей областью. Если это ненулевое значение, переменная попадает в диапазон смещений текущей области.  
  
 `endOffset`  
 окне Конечное смещение для переменной. Этот параметр необязателен. Если значение равно 0, этот параметр не учитывается, и переменная определяется всей областью. Если это ненулевое значение, переменная попадает в диапазон смещений текущей области.  
  
## <a name="return-value"></a>Возвращаемое значение  
 S_OK, если метод выполнен. в противном случае E_FAIL или другой код ошибки.  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** Корсим. idl, Корсим. h  
  
## <a name="see-also"></a>Дополнительно

- [Интерфейс ISymUnmanagedWriter](isymunmanagedwriter-interface.md)
- [Метод DefineGlobalVariable](isymunmanagedwriter-defineglobalvariable-method.md)
- [Метод DefineLocalVariable2](isymunmanagedwriter2-definelocalvariable2-method.md)
