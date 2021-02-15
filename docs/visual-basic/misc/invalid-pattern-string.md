---
description: 'Дополнительные сведения: недопустимая строка шаблона'
title: Недопустимая строка шаблона
ms.date: 07/20/2015
ms.assetid: ec1aecdb-5339-4a93-be71-eec56b1d7438
ms.openlocfilehash: 4fbf16dd43ac4ae44e1a99d85caae4a7baf99109
ms.sourcegitcommit: 10e719780594efc781b15295e499c66f316068b8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/14/2021
ms.locfileid: "100462065"
---
# <a name="invalid-pattern-string"></a>Недопустимая строка шаблона

Строка шаблона, указанная в операции поиска `Like` , является недопустимой.  
  
## <a name="to-correct-this-error"></a>Исправление ошибки  
  
1. Просмотрите допустимые символы для выражений списка.  
  
2. В диапазоне шаблона убедитесь, что знак в начале диапазона меньше знака в конце диапазона, как в `[a-z]`.  
  
3. В диапазоне шаблона убедитесь, что не отсутствуют дефисы, указанные рядом друг с другом, как в `[a--z]`.  
  
4. Завершите диапазон шаблона закрывающей скобкой.  
  
## <a name="see-also"></a>См. также раздел

- [Оператор Like](../language-reference/operators/like-operator.md)
