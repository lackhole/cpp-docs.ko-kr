---
title: 심각한 오류 C1004
ms.date: 11/04/2016
f1_keywords:
- C1004
helpviewer_keywords:
- C1004
ms.assetid: dbe034b0-6eb0-41b4-a50c-2fccf9e78ad4
ms.openlocfilehash: 13fb8963b33569facf62ccedfe9ce8b7bbbbfdc3
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62383208"
---
# <a name="fatal-error-c1004"></a>심각한 오류 C1004

예기치 않은 파일의 끝

컴파일러는 구문 확인 하지 않고 소스 파일의 끝에 도달 합니다. 코드를 다음 요소 중 누락 될 수 있습니다.

- 닫는 중괄호

- 닫는 괄호

- 닫는 주석 표식 (* /)

- 세미콜론

이 오류를 해결 하려면 다음을 확인 합니다.

- 기본 디스크 드라이브에 임시 파일을 소스 파일로 배의 공간에 대 한 필요한 공간이 부족 합니다.

- `#if` 닫는 false 인 계산 되는 지시문 `#endif` 지시문입니다.

- 소스 파일을 캐리지 리턴 및 줄 바꿈 종료 되지 않습니다.

다음 샘플에서는 C1004 오류가 생성 됩니다.

```
// C1004.cpp
#if TEST
int main() {}
// C1004
```

해결 방법:

```
// C1004b.cpp
#if TEST
#endif

int main() {}
```