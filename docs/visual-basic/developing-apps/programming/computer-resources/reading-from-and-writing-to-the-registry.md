---
title: Чтение данных из реестра и запись в реестр
ms.date: 07/20/2015
helpviewer_keywords:
- My.Computer.Registry object, tasks
- registry [Visual Basic], writing to
- registry [Visual Basic], reading
ms.assetid: a13da106-185b-41d7-b23c-416da65e21e4
ms.openlocfilehash: bb400ef89edaa4eb743aee3a7f2cc5b9dfec4534
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/04/2020
ms.locfileid: "84360063"
---
# <a name="reading-from-and-writing-to-the-registry-visual-basic"></a>Чтение данных из реестра и запись в реестр (Visual Basic)

В этом разделе описываются задачи и приводятся основные разделы, связанные с реестром.  
  
 При программировании в Visual Basic можно получить доступ к реестру с помощью функций, предоставляемых Visual Basic, или классов платформы .NET Framework для работы с реестром. Реестр содержит данные, исходящие как от операционной системы, так и от приложений, установленных на компьютере. Работа с реестром может привести к нарушению безопасности, допуская несанкционированный доступ к системным ресурсам или защищенной информации.  
  
## <a name="in-this-section"></a>Содержание  

 [Практическое руководство. Создание раздела реестра и задание его значения](how-to-create-a-registry-key-and-set-its-value.md)  
 Описывает использование методов `CreateSubKey` и `SetValue` объекта `My.Computer.Registry` для создания раздела реестра и присвоения ему значения.  
  
 [Практическое руководство. Чтение значения из раздела реестра](how-to-read-a-value-from-a-registry-key.md)  
 Описывает использование метода `GetValue` объекта `My.Computer.Registry` для чтения значения из раздела реестра.  
  
 [Практическое руководство. Удаление раздела реестра](how-to-delete-a-registry-key.md)  
 Описывает использование метода `DeleteSubKey` свойства `My.Computer.Registry.CurrentUser` для удаления раздела реестра.  
  
 [Чтение реестра и запись в него с использованием пространства имен Microsoft.Win32](reading-from-and-writing-to-the-registry-using-the-microsoft-win32-namespace.md)  
 Описывает использование классов `Registry` и `RegistryKey` платформы .NET Framework для доступа к реестру.  
  
 [Безопасность и реестр](security-and-the-registry.md)  
 Описывает вопросы безопасности, связанные с реестром.  
  
## <a name="related-sections"></a>Связанные разделы  

 <xref:Microsoft.VisualBasic.MyServices.RegistryProxy>  
 Список и описание членов объекта `My.Computer.Registry`.  
  
 <xref:Microsoft.Win32.Registry>  
 Обзор класса `Registry` со ссылками на отдельные разделы и члены.
