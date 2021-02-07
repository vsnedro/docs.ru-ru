---
description: 'Дополнительные сведения о методе: ISymUnmanagedWriter:: Сетсиматтрибуте'
title: Метод ISymUnmanagedWriter::SetSymAttribute
ms.date: 03/30/2017
api_name:
- ISymUnmanagedWriter.SetSymAttribute
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedWriter::SetSymAttribute
helpviewer_keywords:
- SetSymAttribute method [.NET Framework debugging]
- ISymUnmanagedWriter::SetSymAttribute method [.NET Framework debugging]
ms.assetid: 64d9b80e-b883-4539-89c7-03573185a1eb
topic_type:
- apiref
ms.openlocfilehash: 0509e6430646fa67112b29d30d5053eb4a541415
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2021
ms.locfileid: "99761997"
---
# <a name="isymunmanagedwritersetsymattribute-method"></a>Метод ISymUnmanagedWriter::SetSymAttribute

Определяет настраиваемый атрибут на основе его имени. Эти атрибуты хранятся в хранилище символов в отличие от пользовательских атрибутов метаданных.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
HRESULT SetSymAttribute(  
    [in] mdToken parent,  
    [in] const WCHAR *name,  
    [in] ULONG32 cData,  
    [in, size_is(cData)] unsigned char data[]);  
```  
  
## <a name="parameters"></a>Параметры  

 `parent`  
 окне Токен метаданных, для которого определяется атрибут.  
  
 `name`  
 окне Указатель на объект `WCHAR` , содержащий имя атрибута.  
  
 `cData`  
 окне Значение типа `ULONG32` , указывающее размер `data` массива.  
  
 `data`  
 окне Значение атрибута.  
  
## <a name="return-value"></a>Возвращаемое значение  

 S_OK, если метод выполнен. в противном случае E_FAIL или другой код ошибки.  
  
## <a name="requirements"></a>Требования  

 **Заголовок:** Корсим. idl, Корсим. h  
  
## <a name="see-also"></a>См. также

- [Интерфейс ISymUnmanagedWriter](isymunmanagedwriter-interface.md)
