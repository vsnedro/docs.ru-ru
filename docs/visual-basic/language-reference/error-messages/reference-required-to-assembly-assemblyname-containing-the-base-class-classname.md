---
title: Требуется ссылка на сборку <assemblyname>, содержащую базовый класс <classname>
ms.date: 07/20/2015
f1_keywords:
- bc30007
- vbc30007
helpviewer_keywords:
- BC30007
ms.assetid: 5f34cf47-6c6e-4954-bd8e-d6b020b75fb7
ms.openlocfilehash: 07c09d0dfcb374b974fbda9099c4e85d6d054753
ms.sourcegitcommit: d2db216e46323f73b32ae312c9e4135258e5d68e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/22/2020
ms.locfileid: "90870905"
---
# <a name="reference-required-to-assembly-assemblyname-containing-the-base-class-classname"></a>Требуется ссылка на сборку \<assemblyname>, содержащую базовый класс \<classname>

Требуется ссылка на сборку " \<assemblyname> ", содержащую базовый класс " \<classname> ". Добавьте эту ссылку в проект.  
  
 Класс определяется в библиотеке динамической компоновки (DLL) или в сборке, на которую в проекте нет прямой ссылки. Компилятору Visual Basic требуется ссылка, чтобы избежать неоднозначности в случае, если класс определен в нескольких библиотеках DLL или сборках.  
  
 **Идентификатор ошибки:** BC30007  
  
## <a name="to-correct-this-error"></a>Исправление ошибки  
  
- Включите в ссылки проекта имя библиотеки DLL или сборки, на которую нет ссылки.  
  
## <a name="see-also"></a>См. также

- [Управление ссылками в проекте](/visualstudio/ide/managing-references-in-a-project)
- [Troubleshooting Broken References](/visualstudio/ide/troubleshooting-broken-references)
