---
description: 'Дополнительные сведения о: BC30909: " <membername> " не может представлять тип " <typename> " за пределами проекта через <containertype> "<containertypename>'
title: <membername> не может представлять тип <typename> вне проекта посредством <containertype><containertypename>
ms.date: 07/20/2015
f1_keywords:
- bc30909
- vbc30909
helpviewer_keywords:
- BC30909
ms.assetid: ffa7395d-e182-4087-8ce8-079810fdae54
ms.openlocfilehash: e2cc1d950b646bb787dfe714c39efea78a530129
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2021
ms.locfileid: "99795863"
---
# <a name="bc30909-membername-cannot-expose-type-typename-outside-the-project-through-containertype-containertypename"></a>BC30909: " \<membername> " не может представлять тип " \<typename> " за пределами проекта через \<containertype> " \<containertypename> "

Переменная, параметр процедуры или возвращаемое значение функции предоставляется за пределами своего контейнера, но она объявляется как тип, который не должен предоставляться за пределами контейнера.

 В приведенном ниже коде показана ситуация, которая приводит к возникновению этой ошибки.

```vb
Private Class privateClass
End Class
Public Class mainClass
    Public exposedVar As New privateClass
End Class
```

 Тип, который объявлен как `Protected` , `Friend` , `Protected Friend` или, `Private` предназначен для ограниченного доступа за пределами контекста объявления. Использование его в качестве типа данных переменной с меньшим доступом было бы непреднамеренно. В предыдущем скелете кода `exposedVar` имеет значение `Public` и будет предоставлять `privateClass` код, который не должен иметь к нему доступа.

 **Идентификатор ошибки:** BC30909

## <a name="to-correct-this-error"></a>Исправление ошибки

- Измените уровень доступа переменной, параметра процедуры или функции, чтобы он был по крайней мере ограничен уровнем доступа его типа данных.

## <a name="see-also"></a>См. также

- [Уровни доступа в Visual Basic](../../programming-guide/language-features/declared-elements/access-levels.md)
