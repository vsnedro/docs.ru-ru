---
description: 'Дополнительные сведения о: BC30007: требуется ссылка на сборку " <assemblyname> ", содержащую базовый класс<classname>'
title: Требуется ссылка на сборку <assemblyname>, содержащую базовый класс <classname>
ms.date: 07/20/2015
f1_keywords:
- bc30007
- vbc30007
helpviewer_keywords:
- BC30007
ms.assetid: 5f34cf47-6c6e-4954-bd8e-d6b020b75fb7
ms.openlocfilehash: f01795d3e8147015f9f46697b047a8c63099ff32
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2021
ms.locfileid: "99792054"
---
# <a name="bc30007-reference-required-to-assembly-assemblyname-containing-the-base-class-classname"></a>BC30007: требуется ссылка на сборку " \<assemblyname> ", содержащую базовый класс " \<classname> "

Требуется ссылка на сборку " \<assemblyname> ", содержащую базовый класс " \<classname> ". Добавьте эту ссылку в проект.

 Класс определяется в библиотеке динамической компоновки (DLL) или в сборке, на которую в проекте нет прямой ссылки. Компилятору Visual Basic требуется ссылка, чтобы избежать неоднозначности в случае, если класс определен в нескольких библиотеках DLL или сборках.

 **Идентификатор ошибки:** BC30007

## <a name="to-correct-this-error"></a>Исправление ошибки

- Включите в ссылки проекта имя библиотеки DLL или сборки, на которую нет ссылки.

## <a name="see-also"></a>См. также раздел

- [Управление ссылками в проекте](/visualstudio/ide/managing-references-in-a-project)
- [Troubleshooting Broken References](/visualstudio/ide/troubleshooting-broken-references)
