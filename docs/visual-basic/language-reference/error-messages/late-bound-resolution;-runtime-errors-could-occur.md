---
description: 'Дополнительные сведения о: BC42017: разрешение с поздним связыванием; могут возникнуть ошибки времени выполнения'
title: Разрешение позднего связывания; возможно возникновение ошибок времени выполнения
ms.date: 07/20/2015
f1_keywords:
- vbc42017
- BC42017
helpviewer_keywords:
- BC42017
ms.assetid: 45f552c8-57c6-44c0-97d3-e510119b257a
ms.openlocfilehash: 2c783a7aff46df8ab033463f49c45f4c797220ea
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2021
ms.locfileid: "99795928"
---
# <a name="bc42017-late-bound-resolution-runtime-errors-could-occur"></a>BC42017: разрешение с поздним связыванием; могут возникнуть ошибки времени выполнения

Объект присваивается переменной, объявленной с [типом данных Object](../data-types/object-data-type.md).

 При объявлении переменной как `Object` , компилятор должен выполнить *позднее связывание*, что приводит к дополнительным операциям во время выполнения. Это также подвергает ваше приложение риску ошибок времени выполнения. Например, если присвоить значение <xref:System.Windows.Forms.Form> `Object` переменной и попытаться получить доступ к <xref:System.Xml.XmlDocument.NameTable%2A?displayProperty=nameWithType> свойству, среда выполнения выдаст исключение, <xref:System.MemberAccessException> поскольку <xref:System.Windows.Forms.Form> класс не предоставляет `NameTable` свойство.

 Если объявить переменную с конкретным типом, компилятор может выполнять *раннее связывание* во время компиляции. Это приводит к повышению производительности, управляемому доступу к членам конкретного типа и повышению удобочитаемости кода.

 По умолчанию данное сообщение является предупреждением. Сведения о сокрытии предупреждений или обработке предупреждений как ошибок см. в разделе [Configuring Warnings in Visual Basic](/visualstudio/ide/configuring-warnings-in-visual-basic).

 **Идентификатор ошибки:** BC42017

## <a name="to-correct-this-error"></a>Исправление ошибки

- Если возможно, объявите переменную с конкретным типом.

## <a name="see-also"></a>См. также

- [Раннее и позднее связывание](../../programming-guide/language-features/early-late-binding/index.md)
- [Объявление объектной переменной](../../programming-guide/language-features/variables/object-variable-declaration.md)
