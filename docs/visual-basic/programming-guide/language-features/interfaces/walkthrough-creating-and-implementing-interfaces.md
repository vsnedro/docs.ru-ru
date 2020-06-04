---
title: Создание и реализация интерфейсов
ms.date: 07/20/2015
helpviewer_keywords:
- interfaces [Visual Basic], walkthroughs
- interfaces [Visual Basic], testing
- interface implementation [Visual Basic], walkthrough
- interfaces [Visual Basic], creating
ms.assetid: ded82af2-9f52-4232-98ef-fe458180f112
ms.openlocfilehash: 89e8f91a04b25b84bc783d5c4f4b91cf12426f72
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/04/2020
ms.locfileid: "84405071"
---
# <a name="walkthrough-creating-and-implementing-interfaces-visual-basic"></a>Пошаговое руководство. Создание и реализация интерфейсов (Visual Basic)

Интерфейсы описывают характеристики свойств, методов и событий, но не содержат сведений о реализации до структур или классов.  
  
 В этом пошаговом руководстве показано, как объявить и реализовать интерфейс.  
  
> [!NOTE]
> В этом пошаговом руководстве не содержатся сведения о создании пользовательского интерфейса.  
  
[!INCLUDE[note_settings_general](~/includes/note-settings-general-md.md)]  
  
## <a name="to-define-an-interface"></a>Определение интерфейса
  
1. Откройте новый проект приложения Windows на Visual Basic.  
  
2. Добавьте в проект новый модуль, выбрав в меню **проект** пункт **Добавить модуль** .  
  
3. Присвойте новому модулю имя `Module1.vb` и нажмите кнопку **Добавить**. Отобразится код для нового модуля.  
  
4. Определите интерфейс с именем `TestInterface` в `Module1` , введя `Interface TestInterface` между `Module` `End Module` операторами и, а затем нажав клавишу ВВОД. **Редактор кода** смещает `Interface` ключевое слово и добавляет `End Interface` оператор для формирования блока кода.  
  
5. Определите свойство, метод и событие для интерфейса, поместив следующий код между `Interface` `End Interface` операторами и:  
  
     [!code-vb[VbVbalrOOP#98](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOOP/VB/OOP.vb#98)]
  
## <a name="implementation"></a>Реализация

 Вы можете заметить, что синтаксис, используемый для объявления членов интерфейса, отличается от синтаксиса, используемого для объявления членов класса. Это различие отражает тот факт, что интерфейсы не могут содержать код реализации.  
  
### <a name="to-implement-the-interface"></a>Реализация интерфейса
  
1. Добавьте класс с именем, `ImplementationClass` добавив следующий оператор в `Module1` , после `End Interface` оператора, но перед `End Module` оператором, а затем нажав клавишу ВВОД:  
  
     [!code-vb[VbVbalrOOP#99](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOOP/VB/OOP.vb#99)]
  
     При работе в интегрированной среде разработки **Редактор кода** предоставляет соответствующий `End Class` оператор при нажатии клавиши ВВОД.  
  
2. Добавьте следующий `Implements` оператор в `ImplementationClass` , который именует интерфейс, реализуемый классом:  
  
     [!code-vb[VbVbalrOOP#100](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOOP/VB/OOP.vb#100)]
  
     При указании отдельно от других элементов в верхней части класса или структуры `Implements` оператор указывает, что класс или структура реализуют интерфейс.  
  
     При работе в интегрированной среде разработки **Редактор кода** реализует члены класса, необходимые `TestInterface` при нажатии клавиши ВВОД, и вы можете пропустить следующий шаг.  
  
3. Если вы не работаете в интегрированной среде разработки, необходимо реализовать все члены интерфейса `MyInterface` . Добавьте следующий код в `ImplementationClass` для реализации `Event1` , `Method1` и `Prop1` :  
  
     [!code-vb[VbVbalrOOP#101](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOOP/VB/OOP.vb#101)]
  
     `Implements`Оператор именует интерфейс и член интерфейса, который реализуется.  
  
4. Завершите определение `Prop1` , добавив закрытое поле в класс, который сохранил значение свойства:  
  
     [!code-vb[VbVbalrOOP#102](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOOP/VB/OOP.vb#102)]
  
     Возврат значения `pval` из метода доступа get свойства.  
  
     [!code-vb[VbVbalrOOP#103](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOOP/VB/OOP.vb#103)]
  
     Задайте значение `pval` в методе доступа к набору свойств.  
  
     [!code-vb[VbVbalrOOP#104](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOOP/VB/OOP.vb#104)]
  
5. Завершите определение `Method1` , добавив следующий код.  
  
     [!code-vb[VbVbalrOOP#105](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOOP/VB/OOP.vb#105)]
  
### <a name="to-test-the-implementation-of-the-interface"></a>Тестирование реализации интерфейса
  
1. Щелкните правой кнопкой мыши форму запуска проекта в **Обозреватель решений**и выберите пункт **Просмотреть код**. Редактор отображает класс для начальной формы. По умолчанию вызывается форма запуска `Form1` .  
  
2. Добавьте в `testInstance` класс следующее поле `Form1` :  
  
     [!code-vb[VbVbalrOOP#120](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOOP/VB/OOP.vb#120)]
  
     Если объявить `testInstance` как `WithEvents` , `Form1` класс может управлять его событиями.  
  
3. Добавьте следующий обработчик событий в `Form1` класс для обработки событий, вызванных `testInstance` :  
  
     [!code-vb[VbVbalrOOP#106](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOOP/VB/OOP.vb#106)]
  
4. Добавьте подпрограммы с именем `Test` в `Form1` класс для проверки класса реализации:  
  
     [!code-vb[VbVbalrOOP#107](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOOP/VB/OOP.vb#107)]
  
     `Test`Процедура создает экземпляр класса, реализующего `MyInterface` , присваивает этот экземпляр `testInstance` полю, устанавливает свойство и запускает метод через интерфейс.  
  
5. Добавьте код для вызова `Test` процедуры из `Form1 Load` процедуры формы запуска:  
  
     [!code-vb[VbVbalrOOP#108](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOOP/VB/OOP.vb#108)]
  
6. Выполните `Test` процедуру, нажав клавишу F5. Отображается сообщение «Prop1 имело значение 9». После нажатия кнопки ОК отображается сообщение "параметр X для Method1 равен 5". Нажмите кнопку ОК, после чего появится сообщение "обработчик событий захватил событие".  
  
## <a name="see-also"></a>См. также раздел

- [Оператор Implements](../../../language-reference/statements/implements-statement.md)
- [Интерфейсы](index.md)
- [Оператор Interface](../../../language-reference/statements/interface-statement.md)
- [Оператор Event](../../../language-reference/statements/event-statement.md)
