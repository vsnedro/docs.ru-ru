---
title: Переменная использует неподдерживаемый тип автоматизации
ms.date: 07/20/2015
f1_keywords:
- vbrID458
ms.assetid: bde4f4da-493b-452c-b6e4-1d370edba4cd
ms.openlocfilehash: 7d52189e31823b63547c757434847c0e1717aada
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/04/2020
ms.locfileid: "84406551"
---
# <a name="variable-uses-an-automation-type-not-supported-in-visual-basic"></a>Переменная использует тип автоматизации, не поддерживаемый в Visual Basic

Предпринята попытка использовать переменную, определенную в библиотеке типов или библиотеке объектов, которая имеет тип данных, не поддерживаемый Visual Basic.

## <a name="to-correct-this-error"></a>Исправление ошибки

- Используйте переменную типа, распознаваемый Visual Basic.

     -или-

- Если эта ошибка возникает при использовании `FileGet` или `FileGetObject` , убедитесь, что файл, который вы пытаетесь использовать, записан в с помощью `FilePut` или `FilePutObject` .

## <a name="see-also"></a>См. также раздел

- [Типы данных](../data-types/index.md)
