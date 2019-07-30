---
title: 알고리즘
ms.date: 10/18/2018
helpviewer_keywords:
- libraries [C++], C++ algorithm conventions
- algorithms [C++], C++
- C++ Standard Library, algorithms
- algorithm template function C++ library conventions
- conventions [C++], C++ algorithm
ms.assetid: dec9b373-7d5c-46cc-b7d2-21a938ecd0a6
ms.openlocfilehash: d363dc3f06222121ac5efc79b30516ebd55ff539
ms.sourcegitcommit: 0dcab746c49f13946b0a7317fc9769130969e76d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/24/2019
ms.locfileid: "68456494"
---
# <a name="algorithms"></a>알고리즘

알고리즘은 C++ 표준 라이브러리의 기본적인 부분입니다. 알고리즘은 컨테이너 자체가 아니라 반복기에서 작동합니다. 따라서 모두는 아니지만 대부분의 C++ 표준 라이브러리 컨테이너에서 동일한 알고리즘을 사용할 수 있습니다. 이 섹션에서는 C++ 표준 라이브러리 알고리즘의 규칙 및 용어를 설명합니다.

## <a name="remarks"></a>설명

알고리즘 템플릿 함수에 대한 설명은 다음과 같은 여러 약어 구를 사용합니다.

- \["범위 *A*, *b*)" 구는 *a* 부터 *b*까지까지 0 개 이상의 불연속 값의 시퀀스를 의미 합니다. 범위는 a에서 *B* 에 연결할 수 있는 경우에만 유효 합니다. *n* (*n* = *a*) 개체에 *를* 저장 하 고, 개체를 0 번 이상 (+ +*N*) 증가 시키고 개체를 *B* 와 동일 하 게 비교할 수 있습니다 *.* 한정 된 증분 수 (*N* == *B*)입니다.

- "N, \[ *b* *범위의 각* *n* " 구는 *n* 이 *a* 값으로 시작 하 고 *B*값과 같을 때까지 0 번 이상 증가 함을 의미 합니다. *N* == *B*의 경우는 범위에 포함되지 않습니다.

- " *X*인 *a*, *b*범위의  \[가장 낮은 값 N"은 x 조건이 충족 될 때까지 *x* 조건이 *a*, *b*범위의 \[각 *n* 에 대해 확인 됨을 의미 합니다. 조건 *X* 에 도달 했습니다.

- " *X* 는 a, b 범위의   \[  \[가장 높은 값 *n* 은 a, b)에서 각 *n* 에 대해 *x* 가 결정 됨을 의미 합니다. 함수는 *X* 조건이 충족 될 때마다 *N* 의 복사본을 *K* 에 저장 합니다. 이러한 저장이 발생 하는 경우 함수는 *B*와 같은 *N*의 최종 값을 *K*값으로 바꿉니다. 그러나 양방향 또는 임의 액세스 반복기의 경우 *N*이 범위의 가장 높은 값부터 시작하고 *X* 조건이 충족될 때까지 범위에서 감소함을 의미할 수도 있습니다.

- *X* - *Y*와 같은 식입니다. 여기서 *X* 및 *Y*는 임의 액세스 반복기 이외의 반복기일 수 있으며 수학적 의미로 사용됩니다. 이러한 값을 확인 해야 하는 **-** 경우 함수는 연산자를 반드시 계산 하지 않습니다. *X* + *N* 및 *X* - *N* 같은 식에 대해서도 마찬가지입니다. 여기서 *N*은 정수 형식입니다.

여러 알고리즘은에서와 같이 `operator==`쌍으로 비교 하 여 **bool** 결과를 생성 하는 조건자를 사용 합니다. 조건자 함수 `operator==` 또는 해당 대체 항목은 피연산자 중 하나를 변경하면 안 됩니다. 이 메서드는 평가할 때마다 동일한 **bool** 결과를 생성 해야 하며, 두 피연산자 중 하나의 복사본을 피연산자로 대체할 경우 동일한 결과를 생성 해야 합니다.

여러 알고리즘이 시퀀스의 요소 쌍에 대해 엄격하고 약한 순서를 적용해야 하는 조건자를 사용합니다. 조건자 *pred*(*X*, *Y*):

- Strict는 *pred*(*x*, *x*)가 false 임을 의미 합니다.

- *Pred*(*x*, *y*) & & \! *pred*(*y*, *x*)를 사용 하는 경우 \!Weak은 *x* 및 *y* 에 동일한 순서가 지정 됨을 의미 합니다 (*x* == *y* 는 그렇지 않습니다. 정의 해야 합니다.

- 순서 지정은 *pred*(*x*, *Y*) & & *pred*(*y*, *z*)가 *pred*(*x*, *z*)를 암시 함을 의미 합니다.

이러한 알고리즘 중 일부는 *X* \< *Y* 조건자를 암시적으로 사용합니다. 일반적으로 엄격 하 고 약한 순서 요구 사항을 충족 하는 다른 조건자 `less`는 *x* > *Y*, (*x*, `greater` *y*) 및 (*x*, *y*)입니다. 그러나 *X* \<= *Y* 및 *X* >= *Y*와 같은 조건자는 이 요구 사항을 충족하지 않습니다.

\[ *First*, *last*) 범위에서 반복기에 의해 지정 된 요소의 시퀀스는 0 범위의 \[각 *N* 에 대해 **<** *last* - First 인 경우 연산자에 의해 순서가 지정 된 시퀀스입니다.) 및 범위의 각 *M* (*N*, *Last* - *first*)은 조건자 \!(\*(*first* + *M*) < \*(First + *N*))는 true입니다. 요소는 오름차순으로 정렬됩니다. 조건자 함수 `operator<` 또는 해당 대체 항목은 피연산자 중 하나를 변경하면 안 됩니다. 이 메서드는 평가할 때마다 동일한 **bool** 결과를 생성 해야 하며, 두 피연산자 중 하나의 복사본을 피연산자로 대체할 경우 동일한 결과를 생성 해야 합니다. 또한 비교하는 피연산자에 엄격하고 약한 순서를 적용해야 합니다.

범위 \[ `operator<` \[  -   에서 반복기에 의해 지정 된 요소의 시퀀스는 1의 각 N에 대 한 1, Last First)에 의해 정렬 된 힙입니다. `First` `Last` 조건자 \!(\*_first_ *(first*N))는 true입니다. +  < \* 첫 번째 요소가 가장 큽니다. 그 외의 내부 구조는 템플릿 함수 [make_heap](../standard-library/algorithm-functions.md#make_heap), [pop_heap](../standard-library/algorithm-functions.md#pop_heap)및 [push_heap](../standard-library/algorithm-functions.md#push_heap)으로만 알려져 있습니다. 정렬 된 시퀀스와 마찬가지로 조건자 함수 또는이 `operator<`에 대 한 대체 함수는 피연산자 중 하나를 변경 하지 않아야 하 고 비교 하는 피연산자에서 엄격한 약한 순서를 적용 해야 합니다. 이 메서드는 평가할 때마다 동일한 **bool** 결과를 생성 해야 하며, 두 피연산자 중 하나의 복사본을 피연산자로 대체할 경우 동일한 결과를 생성 해야 합니다.

C++ 표준 라이브러리 알고리즘은 [\<algorithm>](../standard-library/algorithm.md) 및 [\<numeric>](../standard-library/numeric.md) 헤더 파일에 있습니다.

## <a name="see-also"></a>참고자료

[C++ 표준 라이브러리 참조](../standard-library/cpp-standard-library-reference.md)\
[C++ 표준 라이브러리의 스레드 보안](../standard-library/thread-safety-in-the-cpp-standard-library.md)
