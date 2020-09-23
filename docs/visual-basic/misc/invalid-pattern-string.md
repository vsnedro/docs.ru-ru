---
title: Недопустимая строка шаблона
ms.date: 07/20/2015
ms.assetid: ec1aecdb-5339-4a93-be71-eec56b1d7438
ms.openlocfilehash: 5ef12ac27e96205f9ef1c964293847f56b11cb78
ms.sourcegitcommit: bf5c5850654187705bc94cc40ebfb62fe346ab02
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/23/2020
ms.locfileid: "91090694"
---
# <a name="invalid-pattern-string"></a>Недопустимая строка шаблона

Строка шаблона, указанная в операции поиска `Like` , является недопустимой.  
  
## <a name="to-correct-this-error"></a>Исправление ошибки  
  
1. Просмотрите допустимые символы для выражений списка.  
  
2. В диапазоне шаблона убедитесь, что знак в начале диапазона меньше знака в конце диапазона, как в `[a-z]`.  
  
3. В диапазоне шаблона убедитесь, что не отсутствуют дефисы, указанные рядом друг с другом, как в `[a--z]`.  
  
4. Завершите диапазон шаблона закрывающей скобкой.  
  
## <a name="see-also"></a>См. также

- [Оператор Like](../language-reference/operators/like-operator.md)
