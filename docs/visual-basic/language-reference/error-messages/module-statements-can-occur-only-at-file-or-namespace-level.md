---
description: 'Дополнительные сведения о: BC30617: операторы "Module" могут использоваться только на уровне файла или пространства имен'
title: Операторы Module могут присутствовать только на уровне файлов или пространств имен
ms.date: 07/20/2015
f1_keywords:
- bc30617
- vbc30617
helpviewer_keywords:
- BC30617
ms.assetid: 5e9de8e5-d26b-4fb2-9e28-814413fe9cef
ms.openlocfilehash: f5c3ea0cd1c08fb0243043ae50e707e2c59b00f2
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2021
ms.locfileid: "99795785"
---
# <a name="bc30617-module-statements-can-occur-only-at-file-or-namespace-level"></a>BC30617: операторы "Module" могут использоваться только на уровне файла или пространства имен

`Module` операторы должны находиться в верхней части исходного файла сразу после `Option` и `Imports` инструкций, глобальных атрибутов и объявлений пространств имен, но перед всеми остальными объявлениями.

 **Идентификатор ошибки:** BC30617

## <a name="to-correct-this-error"></a>Исправление ошибки

- Переместите оператор `Module` в начало объявления пространства имен или исходного файла.

## <a name="see-also"></a>См. также

- [Оператор Module](../statements/module-statement.md)
