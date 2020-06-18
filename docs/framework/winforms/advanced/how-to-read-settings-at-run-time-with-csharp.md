---
title: 'Как выполнить: Считывание параметров во время выполнения с помощью C#'
description: Узнайте, как считывать параметры уровня приложения и пользователя во время выполнения с помощью C# через объект Properties.
ms.date: 03/30/2017
helpviewer_keywords:
- application settings [Windows Forms], reading
- application settings [Windows Forms], run time
- application settings [Windows Forms], C#
ms.assetid: dbe8bf09-5e1c-49da-9192-154033d7240b
ms.openlocfilehash: d784544e018bb693c501e35ea36fcae1946ef5eb
ms.sourcegitcommit: 3824ff187947572b274b9715b60c11269335c181
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/17/2020
ms.locfileid: "84903359"
---
# <a name="how-to-read-settings-at-run-time-with-c"></a>Руководство. чтение параметров во время выполнения с помощью C\#

Параметры области приложения и параметры области пользователя можно считывать во время выполнения с помощью объекта "Свойства". Объект Properties предоставляет все параметры по умолчанию для проекта с помощью элемента properties. Settings. Default в пространстве имен по умолчанию для проекта, в котором они определены.  
  
## <a name="to-read-settings-at-run-time-with-c"></a>Чтение параметров во время выполнения с помощью C\#
  
Доступ к соответствующему параметру через элемент Properties.Settings.Default. В следующем примере показано, как назначить параметр с именем `myColor` свойству BackColor. Необходимо наличие ранее созданного файла параметров, содержащего параметр с именем `myColor` и типом `System.Drawing.Color`. Сведения о создании файла параметров см. в разделе [инструкции. Создание нового параметра во время разработки](how-to-create-a-new-setting-at-design-time.md).  
  
```csharp
this.BackColor = Properties.Settings.Default.myColor;  
```  
  
## <a name="see-also"></a>См. также раздел

- [Использование параметров приложения и параметров пользователя](using-application-settings-and-user-settings.md)
- [Как выполнить: Написание параметров пользователя во время выполнения с помощью C#](how-to-write-user-settings-at-run-time-with-csharp.md)
- [Общие сведения о параметрах приложений](application-settings-overview.md)
