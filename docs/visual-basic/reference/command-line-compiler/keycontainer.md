---
description: 'Дополнительные сведения: -keycontainer'
title: -keycontainer
ms.date: 03/10/2018
helpviewer_keywords:
- -keycontainer compiler option [Visual Basic]
- keycontainer compiler option [Visual Basic]
- /keycontainer compiler option [Visual Basic]
ms.assetid: 6a9bc861-1752-4db1-9f64-b5252f0482cc
ms.openlocfilehash: d8b83162d9404eb2ce80e5e531457360b040f27d
ms.sourcegitcommit: 10e719780594efc781b15295e499c66f316068b8
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/14/2021
ms.locfileid: "100436816"
---
# <a name="-keycontainer"></a>-keycontainer

Указывает имя контейнера для пары ключей, чтобы задать для сборки строгое имя.  
  
## <a name="syntax"></a>Синтаксис  
  
```console  
-keycontainer:container  
```  
  
## <a name="arguments"></a>Аргументы  
  
|Термин|Определение|  
|---|---|  
|`container`|Обязательный. Файл контейнера, содержащий ключ. Если имя файла содержит пробел, заключите это имя в кавычки (" ").|  
  
## <a name="remarks"></a>Примечания  

 Компилятор создает компонент, который можно сделать общим, вставляя в манифест сборки открытый ключ и подписывая окончательную сборку закрытым ключом. Чтобы создать файл ключа, в командной строке введите `sn -k file`. Параметр `-i` устанавливает пару ключей в контейнер. Дополнительные сведения см. в статье [Sn.exe (средство строгих имен)](../../../framework/tools/sn-exe-strong-name-tool.md).  
  
 При компиляции с параметром `-target:module` имя файла ключа сохраняется в модуле и включается в сборку, создаваемую при компиляции с параметром [-addmodule](addmodule.md).  
  
 Этот параметр можно также указать в исходном коде любого модуля MSIL в качестве настраиваемого атрибута (<xref:System.Reflection.AssemblyKeyNameAttribute>).  
  
 Также можно передать сведения о шифровании компилятору с помощью параметра [-keyfile](keyfile.md). Если требуется использовать частично подписанную сборку, применяйте параметр [-delaysign](delaysign.md).  
  
 Дополнительные сведения см. в статье [Создание и использование сборок со строгими именами](../../../standard/assembly/create-use-strong-named.md).  
  
> [!NOTE]
> Параметр `-keycontainer` недоступен в среде разработки Visual Studio. Он доступен только при компиляции из командной строки.  
  
## <a name="example"></a>Пример  

 Следующий код компилирует исходный файл `Input.vb` и определяет контейнер ключей.  
  
```console  
vbc -keycontainer:key1 input.vb  
```  
  
## <a name="see-also"></a>См. также

- [Сборки в .NET](../../../standard/assembly/index.md)
- [Компилятор Visual Basic с интерфейсом командной строки](index.md)
- [-keyfile](keyfile.md)
- [Примеры командных строк компиляции](sample-compilation-command-lines.md)
