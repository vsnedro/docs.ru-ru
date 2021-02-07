---
description: 'Дополнительные сведения: переменная использует тип автоматизации, который не поддерживается в Visual Basic'
title: Переменная использует неподдерживаемый тип автоматизации
ms.date: 07/20/2015
f1_keywords:
- vbrID458
ms.assetid: bde4f4da-493b-452c-b6e4-1d370edba4cd
ms.openlocfilehash: 9aa8f8a2a49e54c547dc47d38305d40f855b1815
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2021
ms.locfileid: "99666151"
---
# <a name="variable-uses-an-automation-type-not-supported-in-visual-basic"></a>Переменная использует тип автоматизации, не поддерживаемый в Visual Basic

Предпринята попытка использовать переменную, определенную в библиотеке типов или библиотеке объектов, которая имеет тип данных, не поддерживаемый Visual Basic.

## <a name="to-correct-this-error"></a>Исправление ошибки

- Используйте переменную типа, распознаваемый Visual Basic.

     -или-

- Если эта ошибка возникает при использовании `FileGet` или `FileGetObject` , убедитесь, что файл, который вы пытаетесь использовать, записан в с помощью `FilePut` или `FilePutObject` .

## <a name="see-also"></a>См. также

- [Типы данных](../data-types/index.md)
