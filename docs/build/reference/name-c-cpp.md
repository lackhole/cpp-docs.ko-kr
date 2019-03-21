---
title: NAME(C/C++)
ms.date: 11/04/2016
f1_keywords:
- name
helpviewer_keywords:
- NAME .def file statement
ms.assetid: 5c9b6bd8-9275-46a5-afba-f17a5936dc26
ms.openlocfilehash: d0813befc622db72e095c449794405fc5d58465b
ms.sourcegitcommit: 8105b7003b89b73b4359644ff4281e1595352dda
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/14/2019
ms.locfileid: "57812189"
---
# <a name="name-cc"></a>NAME(C/C++)

기본 출력 파일의 이름을 지정합니다.

```
NAME [application][BASE=address]
```

## <a name="remarks"></a>설명

출력 파일 이름을 지정 하는 해당 하는 방법은 된를 [/out](out-output-file-name.md) 링커 옵션 및 기본 주소를 설정 하는 동일한 방법을 사용 하 여는 [/base](base-base-address.md) 링커 옵션. 모두 지정 하면 / 아웃 재정의 **이름을**입니다.

DLL을 빌드하는 경우 이름을 DLL 이름에만 적용 됩니다.

## <a name="see-also"></a>참고자료

[모듈 정의 문의 규칙](rules-for-module-definition-statements.md)
