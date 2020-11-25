---
title: Интерфейс ISymUnmanagedVariable
ms.date: 03/30/2017
api_name:
- ISymUnmanagedVariable
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedVariable
helpviewer_keywords:
- ISymUnmanagedVariable interface [.NET Framework debugging]
ms.assetid: 704c69ba-77bc-40d7-8c0c-400061686321
topic_type:
- apiref
ms.openlocfilehash: 93e1f8eb17f06e42ddb243f88c593979fcb28030
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/24/2020
ms.locfileid: "95733286"
---
# <a name="isymunmanagedvariable-interface"></a>Интерфейс ISymUnmanagedVariable

Представляет переменную, например параметр, локальную переменную или поле.  
  
## <a name="methods"></a>Методы  
  
|Метод|Описание|  
|------------|-----------------|  
|[Метод GetAddressField1](isymunmanagedvariable-getaddressfield1-method.md)|Возвращает первое поле адреса для этой переменной. Его значение зависит от типа адреса.|  
|[Метод GetAddressField2](isymunmanagedvariable-getaddressfield2-method.md)|Получает второе поле адреса для этой переменной. Его значение зависит от типа адреса.|  
|[Метод GetAddressField3](isymunmanagedvariable-getaddressfield3-method.md)|Возвращает третье поле адреса для этой переменной. Его значение зависит от типа адреса.|  
|[Метод GetAddressKind](isymunmanagedvariable-getaddresskind-method.md)|Возвращает тип адреса этой переменной.|  
|[Метод GetAttributes](isymunmanagedvariable-getattributes-method.md)|Возвращает флаги атрибута для этой переменной.|  
|[Метод GetEndOffset](isymunmanagedvariable-getendoffset-method.md)|Возвращает конечное смещение данной переменной в родительском объекте.|  
|[Метод GetName](isymunmanagedvariable-getname-method.md)|Возвращает имя этой переменной.|  
|[Метод GetSignature](isymunmanagedvariable-getsignature-method.md)|Возвращает сигнатуру этой переменной.|  
|[Метод GetStartOffset](isymunmanagedvariable-getstartoffset-method.md)|Возвращает начальное смещение этой переменной в родительском элементе.|  
  
## <a name="requirements"></a>Требования  

 **Заголовок:** Корсим. idl, Корсим. h  
  
## <a name="see-also"></a>См. также раздел

- [Интерфейсы хранилища символов диагностики](diagnostics-symbol-store-interfaces.md)
