---
title: <interfacename>.<membername> уже реализован базовым классом <baseclassname>. Предполагается повторная реализация <type>
ms.date: 07/20/2015
f1_keywords:
- vbc42015
- bc42015
helpviewer_keywords:
- BC42015
ms.assetid: 658c070a-113e-4bd8-b294-12c243191160
ms.openlocfilehash: 8137f6b1712b6a0752a991f5a3d598b5f958252c
ms.sourcegitcommit: ff5a4eb5cffbcac9521bc44a907a118cd7e8638d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/17/2020
ms.locfileid: "92162821"
---
# <a name="bc42015-interfacenamemembername-is-already-implemented-by-the-base-class-baseclassname-re-implementation-of-type-assumed"></a>BC42015: " \<interfacename> . \<membername> " уже реализован базовым классом " \<baseclassname> ". Предполагается повторная реализация \<type>

Свойство, процедура или событие в производном классе использует `Implements` предложение, задающее член интерфейса, который уже реализован в базовом классе.

 Производный класс может повторно реализовать элемент интерфейса, который реализован его базовым классом. Это не та же переопределяющая реализация базового класса. Для получения дополнительной информации см. [Implements](../statements/implements-clause.md).

 По умолчанию данное сообщение является предупреждением. Сведения о сокрытии предупреждений или обработке предупреждений как ошибок см. в разделе [Configuring Warnings in Visual Basic](/visualstudio/ide/configuring-warnings-in-visual-basic).

 **Идентификатор ошибки:** BC42015

## <a name="to-correct-this-error"></a>Исправление ошибки

- Если вы собираетесь реализовать элемент интерфейса, вам не нужно предпринимать никаких действий. Код в производном классе обращается к повторно реализованному элементу, если не используется `MyBase` ключевое слово для доступа к реализации базового класса.

- Если вы не собираетесь реализовать элемент интерфейса, удалите предложение `Implements` из свойства, процедуры или объявления события.

## <a name="see-also"></a>См. также

- [Интерфейсы](../../programming-guide/language-features/interfaces/index.md)
