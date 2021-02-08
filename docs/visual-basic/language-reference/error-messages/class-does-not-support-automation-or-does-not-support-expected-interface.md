---
description: 'Дополнительные сведения о: класс не поддерживает автоматизацию или не поддерживает ожидаемый интерфейс'
title: Класс не поддерживает автоматизацию или не поддерживает ожидаемый интерфейс
ms.date: 07/20/2015
f1_keywords:
- vbrID430
ms.assetid: d985bb7e-e48e-443e-86f2-ddb86758757c
ms.openlocfilehash: cc5ae539064b8d049e2808d916f9f4b75f7e94c9
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2021
ms.locfileid: "99796799"
---
# <a name="class-does-not-support-automation-or-does-not-support-expected-interface"></a>Класс не поддерживает автоматизацию или не поддерживает ожидаемый интерфейс

Либо класс, указанный вами в вызове функции `GetObject` или `CreateObject`, не предоставил интерфейс программирования, либо вы изменили проект с .DLL на .EXE или наоборот.  
  
## <a name="to-correct-this-error"></a>Исправление ошибки  
  
1. Просмотрите документацию по приложению, которое создало данный объект, чтобы узнать об ограничениях на использование автоматизации с объектом такого класса.  
  
2. Если вы изменили проект с .DLL на .EXE или наоборот, необходимо вручную отменить регистрацию старого проекта .DLL или .EXE.  
  
## <a name="see-also"></a>См. также

- [Типы ошибок](../../programming-guide/language-features/error-types.md)
- [Обращайтесь к нам](/visualstudio/ide/feedback-options)
