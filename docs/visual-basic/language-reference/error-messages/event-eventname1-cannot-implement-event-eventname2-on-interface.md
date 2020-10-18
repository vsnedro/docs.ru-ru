---
title: Событие <eventname1> не может реализовать событие <eventname2> в интерфейсе <interface>, так как их делегируемые типы <delegate1> и <delegate2> не совпадают
ms.date: 07/20/2015
f1_keywords:
- vbc31423
- bc31423
helpviewer_keywords:
- BC31423
ms.assetid: 2e754b66-5836-48ff-9697-b9c0d7085f18
ms.openlocfilehash: d0b2b095ed355b420b28e87ed0b9d6a31f049ebf
ms.sourcegitcommit: ff5a4eb5cffbcac9521bc44a907a118cd7e8638d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/17/2020
ms.locfileid: "92162028"
---
# <a name="bc31423-event-eventname1-cannot-implement-event-eventname2-on-interface-interface-because-their-delegate-types-delegate1-and-delegate2-do-not-match"></a>BC31423: событие " \<eventname1> " не может реализовать событие " \<eventname2> " для интерфейса " \<interface> ", так как их типы делегатов " \<delegate1> " и " \<delegate2> " не совпадают

Visual Basic не может реализовать событие, так как тип делегата события не соответствует типу делегата события в интерфейсе. Эта ошибка может возникнуть при определении нескольких событий в интерфейсе и последующей попытке их совместной реализации с использованием одного события. Событие может реализовывать два или более событий, только если все они объявлены с помощью синтаксиса `As` и указывают один и тот же тип делегата.

 **Идентификатор ошибки:** BC31423

## <a name="to-correct-this-error"></a>Исправление ошибки

- Реализуйте события по отдельности.

     —или—

- Определите события в интерфейсе с помощью `As` синтаксиса и укажите тот же тип делегата.

## <a name="see-also"></a>См. также

- [Оператор Event](../statements/event-statement.md)
- [Оператор Delegate](../statements/delegate-statement.md)
- [События](../../programming-guide/language-features/events/index.md)
