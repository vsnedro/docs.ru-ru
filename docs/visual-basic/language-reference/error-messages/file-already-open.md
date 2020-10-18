---
title: Файл уже открыт
ms.date: 07/20/2015
f1_keywords:
- vbrID55
ms.assetid: d674a0fb-ef16-4cc2-9da7-709a8a07dbea
ms.openlocfilehash: ce8f8bf96d7355e45b2df82e8a131472c2ed2367
ms.sourcegitcommit: ff5a4eb5cffbcac9521bc44a907a118cd7e8638d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/17/2020
ms.locfileid: "92162756"
---
# <a name="file-already-open"></a>Файл уже открыт

Иногда файл должен быть закрыт, прежде чем `FileOpen` может произойти другая операция. Некоторые из возможных причин этой ошибки:

- Операция последовательного режима вывода `FileOpen` была выполнена для уже открытого файла

- Оператор ссылается на открытый файл.

## <a name="to-correct-this-error"></a>Исправление ошибки

- Закройте файл перед выполнением инструкции.

## <a name="see-also"></a>См. также

- <xref:Microsoft.VisualBasic.FileSystem.FileOpen%2A>
