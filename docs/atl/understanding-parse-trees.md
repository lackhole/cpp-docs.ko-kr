---
title: ATL 등록자 및 구문 분석 트리
ms.date: 11/04/2016
helpviewer_keywords:
- parse trees
ms.assetid: 668ce2dd-a1c3-4ca0-8135-b25267cb6a85
ms.openlocfilehash: e1aea573e78e6f6a9a86bc4e3987ee448815f329
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62196170"
---
# <a name="understanding-parse-trees"></a>구문 분석 트리 이해

여기서 각 구문 분석 트리 형식은 등록자 스크립트에서 하나 이상의 구문 분석 트리를 정의할 수 있습니다.

```
<root key>{<registry expression>}+
```

다음은 각 문자에 대한 설명입니다.

```
<root key> ::= HKEY_CLASSES_ROOT | HKEY_CURRENT_USER |
    HKEY_LOCAL_MACHINE | HKEY_USERS |
    HKEY_PERFORMANCE_DATA | HKEY_DYN_DATA |
    HKEY_CURRENT_CONFIG | HKCR | HKCU |
    HKLM | HKU | HKPD | HKDD | HKCC
<registry expression> ::= <Add Key> | <Delete Key>
<Add Key> ::= [ForceRemove | NoRemove | val]<Key Name> [<Key Value>][{<Add Key>}]
<Delete Key> ::= Delete<Key Name>
<Key Name> ::= '<AlphaNumeric>+'
<AlphaNumeric> ::= any character not NULL, i.e. ASCII 0
<Key Value> ::== <Key Type><Key Name>
<Key Type> ::= s | d
<Key Value> ::= '<AlphaNumeric>'
```

> [!NOTE]
> `HKEY_CLASSES_ROOT` 및 `HKCR` 동일 합니다. `HKEY_CURRENT_USER` 고 `HKCU` ; 동일 하며 등입니다.

구문 분석 트리 여러 키와 하위 키를 추가할 수는 \<루트 키 >입니다. 이 과정에서 해당 하위 키의 핸들을 열어 둡니다 파서는 모든 하위 키를 구문 분석을 완료 될 때까지. 다음 예제와 같이이 방법은 한 번에 하나의 키를 운영 보다 더 효율적입니다.

```
HKEY_CLASSES_ROOT
{
    'MyVeryOwnKey'
    {
        'HasASubKey'
        {
            'PrettyCool'
        }
    }
}
```

등록 기관은 처음 여기서 열립니다 (만듭니다) `HKEY_CLASSES_ROOT\MyVeryOwnKey`합니다. 그런 다음 발견 하는 `MyVeryOwnKey` 하위 키가 있습니다. 키를 닫을 것이 아니라 `MyVeryOwnKey`, 등록 기관에 핸들을 유지 하 고 엽니다 (만듭니다) `HasASubKey` 이 부모 핸들을 사용 하 여 합니다. (시스템 레지스트리에 낮아질 수 있습니다 부모 핸들이 열릴 때.) 를 열 `HKEY_CLASSES_ROOT\MyVeryOwnKey` 를 연 다음 `HasASubKey` 사용 하 여 `MyVeryOwnKey` 부모 여 보다 빠르게 그대로 `MyVeryOwnKey`, 닫는 `MyVeryOwnKey`을 연 다음 `MyVeryOwnKey\HasASubKey`합니다.

## <a name="see-also"></a>참고자료

[등록자 스크립트 만들기](../atl/creating-registrar-scripts.md)
