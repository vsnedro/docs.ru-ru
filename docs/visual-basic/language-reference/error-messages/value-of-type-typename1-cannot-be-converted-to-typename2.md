---
description: 'Дополнительные сведения о: BC30955: значение типа " <typename1> " не может быть преобразовано в "<typename2>'
title: Значение типа <typename1> невозможно привести к <typename2>
ms.date: 07/20/2015
f1_keywords:
- vbc30955
- bc30955
helpviewer_keywords:
- BC30955
ms.assetid: 966b61eb-441e-48b0-bedf-ca95384ecb8b
ms.openlocfilehash: e03201d5dbb84faf06b7acbe42fe6b3bb4272ab9
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2021
ms.locfileid: "99666255"
---
# <a name="bc30955-value-of-type-typename1-cannot-be-converted-to-typename2"></a>BC30955: значение типа " \<typename1> " не может быть преобразовано в " \<typename2> "

Значение типа " \<typename1> " не может быть преобразовано в " \<typename2> ". Несоответствие типов может быть вызвано смешением ссылки на файл со ссылкой проекта на сборку " \<assemblyname> ". Попробуйте заменить ссылку на файл " \<filepath> " в проекте " \<projectname1> " ссылкой проекта на " \<projectname2> ".

 В ситуации, когда проект делает ссылку на проект и ссылку на файл, компилятор не может гарантировать, что один тип можно преобразовать в другой.

 В следующем псевдо-коде показана ситуация, которая может вызвать эту ошибку.

 `' ================ Visual Basic project P1 ================`

 `'        P1 makes a PROJECT REFERENCE to project P2`

 `'        and a FILE REFERENCE to project P3.`

 `Public commonObject As P3.commonClass`

 `commonObject = P2.getCommonClass()`

 `' ================ Visual Basic project P2 ================`

 `'        P2 makes a PROJECT REFERENCE to project P3`

 `Public Function getCommonClass() As P3.commonClass`

 `Return New P3.commonClass`

 `End Function`

 `' ================ Visual Basic project P3 ================`

 `Public Class commonClass`

 `End Class`

 Project `P1` делает косвенную ссылку на проект через проект `P2` `P3` , а также прямую ссылку на файл `P3` . В объявлении `commonObject` используется ссылка на файл `P3` , а в вызове `P2.getCommonClass` используется ссылка на проект `P3` .

 Проблема в этой ситуации заключается в том, что ссылка на файл указывает путь к файлу и имя выходного файла `P3` (обычно p3.dll), а ссылки проекта определяют исходный проект ( `P3` ) по имени проекта. По этой причине компилятор не может гарантировать, что тип `P3.commonClass` поступает из одного и того же исходного кода через две разные ссылки.

 Эта ситуация обычно возникает, если ссылки на проект и ссылки на файлы являются смешанными. На предыдущем рисунке проблема не возникнет, если `P1` сделать прямую ссылку на проект `P3` вместо ссылки на файл.

 **Идентификатор ошибки:** BC30955

## <a name="to-correct-this-error"></a>Исправление ошибки

- Измените ссылку на файл на ссылку на проект.

## <a name="see-also"></a>См. также

- [Преобразование типов в Visual Basic](../../programming-guide/language-features/data-types/type-conversions.md)
- [Управление ссылками в проекте](/visualstudio/ide/managing-references-in-a-project)
