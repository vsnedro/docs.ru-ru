---
title: -delaysign
ms.date: 03/10/2018
helpviewer_keywords:
- delaysign compiler option [Visual Basic]
- -delaysign compiler option [Visual Basic]
- -delaysign compiler option [Visual Basic]
ms.assetid: c76e61a4-1884-4252-9fb2-377f99caa690
ms.openlocfilehash: 3ee94df096b756be544964cfbbd405355e3f728f
ms.sourcegitcommit: 1f12db2d852d05bed8c53845f0b5a57a762979c8
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/18/2019
ms.locfileid: "72581272"
---
# <a name="-delaysign"></a>-delaysign

Указывает, будет ли сборка полностью или частично подписана.

## <a name="syntax"></a>Синтаксис

```console
-delaysign[+ | -]
```

## <a name="arguments"></a>Аргументы

`+` &#124; `-`  
Необязательный элемент. Если требуется полностью подписанная сборка, используйте `-delaysign-`. Используйте `-delaysign+`, если необходимо поместить открытый ключ в сборку и зарезервировать пространство для подписанного хэша. Значение по умолчанию — `-delaysign-`.

## <a name="remarks"></a>Примечания

Параметр `-delaysign` не имеет никакого эффекта, если вместе с ним не указан параметр [-keyfile](../../../visual-basic/reference/command-line-compiler/keyfile.md) или [-keycontainer](../../../visual-basic/reference/command-line-compiler/keycontainer.md).

При запросе полностью подписанной сборки компилятор хэширует файл, содержащий манифест (метаданные сборки), и подписывает хэш закрытым ключом. Итоговая цифровая подпись хранится в файле, содержащем манифест. При использовании отложенной подписи компилятор не вычисляет и не сохраняет подпись, а резервирует место в файле для добавления подписи в сборку в будущем.

Например, с помощью `-delaysign+` разработчик в организации может распространять неподписанные тестовые версии сборки, которые тест-инженеры могут зарегистрировать в глобальном кэше сборок и впоследствии использовать. После завершения работы над сборкой лицо, ответственное за закрытый ключ организации, может полностью подписать сборку. Такая схема защищает закрытый ключ организации от раскрытия и при этом позволяет всем разработчикам работать со сборками.

Дополнительные сведения см. в статье [Создание и использование сборок со строгими именами](../../../standard/assembly/create-use-strong-named.md).

### <a name="to-set--delaysign-in-the-visual-studio-integrated-development-environment"></a>Задание параметра -delaysign в интегрированной среде разработки Visual Studio

1. Выберите проект в **Обозревателе решений**. В меню **Проект** выберите пункт **Свойства**.

2. Откройте вкладку **Подписывание**.

3. Задайте значение в поле **Только отложенная подпись**.

## <a name="see-also"></a>См. также

- [Компилятор Visual Basic с интерфейсом командной строки](../../../visual-basic/reference/command-line-compiler/index.md)
- [-keyfile](../../../visual-basic/reference/command-line-compiler/keyfile.md)
- [-keycontainer](../../../visual-basic/reference/command-line-compiler/keycontainer.md)
- [Примеры командных строк компиляции](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)
