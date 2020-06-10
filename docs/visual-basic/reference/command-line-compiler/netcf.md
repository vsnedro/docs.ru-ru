---
title: -netcf
ms.date: 03/13/2018
f1_keywords:
- /netcf
- -netcf
helpviewer_keywords:
- -netcf compiler option [Visual Basic]
- netcf compiler option [Visual Basic]
- /netcf compiler option [Visual Basic]
ms.assetid: db7cfa59-c315-401c-a59b-0daf355343d6
ms.openlocfilehash: 16fb6b3b63c848ea6c09cc18b0fcc488670f0926
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/04/2020
ms.locfileid: "84397479"
---
# <a name="-netcf"></a>-netcf

Задает для компилятора нацеливание на .NET Compact Framework.

## <a name="syntax"></a>Синтаксис

```console
-netcf
```

## <a name="remarks"></a>Примечания

Параметр `-netcf` указывает компилятору Visual Basic, что нужно нацеливать сборку на .NET Compact Framework вместо полной версии .NET Framework. Все функции языка, которые присутствуют только в полной версии .NET Framework, при этом отключаются.

Параметр `-netcf` предназначен для использования с [-sdkpath](sdkpath.md). Параметр `-netcf` позволяет отключить те же функции языка, которые отсутствуют в файлах с нацеливанием на `-sdkpath`.

> [!NOTE]
> Параметр `-netcf` недоступен в среде разработки Visual Studio. Он доступен только при компиляции из командной строки. Параметр `-netcf` задается, когда загружается проект устройства Visual Basic.

Параметр `-netcf` изменяет следующие функции языка:

- Блокируется ключевое слово [End \<keyword>Statement](../../language-reference/statements/end-keyword-statement.md), которое завершает выполнение программы. Следующая программа будет успешно скомпилирована и выполнена без `-netcf`, но возвратит ошибку во время компиляции с параметром `-netcf`.

  [!code-vb[VbVbalrCompiler#34](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrCompiler/VB/netcf.vb#34)]

- Блокируется позднее связывание во всех его проявлениях. При обнаружении любых сценариев позднего связывания создаются ошибки времени компиляции. Следующая программа будет успешно скомпилирована и выполнена без `-netcf`, но возвратит ошибку во время компиляции с параметром `-netcf`.

  [!code-vb[VbVbalrCompiler#35](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrCompiler/VB/OptionStrictOff.vb#35)]

- Блокируются модификаторы [Auto](../../language-reference/modifiers/auto.md), [Ansi](../../language-reference/modifiers/ansi.md) и [Unicode](../../language-reference/modifiers/unicode.md). Синтаксис [инструкции Declare](../../language-reference/statements/declare-statement.md) изменяется на `Declare Sub|Function name Lib "library" [Alias "alias"] [([arglist])]`. В следующем коде показано влияние параметра `-netcf` на процесс компиляции.

  [!code-vb[VbVbalrCompiler#36](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrCompiler/VB/OptionStrictOff.vb#36)]

- Использование ключевых слов Visual Basic 6.0, которые были удалены из Visual Basic, приводит к созданию другой ошибки, если используется параметр `-netcf`. Это влияет на сообщения об ошибках для следующих ключевых слов:

  - `Open`

  - `Close`

  - `Put`

  - `Print`

  - `Write`

  - `Input`

  - `Lock`

  - `Unlock`

  - `Seek`

  - `Width`

  - `Name`

  - `FreeFile`

  - `EOF`

  - `Loc`

  - `LOF`

  - `Line`

## <a name="example"></a>Пример

В следующем примере кода выполняется компиляция `Myfile.vb` в .NET Compact Framework с использованием версий библиотек mscorlib.dll и Microsoft.VisualBasic.dll, которые находятся в каталоге установки .NET Compact Framework по умолчанию на диске C. Как правило, следует использовать самую последнюю версию .NET Compact Framework.

```console
vbc -netcf -sdkpath:"c:\Program Files\Microsoft Visual Studio .NET 2003\CompactFrameworkSDK\v1.0.5000\Windows CE " myfile.vb
```

## <a name="see-also"></a>См. также

- [Компилятор Visual Basic с интерфейсом командной строки](index.md)
- [Примеры командных строк компиляции](sample-compilation-command-lines.md)
- [-sdkpath](sdkpath.md)
