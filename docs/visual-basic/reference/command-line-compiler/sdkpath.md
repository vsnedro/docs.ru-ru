---
title: -sdkpath
ms.date: 07/20/2015
f1_keywords:
- sdkpath
- -sdkpath
helpviewer_keywords:
- -sdkpath compiler option [Visual Basic]
- /sdkpath compiler option [Visual Basic]
- sdkpath compiler option [Visual Basic]
ms.assetid: fec8a3f1-b791-4a37-8af7-344859f8212d
ms.openlocfilehash: 46cec7ac3cb78c4fc97e299535f9085eff6daeff
ms.sourcegitcommit: eff6adb61852369ab690f3f047818c90580e7eb1
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/07/2019
ms.locfileid: "72004690"
---
# <a name="-sdkpath"></a>-sdkpath
Задает расположение библиотек mscorlib.dll и Microsoft.VisualBasic.dll.  
  
## <a name="syntax"></a>Синтаксис  
  
```console  
-sdkpath:path  
```  
  
## <a name="arguments"></a>Аргументы  
 `path`  
 Каталог, содержащий версии библиотек mscorlib.dll и Microsoft.VisualBasic.dll, которые следует использовать для компиляции. Этот путь является не проверенным до его загрузки. Если имя каталога содержит пробел, заключите это имя в кавычки (" ").  
  
## <a name="remarks"></a>Примечания  
 Этот параметр указывает компилятору Visual Basic, что нужно загрузить файлы mscorlib.dll и Microsoft.VisualBasic.dll из нестандартного расположения. Параметр `-sdkpath` предназначен для использования с параметром [-netcf](../../../visual-basic/reference/command-line-compiler/netcf.md). .NET Compact Framework использует разные версии этих библиотек поддержки, чтобы исключить использование типов и языковых компонентов, отсутствующих на устройствах.  
  
> [!NOTE]
> Параметр `-sdkpath` недоступен в среде разработки Visual Studio. Его можно использовать только при компиляции из командной строки. Параметр `-sdkpath` задается, когда загружается проект устройства Visual Basic.  
  
 С помощью параметра `-vbruntime` можно указать, что компилятор должен выполнять компиляцию без обращения к библиотеке времени выполнения Visual Basic. Дополнительные сведения см. в описании параметра [-vbruntime](../../../visual-basic/reference/command-line-compiler/vbruntime.md).  
  
## <a name="example"></a>Пример  
 В следующем примере кода выполняется компиляция `Myfile.vb` в .NET Compact Framework с использованием версий библиотек Mscorlib.dll и Microsoft.VisualBasic.dll, которые находятся в каталоге установки .NET Compact Framework по умолчанию на диске C. Как правило, следует использовать самую последнюю версию .NET Compact Framework.  
  
```console
vbc -netcf -sdkpath:"c:\Program Files\Microsoft Visual Studio .NET 2003\CompactFrameworkSDK\v1.0.5000\Windows CE " myfile.vb  
```  
  
## <a name="see-also"></a>См. также

- [Компилятор Visual Basic с интерфейсом командной строки](../../../visual-basic/reference/command-line-compiler/index.md)
- [Примеры командных строк компиляции](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)
- [-netcf](../../../visual-basic/reference/command-line-compiler/netcf.md)
- [-vbruntime](../../../visual-basic/reference/command-line-compiler/vbruntime.md)
