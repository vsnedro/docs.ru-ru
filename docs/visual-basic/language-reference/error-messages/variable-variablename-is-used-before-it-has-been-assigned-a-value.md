---
description: 'Дополнительные сведения о: BC42104: переменная " <variablename> " используется до того, как ей было присвоено значение'
title: Переменная <variablename> используется до того, как ей присвоено значение
ms.date: 07/20/2015
f1_keywords:
- vbc42104
- BC42104
helpviewer_keywords:
- BC42104
ms.assetid: 6909aa0b-b4a1-46f5-a18c-ba3e565c1dd8
ms.openlocfilehash: 501c3e3971c5ca0ebdba6981134f5029b77d0075
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2021
ms.locfileid: "99701499"
---
# <a name="bc42104-variable-variablename-is-used-before-it-has-been-assigned-a-value"></a>BC42104: переменная " \<variablename> " используется до того, как ей было присвоено значение

Переменная " \<variablename> " используется до того, как ей было присвоено значение. Во время выполнения может возникнуть исключение "пустая ссылка".

 Приложение имеет по крайней мере один возможный путь в коде, который считывает переменную, прежде чем ей будет присвоено значение.

 Если переменной никогда не назначалось значение, она содержит значение по умолчанию для своего типа данных. Для ссылочного типа данных значение по умолчанию — [Nothing](../nothing.md). Чтение переменной ссылки, которая имеет значение `Nothing` , в некоторых случаях может привести к исключению <xref:System.NullReferenceException> .

 По умолчанию данное сообщение является предупреждением. Дополнительные сведения о скрытии предупреждений или обработке предупреждений как ошибок см. в разделе [Configuring Warnings in Visual Basic](/visualstudio/ide/configuring-warnings-in-visual-basic).

 **Идентификатор ошибки:** BC42104

## <a name="to-correct-this-error"></a>Исправление ошибки

- Проверьте логику потока управления и убедитесь, что переменная имеет допустимое значение, прежде чем управление передается в любую инструкцию, которая ее считывает.

- Один из способов гарантировать, что переменная всегда имеет допустимое значение, — инициализировать ее как часть объявления. См. раздел "Инициализация" в [операторе Dim](../statements/dim-statement.md).

## <a name="see-also"></a>См. также

- [Оператор Dim](../statements/dim-statement.md)
- [Объявление переменной](../../programming-guide/language-features/variables/variable-declaration.md)
- [Устранение неполадок, связанных с переменными](../../programming-guide/language-features/variables/troubleshooting-variables.md)
