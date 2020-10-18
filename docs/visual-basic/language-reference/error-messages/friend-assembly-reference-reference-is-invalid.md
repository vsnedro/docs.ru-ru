---
title: Ссылка <reference> на дружественную сборку является недопустимой
ms.date: 07/20/2015
f1_keywords:
- vbc31535
- bc31535
helpviewer_keywords:
- BC31535
ms.assetid: 6540c1d0-bb19-4051-a579-2e4f9094585e
ms.openlocfilehash: a42dd99ffaa06dce4823ce5d022fac02ae99c6bd
ms.sourcegitcommit: ff5a4eb5cffbcac9521bc44a907a118cd7e8638d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/17/2020
ms.locfileid: "92160715"
---
# <a name="bc31535-friend-assembly-reference-reference-is-invalid"></a>BC31535: Недопустимая ссылка на дружественную сборку \<reference>

Недопустимая ссылка на дружественную сборку \<reference> . Для сборок, подписанных строгим именем, в объявлении InternalsVisibleTo должен быть указан открытый ключ.

 Имя сборки, передаваемое <xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute> конструктору атрибута, определяет сборку со строгим именем, но не включает `PublicKey` атрибут.

 **Идентификатор ошибки:** BC31535

## <a name="to-correct-this-error"></a>Исправление ошибки

1. Определите открытый ключ для дружественной сборки со строгими именами. Включите открытый ключ как часть имени сборки, передаваемой <xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute> конструктору атрибута с помощью `PublicKey` атрибута.

## <a name="see-also"></a>См. также

- <xref:System.Reflection.AssemblyName>
- [Дружественные сборки](../../../standard/assembly/friend.md)
