---
title: -nologo
ms.date: 03/13/2018
helpviewer_keywords:
- -nologo compiler option [Visual Basic]
- banners [Visual Basic], suppressing startup
- nologo compiler option [Visual Basic]
- /nologo compiler option [Visual Basic]
ms.assetid: 25ef54b6-d676-4639-a2d2-a747a158bc07
ms.openlocfilehash: 5557d681c5e6901592936efd35b3c552d43e39b0
ms.sourcegitcommit: bf5c5850654187705bc94cc40ebfb62fe346ab02
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/23/2020
ms.locfileid: "91097674"
---
# <a name="-nologo-visual-basic"></a>-nologo (Visual Basic)

Отключает отображение баннера авторских прав и информационных сообщений во время компиляции.  
  
## <a name="syntax"></a>Синтаксис  
  
```console  
-nologo  
```  
  
## <a name="remarks"></a>Примечания  

 При указании `-nologo` компилятор не отображает баннер авторских прав. По умолчанию `-nologo` не действует.  
  
> [!NOTE]
> Параметр `-nologo` недоступен в среде разработки Visual Studio. Его можно использовать только при компиляции из командной строки.  
  
## <a name="example"></a>Пример  

 Следующий код компилирует `T2.vb` и не отображает баннер авторских прав.  
  
```console
vbc -nologo t2.vb  
```  
  
## <a name="see-also"></a>См. также

- [Компилятор Visual Basic с интерфейсом командной строки](index.md)
- [Примеры командных строк компиляции](sample-compilation-command-lines.md)
