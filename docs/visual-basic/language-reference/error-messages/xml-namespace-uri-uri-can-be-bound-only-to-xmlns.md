---
title: URI-код пространства имен XML <uri> может быть связан только с префиксом xmlns
ms.date: 07/20/2015
f1_keywords:
- bc31183
- vbc31183
helpviewer_keywords:
- BC31183
ms.assetid: 0ab1dbce-8397-4959-b2cd-f58798b051a0
ms.openlocfilehash: 1aec6ac0a354bfe7e0378a2e46a70a7161bf6d36
ms.sourcegitcommit: ff5a4eb5cffbcac9521bc44a907a118cd7e8638d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/17/2020
ms.locfileid: "92163250"
---
# <a name="bc31183-xml-namespace-uri-httpwwww3orgxml1998namespace-can-be-bound-only-to-xmlns"></a>BC31183: URI пространства имен XML `http://www.w3.org/XML/1998/namespace` ; может быть привязан только к "xmlns"

Универсальный код ресурса (URI) `http://www.w3.org/XML/1998/namespace` используется в объявлении пространства имен XML. Этот URI является зарезервированным пространством имен и не может быть включен в объявление пространства имен XML.

 **Идентификатор ошибки:** BC31183

## <a name="to-correct-this-error"></a>Исправление ошибки

Удалите объявление пространства имен XML или замените URI `http://www.w3.org/XML/1998/namespace` допустимым URI пространства имен.

## <a name="see-also"></a>См. также

- [Оператор Imports (пространство имен XML)](../statements/imports-statement-xml-namespace.md)
- [XML-литералы](../xml-literals/index.md)
- [XML](../../programming-guide/language-features/xml/index.md)
