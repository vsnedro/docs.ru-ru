---
title: Коллекции узлов в NamedNodeMap и NodeList
ms.date: 03/30/2017
ms.technology: dotnet-standard
ms.assetid: 025954b8-7aa8-47c5-a1c1-f81064fb4d65
ms.openlocfilehash: 3d721e9a6cff87adbf8896b1b37c0e2dfa55fa71
ms.sourcegitcommit: 33deec3e814238fb18a49b2a7e89278e27888291
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/02/2020
ms.locfileid: "84288775"
---
# <a name="node-collections-in-namednodemaps-and-nodelists"></a>Коллекции узлов в NamedNodeMap и NodeList
Можно получить набор узлов и поместить его в упорядоченную или неупорядоченную коллекцию. Если набор узлов помещается в неупорядоченную коллекцию, он получает имя NamedNodeMap согласно спецификации консорциума W3C. В этом типе коллекции данные можно получить по имени или по индексу. Набор узлов, помещенный в упорядоченную коллекцию, согласно спецификации W3C называется NodeList, и данные можно получить по индексу, начинающемуся с нуля. Коллекции NamedNodeMap и NodeList описаны в документах W3C. Реализацией коллекции NamedNodeMap в платформе Microsoft .NET Framework является класс **XmlNamedNodeMap**, а коллекция NodeList реализована в классе **XmlNodeList**.  
  
 Дополнительные сведения о неупорядоченных коллекциях см. в руководстве по [получению неупорядоченных узлов по имени или индексу](unordered-node-retrieval-by-name-or-index.md). Дополнительные сведения об упорядоченных коллекциях см. в руководстве по [получению упорядоченных узлов по индексу](ordered-node-retrieval-by-index.md).  
  
## <a name="see-also"></a>См. также

- [Модель объектов документов XML (DOM)](xml-document-object-model-dom.md)
