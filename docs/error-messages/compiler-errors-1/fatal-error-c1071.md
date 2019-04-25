---
title: 심각한 오류 C1071
ms.date: 11/04/2016
f1_keywords:
- C1071
helpviewer_keywords:
- C1071
ms.assetid: 489f1786-370e-4ecd-af67-538fe6e5bd4e
ms.openlocfilehash: 8fe6b0f3bb1253f72c97f29070ba81cdbdf80508
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62166661"
---
# <a name="fatal-error-c1071"></a>심각한 오류 C1071

주석에서 예기치 않은 파일의 끝이 나타났습니다.

컴파일러는 주석을 검색 하는 동안 파일의 끝에 도달 합니다.

### <a name="to-fix-by-checking-the-following-possible-causes"></a>다음과 같은 가능한 원인을 확인하여 수정하려면

1. 주석 종결자 (* /).

1. 소스 파일의 마지막 줄에서 주석 다음 줄 바꿈 문자가 없습니다.

다음 샘플에서는 C1071를 생성합니다.

```
// C1071.cpp
int main() {
}

/* this comment is fine */
/* forgot the closing tag        // C1071
```