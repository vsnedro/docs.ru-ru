---
description: 'Дополнительные сведения о: BC30202: требуется "Optional"'
title: Ожидается Optional
ms.date: 07/20/2015
f1_keywords:
- bc30202
- vbc30202
helpviewer_keywords:
- BC30202
ms.assetid: 6f75060c-2db4-4a79-b5d1-5780c09a74cd
ms.openlocfilehash: 543dbf6226d4d298d46764ee506b55e770c91604
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2021
ms.locfileid: "99795551"
---
# <a name="bc30202-optional-expected"></a>BC30202: требуется "Optional"

За дополнительным аргументом в объявлении процедуры следует обязательный аргумент. Каждый аргумент, следующий за необязательным аргументом, также должен быть необязательным.

 **Идентификатор ошибки:** BC30202

## <a name="to-correct-this-error"></a>Исправление ошибки

- Если аргумент должен быть обязательным, переместите его перед первым необязательным аргументом в списке аргументов.

- Если аргумент должен быть необязательным, используйте `Optional` ключевое слово.

## <a name="see-also"></a>См. также

- [Необязательные параметры](../../programming-guide/language-features/procedures/optional-parameters.md)
