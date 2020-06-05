---
title: Операторы сравнения
ms.date: 07/20/2015
f1_keywords:
- vb.<>
- vb.>=
- vb.<=
- vb.>
- vb.<
helpviewer_keywords:
- greater than or equal to operator [Visual Basic]
- '>= operator [Visual Basic]'
- = operator [Visual Basic]
- < operator [Visual Basic]
- less than operator [Visual Basic]
- relational operators [Visual Basic], syntax
- Like operator [Visual Basic]
- <> operator [Visual Basic]
- '> operator [Visual Basic]'
- equal operator [Visual Basic]
- less than or equal to operator [Visual Basic]
- symbols, operators
- greater than operator [Visual Basic]
- comparing values [Visual Basic]
- operators [Visual Basic], relational
- string comparison [Visual Basic]
- not equal to comparison operator [Visual Basic]
- <= operator [Visual Basic]
- operators [Visual Basic], comparison
- Is operator [Visual Basic]
- comparison operators [Visual Basic], Visual Basic
ms.assetid: d6cb12a8-e52e-46a7-8aaf-f804d634a825
ms.openlocfilehash: bcd51d70c5c7bd08991c7433e244316a82daa9da
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/04/2020
ms.locfileid: "84371795"
---
# <a name="comparison-operators-visual-basic"></a>Операторы сравнения (Visual Basic)
Ниже приведены операторы сравнения, определенные в Visual Basic.

 `<`станции

 `<=`станции

 `>`станции

 `>=`станции

 `=`станции

 `<>`станции

 [Оператор is](is-operator.md)

 [Оператор IsNot](isnot-operator.md)

 [Оператор Like](like-operator.md)

 Эти операторы сравнивают два выражения, чтобы определить, равны ли они, и если нет, то их отличия. `Is`, `IsNot` и `Like` подробно обсуждаются на отдельных страницах справки. Реляционные операторы сравнения подробно обсуждаются на этой странице.

## <a name="syntax"></a>Синтаксис
  
```vb
result = expression1 comparisonoperator expression2  
result = object1 [Is | IsNot] object2  
result = string Like pattern  
```  
  
## <a name="parts"></a>Компоненты
 `result`  
 Обязательный. `Boolean`Значение, представляющее результат сравнения.

 `expression1`, `expression2`  
 Обязательный. Любое выражение.

 `comparisonoperator`  
 Обязательный. Любой оператор реляционного сравнения.

 `object1`, `object2`  
 Обязательный. Имена ссылочных объектов.

 `string`  
 Обязательный. Произвольное выражение `String` .

 `pattern`  
 Обязательный. Любое `String` выражение или диапазон символов.

## <a name="remarks"></a>Комментарии
 В следующей таблице содержится список реляционных операторов сравнения и условий, определяющих, `result` является ли `True` `False` .

|Оператор|`True`, если|`False`, если|
|--------------|---------------|----------------|
|`<`(Меньше)|`expression1` < `expression2`|`expression1` >= `expression2`|
|`<=`(Меньше или равно)|`expression1` <= `expression2`|`expression1` > `expression2`|
|`>`(Больше)|`expression1` > `expression2`|`expression1` <= `expression2`|
|`>=`(Больше или равно)|`expression1` >= `expression2`|`expression1` < `expression2`|
|`=`(Равно)|`expression1` = `expression2`|`expression1` <> `expression2`|
|`<>`(Не равно)|`expression1` <> `expression2`|`expression1` = `expression2`|

> [!NOTE]
> [Оператор =](assignment-operator.md) также используется в качестве оператора присваивания.

 `Is`Оператор, `IsNot` оператор и `Like` оператор имеют специальные функции сравнения, отличные от операторов в предыдущей таблице.

## <a name="comparing-numbers"></a>Сравнение чисел
 При сравнении выражения типа `Single` с одним из типов `Double` `Single` выражение преобразуется в `Double` . Это поведение противоположено поведению, обнаруженному в Visual Basic 6.

 Аналогично, при сравнении выражения типа `Decimal` с выражением типа `Single` или `Double` `Decimal` выражение преобразуется в тип `Single` или `Double` . Для `Decimal` выражений любое значение дробной части меньше 1E-28 может быть потеряно. Такая утрата дробных значений может привести к тому, что два значения будут сравниваться как равные, если это не так. По этой причине следует соблюдать осторожность при использовании равенства ( `=` ) для сравнения двух переменных с плавающей запятой. Безопаснее проверить, является ли абсолютное значение разницы между двумя числами меньше, чем небольшая допустимая погрешность.

### <a name="floating-point-imprecision"></a>Точность чисел с плавающей запятой
 При работе с числами с плавающей запятой следует помнить, что они не всегда имеют точное представление в памяти. Это может привести к непредвиденным результатам некоторых операций, таких как сравнение значений и [оператор Mod](mod-operator.md). Дополнительные сведения см. в разделе [Устранение неполадок типов данных](../../programming-guide/language-features/data-types/troubleshooting-data-types.md).

