---
title: Практическое руководство. Объявление константы
ms.date: 07/20/2015
f1_keywords:
- vb.constant
helpviewer_keywords:
- Integer data type [Visual Basic], declaring constants
- Single data type [Visual Basic], declaring constants
- Const statement [Visual Basic], declaring constants
- procedures [Visual Basic], declaration
- data types [Visual Basic], constants
- Long data type [Visual Basic], declaring constants
- Visual Basic code, declaring variables and constants
- Double data type [Visual Basic], declaring constants
- Boolean data type [Visual Basic], declaring constants
- modules, declaring constants
- Byte data type [Visual Basic], declaring constants
- constants [Visual Basic], declaring
- Date data type [Visual Basic], declaring constants
- String data type [Visual Basic], declaring constants
- declaring constants [Visual Basic], const keyword
- Currency data type [Visual Basic], declaring constants and variants
- module-level constants and variables
- Object data type [Visual Basic], declaring constants
ms.assetid: f901b4fa-481f-4621-822e-427060577ad1
ms.openlocfilehash: 138dd58dac9d1983e35e61f8b98a77810fc6e38b
ms.sourcegitcommit: bf5c5850654187705bc94cc40ebfb62fe346ab02
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/23/2020
ms.locfileid: "91058850"
---
# <a name="how-to-declare-a-constant-visual-basic"></a>Практическое руководство. Объявление константы (Visual Basic)

Используйте оператор, `Const` чтобы объявить константу и задать ее значение. Объявляя константу, можно присвоить значение понятному имени. После объявления константы ее нельзя изменить или присвоить ей новое значение.  
  
 Константа объявляется в процедуре или в разделе объявлений модуля, класса или структуры. Константы уровня класса или структуры `Private` по умолчанию, но также могут быть объявлены как `Public` , `Friend` , `Protected` или `Protected Friend` для соответствующего уровня доступа к коду.  
  
 Константа должна иметь допустимое символьное имя (правила совпадают с правилами для создания имен переменных) и выражение, состоящее из числовых или строковых констант и операторов (но не для вызовов функций).  
  
[!INCLUDE[note_settings_general](~/includes/note-settings-general-md.md)]  
  
### <a name="to-declare-a-constant"></a>Объявление константы  
  
- Напишите объявление, включающее описатель доступа, `Const` ключевое слово и выражение, как показано в следующих примерах:  
  
     [!code-vb[VbEnumsTask#8](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbEnumsTask/VB/Class2.vb#8)]  
  
     Если [параметр Infer](../../../language-reference/statements/option-infer-statement.md) имеет значение `Off` и [Option строго](../../../language-reference/statements/option-strict-statement.md) имеет значение `On` , необходимо явно объявить константу, указав тип данных (,,,,,,,,, `Boolean` `Byte` `Char` `DateTime` `Decimal` `Double` `Integer` `Long` `Short` `Single` или `String` ).  
  
     Если `Option Infer` имеет значение `On` или `Option Strict` является `Off` , можно объявить константу без указания типа данных с `As` предложением. Компилятор определяет тип константы на основе типа выражения. Дополнительные сведения см. в разделе [константные и литеральные типы данных](constant-and-literal-data-types.md).  
  
### <a name="to-declare-a-constant-that-has-an-explicitly-stated-data-type"></a>Объявление константы с явно указанным типом данных  
  
- Напишите объявление, включающее `As` ключевое слово и явный тип данных, как показано в следующих примерах:  
  
     [!code-vb[VbEnumsTask#9](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbEnumsTask/VB/Class2.vb#9)]  
  
     В одной строке можно объявить несколько констант, хотя код более удобен для чтения, если объявить только одну константу в строке. При объявлении нескольких констант в одной строке все они должны иметь одинаковый уровень доступа ( `Public` ,,, `Private` `Friend` `Protected` или `Protected Friend` ).  
  
### <a name="to-declare-multiple-constants-on-a-single-line"></a>Объявление нескольких констант в одной строке  
  
- Разделяйте объявления запятыми и пробелами, как показано в следующем примере:  
  
    ```vb  
    Public Const Four As Integer = 4, Five As Integer = 5, Six As Integer = 44  
    ```  
  
## <a name="see-also"></a>См. также

- [Оператор Const](../../../language-reference/statements/const-statement.md)
- [Типы данных констант и литералов](constant-and-literal-data-types.md)
- [Общие сведения о константах](constants-overview.md)
- [Практическое руководство. Объявление константы](how-to-declare-a-constant.md)
- [Константы, определенные пользователем](user-defined-constants.md)
- [Типы данных констант и литералов](constant-and-literal-data-types.md)
- [Практическое руководство. Группирование значений связанных констант](how-to-group-related-constant-values-together.md)
- [Общие сведения о перечислениях](enumerations-overview.md)
- [Практическое руководство. Объявление перечислений](how-to-declare-enumerations.md)
- [Практическое руководство. Ссылка на элемент перечисления](how-to-refer-to-an-enumeration-member.md)
- [Перечисления и уточнение имен](enumerations-and-name-qualification.md)
- [Практическое руководство. Перебор элементов перечисления](how-to-iterate-through-an-enumeration.md)
- [Практическое руководство. Определение строки, связанной со значением из перечисления](how-to-determine-the-string-associated-with-an-enumeration-value.md)
- [Когда следует использовать перечисление](when-to-use-an-enumeration.md)

- [Общие сведения о перечислениях](enumerations-overview.md)
- [Общие сведения о константах](constants-overview.md)
- [Практическое руководство. Объявление перечисления](how-to-declare-enumerations.md)
- [Перечисления и уточнение имен](enumerations-and-name-qualification.md)
- [Оператор Option Strict](../../../language-reference/statements/option-strict-statement.md)
- [Константы и перечисления](../../../language-reference/constants-and-enumerations.md)
