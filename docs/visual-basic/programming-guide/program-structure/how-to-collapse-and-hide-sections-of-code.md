---
description: Дополнительные сведения о том, как сворачивать и скрывать разделы кода (Visual Basic).
title: Практическое руководство. Сворачивание и скрытие частей кода
ms.date: 07/20/2015
helpviewer_keywords:
- Visual Basic, code collapsing
- Visual Basic, code hiding
- Visual Basic code, collapsing and hiding
ms.assetid: b770e8f5-e07d-491a-ab4b-a977980f9ba2
ms.openlocfilehash: b93a2190bd6266c6f9fa5cb06eb249ca174c8067
ms.sourcegitcommit: 10e719780594efc781b15295e499c66f316068b8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/14/2021
ms.locfileid: "100475972"
---
# <a name="how-to-collapse-and-hide-sections-of-code-visual-basic"></a>Практическое руководство. Сворачивание и скрытие частей кода (Visual Basic)

`#Region`Директива позволяет сворачивать и скрывать разделы кода в файлах Visual Basic. `#Region`Директива позволяет указать блок кода, который можно развернуть или свернуть при использовании редактора кода Visual Studio. Возможность скрывать код выборочно делает файлы более управляемыми и удобочитаемыми. Дополнительные сведения см. в разделе [Структура](/visualstudio/ide/outlining).

`#Region` директивы поддерживают семантику блока кода, такую как `#If...#End If` . Это означает, что они не могут начинаться в одном блоке и заканчиваться другим; Начало и конец должны находиться в одном блоке. `#Region` директивы не поддерживаются в функциях.

## <a name="to-collapse-and-hide-a-section-of-code"></a>Сворачивание и скрытие раздела кода

Поместите раздел кода между `#Region` `#End Region` операторами и, как показано в следующем примере:

[!code-vb[VbVbalrConditionalComp#6](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrConditionalComp/VB/Class1.vb#6)]

Этот `#Region` блок можно использовать несколько раз в файле кода, поэтому пользователи могут определять собственные блоки процедур и классов, которые, в свою очередь, могут быть свернуты. `#Region` блоки также могут быть вложены в другие `#Region` блоки.

> [!NOTE]
> Скрытие кода не мешает его компиляции и не влияет на `#If...#End If` инструкции.

## <a name="see-also"></a>См. также раздел

- [Условная компиляция](conditional-compilation.md)
- [Директива #Region](../../language-reference/directives/region-directive.md)
- [Директивы #If...Then...#Else](../../language-reference/directives/if-then-else-directives.md)
- [Структура](/visualstudio/ide/outlining)
