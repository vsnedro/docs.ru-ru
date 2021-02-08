---
description: 'Дополнительные сведения: <commonBehaviors>'
title: <commonBehaviors>
ms.date: 03/30/2017
ms.assetid: 5260aeca-388d-4e82-94c0-124fa8054cf5
ms.openlocfilehash: 2fa7397a2833623728bcca286682178d1cf3e1df
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2021
ms.locfileid: "99802324"
---
# \<commonBehaviors>

Раздел `commonBehaviors` может определяться только в файле machine.config. В нем определяются две дочерние коллекции с именами `endpointBehaviors` и `serviceBehaviors`.  Каждая коллекция определяет элементы поведения, используемые всеми конечными точками и службами WCF на компьютере соответственно. Поведения, определенные в `endpointBehaviors`, применяются только к клиентам, а поведения, определенные в `serviceBehaviors`, применяются только к службам. Если поведение определяется как в разделе `commonBehaviors`, так и в разделе `behaviors`, преимущество имеет поведение в разделе `behaviors`.
