---
ms.openlocfilehash: dfa8235fcfd868b80d3a610bddb492899519e289
ms.sourcegitcommit: 81f1bba2c97a67b5ca76bcc57b37333ffca60c7b
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/10/2020
ms.locfileid: "97009073"
---
### <a name="xml-parsing-changes"></a>Изменения синтаксического анализа языка XML

| Имя    | Значение   |
|:--------|:--------|
| Область   | Дополнительный номер   |
| Version | 4.5.2   |
| Type    | Среда выполнения |

#### <a name="details"></a>Сведения

По соображениям безопасности в API синтаксического анализа языка XML были внесены следующие изменения.

- Для <xref:System.Xml.XmlReaderSettings.MaxCharactersFromEntities?displayProperty=nameWithType> устанавливается значение 10 миллионов при инициализации <xref:System.Xml.XmlReaderSettings>.
- По умолчанию свойству <xref:System.Xml.XmlReaderSettings.XmlResolver?displayProperty=nameWithType> присваивается значение `null`.

> [!NOTE]
> <xref:System.Xml.XmlReaderSettings> используется всеми средствами синтаксического анализа XML, поэтому хотя это изменение помогает в случае <xref:System.Xml.XmlReader>, оно также влияет на другие сценарии.

#### <a name="suggestion"></a>Предложение

Чтобы вернуться к предыдущему поведению, можно задать значение в реестре. Добавьте значение DWORD с именем `EnableLegacyXmlSettings` в раздел реестра `HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\.NETFramework\XML` и задайте для него значение `1`. Вместо этого можно также добавить значение реестра в куст HKEY_CURRENT_USER.

#### <a name="affected-apis"></a>Затронутые API

- <xref:System.Xml.XmlReaderSettings.MaxCharactersFromEntities?displayProperty=fullName>
- <xref:System.Xml.XmlReaderSettings.XmlResolver?displayProperty=fullName>

Затрагиваются также все API XML, которые прямо или косвенно зависят от <xref:System.Xml.XmlResolver>.

<!--

#### Affected APIs

- `P:System.Xml.XmlReaderSettings.MaxCharactersFromEntities`
- `P:System.Xml.XmlReaderSettings.XmlResolver`

-->
