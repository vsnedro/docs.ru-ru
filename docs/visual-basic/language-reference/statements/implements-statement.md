---
title: Оператор Implements
ms.date: 07/20/2015
f1_keywords:
- vb.Implements
- Implements
helpviewer_keywords:
- Implements statement [Visual Basic], syntax
- Implements statement [Visual Basic]
- interface implementation [Visual Basic], Implements statement
ms.assetid: 1fafb83f-f55a-4215-8ea9-681e8622613d
ms.openlocfilehash: b982057d2094f807b68d5190dfad388fb9a2c65a
ms.sourcegitcommit: d2db216e46323f73b32ae312c9e4135258e5d68e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/22/2020
ms.locfileid: "90873237"
---
# <a name="implements-statement"></a>Оператор Implements

Указывает один или несколько интерфейсов или элементов интерфейса, которые должны быть реализованы в определении класса или структуры, в котором они отображаются.  
  
## <a name="syntax"></a>Синтаксис  
  
```vb  
Implements interfacename [, ...]  
' -or-  
Implements interfacename.interfacemember [, ...]  
```  
  
## <a name="parts"></a>Компоненты  

 `interfacename`  
 Обязательный элемент. Интерфейс, свойства, процедуры и события которого должны быть реализованы соответствующими элементами в классе или структуре.  
  
 `interfacemember`  
 Обязательный элемент. Член реализуемого интерфейса.  
  
## <a name="remarks"></a>Remarks  

 Интерфейс — это коллекция прототипов, представляющих члены (свойства, процедуры и события), которые инкапсулирует интерфейс. Интерфейсы содержат только объявления для членов; классы и структуры реализуют эти члены. Дополнительные сведения см. в разделе [Интерфейсы](../../programming-guide/language-features/interfaces/index.md).  
  
 `Implements`Оператор должен следовать непосредственно за `Class` `Structure` оператором или.  
  
 При реализации интерфейса необходимо реализовать все члены, объявленные в интерфейсе. Пропуск любого члена считается синтаксической ошибкой. Для реализации отдельного элемента необходимо указать ключевое слово [Implements](implements-clause.md) (отдельно от `Implements` оператора) при объявлении члена в классе или структуре. Дополнительные сведения см. в разделе [Интерфейсы](../../programming-guide/language-features/interfaces/index.md).  
  
 Классы могут использовать [закрытые](../modifiers/private.md) реализации свойств и процедур, но эти члены доступны только путем приведения экземпляра реализующего класса к переменной, объявленной как тип интерфейса.  
  
## <a name="example"></a>Пример  

 В следующем примере показано, как использовать `Implements` инструкцию для реализации членов интерфейса. Он определяет интерфейс с именем `ICustomerInfo` с событием, свойством и процедурой. Класс `customerInfo` реализует все члены, определенные в интерфейсе.  
  
 [!code-vb[VbVbalrStatements#33](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#33)]  
  
 Обратите внимание, что класс `customerInfo` использует `Implements` оператор в отдельной строке исходного кода, чтобы указать, что класс реализует все члены `ICustomerInfo` интерфейса. Затем каждый член класса использует `Implements` ключевое слово как часть его объявления члена, чтобы указать, что он реализует этот член интерфейса.  
  
## <a name="example"></a>Пример  

 В следующих двух процедурах показано, как можно использовать интерфейс, реализованный в предыдущем примере. Чтобы протестировать реализацию, добавьте эти процедуры в проект и вызовите `testImplements` процедуру.  
  
 [!code-vb[VbVbalrStatements#34](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#34)]  
  
## <a name="see-also"></a>См. также

- [Реализации](implements-clause.md)
- [Оператор Interface](interface-statement.md)
- [Интерфейсы](../../programming-guide/language-features/interfaces/index.md)
