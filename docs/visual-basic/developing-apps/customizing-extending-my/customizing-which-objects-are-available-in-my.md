---
description: 'Узнайте подробнее о: Настройка доступа к объектам через My (Visual Basic)'
title: Настройка доступа к объектам через My
ms.date: 07/20/2015
helpviewer_keywords:
- My namespace [Visual Basic], customizing
- My namespace
ms.assetid: 4e8279c2-ed5b-4681-8903-8a6671874000
ms.openlocfilehash: 065f7e645a5530db1e485ee3f8ea50f8a163f9e8
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2021
ms.locfileid: "99731439"
---
# <a name="customizing-which-objects-are-available-in-my-visual-basic"></a>Настройка доступа к объектам через My (Visual Basic)

В этой статье показано, как управлять доступностью объектов `My` с помощью константы условной компиляции `_MYTYPE` проекта. Интегрированная среда разработки (IDE) Visual Studio позволяет использовать константу условной компиляции `_MYTYPE` для проекта в соответствии с типом проекта.  
  
## <a name="predefined-_mytype-values"></a>Предопределенные значения \_MYTYPE  

Чтобы задать константу условной компиляции `_MYTYPE`, используйте параметр компилятора `/define`. При указании собственного значения для константы `_MYTYPE` заключите строковое значение в последовательности, состоящие из обратной косой черты и кавычек (\\"). Например, можно использовать такую последовательность:  
  
```console  
/define:_MYTYPE=\"WindowsForms\"  
```  
  
 В этой таблице приводятся значения константы условной компиляции `_MYTYPE` для нескольких типов проектов.  
  
|Тип проекта|Значение \_MYTYPE|  
|------------------|--------------------|  
|Библиотека классов|"Windows"|  
|Консольное приложение|"Console"|  
|Интернет|"Web"|  
|Библиотека веб-элементов управления|"WebControl"|  
|Приложение Windows|"WindowsForms"|  
|Приложение Windows при запуске с помощью пользовательского объекта `Sub Main`|"WindowsFormsWithCustomSubMain"|  
|Библиотека элементов управления Windows|"Windows"|  
|Служба Windows|"Console"|  
|Empty|"Empty"|  
  
> [!NOTE]
> Все сравнения строк условной компиляции учитывают регистр, независимо от того, как задана инструкция `Option Compare`.  
  
## <a name="dependent-_my-compilation-constants"></a>Зависимые константы компиляции \_MY  

Константа условной компиляции `_MYTYPE` управляет значениями других констант компиляции `_MY`:  
  
|\_MYTYPE|\_MYAPPLICATIONTYPE|\_MYCOMPUTERTYPE|\_MYFORMS|\_MYUSERTYPE|\_MYWEBSERVICES|  
|--------------|-------------------------|----------------------|---------------|------------------|---------------------|  
|"Console"|"Console"|"Windows"|Не определено|"Windows"|TRUE|  
|"Custom"|Не определено|Не определено|Не определено|Не определено|Не определено|  
|"Empty"|Не определено|Не определено|Не определено|Не определено|Не определено|  
|"Web"|Не определено|"Web"|FALSE|"Web"|FALSE|  
|"WebControl"|Не определено|"Web"|FALSE|"Web"|TRUE|  
|"Windows" или ""|"Windows"|"Windows"|Не определено|"Windows"|TRUE|  
|"WindowsForms"|"WindowsForms"|"Windows"|TRUE|"Windows"|TRUE|  
|"WindowsFormsWithCustomSubMain"|"Console"|"Windows"|TRUE|"Windows"|TRUE|  
  
 По умолчанию неопределенные константы условной компиляции разрешаются в `FALSE`. Вы можете указать значения для неопределенных констант при компиляции проекта, чтобы переопределить поведение по умолчанию.  
  
> [!NOTE]
> Если `_MYTYPE` имеет значение "Custom", это значит, что проект содержит пространство имен `My`, но не содержит объектов. Если же для `_MYTYPE` задать значение "Empty", компилятор не будет добавлять пространство имен `My` и его объекты.  
  
 В этой таблице описаны результаты применения предопределенных значений констант компиляции `_MY`.  
  
|Константа|Значение|  
|--------------|-------------|  
|`_MYAPPLICATIONTYPE`|Включает `My.Application`, если для константы задано значение "Console," "Windows" или "WindowsForms":<br /><br /> – Версия "Console" является производной от <xref:Microsoft.VisualBasic.ApplicationServices.ConsoleApplicationBase> и содержит меньше элементов, чем версия "Windows".<br />– Версия "Windows" является производной от <xref:Microsoft.VisualBasic.ApplicationServices.ApplicationBase> и содержит меньше элементов, чем версия WindowsForms.<br />– Версия "WindowsForms" `My.Application` является производной от <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase>. Если константа `TARGET` определена как "winexe", тогда класс будет включать метод `Sub Main`.|  
|`_MYCOMPUTERTYPE`|Включает `My.Computer`, если для константы задано значение "Web" или "Windows":<br /><br /> – Версия "Web" является производной от <xref:Microsoft.VisualBasic.Devices.ServerComputer> и содержит меньше элементов, чем версия "Windows".<br />– Версия "Windows" объекта `My.Computer` является производной от <xref:Microsoft.VisualBasic.Devices.Computer>.|  
|`_MYFORMS`|Включает `My.Forms`, если для константы задано значение `TRUE`.|  
|`_MYUSERTYPE`|Включает `My.User`, если для константы задано значение "Web" или "Windows":<br /><br /> – Версия "Web" объекта `My.User` связана с удостоверением пользователя для текущего HTTP-запроса.<br />– Версия "Windows" объекта `My.User` связана с текущим субъектом потока.|  
|`_MYWEBSERVICES`|Включает `My.WebServices`, если для константы задано значение `TRUE`.|  
|`_MYTYPE`|Включает `My.Log`, `My.Request` и `My.Response`, если для константы задано значение "Web".|  
  
## <a name="see-also"></a>См. также

- <xref:Microsoft.VisualBasic.ApplicationServices.ApplicationBase>
- <xref:Microsoft.VisualBasic.Devices.Computer>
- <xref:Microsoft.VisualBasic.Logging.Log>
- <xref:Microsoft.VisualBasic.ApplicationServices.User>
- [Зависимость My от типа проекта](../development-with-my/how-my-depends-on-project-type.md)
- [Условная компиляция](../../programming-guide/program-structure/conditional-compilation.md)
- [-define (Visual Basic)](../../reference/command-line-compiler/define.md)
- [Объект My.Forms](../../language-reference/objects/my-forms-object.md)
- [Объект My.Request](../../language-reference/objects/my-request-object.md)
- [Объект My.Response](../../language-reference/objects/my-response-object.md)
- [Объект My.WebServices](../../language-reference/objects/my-webservices-object.md)
