---
title: 컴파일러 경고(수준 4) C4062
ms.date: 04/05/2019
f1_keywords:
- C4062
helpviewer_keywords:
- C4062
ms.assetid: 36d1c6ae-c917-4b08-bf30-2eb49ee94169
ms.openlocfilehash: 79658afc31565b708cdbd8a88f49b887cdd10cf3
ms.sourcegitcommit: 72583d30170d6ef29ea5c6848dc00169f2c909aa
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/18/2019
ms.locfileid: "59237187"
---
# <a name="compiler-warning-level-4-c4062"></a>컴파일러 경고(수준 4) C4062

> 열거자 '*식별자*'의 switch에 '*열거형*' 처리 되지 않습니다

열거자 *식별자* 에 연결 되지 않은 `case` 처리기에는 `switch` 문이 되며 없습니다 `default` catch 할 수 있는 레이블을 합니다. 누락 된 사례를 감독 수 있으며 코드의 잠재적 오류입니다. 사용 되지 않는 열거자에 관련된 경고에 대 한 `switch` 문이 있는 `default` 사례를 참조 하십시오 [C4061](compiler-warning-level-4-c4061.md)합니다.

기본적으로 이 경고는 해제되어 있습니다. 기본적으로 해제 되어 있는 경고를 사용 하는 방법에 대 한 자세한 내용은 참조 하세요. [컴파일러 경고는 기본적으로 해제 되어](../../preprocessor/compiler-warnings-that-are-off-by-default.md)입니다.

## <a name="example"></a>예제

다음 샘플 C4062를 생성 및이 해결 하는 방법을 보여 줍니다.

```cpp
// C4062.cpp
// compile with: /EHsc /W4
#pragma warning(default : 4062)
enum E { a, b, c };
void func ( E e ) {
   switch(e) {
      case a:
      case b:
   // case c:  // to fix, uncomment this line
      break;   // no default label
   }   // C4062, enumerator 'c' not handled
}

int main() {
}
```

## <a name="see-also"></a>참고자료

[컴파일러 경고(수준 4) C4061](compiler-warning-level-4-c4061.md)
