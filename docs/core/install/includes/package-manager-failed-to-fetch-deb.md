---
ms.openlocfilehash: 15418d1ac3ade6a0fa35ca61a02134e20af1baea
ms.sourcegitcommit: cdb295dd1db589ce5169ac9ff096f01fd0c2da9d
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/09/2020
ms.locfileid: "84602744"
---

При установке пакета .NET Core может появиться примерно такое сообщение об ошибке: `Failed to fetch ... File has unexpected size ... Mirror sync in progress?`. Эта ошибка может означать, что веб-канал пакета для .NET Core сейчас обновляется до новой версии пакета и следует повторить попытку позже. Во время обновления веб-канал пакета остается недоступным не более 30 минут. Если вы продолжаете получать эту ошибку через 30 минут, отправьте заявку о проблеме на адрес <https://github.com/dotnet/core/issues>.
