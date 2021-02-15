---
description: 'Дополнительные сведения: VbStrConv. Wide и VbStrConv. Narrow не могут быть объединены'
title: VbStrConv.Wide и VbStrConv.Narrow не могут использоваться вместе
ms.date: 07/20/2015
f1_keywords:
- vbrArgument_IllegalWideNarrow
ms.assetid: a53b4e6a-36b1-4e36-b2c5-8196313ec599
ms.openlocfilehash: 422c699bd06709368ea4f8948c4b2824a643e342
ms.sourcegitcommit: 10e719780594efc781b15295e499c66f316068b8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/14/2021
ms.locfileid: "100475673"
---
# <a name="vbstrconvwide-and-vbstrconvnarrow-cannot-be-combined"></a>VbStrConv.Wide и VbStrConv.Narrow не могут использоваться вместе

Приложение пытается объединить взаимоисключающие элементы `VbStrConv` и `Wide` перечисления `Narrow`.  
  
## <a name="to-correct-this-error"></a>Исправление ошибки  
  
1. Удалите `VbStrConv.Wide` или `VbStrConv.Narrow`.  
  
## <a name="see-also"></a>См. также раздел

- <xref:System.Globalization>

- [Разработка глобализованных и локализованных приложений](/visualstudio/ide/globalizing-and-localizing-applications)
