---
description: 'Дополнительные сведения: -quiet'
title: -quiet
ms.date: 07/20/2015
f1_keywords:
- -quiet
- quiet
helpviewer_keywords:
- -quiet compiler option [Visual Basic]
- /quiet compiler option [Visual Basic]
- quiet compiler option [Visual Basic]
ms.assetid: 5d77fa23-4c50-4708-8535-649912b098e8
ms.openlocfilehash: 23e1b6472e80ac6ca2ecea5c4390b43722ccebb6
ms.sourcegitcommit: 10e719780594efc781b15295e499c66f316068b8
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/14/2021
ms.locfileid: "100432732"
---
# <a name="-quiet"></a>-quiet

Запрещает компилятору показывать код синтаксических ошибок и предупреждений.

## <a name="syntax"></a>Синтаксис

```console
-quiet
```

## <a name="remarks"></a>Примечания

По умолчанию `-quiet` не действует. Когда компилятор сообщает об ошибке или предупреждении, связанных с синтаксисом, он также выводит соответствующую строку из исходного кода. Для приложений, анализирующих выходные данные компилятора, может быть удобнее, чтобы компилятор выводил только текстовую часть диагностической информации.

В следующем примере `Module1` выводит ошибку, включающую в себя исходный код, при компиляции без `-quiet`.

```vb
Module Module1
    Sub Main()
        x()
    End Sub
End Module
```

Результат

```console
C:\projects\vb2.vb(3) : error BC30451: 'x' is not declared. It may be inaccessible due to its protection level.

        x()
        ~
```

При компиляции с `-quiet` компилятор выводит только следующие данные:

```console
E:\test\t2.vb(3) : error BC30451: Name 'x' is not declared.
```

> [!NOTE]
> Параметр `-quiet` недоступен в среде разработки Visual Studio. Он доступен только при компиляции из командной строки.

## <a name="example"></a>Пример

Следующий код компилирует `T2.vb` и не отображает код для диагностической информации компилятора, связанной с синтаксисом:

```console
vbc -quiet t2.vb
```

## <a name="see-also"></a>См. также

- [Компилятор Visual Basic с интерфейсом командной строки](index.md)
- [Примеры командных строк компиляции](sample-compilation-command-lines.md)
