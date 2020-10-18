---
title: Ожидается Optional
ms.date: 07/20/2015
f1_keywords:
- bc30202
- vbc30202
helpviewer_keywords:
- BC30202
ms.assetid: 6f75060c-2db4-4a79-b5d1-5780c09a74cd
ms.openlocfilehash: 9c717cef2052722563e04595ef7a808ea103a75d
ms.sourcegitcommit: ff5a4eb5cffbcac9521bc44a907a118cd7e8638d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/17/2020
ms.locfileid: "92159824"
---
# <a name="bc30202-optional-expected"></a>BC30202: требуется "Optional"

За дополнительным аргументом в объявлении процедуры следует обязательный аргумент. Каждый аргумент, следующий за необязательным аргументом, также должен быть необязательным.

 **Идентификатор ошибки:** BC30202

## <a name="to-correct-this-error"></a>Исправление ошибки

- Если аргумент должен быть обязательным, переместите его перед первым необязательным аргументом в списке аргументов.

- Если аргумент должен быть необязательным, используйте `Optional` ключевое слово.

## <a name="see-also"></a>См. также

- [Необязательные параметры](../../programming-guide/language-features/procedures/optional-parameters.md)
