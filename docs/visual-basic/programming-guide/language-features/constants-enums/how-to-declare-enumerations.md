---
title: Практическое руководство. Объявление перечислений
ms.date: 07/20/2015
helpviewer_keywords:
- declarations [Visual Basic], enumerations
- enumerations [Visual Basic], declaring
- declaring enumerations [Visual Basic]
ms.assetid: db4ca1c3-f429-4c81-ae81-29e0157b29fd
ms.openlocfilehash: 752b425ba32efe41a1ab1aa75de20039d36f5e50
ms.sourcegitcommit: bf5c5850654187705bc94cc40ebfb62fe346ab02
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/23/2020
ms.locfileid: "91058902"
---
# <a name="how-to-declare-enumerations-visual-basic"></a>Практическое руководство. Объявление перечисления (Visual Basic)

Перечисление создается с помощью `Enum` инструкции в разделе Declarations класса или модуля. Нельзя объявить перечисление в методе. Чтобы указать соответствующий уровень доступа, используйте,, `Private` `Protected` `Friend` или `Public` .  
  
 `Enum`Тип имеет имя, базовый тип и набор полей, каждый из которых представляет константу. Имя должно быть допустимым квалификатором Visual Basic .NET. Базовый тип должен быть одним из целочисленных типов — `Byte` , `Short` `Long` или `Integer` . Значение по умолчанию — `Integer`. Перечисления всегда являются строго типизированными и не взаимозаменяемы с целочисленными типами чисел.  
  
 Перечисления не могут иметь значения с плавающей запятой. Если перечислению присвоено значение с плавающей запятой `Option Strict On` , то это приведет к ошибке компилятора. Если `Option Strict` равно `Off` , значение автоматически преобразуется в `Enum` тип.  
  
 Сведения об именах и об использовании `Imports` инструкции для уточнения имен не нужны, см. в разделе [перечисления и квалификация имени](enumerations-and-name-qualification.md).  
  
### <a name="to-declare-an-enumeration"></a>Объявление перечисления  
  
1. Напишите объявление, которое включает уровень доступа кода, `Enum` ключевое слово и допустимое имя, как в следующих примерах, каждый из которых объявляет другой `Enum` .  
  
     [!code-vb[VbEnumsTask#3](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbEnumsTask/VB/Class2.vb#3)]  
  
2. Определите константы в перечислении. По умолчанию первая константа в перечислении инициализируется в `0` , а последующие константы инициализируются значением, которое больше, чем предыдущая константа. Например, следующее перечисление `Days` содержит константу с именем, константу с именем и значением, `Sunday` `0` `Monday` `1` константу с именем `Tuesday` `2` и т. д.  
  
     [!code-vb[VbEnumsTask#4](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbEnumsTask/VB/Class2.vb#4)]  
  
3. Можно явно назначать значения константам в перечислении с помощью оператора присваивания. Можно назначить любое целочисленное значение, включая отрицательные числа. Например, для представления ошибок могут потребоваться константы со значениями меньше нуля. В следующем перечислении константе `Invalid` явно присваивается значение `–1` , а константе `Sunday` присваивается значение `0` . Так как это первая константа в перечислении, она `Saturday` также инициализируется значением `0` . Значение `Monday` равно `1` (на единицу больше, чем значение `Sunday` ); значение `Tuesday` равно `2` и т. д.  
  
     [!code-vb[VbEnumsTask#5](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbEnumsTask/VB/Class2.vb#5)]  
  
### <a name="to-declare-an-enumeration-as-an-explicit-type"></a>Объявление перечисления в явном типе  
  
- Укажите тип перечисления с помощью `As` предложения, как показано в следующем примере.  
  
     [!code-vb[VbEnumsTask#6](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbEnumsTask/VB/Class2.vb#6)]  
  
## <a name="see-also"></a>См. также

- [Перечисления и уточнение имен](enumerations-and-name-qualification.md)
- [Практическое руководство. Ссылка на элемент перечисления](how-to-refer-to-an-enumeration-member.md)
- [Практическое руководство. Перебор элементов перечисления в Visual Basic](how-to-iterate-through-an-enumeration.md)
- [Практическое руководство. Определение строки, связанной со значением из перечисления](how-to-determine-the-string-associated-with-an-enumeration-value.md)
- [Когда следует использовать перечисление](when-to-use-an-enumeration.md)
- [Общие сведения о константах](constants-overview.md)
- [Типы данных констант и литералов](constant-and-literal-data-types.md)
- [Константы и перечисления](../../../language-reference/constants-and-enumerations.md)
