---
title: <typename> является типом делегата
ms.date: 07/20/2015
f1_keywords:
- bc32008
- vbc32008
helpviewer_keywords:
- BC32008
ms.assetid: dc6abba0-a9ad-450f-8899-87265bc84abc
ms.openlocfilehash: 7056bbf2b4de26feba3bfbe0e02b3239311271c9
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/04/2020
ms.locfileid: "84382176"
---
# <a name="typename-is-a-delegate-type"></a>\<typename> является типом делегата
" \<typename> " является типом делегата. Конструкция делегата позволяет использовать только одно выражение AddressOf в качестве списка аргументов. Часто выражение AddressOf можно использовать вместо конструкции делегата.  
  
 `New`Предложение, создающее экземпляр класса делегата, предоставляет конструктору делегата недопустимый список аргументов.  
  
 `AddressOf`При создании нового экземпляра делегата можно указать только одно выражение.  
  
 Эта ошибка может возникнуть, если вы не передаете аргументы конструктору делегата, если передаете несколько аргументов или передаете один аргумент, который не является допустимым `AddressOf` выражением.  
  
 **Идентификатор ошибки:** BC32008  
  
## <a name="to-correct-this-error"></a>Исправление ошибки  
  
- Используйте одно `AddressOf` выражение в списке аргументов для класса делегата в `New` предложении.  
  
## <a name="see-also"></a>См. также раздел

- [Оператор New](../operators/new-operator.md)
- [Оператор AddressOf](../operators/addressof-operator.md)
- [Делегаты](../../programming-guide/language-features/delegates/index.md)
- [Практическое руководство. Вызов метода делегата](../../programming-guide/language-features/delegates/how-to-invoke-a-delegate-method.md)
