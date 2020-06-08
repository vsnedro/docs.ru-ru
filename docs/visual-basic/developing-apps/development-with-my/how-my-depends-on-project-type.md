---
title: Зависимость My от типа проекта
ms.date: 07/20/2015
helpviewer_keywords:
- _MYTYPE
ms.assetid: c188b38e-bd9d-4121-9983-41ea6a94d28e
ms.openlocfilehash: 740185d8030c09e8813bc7680b451f6326588593
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/04/2020
ms.locfileid: "84411718"
---
# <a name="how-my-depends-on-project-type-visual-basic"></a>Зависимость My от типа проекта (Visual Basic)

`My` предоставляет только те объекты, которые требуются для конкретного типа проекта. Например, объект `My.Forms` доступен в приложении Windows Forms, но отсутствует в консольном приложении. В этой статье показано, какие объекты `My` доступны в разных типах проектов.  
  
## <a name="my-in-windows-applications-and-web-sites"></a>Использование My в приложениях Windows и веб-сайтах  

 `My` предоставляет только те объекты, которые требуются в текущем типе проекта. Неприменимые объекты будут заблокированы. Например, на следующем рисунке показана объектная модель `My` в проекте Windows Forms.  
  
 ![Схема, на которой показана объектная модель My в приложении Windows Forms.](./media/how-my-depends-on-project-type/my-object-model-windows-forms.png)  
  
 В проекте веб-сайта `My` предоставляет объекты, необходимые веб-разработчику (например, объекты `My.Request` и `My.Response`). Неприменимые объекты будут заблокированы (например, объект `My.Forms`). На следующем рисунке показана объектная модель `My` в проекте веб-сайта.  
  
 ![Схема, на которой показана объектная модель My в веб-приложении.](./media/how-my-depends-on-project-type/my-object-model-web.png)  
  
## <a name="project-details"></a>Сведения о проекте  

 В следующей таблице показано, какие объекты `My` доступны по умолчанию для восьми типов проектов: Windows-приложение, библиотека классов, консольное приложение, библиотека элементов управления Windows, библиотека веб-элементов управления, служба Windows, пустой проект и веб-сайт.  
  
 Существует три версии объекта `My.Application`, две версии объекта `My.Computer` и две версии объекта `My.User`. Сведения об этих версиях см. в сносках под таблицей.  
  
|Объект My|Приложение Windows|Библиотека классов|Консольное приложение|Библиотека элементов управления Windows|Библиотека веб-элементов управления|Служба Windows|Empty|Веб-сайт|  
|---|---|---|---|---|---|---|---|---|  
|`My.Application`|**Да** <sup>1</sup>|**Да** <sup>2</sup>|**Да** <sup>3</sup>|**Да** <sup>2</sup>|Нет|**Да** <sup>3</sup>|Нет|Нет|  
|`My.Computer`|**Да** <sup>4</sup>|**Да** <sup>4</sup>|**Да** <sup>4</sup>|**Да** <sup>4</sup>|**Да** <sup>5</sup>|**Да** <sup>4</sup>|Нет|**Да** <sup>5</sup>|  
|`My.Forms`|**Да**|Нет|Нет|**Да**|Нет|Нет|Нет|Нет|  
|`My.Log`|Нет|Нет|Нет|Нет|Нет|Нет|Нет|**Да**|  
|`My.Request`|Нет|Нет|Нет|Нет|Нет|Нет|Нет|**Да**|  
|`My.Resources`|**Да**|**Да**|**Да**|**Да**|**Да**|**Да**|Нет|Нет|  
|`My.Response`|Нет|Нет|Нет|Нет|Нет|Нет|Нет|**Да**|  
|`My.Settings`|**Да**|**Да**|**Да**|**Да**|**Да**|**Да**|Нет|Нет|  
|`My.User`|**Да** <sup>6</sup>|**Да** <sup>6</sup>|**Да** <sup>6</sup>|**Да** <sup>6</sup>|**Да** <sup>7</sup>|**Да** <sup>6</sup>|Нет|**Да** <sup>7</sup>|  
|`My.WebServices`|**Да**|**Да**|**Да**|**Да**|**Да**|**Да**|Нет|Нет|  
  
 <sup>1</sup> Версия `My.Application` для Windows Forms. Является производной от версии для консольного приложения (см. примечание 3). В ней включена поддержка взаимодействия с окнами приложения и предоставляется модель приложения Visual Basic.  
  
 <sup>2</sup> Версия `My.Application` для библиотеки. Предоставляет базовые функции, необходимые для приложения: элементы для записи в журнал приложений и доступа к сведениям о приложении.  
  
 <sup>3</sup> Версия `My.Application` для консоли. Является производной от версии для библиотеки (см. примечание 2). В ней добавлены элементы для обращения к аргументам командной строки приложения и сведения о развертывании ClickOnce.  
  
 <sup>4</sup> Версия `My.Computer` для Windows. Является производной от версии для сервера (см. примечание 5). Предоставляет доступ к нужным объектам на клиентском компьютере, таким как клавиатура, экран и мышь.  
  
 <sup>5</sup> Версия `My.Computer` для сервера. Предоставляет основные сведения о компьютере, такие как имя, доступ к данным о времени и т. д.  
  
 <sup>6</sup> Версия `My.User` для Windows. Этот объект связан с текущим удостоверением потока.  
  
 <sup>7</sup> Версия `My.User` для веб-приложений. Этот объект связан с удостоверением пользователя для текущего HTTP-запроса приложения.  
  
## <a name="see-also"></a>См. также

- <xref:Microsoft.VisualBasic.ApplicationServices.ApplicationBase>
- <xref:Microsoft.VisualBasic.Devices.Computer>
- <xref:Microsoft.VisualBasic.Logging.Log>
- <xref:Microsoft.VisualBasic.ApplicationServices.User>
- [Настройка доступа к объектам через My](../customizing-extending-my/customizing-which-objects-are-available-in-my.md)
- [Условная компиляция](../../programming-guide/program-structure/conditional-compilation.md)
- [-define (Visual Basic)](../../reference/command-line-compiler/define.md)
- [Объект My.Forms](../../language-reference/objects/my-forms-object.md)
- [Объект My.Request](../../language-reference/objects/my-request-object.md)
- [Объект My.Response](../../language-reference/objects/my-response-object.md)
- [Объект My.WebServices](../../language-reference/objects/my-webservices-object.md)
