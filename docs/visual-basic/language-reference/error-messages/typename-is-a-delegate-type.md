---
description: 'Дополнительные сведения о: BC32008: " <typename> " является типом делегата'
title: <typename> является типом делегата
ms.date: 07/20/2015
f1_keywords:
- bc32008
- vbc32008
helpviewer_keywords:
- BC32008
ms.assetid: dc6abba0-a9ad-450f-8899-87265bc84abc
ms.openlocfilehash: 72aac48038c433b7938c54e7f1138a5b91bf7689
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2021
ms.locfileid: "99675030"
---
# <a name="bc32008-typename-is-a-delegate-type"></a>BC32008: " \<typename> " является типом делегата

" \<typename> " является типом делегата. Конструкция делегата позволяет использовать только одно выражение AddressOf в качестве списка аргументов. Часто выражение AddressOf можно использовать вместо конструкции делегата.

 `New`Предложение, создающее экземпляр класса делегата, предоставляет конструктору делегата недопустимый список аргументов.

 `AddressOf`При создании нового экземпляра делегата можно указать только одно выражение.

 Эта ошибка может возникнуть, если вы не передаете аргументы конструктору делегата, если передаете несколько аргументов или передаете один аргумент, который не является допустимым `AddressOf` выражением.

 **Идентификатор ошибки:** BC32008

## <a name="to-correct-this-error"></a>Исправление ошибки

- Используйте одно `AddressOf` выражение в списке аргументов для класса делегата в `New` предложении.

## <a name="see-also"></a>См. также

- [Создание оператора](../operators/new-operator.md)
- [Оператор AddressOf](../operators/addressof-operator.md)
- [Делегаты](../../programming-guide/language-features/delegates/index.md)
- [Практическое руководство. Вызов метода делегата](../../programming-guide/language-features/delegates/how-to-invoke-a-delegate-method.md)
