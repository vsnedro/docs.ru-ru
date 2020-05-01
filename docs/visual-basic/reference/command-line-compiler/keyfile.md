---
title: -keyfile
ms.date: 03/10/2018
helpviewer_keywords:
- /keyfile compiler option [Visual Basic]
- keyfile compiler option [Visual Basic]
- -keyfile compiler option [Visual Basic]
ms.assetid: ffa82a4b-517a-4c6c-9889-5bae7b534bb8
ms.openlocfilehash: cffc3c5f0ff3dd48ca2c74bde346a967b209dc5f
ms.sourcegitcommit: 43d10ef65f0f1fd6c3b515e363bde11a3fcd8d6d
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/04/2020
ms.locfileid: "78266746"
---
# <a name="-keyfile"></a>-keyfile
Указывает файл, содержащий ключ или пару ключей, чтобы задать для сборки строгое имя.  
  
## <a name="syntax"></a>Синтаксис  
  
```console
-keyfile:file  
```  
  
## <a name="arguments"></a>Аргументы  
 `file`  
 Обязательный. Файл, который содержит ключ. Если имя файла содержит пробел, заключите это имя в кавычки (" ").  
  
## <a name="remarks"></a>Примечания  
 Компилятор вставляет открытый ключ в манифест сборки, а затем подписывает окончательную сборку закрытым ключом. Чтобы создать файл ключа, в командной строке введите `sn -k file`. Дополнительные сведения см. в статье [Sn.exe (средство строгих имен)](../../../framework/tools/sn-exe-strong-name-tool.md).  
  
 При компиляции с параметром `-target:module` имя файла ключа сохраняется в модуле и включается в сборку, создаваемую при компиляции с параметром [-addmodule](../../../visual-basic/reference/command-line-compiler/addmodule.md).  
  
 Также можно передать сведения о шифровании компилятору с помощью параметра [-keycontainer](../../../visual-basic/reference/command-line-compiler/keycontainer.md). Если требуется использовать частично подписанную сборку, применяйте параметр [-delaysign](../../../visual-basic/reference/command-line-compiler/delaysign.md).  
  
 Этот параметр можно также указать в исходном коде любого модуля MSIL в качестве настраиваемого атрибута (<xref:System.Reflection.AssemblyKeyFileAttribute>).  
  
 Если для одной процедуры компиляции одновременно заданы параметры `-keyfile` и [-keycontainer](../../../visual-basic/reference/command-line-compiler/keycontainer.md) (в командной строке или с помощью пользовательских атрибутов), то сначала компилятор пытается использовать контейнер ключей. В случае успеха сборка подписывается данными контейнера ключей. Если компилятору не удастся обнаружить контейнер ключей, будет предпринята попытка использовать файл, заданный параметром `-keyfile`. В случае успеха сборка подписывается данными из файла ключей, и эти данные о ключах помещаются в контейнер ключей (аналогично команде `sn -i`). Теперь при следующей компиляции контейнер ключей будет действителен.  
  
 Обратите внимание, что файл ключей может содержать только открытый ключ.  
  
 Дополнительные сведения см. в статье [Создание и использование сборок со строгими именами](../../../standard/assembly/create-use-strong-named.md).  
  
> [!NOTE]
> Параметр `-keyfile` недоступен в среде разработки Visual Studio. Он доступен только при компиляции из командной строки.

## <a name="example"></a>Пример

Следующий код компилирует `Input.vb` и определяет файл ключей.

```console
vbc -keyfile:myfile.sn input.vb
```

## <a name="see-also"></a>См. также

- [Сборки в .NET](../../../standard/assembly/index.md)
- [Компилятор Visual Basic с интерфейсом командной строки](../../../visual-basic/reference/command-line-compiler/index.md)
- [-reference (Visual Basic)](../../../visual-basic/reference/command-line-compiler/reference.md)
- [Примеры командных строк компиляции](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)
