---
description: 'Дополнительные сведения: ссылки и оператор Imports (Visual Basic)'
title: Ссылки и оператор Imports
ms.date: 07/20/2015
helpviewer_keywords:
- assemblies [Visual Basic], namespaces
- references [Visual Basic], assembly
- namespaces [Visual Basic], assemblies
- referencing assemblies
- Imports statement [Visual Basic], referencing assemblies
- assemblies [Visual Basic], references
ms.assetid: 38149bd4-0a6f-4b31-b5f8-94a8c33f1600
ms.openlocfilehash: 3ca685d33f69224a6eea324d7357be4b5203eb45
ms.sourcegitcommit: 10e719780594efc781b15295e499c66f316068b8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/14/2021
ms.locfileid: "100468243"
---
# <a name="references-and-the-imports-statement-visual-basic"></a>Ссылки и оператор Imports (Visual Basic)

Можно сделать внешние объекты доступными для проекта, выбрав команду **Добавить ссылку** в меню **проект** . Ссылки в Visual Basic могут указывать на сборки, которые подобны библиотекам типов, но содержат дополнительные сведения.  
  
## <a name="the-imports-statement"></a>Оператор Imports  

 Сборки включают одно или несколько пространств имен. При добавлении ссылки на сборку можно также добавить `Imports` инструкцию в модуль, управляющий видимостью пространств имен этой сборки в модуле. `Imports`Оператор предоставляет контекст области, который позволяет использовать только часть пространства имен, необходимую для предоставления уникальной ссылки.  
  
 `Imports`Оператор имеет следующий синтаксис:  
  
 `Imports [Aliasname =] Namespace`  
  
 `Aliasname` ссылается на короткое имя, которое можно использовать в коде для ссылки на импортированное пространство имен. `Namespace` — Это пространство имен, доступное через ссылку на проект, через определение в проекте или с помощью предыдущей `Imports` инструкции.  
  
 Модуль может содержать любое количество `Imports` инструкций. Они должны располагаться после любых `Option` операторов, если они есть, но перед любым другим кодом.  
  
> [!NOTE]
> Не путайте ссылки на проект с `Imports` оператором или `Declare` инструкцией. Ссылки проекта делают внешние объекты, такие как объекты в сборках, доступными для Visual Basic проектов. `Imports`Оператор используется для упрощения доступа к ссылкам на проекты, но не предоставляет доступ к этим объектам. `Declare`Оператор используется для объявления ссылки на внешнюю процедуру в библиотеке динамической компоновки (DLL).  
  
## <a name="using-aliases-with-the-imports-statement"></a>Использование псевдонимов с оператором Imports  

 `Imports`Оператор упрощает доступ к методам классов, устраняя необходимость явно вводить полные имена ссылок. Псевдонимы позволяют назначить более дружественное имя только одной части пространства имен. Например, последовательность возврата каретки/перевода строки, которая приводит к отображению одного фрагмента текста на нескольких строках, является частью <xref:Microsoft.VisualBasic.ControlChars> модуля в <xref:Microsoft.VisualBasic?displayProperty=nameWithType> пространстве имен. Чтобы использовать эту константу в программе без псевдонима, необходимо ввести следующий код:  
  
 [!code-vb[VbVbalrApplication#3](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrApplication/VB/Class1.vb#3)]  
  
 `Imports` операторы всегда должны быть первыми строками, непосредственно следующими `Option` за любыми операторами в модуле. В следующем фрагменте кода показано, как импортировать и назначить для модуля псевдоним <xref:Microsoft.VisualBasic.ControlChars?displayProperty=nameWithType> .  
  
 [!code-vb[VbVbalrApplication#4](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrApplication/VB/Class1.vb#4)]  
  
 Дальнейшие ссылки на это пространство имен могут быть значительно короче:  
  
 [!code-vb[VbVbalrApplication#5](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrApplication/VB/Class1.vb#5)]  
  
 Если `Imports` инструкция не включает имя псевдонима, элементы, определенные в импортированном пространстве имен, могут использоваться в модуле без уточнения. Если имя псевдонима указано, оно должно использоваться в качестве квалификатора для имен, содержащихся в этом пространстве имен.  
  
## <a name="see-also"></a>См. также раздел

- <xref:Microsoft.VisualBasic.ControlChars>
- <xref:Microsoft.VisualBasic>
- [Пространства имен в Visual Basic](namespaces.md)
- [Сборки в .NET](../../../standard/assembly/index.md)
- [Оператор Imports (пространство имен .NET и тип)](../../language-reference/statements/imports-statement-net-namespace-and-type.md)