## <a name="comparing-strings"></a>Сравнение строк
 При сравнении строк строковые выражения оцениваются на основе их порядка сортировки в алфавитном порядке, который зависит от `Option Compare` параметра.

 `Option Compare Binary`базовые сравнения строк в порядке сортировки, производном от внутренних двоичных представлений символов. Порядок сортировки определяется кодовой страницей. В следующем примере показан типичный порядок двоичной сортировки.

 `A < B < E < Z < a < b < e < z < À < Ê < Ø < à < ê < ø`

 `Option Compare Text`сравнения строк при сравнении без учета регистра, порядок сортировки текста определяется языковым стандартом приложения. При задании `Option Compare Text` и сортировке символов в предыдущем примере применяется следующий порядок сортировки текста:

 `(A=a) < (À= à) < (B=b) < (E=e) < (Ê= ê) < (Ø = ø) < (Z=z)`

### <a name="locale-dependence"></a>Зависимость от локали
 При установке `Option Compare Text` результат сравнения строк может зависеть от языкового стандарта, в котором выполняется приложение. Два символа могут сравниваться как одинаковые в одном языковом стандарте, но не в другом. Если вы используете сравнение строк для принятия важных решений, например, принимаете ли вы попытку входа в систему, вы должны быть извещены о конфиденциальности языкового стандарта. Рекомендуется либо задать `Option Compare Binary` , либо вызвать метод <xref:Microsoft.VisualBasic.Strings.StrComp%2A> , который учитывает языковой стандарт.

## <a name="typeless-programming-with-relational-comparison-operators"></a>Программирование без типов с помощью реляционных операторов сравнения
 Использование реляционных операторов сравнения с `Object` выражениями не допускается в `Option Strict On` . Если `Option Strict` имеет значение `Off` , а `expression1` либо `expression2` является `Object` выражением, типы времени выполнения определяют, как они сравниваются. В следующей таблице показано, как сравниваются выражения и результат сравнения, в зависимости от типа операндов среды выполнения.

|Если операнды|Сравнение:|
|---------------------|-------------------|
|Как`String`|Сравнение сортировки на основе характеристик сортировки строк.|
|Оба числовых|Объекты, преобразованные в `Double` , числовое сравнение.|
|Один числовой и один`String`|`String`Преобразуется в `Double` и выполняется числовое сравнение. Если объект `String` не может быть преобразован в `Double` , <xref:System.InvalidCastException> создается исключение.|
|Один или оба являются ссылочными типами, отличными от`String`|Возникает исключение <xref:System.InvalidCastException>.|

 Числовые сравнения обрабатываются `Nothing` как 0. Сравнения строк обрабатываются `Nothing` как `""` (пустая строка).

## <a name="overloading"></a>Перегрузка
 Реляционные операторы сравнения ( `<` . `<=`, `>` , `>=` , `=` , `<>` ) могут быть *перегружены*. Это означает, что класс или структура могут переопределять их поведение, когда операнд имеет тип этого класса или структуры. Если в коде используются какие-либо из этих операторов в таком классе или структуре, убедитесь, что вы понимаете переопределенное поведение. Для получения дополнительной информации см. [Operator Procedures](../../programming-guide/language-features/procedures/operator-procedures.md).

 Обратите внимание, что [оператор =](assignment-operator.md) можно перегружать только как оператор реляционного сравнения, а не как оператор присваивания.

## <a name="example"></a>Пример
 В следующем примере показаны различные варианты использования реляционных операторов сравнения, которые используются для сравнения выражений. Реляционные операторы сравнения возвращают `Boolean` результат, который представляет, принимает ли указанное выражение значение `True` . При применении `>` `<` операторов and к строкам сравнение выполняется с использованием обычного алфавитного порядка сортировки строк. Этот порядок может зависеть от настроек языкового стандарта. Учитывается ли сортировка с учетом регистра или не зависит от параметра [параметра Compare](../statements/option-compare-statement.md) .

 [!code-vb[VbVbalrOperators#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#1)]

 В предыдущем примере первое сравнение возвращает, `False` а оставшиеся сравнения возвращают `True` .

## <a name="see-also"></a>См. также раздел

- <xref:System.InvalidCastException>
- [Оператор =](assignment-operator.md)
- [Порядок применения операторов в Visual Basic](operator-precedence.md)
- [Список операторов, сгруппированных по функциональному назначению](operators-listed-by-functionality.md)
- [Устранение неполадок, связанных с типами данных](../../programming-guide/language-features/data-types/troubleshooting-data-types.md)
- [Comparison Operators in Visual Basic](../../programming-guide/language-features/operators-and-expressions/comparison-operators.md)
