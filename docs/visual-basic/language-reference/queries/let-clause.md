---
title: Предложение Let
ms.date: 07/20/2015
f1_keywords:
- vb.QueryLet
helpviewer_keywords:
- queries [Visual Basic], Let
- Let clause [Visual Basic]
- Let statement [Visual Basic]
ms.assetid: 981aa516-16eb-4c53-b1f1-5aa3e82f316e
ms.openlocfilehash: a6ff3fc80a2b6752c61a8b8f7d4ce62b5a46baad
ms.sourcegitcommit: d2db216e46323f73b32ae312c9e4135258e5d68e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/22/2020
ms.locfileid: "90869878"
---
# <a name="let-clause-visual-basic"></a>Предложение Let (Visual Basic)

Выполняет вычисление значения и присваивает его новой переменной в запросе.  
  
## <a name="syntax"></a>Синтаксис  
  
```vb  
Let variable = expression [, ...]  
```  
  
## <a name="parts"></a>Компоненты  
  
|Термин|Определение|  
|---|---|  
|`variable`|Обязательный. Псевдоним, который может использоваться для ссылки на результаты предоставляемого выражения.|  
|`expression`|Обязательный элемент. Выражение, которое будет вычислено и назначено указанной переменной.|  
  
## <a name="remarks"></a>Remarks  

 `Let`Предложение позволяет вычислять значения для каждого результата запроса и ссылаться на них с помощью псевдонима. Псевдоним можно использовать в других предложениях, например в `Where` предложении. `Let`Предложение позволяет создать инструкцию запроса, которая будет проще читать, поскольку можно указать псевдоним для предложения выражения, включенного в запрос, и заменить псевдоним при каждом использовании предложения Expression.  
  
 В предложение можно включить любое количество `variable` `expression` назначений и `Let` . Разделяйте каждое назначение запятой (,).  
  
## <a name="example"></a>Пример  

 В следующем примере кода предложение используется `Let` для расчета скидки на 10% для продуктов.  
  
 [!code-vb[VbSimpleQuerySamples#16](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbSimpleQuerySamples/VB/QuerySamples1.vb#16)]  
  
## <a name="see-also"></a>См. также

- [Introduction to LINQ in Visual Basic](../../programming-guide/language-features/linq/introduction-to-linq.md) (Знакомство с LINQ в Visual Basic)
- [Запросы](index.md)
- [Предложение SELECT](select-clause.md)
- [Предложение FROM](from-clause.md)
- [Предложение WHERE](where-clause.md)
