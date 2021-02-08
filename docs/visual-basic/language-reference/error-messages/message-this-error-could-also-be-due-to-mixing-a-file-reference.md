---
description: 'Дополнительные сведения о: BC30971. <message> Эта ошибка может также быть вызвана смешением ссылки на файл со ссылкой проекта на сборку<assemblyname>'
title: <message> Эта ошибка может также быть вызвана смешением ссылки на файл и ссылки проекта на сборку <assemblyname>
ms.date: 07/20/2015
f1_keywords:
- bc30971
- vbc30971
helpviewer_keywords:
- BC30971
ms.assetid: 75d2e8b5-2fdc-4623-8b32-cba805dab7db
ms.openlocfilehash: c3b7c27c3f253389cd0a8e725ddcae3816c612b5
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2021
ms.locfileid: "99795850"
---
# <a name="bc30971-message-this-error-could-also-be-due-to-mixing-a-file-reference-with-a-project-reference-to-assembly-assemblyname"></a>BC30971. \<message> Эта ошибка может также быть вызвана смешением ссылки на файл со ссылкой проекта на сборку " \<assemblyname> "

\<message> Эта ошибка может также быть вызвана смешением ссылки на файл со ссылкой проекта на сборку \<assemblyname> . В этом случае попробуйте заменить ссылку на файл " \<assemblyfilename> " в проекте " \<projectname1> " ссылкой проекта на " \<projectname2> ".

 Код в проекте обращается к члену другого проекта, но конфигурация решения не позволяет компилятору Visual Basic разрешить ссылку.

 Для доступа к типу, определенному в другой сборке, компилятор Visual Basic должен иметь ссылку на эту сборку. Это должна быть одна однозначная ссылка, не вызывающая циклических ссылок между проектами.

 **Идентификатор ошибки:** BC30971

## <a name="to-correct-this-error"></a>Исправление ошибки

1. Определите, какой проект создает наиболее подходящую сборку для проекта, чтобы ссылаться на нее в дальнейшем. Для этого можно использовать такие критерии, как простота доступа к файлам и частота обновления.

2. В свойствах проекта добавьте ссылку на проект, содержащий сборку, определяющую используемый тип.

## <a name="see-also"></a>См. также раздел

- [Управление ссылками в проекте](/visualstudio/ide/managing-references-in-a-project)
- [References to Declared Elements](../../programming-guide/language-features/declared-elements/references-to-declared-elements.md)

- [Управление свойствами проектов и решений](/visualstudio/ide/managing-project-and-solution-properties)
- [Troubleshooting Broken References](/visualstudio/ide/troubleshooting-broken-references)
