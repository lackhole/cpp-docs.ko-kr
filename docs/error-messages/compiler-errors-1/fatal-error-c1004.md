---
title: 심각한 오류 C1004
ms.date: 11/04/2016
f1_keywords:
- C1004
helpviewer_keywords:
- C1004
ms.assetid: dbe034b0-6eb0-41b4-a50c-2fccf9e78ad4
ms.openlocfilehash: 82a1a3e410505be53d4356e46d5521aebb72763c
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/03/2019
ms.locfileid: "74756970"
---
# <a name="fatal-error-c1004"></a>심각한 오류 C1004

예기치 않은 파일의 끝이 있습니다.

컴파일러가 구문을 확인 하지 않고 소스 파일의 끝에 도달 했습니다. 코드에 다음 요소 중 하나가 없을 수 있습니다.

- 닫는 중괄호

- 닫는 괄호

- 닫는 주석 표식 (*/)

- 세미콜론

이 오류를 해결 하려면 다음을 확인 하십시오.

- 기본 디스크 드라이브에 임시 파일의 공간이 부족 하 여 원본 파일 만큼 공간이 두 배 정도 필요 합니다.

- False로 계산 되는 `#if` 지시문에는 closing `#endif` 지시문이 없습니다.

- 원본 파일이 캐리지 리턴 및 줄 바꿈으로 끝나지 않습니다.

다음 샘플에서는 C1004를 생성 합니다.

```cpp
// C1004.cpp
#if TEST
int main() {}
// C1004
```

가능한 해결 방법:

```cpp
// C1004b.cpp
#if TEST
#endif

int main() {}
```
