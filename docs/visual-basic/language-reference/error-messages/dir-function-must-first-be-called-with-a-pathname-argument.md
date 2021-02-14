---
description: 'Дополнительные сведения о: функция Dir должна сначала вызываться с аргументом "PathName"'
title: Функция Dir должна первый раз вызываться с аргументом PathName
ms.date: 07/20/2015
f1_keywords:
- vbrDIR_IllegalCall
ms.assetid: 7b5d149f-be91-4ac3-8262-86a360894e7d
ms.openlocfilehash: 076828978b27911a97a4767cde1b1d7b04317a31
ms.sourcegitcommit: 10e719780594efc781b15295e499c66f316068b8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/14/2021
ms.locfileid: "100479976"
---
# <a name="dir-function-must-first-be-called-with-a-pathname-argument"></a>Функция Dir должна первый раз вызываться с аргументом PathName

Начальный вызов `Dir` функции не включает `PathName` аргумент. Первый вызов `Dir` должен включать `PathName` , но последующие вызовы `Dir` не обязательно должны включать параметры для получения следующего элемента.

## <a name="to-correct-this-error"></a>Исправление ошибки

- Укажите `PathName` аргумент в вызове функции.

## <a name="see-also"></a>См. также раздел

- <xref:Microsoft.VisualBasic.FileSystem.Dir%2A>
