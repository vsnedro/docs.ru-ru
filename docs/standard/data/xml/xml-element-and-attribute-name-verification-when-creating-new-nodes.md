---
title: Проверка имен XML-элементов и атрибутов при создании новых узлов
ms.date: 03/30/2017
ms.technology: dotnet-standard
ms.assetid: b489f647-a175-4659-ada4-170058bb41d0
ms.openlocfilehash: 1da893261b35c6b57c4f08eb53b7701ec1d81fae
ms.sourcegitcommit: 33deec3e814238fb18a49b2a7e89278e27888291
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/02/2020
ms.locfileid: "84289854"
---
# <a name="xml-element-and-attribute-name-verification-when-creating-new-nodes"></a>Проверка имен XML-элементов и атрибутов при создании новых узлов
Модель XML DOM проверяет допустимость имен при создании новых узлов элементов или узлов атрибутов. Если имена содержат недопустимые символы, возникает исключение. Чтобы гарантировать допустимость и правильную кодировку имен, необходимо использовать класс **XmlConvert** для кодирования и декодирования имен на уровне приложения. Класс **XmlWriter** содержит методы, которые выполняют дополнительную работу, чтобы обеспечить формирование XML-документов правильного формата.  
  
## <a name="see-also"></a>См. также

- [Модель объектов документов XML (DOM)](xml-document-object-model-dom.md)
