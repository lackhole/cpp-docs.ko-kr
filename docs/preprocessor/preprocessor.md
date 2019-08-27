---
title: 전처리기
ms.date: 11/04/2016
helpviewer_keywords:
- preprocessor
ms.assetid: e120eda3-b413-49f1-a07c-e9fb128cf500
ms.openlocfilehash: b1443d88fdba470cb8ed5058c9a9012bfbdc5bc7
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62179856"
---
# <a name="preprocessor"></a>전처리기
전처리기는 첫 번째 변환 단계의 일부로 소스 파일의 텍스트를 조작하는 텍스트 처리기입니다. 전처리기는 소스 텍스트를 구문 분석하지 않지만 매크로 호출을 찾기 위해 소스 텍스트를 토큰으로 나눕니다. 컴파일러는 일반적으로 첫 번째 단계에서 전처리기를 호출하지만, 컴파일 없이 텍스트를 처리하기 위해 전처리기를 별도로 호출할 수도 있습니다.

전처리기에 대한 참조 자료에는 다음 단원이 포함되어 있습니다.

- [전처리기 지시문](../preprocessor/preprocessor-directives.md)

- [전처리기 연산자](../preprocessor/preprocessor-operators.md)

- [미리 정의된 매크로](../preprocessor/predefined-macros.md)

- [pragma](../preprocessor/pragma-directives-and-the-pragma-keyword.md)

**Microsoft 전용**

[/E](../build/reference/e-preprocess-to-stdout.md)나 [/EP](../build/reference/ep-preprocess-to-stdout-without-hash-line-directives.md) 컴파일러 옵션을 사용하여 전처리된 이후의 결과물을 확인할 수 있습니다. 두 옵션 모두 전처리기를 호출하고 결과 텍스트를 표준 출력 디바이스(대부분의 경우 콘솔)에 출력합니다. 두 옵션의 차이점은 /E는 `#line` 지시문을 포함하고 /EP는 제거한다는 점입니다.

**Microsoft 전용 종료**

##  <a name="_predir_special_terminology"></a> 특수 용어

전처리기 문서에서 "인수"라는 용어는 함수에 전달되는 값(entity)을 나타냅니다. 인수를 설명할 때 함수 정의부에 지정된 인수 선언 그대로를 나타내는 "형식(formal)" 인수나 값으로, 혹은 함수가 실제 호출될 때의 "실제(actual)"라는 단어로 바뀌거나 수식될 수 있습니다.

"변수"라는 용어는 간단한 C 형식 데이터 개체를 나타냅니다. "개체"라는 용어는 C++ 개체 및 변수를 둘 다 나타내는 포괄적인 용어입니다.

## <a name="see-also"></a>참고자료

[ 전처리기 참조](../preprocessor/c-cpp-preprocessor-reference.md)<br/>
[변환 단계](../preprocessor/phases-of-translation.md)