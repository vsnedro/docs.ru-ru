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
ms.openlocfilehash: 4bf832651d9753c41ee5a02defec4adc55af1ff1
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/04/2020
ms.locfileid: "84359765"
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
|`expression`|Обязательный. Выражение, которое будет вычислено и назначено указанной переменной.|  
  
## <a name="remarks"></a>Комментарии  
 `Let`Предложение позволяет вычислять значения для каждого результата запроса и ссылаться на них с помощью псевдонима. Псевдоним можно использовать в других предложениях, например в `Where` предложении. `Let`Предложение позволяет создать инструкцию запроса, которая будет проще читать, поскольку можно указать псевдоним для предложения выражения, включенного в запрос, и заменить псевдоним при каждом использовании предложения Expression.  
  
 В предложение можно включить любое количество `variable` `expression` назначений и `Let` . Разделяйте каждое назначение запятой (,).  
  
## <a name="example"></a>Пример  
 В следующем примере кода предложение используется `Let` для расчета скидки на 10% для продуктов.  
  
 [!code-vb[VbSimpleQuerySamples#16](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbSimpleQuerySamples/VB/QuerySamples1.vb#16)]  
  
## <a name="see-also"></a>См. также раздел

- [Introduction to LINQ in Visual Basic](../../programming-guide/language-features/linq/introduction-to-linq.md) (Знакомство с LINQ в Visual Basic)
- [Запросы](index.md)
- [Предложение SELECT](select-clause.md)
- [Предложение FROM](from-clause.md)
- [Предложение WHERE](where-clause.md)
