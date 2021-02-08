---
description: Дополнительные сведения о функции "Dir" должны быть вызваны с аргументом "PathName".
title: Функция Dir должна первый раз вызываться с аргументом PathName
ms.date: 07/20/2015
f1_keywords:
- vbrDIR_IllegalCall
ms.assetid: 7b5d149f-be91-4ac3-8262-86a360894e7d
ms.openlocfilehash: ee492a269d41e8c9fe1fddbd59210b59fbe8618c
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2021
ms.locfileid: "99796591"
---
# <a name="dir-function-must-first-be-called-with-a-pathname-argument"></a>Функция Dir должна первый раз вызываться с аргументом PathName

Начальный вызов `Dir` функции не включает `PathName` аргумент. Первый вызов `Dir` должен включать `PathName` , но последующие вызовы `Dir` не обязательно должны включать параметры для получения следующего элемента.

## <a name="to-correct-this-error"></a>Исправление ошибки

- Укажите `PathName` аргумент в вызове функции.

## <a name="see-also"></a>См. также

- <xref:Microsoft.VisualBasic.FileSystem.Dir%2A>
