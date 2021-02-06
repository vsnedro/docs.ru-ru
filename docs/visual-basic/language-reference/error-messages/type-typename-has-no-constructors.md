---
description: 'Дополнительные сведения о: BC30251: тип " <typename> " не имеет конструкторов'
title: В типе <typename> отсутствуют конструкторы
ms.date: 07/20/2015
f1_keywords:
- bc30251
- vbc30251
helpviewer_keywords:
- BC30251
ms.assetid: aff3e1df-abe6-4bc0-9abc-a1e70514c561
ms.openlocfilehash: 32ae854e9f1b037a17d9c378ce7ee4a3f9b43ad2
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2021
ms.locfileid: "99641178"
---
# <a name="bc30251-type-typename-has-no-constructors"></a>BC30251: тип " \<typename> " не имеет конструкторов

Тип не поддерживает вызов в `Sub New()`. Одной из возможных причин является повреждение компилятора или двоичного файла.

 **Идентификатор ошибки:** BC30251

## <a name="to-correct-this-error"></a>Исправление ошибки

1. Если тип находится в другом проекте или в заданном ссылкой файле, переустановите этот проект или файл.

2. Если тип находится в том же самом проекте, перекомпилируйте сборку, содержащую тип.

3. Если ошибка повторяется, переустановите компилятор Visual Basic.

4. Если ошибка не устранена, соберите сведения об условиях ее возникновения и уведомите службу технической поддержки Майкрософт.

## <a name="see-also"></a>См. также

- [Объекты и классы](../../programming-guide/language-features/objects-and-classes/index.md)
- [Обращайтесь к нам](/visualstudio/ide/feedback-options)
