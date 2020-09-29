---
title: -verbose
ms.date: 03/13/2018
helpviewer_keywords:
- verbose compiler option [Visual Basic]
- -verbose compiler option [Visual Basic]
- /verbose compiler option [Visual Basic]
ms.assetid: d1aec0c1-0261-421d-9adc-5b13756100be
ms.openlocfilehash: c5bf988d819a8df8aed99588abbb30e19d14b1ac
ms.sourcegitcommit: bf5c5850654187705bc94cc40ebfb62fe346ab02
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/23/2020
ms.locfileid: "91084987"
---
# <a name="-verbose"></a>-verbose

Заставляет компилятор выдавать подробные сообщения о состоянии и ошибках.  
  
## <a name="syntax"></a>Синтаксис  
  
```console  
-verbose[+ | -]  
```  
  
## <a name="arguments"></a>Аргументы  

 `+` &#124; `-`  
 Необязательный элемент. Указание `-verbose` аналогично указанию `-verbose+` и приводит к тому, что компилятор выдает подробные сообщения. Значение этого параметра по умолчанию равно `-verbose-`.  
  
## <a name="remarks"></a>Примечания  

 Параметр `-verbose` отображает сведения об общем количестве ошибок, выданных компилятором, сообщает о том, какие сборки загружаются модулем, и показывает, какие файлы в данный момент компилируются.  
  
> [!NOTE]
> Параметр `-verbose` недоступен в среде разработки Visual Studio. Его можно использовать только при компиляции из командной строки.  
  
## <a name="example"></a>Пример  

 Следующий код компилирует `In.vb` и предписывает компилятору отображать подробные сведения о состоянии.  
  
```console  
vbc -verbose in.vb  
```  
  
## <a name="see-also"></a>См. также

- [Компилятор Visual Basic с интерфейсом командной строки](index.md)
- [Примеры командных строк компиляции](sample-compilation-command-lines.md)
