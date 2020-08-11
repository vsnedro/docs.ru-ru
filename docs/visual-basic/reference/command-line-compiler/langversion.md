---
title: -langversion
ms.date: 03/10/2018
helpviewer_keywords:
- /langversion compiler option [Visual Basic]
- langversion compiler option [Visual Basic]
- -langversion compiler option [Visual Basic]
ms.assetid: 59b7b0c8-2dde-4e9b-94e7-0237f7e0bafb
ms.openlocfilehash: 286dd8bd9949b584cec38642f44ba9ac5e924732
ms.sourcegitcommit: b7a8b09828bab4e90f66af8d495ecd7024c45042
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87557181"
---
# <a name="-langversion-visual-basic"></a>-langversion (Visual Basic)
Инструктирует компилятор принимать только синтаксис, включенный в заданную версию языка Visual Basic.  
  
## <a name="syntax"></a>Синтаксис  
  
```console  
-langversion:version  
```  
  
## <a name="arguments"></a>Аргументы  
 `version`  
 Обязательный. Версия языка, используемая во время компиляции. Допустимые значения: `9`, `10`, `11`, `12`, `14`, `15`, `15.3`, `15.5`, `default` и `latest`.

 Любое из целых чисел можно также указать, используя `.0` в качестве дополнительной версии, например `11.0`.

 Чтобы просмотреть список всех возможных значений, укажите `-langversion:?` в командной строке.  
  
## <a name="remarks"></a>Примечания  
 Параметр `-langversion` указывает синтаксис, принимаемый компилятором. Например, если указать, что версия языка — 9.0, компилятор выдаст ошибки для синтаксиса, который допустим только в версии 10.0 и более поздних версиях.  
  
 Этот параметр можно использовать при разработке приложений, предназначенных для разных версий .NET Framework. Например, если приложение предназначено для .NET Framework 3.5, можно использовать этот параметр, чтобы не использовать синтаксис из версии языка 10.0.  
  
 Задать `-langversion` напрямую можно только с помощью командной строки. Дополнительные сведения см. в разделе [Указание конкретной версии или профиля .NET Framework](/visualstudio/ide/visual-studio-multi-targeting-overview).  
  
## <a name="example"></a>Пример  
 Следующий код компилирует `sample.vb` для Visual Basic 9.0.  
  
```console  
vbc -langversion:9.0 sample.vb  
```  
  
## <a name="see-also"></a>См. также

- [Компилятор Visual Basic с интерфейсом командной строки](index.md)
- [Примеры командных строк компиляции](sample-compilation-command-lines.md)
