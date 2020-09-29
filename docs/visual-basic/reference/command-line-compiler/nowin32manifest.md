---
title: -nowin32manifest
ms.date: 03/13/2018
helpviewer_keywords:
- /nowin32manifest compiler option [Visual Basic]
- nowin32manifest compiler option [Visual Basic]
- -nowin32manifest compiler option [Visual Basic]
ms.assetid: c0528aae-83b3-4425-99f0-19448e9843e3
ms.openlocfilehash: 8fd902e1317c7c767303bcaa30cdc56cff712558
ms.sourcegitcommit: bf5c5850654187705bc94cc40ebfb62fe346ab02
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/23/2020
ms.locfileid: "91097622"
---
# <a name="-nowin32manifest-visual-basic"></a>-nowin32manifest (Visual Basic)

Указывает компилятору не внедрять манифест приложения в исполняемый файл.  
  
## <a name="syntax"></a>Синтаксис  
  
```console  
-nowin32manifest  
```  
  
## <a name="remarks"></a>Примечания  

 При использовании этого параметра приложение будет подлежать виртуализации в Windows Vista, если манифест приложения не будет предоставлен в файле ресурсов Win32 или на более поздних этапах сборки. Дополнительные сведения о виртуализации см. в статье [ClickOnce Deployment on Windows Vista](/visualstudio/deployment/clickonce-deployment-on-windows-vista) (Развертывание ClickOnce в Windows Vista).  
  
 Дополнительные сведения о создании манифестов см. в разделе [-win32manifest (Visual Basic)](win32manifest.md).  
  
## <a name="see-also"></a>См. также

- [Компилятор Visual Basic с интерфейсом командной строки](index.md)
- [Страница "Приложение" в конструкторе проектов (Visual Basic)](/visualstudio/ide/reference/application-page-project-designer-visual-basic)
