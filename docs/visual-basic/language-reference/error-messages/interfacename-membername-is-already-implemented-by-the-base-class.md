---
title: <interfacename>.<membername> уже реализован базовым классом <baseclassname>. Предполагается повторная реализация <type>
ms.date: 07/20/2015
f1_keywords:
- vbc42015
- bc42015
helpviewer_keywords:
- BC42015
ms.assetid: 658c070a-113e-4bd8-b294-12c243191160
ms.openlocfilehash: 6525ae08b90cc530a8f6a469d35d9ab8c27fb5e3
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/04/2020
ms.locfileid: "84402828"
---
# <a name="interfacenamemembername-is-already-implemented-by-the-base-class-baseclassname-re-implementation-of-type-assumed"></a>\<interfacename>.\<membername> уже реализован базовым классом \<baseclassname>. Предполагается повторная реализация \<type>
Свойство, процедура или событие в производном классе использует `Implements` предложение, задающее член интерфейса, который уже реализован в базовом классе.  
  
 Производный класс может повторно реализовать элемент интерфейса, который реализован его базовым классом. Это не та же переопределяющая реализация базового класса. Для получения дополнительной информации см. [Implements](../statements/implements-clause.md).  
  
 По умолчанию данное сообщение является предупреждением. Сведения о сокрытии предупреждений или обработке предупреждений как ошибок см. в разделе [Configuring Warnings in Visual Basic](/visualstudio/ide/configuring-warnings-in-visual-basic).  
  
 **Идентификатор ошибки:** BC42015  
  
## <a name="to-correct-this-error"></a>Исправление ошибки  
  
- Если вы собираетесь реализовать элемент интерфейса, вам не нужно предпринимать никаких действий. Код в производном классе обращается к повторно реализованному элементу, если не используется `MyBase` ключевое слово для доступа к реализации базового класса.  
  
- Если вы не собираетесь реализовать элемент интерфейса, удалите предложение `Implements` из свойства, процедуры или объявления события.  
  
## <a name="see-also"></a>См. также раздел

- [Интерфейсы](../../programming-guide/language-features/interfaces/index.md)
