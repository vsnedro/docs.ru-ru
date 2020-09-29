---
title: -baseaddress
ms.date: 08/09/2018
f1_keywords:
- /baseaddress
- baseaddress
helpviewer_keywords:
- -baseaddress compiler option [Visual Basic]
- /baseaddress compiler option [Visual Basic]
- baseaddress compiler option [Visual Basic]
ms.assetid: c982bcf2-46e5-47a2-bc8f-a5cc32b7dc47
ms.openlocfilehash: c794d1fc1c9d20e22ffa747e3175c846341ad8ad
ms.sourcegitcommit: bf5c5850654187705bc94cc40ebfb62fe346ab02
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/23/2020
ms.locfileid: "91097765"
---
# <a name="-baseaddress"></a>-baseaddress

Определяет базовый адрес по умолчанию при создании библиотеки DLL.  
  
## <a name="syntax"></a>Синтаксис  
  
```console  
-baseaddress:address  
```  
  
## <a name="arguments"></a>Аргументы  
  
|Термин|Определение|  
|---|---|  
|`address`|Обязательный. Базовый адрес для библиотеки DLL. Этот адрес можно определить как десятичное, шестнадцатеричное или восьмеричное число.|  
  
## <a name="remarks"></a>Примечания  

 Базовый адрес по умолчанию для библиотеки DLL задается платформой .NET Framework.  
  
 Обратите внимание, что младшее слово этого адреса будет округляться. Например, значение 0x11110001 округляется до 0x11110000.  
  
 Чтобы завершить процесс подписи для библиотеки DLL, используйте параметр `–R` средства Strong Name (Sn.exe).  
  
 Этот параметр не учитывается, если целевой объект не является библиотекой DLL.  
  
|Чтобы задать параметр -baseaddress в Visual Studio IDE, сделайте следующее:|  
|---|  
|1.  Выберите проект в **Обозревателе решений**. В меню **Проект** выберите пункт **Свойства**. <br />2.  Откройте вкладку **Компиляция**.<br />3.  Нажмите кнопку **Дополнительно**.<br />4.  Измените значение в поле **Базовый адрес DLL**. **Примечание.**      Поле **Базовый адрес DLL** доступно только для чтения, если целевой объект не является библиотекой DLL.|  
  
## <a name="see-also"></a>См. также

- [Компилятор Visual Basic с интерфейсом командной строки](index.md)
- [-target (Visual Basic)](target.md)
- [Примеры командных строк компиляции](sample-compilation-command-lines.md)
- [Sn.exe (средство Strong Name)](../../../framework/tools/sn-exe-strong-name-tool.md))
