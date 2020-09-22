---
title: Ожидается Optional
ms.date: 07/20/2015
f1_keywords:
- bc30202
- vbc30202
helpviewer_keywords:
- BC30202
ms.assetid: 6f75060c-2db4-4a79-b5d1-5780c09a74cd
ms.openlocfilehash: e212939cf814a9ac632571b2203f2f256dea61ae
ms.sourcegitcommit: d2db216e46323f73b32ae312c9e4135258e5d68e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/22/2020
ms.locfileid: "90873597"
---
# <a name="optional-expected"></a>Ожидается Optional

За дополнительным аргументом в объявлении процедуры следует обязательный аргумент. Каждый аргумент, следующий за необязательным аргументом, также должен быть необязательным.  
  
 **Идентификатор ошибки:** BC30202  
  
## <a name="to-correct-this-error"></a>Исправление ошибки  
  
1. Если аргумент должен быть обязательным, переместите его перед первым необязательным аргументом в списке аргументов.  
  
2. Если аргумент должен быть необязательным, используйте `Optional` ключевое слово.  
  
## <a name="see-also"></a>См. также

- [Необязательные параметры](../../programming-guide/language-features/procedures/optional-parameters.md)
