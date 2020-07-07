---
ms.openlocfilehash: f980c8029375074889505a8eb7e8a65aaa8d74e4
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.contentlocale: ru-RU
ms.lasthandoff: 07/01/2020
ms.locfileid: "85614772"
---
### <a name="resgen-refuses-to-load-content-from-the-web"></a>Resgen не загружает содержимое из Интернета

#### <a name="details"></a>Подробнее

Файлы RESX могут содержать входные данные в двоичном формате. При попытке использовать Resgen для загрузки файла, скачанного из ненадежного расположения, входные данные по умолчанию не загружаются.

#### <a name="suggestion"></a>Предложение

Пользователи Resgen, которым нужно загрузить входные данные в двоичном формате из ненадежных расположений, могут либо удалить отметку интернет-источника из входного файла, либо применить неявное согласие. Добавьте следующий параметр реестра, чтобы применить неявное согласие на уровне компьютера: [HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft.NETFramework\SDK] &quot;AllowProcessOfUntrustedResourceFiles&quot;=&quot;true&quot;.

| name    | Значение       |
|:--------|:------------|
| Область   | Пограничный случай        |
| Version | 4.7.2       |
| Type    | Изменение целевой платформы |
