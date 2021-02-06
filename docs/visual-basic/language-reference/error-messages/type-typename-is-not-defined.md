---
description: 'Дополнительные сведения о: BC30002: тип " <typename> " не определен'
title: Тип <typename> не определен
ms.date: 07/20/2015
f1_keywords:
- vbc30002
- bc30002
helpviewer_keywords:
- BC30002
ms.assetid: b0faf204-57fd-44de-8c05-9db027eea663
ms.openlocfilehash: 48ee0c38492769aea8c1be2e9d54eaa537e35766
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2021
ms.locfileid: "99641128"
---
# <a name="bc30002-type-typename-is-not-defined"></a>BC30002: тип " \<typename> " не определен

Оператор выполнил ссылку на тип, который не был определен. Тип можно определить в операторе объявления, например,, `Enum` `Structure` `Class` или `Interface` .

 **Идентификатор ошибки:** BC30002

## <a name="to-correct-this-error"></a>Исправление ошибки

- Убедитесь, что определение типа и его ссылка используют одинаковое написание.

- Убедитесь, что определение типа доступно для ссылки. Например, если тип находится в другом модуле и был объявлен `Private` , переместите определение типа в ссылающийся модуль или объявите его `Public` .

- Убедитесь, что пространство имен типа не переопределено в проекте. Если это так, используйте `Global` ключевое слово, чтобы полностью определить имя типа. Например, если проект определяет пространство имен с именем `System` , доступ к этому <xref:System.Object?displayProperty=nameWithType> типу невозможен, если он не является полным с `Global` ключевым словом: `Global.System.Object` .

- Если тип определен, но библиотека объектов или библиотека типов, в которой он определен, не зарегистрирована в Visual Basic, щелкните **Добавить ссылку** в меню **проект** , а затем выберите соответствующую библиотеку объектов или библиотеку типов.

- Убедитесь, что тип находится в сборке, которая является частью целевого платформа .NET Framework профиля. Дополнительные сведения см. в разделе [Устранение неполадок, связанных с настройкой для определенных версий платформы .NET Framework](/visualstudio/msbuild/troubleshooting-dotnet-framework-targeting-errors).

## <a name="see-also"></a>См. также

- [Пространства имен в Visual Basic](../../programming-guide/program-structure/namespaces.md)
- [Оператор Enum](../statements/enum-statement.md)
- [Оператор Structure](../statements/structure-statement.md)
- [Оператор Class](../statements/class-statement.md)
- [Оператор Interface](../statements/interface-statement.md)
- [Управление ссылками в проекте](/visualstudio/ide/managing-references-in-a-project)
