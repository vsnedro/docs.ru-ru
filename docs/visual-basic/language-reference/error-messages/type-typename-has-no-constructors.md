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
ms.openlocfilehash: 3961ba557ad2afd9c94f071b6615573419d7325b
ms.sourcegitcommit: 42d436ebc2a7ee02fc1848c7742bc7d80e13fc2f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/04/2021
ms.locfileid: "102106583"
---
# <a name="bc30251-type-typename-has-no-constructors"></a>BC30251: тип " \<typename> " не имеет конструкторов

Тип не поддерживает вызов в `Sub New()`. Одной из возможных причин является повреждение компилятора или двоичного файла.

 **Идентификатор ошибки:** BC30251

## <a name="to-correct-this-error"></a>Исправление ошибки

1. Если тип находится в другом проекте или в заданном ссылкой файле, переустановите этот проект или файл.

2. Если тип находится в том же самом проекте, перекомпилируйте сборку, содержащую тип.

3. Если ошибка повторяется, переустановите компилятор Visual Basic.

4. Если ошибка не устранена, соберите сведения об условиях ее возникновения и уведомите службу технической поддержки Майкрософт.

## <a name="see-also"></a>См. также раздел

- [Объекты и классы](../../programming-guide/language-features/objects-and-classes/index.md)
- [Параметры обратной связи Visual Studio](/visualstudio/ide/feedback-options)
