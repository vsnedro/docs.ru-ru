---
title: -publicsign (параметры компилятора C#)
ms.date: 05/15/2018
f1_keywords:
- /publicsign
helpviewer_keywords:
- -publicsign compiler option [C#]
- publicsign compiler option [C#]
- /publicsign compiler option [C#]
ms.openlocfilehash: 2655e0216a412053e052ab2ec2fcc8c68ea4f968
ms.sourcegitcommit: 0100be20fcf23f61dab672deced70059ed71bb2e
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/17/2020
ms.locfileid: "88268053"
---
# <a name="-publicsign-c-compiler-options"></a>-publicsign (параметры компилятора C#)

Этот параметр указывает компилятору на необходимость применения открытого ключа, но фактически не подписывает сборку. Кроме того, параметр **-publicsign** задает в сборке бит, который сообщает среде выполнения, что файл подписан.

## <a name="syntax"></a>Синтаксис

```console
-publicsign
```

## <a name="arguments"></a>Аргументы

Нет.

## <a name="remarks"></a>Remarks

С параметром **-publicsign** необходимо использовать параметр [-keyfile](keyfile-compiler-option.md) или [-keycontainer](keycontainer-compiler-option.md). Каждый из параметров **keyfile** и **keycontainer** определяет открытый ключ.

Параметры **-publicsign** и **-delaysign** — взаимоисключающие.

При таком подписывании в сборку добавляется открытый ключ. Кроме того, в сборке устанавливается флаг "подписано", хотя фактически сборка не подписывается закрытым ключом. Такой подход иногда называют "фиктивным подписыванием" или "подписыванием OSS". Он полезен на проектах с открытым исходным кодом: людям нужно создавать сборки, которые будут совместимы с выпущенными "полностью подписанными" сборками, но у них нет доступа к закрытому ключу, который использовался для подписывания сборок. Так как потребителям практически никогда не нужно проверять, полностью ли подписана сборка, создаваемые сообществами сборки можно использовать практические во всех случаях, в которых может использоваться полностью подписанная сборка.

### <a name="to-set-this-compiler-option-in-a-csproj-file"></a>Установка параметра компилятора в CSPROJ-файле

Откройте CSPROJ-файл проекта и добавьте следующий элемент:

```xml
<PublicSign>true</PublicSign>
```

## <a name="see-also"></a>См. также раздел

- [-delaysign (параметры компилятора C#)](delaysign-compiler-option.md)
- [-keyfile (параметры компилятора C#)](keyfile-compiler-option.md)
- [-keycontainer (параметры компилятора C#)](keycontainer-compiler-option.md)
- [Параметры компилятора C# ](index.md)
- [Управление свойствами проектов и решений](/visualstudio/ide/managing-project-and-solution-properties)
