---
title: 네임스페이스 이름 변경
ms.date: 10/18/2018
f1_keywords:
- rename_namespace
helpviewer_keywords:
- rename_namespace attribute
ms.assetid: 45006d2b-36cd-4bec-98b9-3b8ec45299e3
ms.openlocfilehash: 7b3917a7114ca44d092f10a7831bb35bc64e9387
ms.sourcegitcommit: 72583d30170d6ef29ea5c6848dc00169f2c909aa
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/18/2019
ms.locfileid: "59039879"
---
# <a name="renamenamespace"></a>네임스페이스 이름 변경

**C++특정**

형식 라이브러리의 콘텐츠가 들어있는 네임스페이스의 이름을 바꿉니다.

## <a name="syntax"></a>구문

```
rename_namespace("NewName")
```

### <a name="parameters"></a>매개 변수

*NewName*<br/>
네임스페이스의 새 이름입니다.

## <a name="remarks"></a>설명

단일 인수를 걸리는 *NewName*, 네임 스페이스에 대 한 새 이름을 지정 합니다.

네임 스페이스를 제거 하려면 사용 합니다 [no_namespace](../preprocessor/no-namespace.md) 특성을 대신 합니다.

**최종 C++ 특정**

## <a name="see-also"></a>참고자료

[#import 특성](../preprocessor/hash-import-attributes-cpp.md)<br/>
[#import Directive](../preprocessor/hash-import-directive-cpp.md)