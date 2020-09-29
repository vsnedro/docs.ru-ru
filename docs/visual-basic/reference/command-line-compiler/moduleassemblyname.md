---
title: -moduleassemblyname
ms.date: 03/13/2018
helpviewer_keywords:
- moduleassemblyname compiler option [Visual Basic]
- /moduleassemblyname compiler option [Visual Basic]
- -moduleassemblyname compiler option [Visual Basic]
ms.assetid: 013a57b6-f425-4dd3-b333-512d72c42f55
ms.openlocfilehash: 9fb9287f9472d4b33eff4cb601aff5eed370b2c0
ms.sourcegitcommit: bf5c5850654187705bc94cc40ebfb62fe346ab02
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/23/2020
ms.locfileid: "91065571"
---
# <a name="-moduleassemblyname"></a>-moduleassemblyname

Задает имя сборки, частью которой будет этот модуль.  
  
## <a name="syntax"></a>Синтаксис  
  
```console  
-moduleassemblyname:assembly_name  
```  
  
## <a name="arguments"></a>Аргументы  
  
|Термин|Определение|  
|---|---|  
|`assembly_name`|Имя сборки, частью которой будет этот модуль.|  
  
## <a name="remarks"></a>Примечания  

 Компилятор обрабатывает параметр `-moduleassemblyname` только в том случае, если был указан параметр `-target:module`. В результате компилятор создает модуль. Модуль, созданный компилятором, действителен только для сборки, указанной с помощью параметра `-moduleassemblyname`. Если разместить модуль в другой сборке, возникнут ошибки во время выполнения.  
  
 Параметр `-moduleassemblyname` требуется только в том случае, если выполняются следующие условия:  
  
- Для типа данных в модуле требуется доступ к типу `Friend` в сборке, на которую указывает ссылка.  
  
- Сборка, на которую указывает ссылка, предоставила дружественной сборке доступ к сборке, в которую будет встроен модуль.  
  
 Дополнительные сведения о создании модуля см. в разделе [-target (Visual Basic)](target.md). Дополнительные сведения о дружественных сборках см. в разделе [Дружественные сборки](../../../standard/assembly/friend.md).  
  
> [!NOTE]
> Параметр `-moduleassemblyname` недоступен в среде разработки Visual Studio. Его можно использовать только при компиляции из командной строки.  
  
## <a name="see-also"></a>См. также

- [Практическое руководство. Создание многофайловой сборки](../../../framework/app-domains/build-multifile-assembly.md)
- [Компилятор Visual Basic с интерфейсом командной строки](index.md)
- [-target (Visual Basic)](target.md)
- [-main](main.md)
- [-reference (Visual Basic)](reference.md)
- [-addmodule](addmodule.md)
- [Сборки в .NET](../../../standard/assembly/index.md)
- [Примеры командных строк компиляции](sample-compilation-command-lines.md)
- [Дружественные сборки](../../../standard/assembly/friend.md)
