---
description: 'Дополнительные сведения о: BC31535: Недопустимая ссылка на дружественную сборку <reference>'
title: Ссылка <reference> на дружественную сборку является недопустимой
ms.date: 07/20/2015
f1_keywords:
- vbc31535
- bc31535
helpviewer_keywords:
- BC31535
ms.assetid: 6540c1d0-bb19-4051-a579-2e4f9094585e
ms.openlocfilehash: e3e08edede9bee4710c415a61592857229ea4f35
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2021
ms.locfileid: "99796201"
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
