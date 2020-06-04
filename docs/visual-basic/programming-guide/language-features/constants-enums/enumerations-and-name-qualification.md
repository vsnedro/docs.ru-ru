---
title: Перечисления и уточнение имен
ms.date: 07/20/2015
helpviewer_keywords:
- declarations [Visual Basic], enumerations
- Imports statement [Visual Basic], namespace declarations
- declaring namespaces [Visual Basic], enumerations
- name collisions
- ambiguous names [Visual Basic], enumerations
- enumerations [Visual Basic], name qualification
- names [Visual Basic], avoiding conflicts
- namespaces [Visual Basic], declaring
- naming conflicts, enumerations
- naming conflicts, qualifying names
- declaring enumerations
- references [Visual Basic], enumeration members
- naming conventions [Visual Basic], naming conflicts
- declarations [Visual Basic], namespaces
ms.assetid: 08ba2738-df52-4140-bc55-f57c871c9b73
ms.openlocfilehash: 4b09284b8282c481e406050d37cbdb2f3c8686bc
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/04/2020
ms.locfileid: "84414509"
---
# <a name="enumerations-and-name-qualification-visual-basic"></a>Перечисления и уточнение имен (Visual Basic)
Обычно при ссылке на член перечисления необходимо уточнить имя члена с помощью имени перечисления. Например, для ссылки на `Sunday` член `Days` перечисления используется следующий синтаксис:  
  
 [!code-vb[VbEnumsTask#18](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbEnumsTask/VB/Class2.vb#18)]  
  
## <a name="using-the-imports-statement"></a>Использование оператора Imports  
 Можно избежать использования полных имен, добавив `Imports` инструкцию в раздел кода объявлений пространств имен, как показано в следующем примере:  
  
 [!code-vb[VbEnumsTask#22](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbEnumsTask/VB/Class1.vb#22)]  
  
 `Imports`Оператор импортирует имена пространств имен из проектов и сборок, на которые имеются ссылки, и из того же проекта, в котором находится модуль, в котором находится инструкция. После добавления этой инструкции можно ссылаться на члены перечисления без уточнения, как показано в следующем примере:  
  
 [!code-vb[VbEnumsTask#24](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbEnumsTask/VB/Class1.vb#24)]  
  
 Организуя наборы связанных констант в перечисления, можно использовать одни и те же имена констант в разных контекстах. Например, можно использовать те же имена для констант дня недели в `Days` `WorkDays` перечислениях и. При использовании `Imports` оператора с перечислениями необходимо избегать неоднозначных ссылок. Рассмотрим следующий пример.  
  
 [!code-vb[VbEnumsTask#22](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbEnumsTask/VB/Class1.vb#22)]  
  
 [!code-vb[VbEnumsTask#25](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbEnumsTask/VB/Class1.vb#25)]  
  
 Если предположить, что `Monday` является членом `Days` перечисления и `Workdays` перечисления, этот код создает ошибку компилятора. Чтобы избежать неоднозначных ссылок при ссылке на отдельную константу, уточните имя константы с его перечислением. Следующий код ссылается на `Saturday` константы в `Days` `WorkDays` перечислениях и.  
  
 [!code-vb[VbEnumsTask#32](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbEnumsTask/VB/Class2.vb#32)]  
  
## <a name="see-also"></a>См. также раздел

- [Константы и перечисления](../../../language-reference/constants-and-enumerations.md)
- [Практическое руководство. Объявление перечисления](how-to-declare-enumerations.md)
- [Практическое руководство. Ссылка на элемент перечисления](how-to-refer-to-an-enumeration-member.md)
- [Практическое руководство. Перебор элементов перечисления в Visual Basic](how-to-iterate-through-an-enumeration.md)
- [Практическое руководство. Определение строки, связанной со значением из перечисления](how-to-determine-the-string-associated-with-an-enumeration-value.md)
- [Когда следует использовать перечисление](when-to-use-an-enumeration.md)
- [Типы данных констант и литералов](constant-and-literal-data-types.md)
- [Оператор Enum](../../../language-reference/statements/enum-statement.md)
- [Оператор Imports (пространство имен .NET и тип)](../../../language-reference/statements/imports-statement-net-namespace-and-type.md)
- [Типы данных](../../../language-reference/data-types/index.md)
