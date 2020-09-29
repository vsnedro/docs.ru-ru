---
title: -highentropyva
ms.date: 03/10/2018
helpviewer_keywords:
- highentropyva compiler option (Visual Basic)
- /highentropyva compiler option (Visual Basic)
ms.assetid: ff25f20a-6ca2-467b-9e52-5cf439f5028e
ms.openlocfilehash: 4d88c302281097fabd0eb361d60319bc8a0daf8d
ms.sourcegitcommit: bf5c5850654187705bc94cc40ebfb62fe346ab02
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/23/2020
ms.locfileid: "91058070"
---
# <a name="-highentropyva-visual-basic"></a>-highentropyva (Visual Basic)

Указывает, что 64-разрядный исполняемый файл или исполняемый файл, отмеченный параметром компилятора [-platform:anycpu](platform.md), поддерживает технологию Address Space Layout Randomization (ASLR) с высокой энтропией.  
  
## <a name="syntax"></a>Синтаксис  
  
```console  
-highentropyva[+ | -]  
```  
  
## <a name="arguments"></a>Аргументы  

 `+` &#124; `-`  
 Необязательный элемент. Этот параметр выключен по умолчанию или если вы указываете `-highentropyva-`. Параметр включен, если вы указываете `-highentropyva` или `-highentropyva+`.  
  
## <a name="remarks"></a>Примечания  

 Если этот параметр указан, совместимые версии ядра Windows могут использовать более высокие степени энтропии, когда ядро вносит элемент случайности в структуру адресного пространства процесса в рамках ASLR. Если ядро использует более высокие степени энтропии, можно выделить больше адресов таким областям памяти, как стеки и кучи. Из-за этого сложнее подобрать расположение определенной области памяти.  
  
 Если этот параметр включен, целевой исполняемый файл и все модули, от которых он зависит, должны быть способны обработать значения указателя, размер которых превышает 4 гигабайта (ГБ), когда они выполняются как 64-разрядный процесс.  
  
## <a name="see-also"></a>См. также

- [Компилятор Visual Basic с интерфейсом командной строки](index.md)
- [Примеры командных строк компиляции](sample-compilation-command-lines.md)
