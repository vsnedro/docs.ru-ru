---
description: -highentropyva (параметры компилятора C#)
title: -highentropyva (параметры компилятора C#)
ms.date: 07/20/2015
f1_keywords:
- /highentropyva
helpviewer_keywords:
- /highentropyva compiler option [C#]
- -highentropyva compiler option [C#]
- highentropyva compiler option [C#]
ms.assetid: eaf409b3-384e-49dd-9417-62453658f421
ms.openlocfilehash: f3cdeb5e63d632fecbbd94501558cc53c28a918a
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/24/2020
ms.locfileid: "91173208"
---
# <a name="-highentropyva-c-compiler-options"></a>-highentropyva (параметры компилятора C#)

Параметр компилятора **-highentropyva** сообщает ядру Windows, поддерживает ли указанный исполняемый файл технологию Address Space Layout Randomization (ASLR) с высокой энтропией.  
  
## <a name="syntax"></a>Синтаксис  
  
```console  
-highentropyva[+ | -]  
```  
  
## <a name="arguments"></a>Аргументы  

 `+` &#124; `-`  
 Этот параметр указывает, что 64-битный исполняемый файл или исполняемый файл, отмеченный параметром компилятора [-platform:anycpu](./platform-compiler-option.md), поддерживает виртуальное адресное пространство с высокой энтропией. Этот параметр отключен по умолчанию. Чтобы включить его, используйте параметр **-highentropyva+** или **-highentropyva**.  
  
## <a name="remarks"></a>Remarks  

 Параметр **-highentropyva** позволяет совместимым версиям ядра Windows использовать более высокие степени энтропии во время смешивания структуры адресного пространства процесса в рамках ASLR. Использование более высоких степеней энтропии означает, что можно выделить больше адресов таким областям памяти, как стеки и кучи. Из-за этого сложнее подобрать расположение определенной области памяти.  
  
 Если указан параметр компилятора **-highentropyva**, целевой исполняемый файл и все модули, от которых он зависит, должны быть способны обработать значения указателя, размер которых превышает 4 гигабайта (ГБ), если они выполняются как 64-разрядный процесс.
