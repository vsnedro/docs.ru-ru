---
title: -win32manifest
ms.date: 03/13/2018
helpviewer_keywords:
- /win32manifest compiler option [Visual Basic]
- win32manifest compiler option [Visual Basic]
- -win32manifest compiler option [Visual Basic]
ms.assetid: 9e3191b4-90db-41c8-966a-28036fd20005
ms.openlocfilehash: 6f77649365f8ca7b163cd55854aa9960d88f2984
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/04/2020
ms.locfileid: "84414263"
---
# <a name="-win32manifest-visual-basic"></a>-win32manifest (Visual Basic)
Определяет пользовательский файл манифеста приложения Win32 для внедрения в переносимый исполняемый файл проекта (PE-файл).  
  
## <a name="syntax"></a>Синтаксис  
  
```console  
-win32manifest: fileName  
```  
  
## <a name="arguments"></a>Аргументы  
  
|Термин|Определение|  
|---|---|  
|`fileName`|Путь к пользовательскому файлу манифеста.|  
  
## <a name="remarks"></a>Примечания  
 По умолчанию компилятор Visual Basic внедряет манифест приложения, определяющий запрошенный уровень выполнения "asInvoker". Он создает манифест в той же папке, в которой создан исполняемый файл; при использовании Visual Studio обычно это папка bin\Debug или bin\Release. Если вы хотите предоставить пользовательский манифест, например, чтобы задать запрошенный уровень выполнения highestAvailable или requireAdministrator, используйте этот параметр, чтобы указать имя файла.  
  
> [!NOTE]
> Этот параметр и параметр [-win32resource](win32resource.md) являются взаимоисключающими. При попытке использовать оба параметра в одной командной строке возникнет ошибка сборки.  
  
 Приложение без манифеста, определяющего запрошенный уровень выполнения, требует виртуализации файлов или реестра с помощью функции "Контроль учетных записей" в Windows Vista. Дополнительные сведения о виртуализации см. в статье [ClickOnce Deployment on Windows Vista](/visualstudio/deployment/clickonce-deployment-on-windows-vista) (Развертывание ClickOnce в Windows Vista).  
  
 Ваше приложение будет виртуализовано, если выполняется одно из следующих условий.  
  
1. Вы используете параметр `-nowin32manifest`, но не предоставляете манифест на более позднем этапе сборки или в файле ресурсов Windows (с расширением RES) с помощью параметра `-win32resource`.  
  
2. Вы предоставляете пользовательский манифест, не определяющий запрошенный уровень выполнения.  
  
 Visual Studio создает файл по умолчанию с расширением .manifest и сохраняет его в каталоги отладки и выпуска вместе с исполняемым файлом. Чтобы просмотреть или изменить файл app.manifest по умолчанию, нажмите **Просмотреть параметры контроля учетных записей** на вкладке **Приложение** в конструкторе проектов. Дополнительные сведения см. в разделе [Application Page, Project Designer (Visual Basic)](/visualstudio/ide/reference/application-page-project-designer-visual-basic).  
  
 Манифест приложения можно предоставить во время пользовательского этапа после сборки или в составе файла ресурсов Win32 с помощью параметра `-nowin32manifest`. Этот же параметр можно использовать, если вы хотите, чтобы ваше приложение требовало виртуализации файлов или реестров в Windows Vista. В этом случае компилятор не будет создавать и внедрять манифест по умолчанию в PE-файл.  
  
## <a name="example"></a>Пример  
 В следующем примере показан манифест по умолчанию, который компилятор Visual C# вставляет в PE.  
  
> [!NOTE]
> Компилятор вставляет в XML-код манифеста стандартное имя приложения, "MyApplication.app". Это позволяет приложениям работать в Windows Server 2003 с пакетом обновления 3.  
  
```xml  
<?xml version="1.0" encoding="utf-8" standalone="yes"?>  
<assembly xmlns="urn:schemas-microsoft-com:asm.v1" manifestVersion="1.0">  
  <assemblyIdentity version="1.0.0.0" name="MyApplication.app"/>  
  <trustInfo xmlns="urn:schemas-microsoft-com:asm.v2">  
    <security>  
      <requestedPrivileges xmlns="urn:schemas-microsoft-com:asm.v3">  
        <requestedExecutionLevel level="asInvoker"/>  
      </requestedPrivileges>  
    </security>  
  </trustInfo>  
</assembly>  
```  
  
## <a name="see-also"></a>См. также

- [Компилятор Visual Basic с интерфейсом командной строки](index.md)
- [-nowin32manifest (Visual Basic)](nowin32manifest.md)
