---
title: Невозможно преобразовать значение типа  в
ms.date: 07/20/2015
f1_keywords:
- vbc31194
- bc31194
helpviewer_keywords:
- BC31194
ms.assetid: 03d50c31-addd-4c90-9c53-725b84f9782e
ms.openlocfilehash: f19f157bd4c76f481aa3232bc33c2a0c6ac21367
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/04/2020
ms.locfileid: "84400283"
---
# <a name="value-of-type-type1-cannot-be-converted-to-type2"></a>Невозможно преобразовать значение типа  в
Значение типа "тип1" не может быть преобразовано в "тип2". Свойство "value" можно использовать для получения строкового значения первого элемента " \<parentElement> ".  
  
 Предпринята попытка неявного приведения XML-литерала к определенному типу. XML-литерал не может быть неявно приведен к указанному типу.  
  
 **Идентификатор ошибки:** BC31194  
  
## <a name="to-correct-this-error"></a>Исправление ошибки  
  
- Используйте свойство `Value` XML-литерала для ссылки на его значение как на `String`. Используйте функцию `CType` , другую функцию преобразования типа или класс <xref:System.Convert> для приведения значения к указанному типу.  
  
## <a name="see-also"></a>См. также раздел

- <xref:System.Convert>
- [Type Conversion Functions](../functions/type-conversion-functions.md)
- [XML-литералы](../xml-literals/index.md)
- [XML](../../programming-guide/language-features/xml/index.md)
