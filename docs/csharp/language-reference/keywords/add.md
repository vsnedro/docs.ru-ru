---
description: Узнайте, как создавать настраиваемые методы доступа к событиям с помощью добавления ключевого слова в C#
title: Справочник по C#. Ключевое слово add
ms.date: 07/20/2015
f1_keywords:
- add_CSharpKeyword
helpviewer_keywords:
- add event accessor [C#]
ms.assetid: faf30b99-10e8-45cd-ab9a-57585d4d1d8d
ms.openlocfilehash: 9daf635206ff9727a4bf333c123f68be812723cd
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/24/2020
ms.locfileid: "91168768"
---
# <a name="add-c-reference"></a>add (Справочник по C#)

Контекстное ключевое слово `add` определяет метод доступа настраиваемого события, который вызывается, когда клиентский код подписывается на [событие](./event.md). Если указан настраиваемый метод доступа `add`, также необходимо указать метод доступа [remove](./remove.md).  
  
## <a name="example"></a>Пример  

В следующем примере показано событие с настраиваемыми методами доступа `add` и [remove](./remove.md). Полный пример см. в статье [Как реализовать события интерфейса (руководство по программированию на C#)](../../programming-guide/events/how-to-implement-interface-events.md).
  
[!code-csharp[csrefKeywordsContextual#15](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsContextual/CS/csrefKeywordsContextual.cs#15)]
  
 Как правило, настраиваемые методы доступа к событиям не используются. В большинстве сценариев достаточно методов доступа, которые автоматически создаются компилятором при объявлении события.  
  
## <a name="see-also"></a>См. также

- [События](../../programming-guide/events/index.md)
