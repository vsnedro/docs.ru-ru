---
ms.openlocfilehash: 53860bb867522503c5cb9bd35e25fadd00a116a2
ms.sourcegitcommit: 97405ed212f69b0a32faa66a5d5fae7e76628b68
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/01/2020
ms.locfileid: "91609169"
---
### <a name="multi-line-aspnet-textbox-spacing-changed-when-using-antixssencoder"></a>Изменены интервалы многострочного текстового поля ASP.NET при использовании AntiXSSEncoder

#### <a name="details"></a>Подробнее

В .NET Framework 4.0 между строками многострочного текстового поля при обратной передаче вставлялись дополнительные строки, если использовался <xref:System.Web.Security.AntiXss.AntiXssEncoder?displayProperty=fullName>. В .NET Framework 4.5 эти дополнительные разрывы строк отсутствуют только в том случае, если веб-приложение предназначено для .NET Framework 4.5

#### <a name="suggestion"></a>Предложение

Имейте в виду, что в веб-приложениях 4.0, перенаправленных на .NET Framework 4.5, многострочные текстовые поля могут быть усовершенствованы, чтобы больше не вставлять дополнительные разрывы строк. Если это нежелательно, для приложения, выполняющегося в .NET Framework 4.5, можно сохранить старое поведение путем изменения версии платформы на .NET Framework 4.0.

| name    | Значение       |
|:--------|:------------|
| Область   | Дополнительный номер       |
| Version | 4.5         |
| Type    | Изменение целевой платформы |
