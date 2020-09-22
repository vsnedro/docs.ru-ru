---
title: Объект My.Settings
ms.date: 07/20/2015
f1_keywords:
- My.MySettingsProperty.Settings
- My.Settings
helpviewer_keywords:
- My.Settings object
ms.assetid: 41f30dc1-202a-4273-b9b7-5728941f996c
ms.openlocfilehash: f3348e9eea5bdd7f4fd911150877c9aefdd66bcc
ms.sourcegitcommit: d2db216e46323f73b32ae312c9e4135258e5d68e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/22/2020
ms.locfileid: "90867301"
---
# <a name="mysettings-object"></a>Объект My.Settings

Предоставляет свойства и методы для доступа к параметрам приложения.  
  
## <a name="remarks"></a>Remarks  

 `My.Settings`Объект предоставляет доступ к параметрам приложения и позволяет динамически сохранять и извлекать параметры свойств и другие сведения для приложения. Дополнительные сведения см. в разделе [Управление параметрами приложения (.NET)](/visualstudio/ide/managing-application-settings-dotnet).  
  
## <a name="properties"></a>Свойства  

 Свойства объекта `My.Settings` обеспечивают доступ к параметрам приложения. Чтобы добавить или удалить параметры, используйте **Конструктор параметров**.  
  
 Каждый параметр имеет **имя**, **Тип**, **область**и **значение**, и эти параметры определяют, как свойство для доступа к каждому параметру отображается в `My.Settings` объекте.  
  
- **Имя** определяет имя свойства.  
  
- **Тип** определяет тип свойства.  
  
- **Область** указывает, доступно ли свойство только для чтения. Если значение — **Application**, свойство доступно только для чтения; Если значение — **User**, свойство доступно для чтения и записи.  
  
- **Значение** является значением свойства по умолчанию.  
  
## <a name="methods"></a>Методы  
  
|Метод|Описание|  
|---|---|  
|`Reload`|Перезагружает пользовательские параметры из последних сохраненных значений.|  
|`Save`|Сохраняет текущие параметры пользователя.|  
  
 `My.Settings`Объект также предоставляет дополнительные свойства и методы, унаследованные от <xref:System.Configuration.ApplicationSettingsBase> класса.  
  
## <a name="tasks"></a>Задания  

 В следующей таблице приведены примеры задач, включающих `My.Settings` объект.  
  
|Кому|См.|  
|---|---|  
|Чтение параметра приложения|[Практическое руководство. Чтение параметров приложения в Visual Basic](../../developing-apps/programming/app-settings/how-to-read-application-settings.md)|  
|Изменение параметров пользователя|[Практическое руководство. Изменение пользовательских параметров в Visual Basic](../../developing-apps/programming/app-settings/how-to-change-user-settings.md)|  
|Сохранить параметры пользователя|[Практическое руководство. Сохранение пользовательских параметров в Visual Basic](../../developing-apps/programming/app-settings/how-to-persist-user-settings.md)|  
|Создание сетки свойств для параметров пользователя|[Практическое руководство. Создание таблицы свойств для пользовательских параметров в Visual Basic](../../developing-apps/programming/app-settings/how-to-create-property-grids-for-user-settings.md)|  
  
## <a name="example"></a>Пример  

 В этом пример выводится значение параметра `Nickname`.  
  
 [!code-vb[VbVbalrMyResources#14](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrMyResources/VB/Form1.vb#14)]  
  
 Для надлежащего выполнения этого примера приложение должно иметь параметр `Nickname` типа `String`.  
  
## <a name="see-also"></a>См. также

- <xref:System.Configuration.ApplicationSettingsBase>
- [Практическое руководство. Чтение параметров приложения в Visual Basic](../../developing-apps/programming/app-settings/how-to-read-application-settings.md)
- [Практическое руководство. Изменение пользовательских параметров в Visual Basic](../../developing-apps/programming/app-settings/how-to-change-user-settings.md)
- [Практическое руководство. Сохранение пользовательских параметров в Visual Basic](../../developing-apps/programming/app-settings/how-to-persist-user-settings.md)
- [Практическое руководство. Создание таблицы свойств для пользовательских параметров в Visual Basic](../../developing-apps/programming/app-settings/how-to-create-property-grids-for-user-settings.md)
- [Управление параметрами приложения (.NET)](/visualstudio/ide/managing-application-settings-dotnet)
