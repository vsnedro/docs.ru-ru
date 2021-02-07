---
description: 'Дополнительные сведения о методе: ISymUnmanagedWriter2::D efineLocalVariable2'
title: Метод ISymUnmanagedWriter2::DefineLocalVariable2
ms.date: 03/30/2017
api_name:
- ISymUnmanagedWriter2.DefineLocalVariable2
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedWriter2::DefineLocalVariable2
helpviewer_keywords:
- ISymUnmanagedWriter2::DefineLocalVariable2 method [.NET Framework debugging]
- DefineLocalVariable2 method [.NET Framework debugging]
ms.assetid: e774eefe-858c-4362-8d2d-28ebf2ba1a24
topic_type:
- apiref
ms.openlocfilehash: 169a086b8420b5dbe20af8e16b21d5b41a958ead
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2021
ms.locfileid: "99761815"
---
# <a name="isymunmanagedwriter2definelocalvariable2-method"></a>Метод ISymUnmanagedWriter2::DefineLocalVariable2

Определяет одну переменную в текущей лексической области видимости. Этот метод может вызываться несколько раз для переменной с тем же именем, которая имеет несколько домов в пределах области. Однако в этом случае значения `startOffset` `endOffset` параметров и не должны перекрываться.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
HRESULT DefineLocalVariable2(  
    [in] const WCHAR  *name,  
    [in] ULONG32      attributes,  
    [in] mdSignature  sigToken,  
    [in] ULONG32      addrKind,  
    [in] ULONG32      addr1,  
    [in] ULONG32      addr2,  
    [in] ULONG32      addr3,  
    [in] ULONG32      startOffset,  
    [in] ULONG32      endOffset);  
```  
  
## <a name="parameters"></a>Параметры  

 `name`  
 окне Имя локальной переменной.  
  
 `attributes`  
 окне Атрибуты локальной переменной.  
  
 `sigToken`  
 окне Маркер метаданных сигнатуры.  
  
 `addrKind`  
 окне Тип адреса.  
  
 `addr1`  
 окне Первый адрес для спецификации параметра.  
  
 `addr2`  
 окне Второй адрес для спецификации параметра.  
  
 `addr3`  
 окне Третий адрес для спецификации параметра.  
  
 `startOffset`  
 окне Начальное смещение для переменной. Этот параметр является необязательным. Если значение равно 0, этот параметр не учитывается, и переменная определяется всей областью. Если это ненулевое значение, переменная попадает в диапазон смещений текущей области.  
  
 `endOffset`  
 окне Конечное смещение для переменной. Этот параметр является необязательным. Если значение равно 0, этот параметр не учитывается, и переменная определяется всей областью. Если это ненулевое значение, переменная попадает в диапазон смещений текущей области.  
  
## <a name="return-value"></a>Возвращаемое значение  

 S_OK, если метод выполнен. в противном случае E_FAIL или другой код ошибки.  
  
## <a name="requirements"></a>Требования  

 **Заголовок:** Корсим. idl  
  
## <a name="see-also"></a>См. также

- [Интерфейс ISymUnmanagedWriter2](isymunmanagedwriter2-interface.md)
- [Метод DefineLocalVariable](isymunmanagedwriter-definelocalvariable-method.md)
