---
description: 'Дополнительные сведения о: класс не поддерживает автоматизацию или не поддерживает ожидаемый интерфейс'
title: Класс не поддерживает автоматизацию или не поддерживает ожидаемый интерфейс
ms.date: 07/20/2015
f1_keywords:
- vbrID430
ms.assetid: d985bb7e-e48e-443e-86f2-ddb86758757c
ms.openlocfilehash: c173eeddf3a34d6af169b91066199ce7d03cf4ba
ms.sourcegitcommit: 42d436ebc2a7ee02fc1848c7742bc7d80e13fc2f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/04/2021
ms.locfileid: "102106635"
---
# <a name="class-does-not-support-automation-or-does-not-support-expected-interface"></a>Класс не поддерживает автоматизацию или не поддерживает ожидаемый интерфейс

Либо класс, указанный вами в вызове функции `GetObject` или `CreateObject`, не предоставил интерфейс программирования, либо вы изменили проект с .DLL на .EXE или наоборот.  
  
## <a name="to-correct-this-error"></a>Исправление ошибки  
  
1. Просмотрите документацию по приложению, которое создало данный объект, чтобы узнать об ограничениях на использование автоматизации с объектом такого класса.  
  
2. Если вы изменили проект с .DLL на .EXE или наоборот, необходимо вручную отменить регистрацию старого проекта .DLL или .EXE.  
  
## <a name="see-also"></a>См. также раздел

- [Типы ошибок](../../programming-guide/language-features/error-types.md)
- [Параметры обратной связи Visual Studio](/visualstudio/ide/feedback-options)
