---
description: 'Дополнительные сведения о: BC30007: требуется ссылка на сборку " <assemblyname> ", содержащую базовый класс " <classname> "'
title: Требуется ссылка на сборку <assemblyname>, содержащую базовый класс <classname>
ms.date: 07/20/2015
f1_keywords:
- bc30007
- vbc30007
helpviewer_keywords:
- BC30007
ms.assetid: 5f34cf47-6c6e-4954-bd8e-d6b020b75fb7
ms.openlocfilehash: e6d4cf660453078d9a0f9825bc81bb990c1f55b9
ms.sourcegitcommit: 10e719780594efc781b15295e499c66f316068b8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/14/2021
ms.locfileid: "100456891"
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
