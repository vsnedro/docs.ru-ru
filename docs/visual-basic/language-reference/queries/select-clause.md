---
title: Предложение Select
ms.date: 07/20/2015
f1_keywords:
- vb.QuerySelect
helpviewer_keywords:
- Select statement [Visual Basic]
- Select clause [Visual Basic]
- queries [Visual Basic], Select
ms.assetid: 27a3f61c-5960-4692-9b91-4d0c4b6178fe
ms.openlocfilehash: d96423efbee075a7ad257df72471c71e38e09b63
ms.sourcegitcommit: d2db216e46323f73b32ae312c9e4135258e5d68e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/22/2020
ms.locfileid: "90875742"
---
# <a name="select-clause-visual-basic"></a>Предложение Select (Visual Basic)

Определяет результат запроса.  
  
## <a name="syntax"></a>Синтаксис  
  
```vb  
Select [ var1 = ] fieldName1 [, [ var2 = ] fieldName2 [...] ]  
```  
  
## <a name="parts"></a>Компоненты  

 `var1`  
 Необязательный элемент. Псевдоним, который может использоваться для ссылки на результаты выражения столбца.  
  
 `fieldName1`  
 Обязательный элемент. Имя поля, возвращаемого в результате запроса.  
  
## <a name="remarks"></a>Remarks  

 Для `Select` определения результатов, возвращаемых из запроса, можно использовать предложение. Это позволяет либо определить члены нового анонимного типа, созданного запросом, либо целевые элементы именованного типа, возвращаемые запросом. `Select`Предложение не является обязательным для запроса. Если `Select` предложение не указано, запрос возвратит тип, основанный на всех членах переменных диапазона, определенных для текущей области. Дополнительные сведения см. в статье [Анонимные типы](../../programming-guide/language-features/objects-and-classes/anonymous-types.md). Когда запрос создает именованный тип, он вернет результат типа, <xref:System.Collections.Generic.IEnumerable%601> где `T` — это созданный тип.  
  
 `Select`Предложение может ссылаться на любые переменные в текущей области. Сюда входят переменные диапазона, определенные в `From` предложении (или `From` предложениях). Он также включает все новые переменные, созданные с помощью псевдонима `Aggregate` `Let` `Group By` предложениями,, или `Group Join` или переменными из предыдущего `Select` предложения в выражении запроса. `Select`Предложение также может включать статические значения. Например, в следующем примере кода показано выражение запроса, в котором `Select` предложение определяет результат запроса как новый анонимный тип с четырьмя элементами: `ProductName` , `Price` , `Discount` и `DiscountedPrice` . `ProductName` `Price` Значения элементов и берутся из переменной диапазона продукта, определенной в `From` предложении. `DiscountedPrice`Значение элемента вычисляется в `Let` предложении. `Discount`Член является статическим значением.  
  
 [!code-vb[VbSimpleQuerySamples#27](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbSimpleQuerySamples/VB/QuerySamples1.vb#27)]  
  
 `Select`Предложение вводит новый набор переменных диапазона для последующих предложений запроса, а предыдущие переменные диапазона больше не находятся в области. Последнее `Select` предложение в выражении запроса определяет возвращаемое значение запроса. Например, следующий запрос возвращает название компании и идентификатор заказа для каждого заказа клиента, для которого сумма превышает 500. Первое `Select` предложение определяет переменные диапазона для `Where` предложения и второе `Select` предложение. Второе `Select` предложение определяет значения, возвращаемые запросом в виде нового анонимного типа.  
  
 [!code-vb[VbSimpleQuerySamples#28](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbSimpleQuerySamples/VB/QuerySamples1.vb#28)]  
  
 Если `Select` предложение определяет один возвращаемый элемент, выражение запроса возвращает коллекцию типа этого отдельного элемента. Если `Select` предложение определяет несколько возвращаемых элементов, выражение запроса возвращает коллекцию нового анонимного типа на основе выбранных элементов. Например, следующие два запроса возвращают коллекции из двух различных типов на основе `Select` предложения. Первый запрос возвращает коллекцию названий компаний в виде строк. Второй запрос возвращает коллекцию `Customer` объектов, заполненных названиями и адресами компании.  
  
 [!code-vb[VbSimpleQuerySamples#29](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbSimpleQuerySamples/VB/QuerySamples1.vb#29)]  
  
## <a name="example"></a>Пример  

 Следующее выражение запроса использует `From` предложение для объявления переменной диапазона `cust` для `customers` коллекции. `Select`Предложение выбирает имя клиента и значение идентификатора и заполняет `CompanyName` `CustomerID` столбцы и новой переменной диапазона. `For Each`Инструкция циклически перебирает каждый возвращаемый объект и отображает `CompanyName` `CustomerID` столбцы и для каждой записи.  
  
 [!code-vb[VbSimpleQuerySamples#30](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbSimpleQuerySamples/VB/QuerySamples1.vb#30)]  
  
## <a name="see-also"></a>См. также

- [Introduction to LINQ in Visual Basic](../../programming-guide/language-features/linq/introduction-to-linq.md) (Знакомство с LINQ в Visual Basic)
- [Запросы](index.md)
- [Предложение FROM](from-clause.md)
- [Предложение WHERE](where-clause.md)
- [Предложение ORDER BY](order-by-clause.md)
- [Анонимные типы](../../programming-guide/language-features/objects-and-classes/anonymous-types.md)
