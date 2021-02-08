---
description: 'Дополнительные сведения о: файл уже открыт'
title: Файл уже открыт
ms.date: 07/20/2015
f1_keywords:
- vbrID55
ms.assetid: d674a0fb-ef16-4cc2-9da7-709a8a07dbea
ms.openlocfilehash: 2f3345c15f4a3095a8e733c2c8424edb25b4dee6
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2021
ms.locfileid: "99796305"
---
# <a name="file-already-open"></a>Файл уже открыт

Иногда файл должен быть закрыт, прежде чем `FileOpen` может произойти другая операция. Некоторые из возможных причин этой ошибки:

- Операция последовательного режима вывода `FileOpen` была выполнена для уже открытого файла

- Оператор ссылается на открытый файл.

## <a name="to-correct-this-error"></a>Исправление ошибки

- Закройте файл перед выполнением инструкции.

## <a name="see-also"></a>См. также

- <xref:Microsoft.VisualBasic.FileSystem.FileOpen%2A>
