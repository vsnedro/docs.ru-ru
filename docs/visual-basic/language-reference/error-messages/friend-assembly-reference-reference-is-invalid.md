---
title: Ссылка <reference> на дружественную сборку является недопустимой
ms.date: 07/20/2015
f1_keywords:
- vbc31535
- bc31535
helpviewer_keywords:
- BC31535
ms.assetid: 6540c1d0-bb19-4051-a579-2e4f9094585e
ms.openlocfilehash: 72c030d18d5339908c5088e104f6a8ad3e76943b
ms.sourcegitcommit: d2db216e46323f73b32ae312c9e4135258e5d68e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/22/2020
ms.locfileid: "90874089"
---
# <a name="friend-assembly-reference-reference-is-invalid"></a>Ссылка \<reference> на дружественную сборку является недопустимой

Недопустимая ссылка на дружественную сборку \<reference> . Для сборок, подписанных строгим именем, в объявлении InternalsVisibleTo должен быть указан открытый ключ.  
  
 Имя сборки, передаваемое <xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute> конструктору атрибута, определяет сборку со строгим именем, но не включает `PublicKey` атрибут.  
  
 **Идентификатор ошибки:** BC31535  
  
## <a name="to-correct-this-error"></a>Исправление ошибки  
  
1. Определите открытый ключ для дружественной сборки со строгими именами. Включите открытый ключ как часть имени сборки, передаваемой <xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute> конструктору атрибута с помощью `PublicKey` атрибута.  
  
## <a name="see-also"></a>См. также

- <xref:System.Reflection.AssemblyName>
- [Дружественные сборки](../../../standard/assembly/friend.md)
