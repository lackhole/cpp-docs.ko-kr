---
title: restrict (C++ AMP)
ms.date: 11/04/2016
f1_keywords:
- cpu_CPP
- amp_CPP
helpviewer_keywords:
- restrict clause (C++ AMP)
ms.assetid: 07d3291f-7edf-456b-8828-283ac8673661
ms.openlocfilehash: 3609e3f0541cfd8a8af8559d8d49e6a77c00d91c
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62403388"
---
# <a name="restrict-c-amp"></a>restrict (C++ AMP)

제한 지정자는 함수 및 람다 선언에 적용할 수 있습니다. 제한 지정자는 C++ AMP(C++ Accelerated Massive Parallelism) 런타임을 사용하는 응용 프로그램의 함수 동작 및 함수의 코드에 제한을 적용합니다.

> [!NOTE]
>  에 대 한 자세한 합니다 **제한** 포함 된 키워드는 **__declspec** 저장소 클래스 특성을 참조 하세요 [제한](../cpp/restrict.md)합니다.

합니다 **제한** 절은 다음 형식:

|절|설명|
|------------|-----------------|
|`restrict(cpu)`|이 함수는 전체 C++ 언어를 사용할 수 있습니다. restrict(cpu) 함수를 사용하여 선언된 다른 함수만 이 함수를 호출할 수 있습니다.|
|`restrict(amp)`|이 함수는 C++ AMP를 통해 가속할 수 있는 C++ 언어의 하위 집합만 사용할 수 있습니다.|
|`restrict(cpu)` 및 `restrict(amp)`의 시퀀스입니다.|이 함수는 `restrict(cpu)` 및 `restrict(amp)` 둘 다의 제한을 따라야 합니다. 이 함수는 `restrict(cpu)`, `restrict(amp)`, `restrict(cpu, amp)` 또는 `restrict(amp, cpu)`를 사용하여 선언된 함수를 통해 호출할 수 있습니다.<br /><br /> `restrict(A) restrict(B)` 형식을 `restrict(A,B)`로 작성할 수 있습니다.|

## <a name="remarks"></a>설명

합니다 **제한** 키워드는 상황별 키워드입니다. 제한 지정자인 `cpu` 및 `amp`는 예약어가 아닙니다. 지정자 목록은 확장할 수 없습니다. 없는 함수는 **제한할** 절이 있는 함수와 동일 하 게는 `restrict(cpu)` 절.

`restrict(amp)` 절이 있는 함수에는 다음 제한이 적용됩니다.

- 이 함수는 `restrict(amp)` 절이 포함된 함수만 호출할 수 있습니다.

- 함수 인라이닝 처리 가능해야 합니다.

- 함수를 선언할 수 있습니다 **int**를 **부호 없는 int**를 **float**, 및 **double** 변수 및 클래스와 포함 된 구조 이러한 형식입니다. **bool** 도 사용할 수 있지만 복합 형식에서 사용 하는 경우 4 바이트 맞춤 이어야 합니다.

- 람다 함수는 참조로 캡처할 수 없으며 포인터를 캡처할 수 없습니다.

- 참조 및 단일 간접 포인터는 로컬 변수, 함수 인수 및 반환 형식으로만 지원됩니다.

- 다음은 허용되지 않습니다.

   - 재귀

   - 사용 하 여 선언 된 변수를 [volatile](../cpp/volatile-cpp.md) 키워드입니다.

   - 가상 함수

   - 함수에 대한 포인터

   - 멤버 함수에 대한 포인터

   - 구조체의 포인터

   - 포인터에 대한 포인터

   - **goto** 문입니다.

   - 레이블 문

   - **시도**, **catch**, 또는 **throw** 문입니다.

   - 전역 변수

   - 정적 변수 사용 하 여 [tile_static 키워드](../cpp/tile-static-keyword.md) 대신 합니다.

   - **dynamic_cast** 캐스팅 합니다.

   - **typeid** 연산자

   - asm 선언

   - vararg

함수 제한 사항 설명은 참조 하세요 [(amp) 제한 사항 제한](https://blogs.msdn.microsoft.com/nativeconcurrency/2011/12/19/restrictamp-restrictions-part-0-of-n-introduction/)합니다.

## <a name="example"></a>예제

다음 예제에서는 사용 하는 방법의 `restrict(amp)`절.

```cpp
void functionAmp() restrict(amp) {}
void functionNonAmp() {}

void callFunctions() restrict(amp)
{
    // int is allowed.
    int x;
    // long long int is not allowed in an amp-restricted function. This generates a compiler error.
    // long long int y;

    // Calling an amp-restricted function is allowed.
    functionAmp();

    // Calling a non-amp-restricted function is not allowed.
    // functionNonAmp();
}
```

## <a name="see-also"></a>참고자료

[C++ AMP(C++ Accelerated Massive Parallelism)](../parallel/amp/cpp-amp-cpp-accelerated-massive-parallelism.md)