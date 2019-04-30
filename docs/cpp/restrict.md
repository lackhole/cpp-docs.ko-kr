---
title: restrict
ms.date: 02/09/2018
f1_keywords:
- restrict_cpp
helpviewer_keywords:
- __declspec keyword [C++], restrict
- restrict __declspec keyword
ms.assetid: f39cf632-68d8-4362-a497-2d4c15693689
ms.openlocfilehash: 40c1c05ca72f639829f2d3658497b0e9f3199640
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62403375"
---
# <a name="restrict"></a>restrict

**Microsoft 전용**

함수 선언 또는 포인터 형식을 반환 하는 정의 적용할 때 **제한할** 반환 되지 않는 개체는 컴파일러에 알립니다 *별칭이 지정*, 즉, 다른 모든 참조 이 대 한 포인터입니다. 이렇게 하면 컴파일러가 추가 최적화를 수행 합니다.

## <a name="syntax"></a>구문

> **__declspec(restrict)** *pointer_return_type* *function*();

## <a name="remarks"></a>설명

컴파일러에 전파 **__declspec(restrict)** 합니다. 예를 들어 CRT `malloc` 함수에는 **__declspec(restrict)** 장식 및 따라서 컴파일러 가정 하 여 메모리 위치로 초기화 된 포인터는 `malloc` 별칭이 지정 되지 않습니다도 이전에 기존 포인터입니다.

컴파일러는 반환 된 포인터가 실제로 별칭이 지정 되지 않음을 확인 하지 않습니다. 개발자의 책임 프로그램 별칭을 지정 하지로 표시 된 포인터를 확인 하는 것은 **__declspec 제한** 한정자입니다.

변수에서 비슷한 의미 체계를 참조 하세요 [__restrict](../cpp/extension-restrict.md)합니다.

함수에는 앨리어싱에 적용 되는 다른 주석을 참조 하세요 [__declspec(noalias)](../cpp/noalias.md)합니다.

에 대 한 자세한 합니다 **제한할** 키워드의 일부인 C++ AMP 참조 [제한 (C++ AMP)](../cpp/restrict-cpp-amp.md).

## <a name="example"></a>예제

다음 샘플의 사용법을 보여 줍니다 **__declspec(restrict)** 합니다.

때 **__declspec(restrict)** 는 포인터를 반환 합니다, 그러면 컴파일러가 반환 값으로 가리키는 메모리 별칭이 지정 되지 함수에 적용 됩니다. 이 예제에서는 포인터 `mempool` 고 `memptr` 전역 되므로 컴파일러는 참조 하는 메모리 별칭이 지정 되지 않음을 확인할 수 없습니다. 내에서 사용 되는 반면 `ma` 와 해당 호출자 `init` 따라서 프로그램에 의해 참조이 고, 그렇지 되지 않는 메모리를 반환 하는 방식으로 **__decslpec(restrict)** 최적화 하는 데 사용 됩니다. 이것은 어떻게 CRT 헤더를 데코 레이트 하는 할당 함수 같은 비슷합니다 `malloc` 를 사용 하 여 **__declspec(restrict)** 기존 포인터 별칭이 지정 되지 않는 메모리는 항상 반환을 나타냅니다.

```C
// declspec_restrict.c
// Compile with: cl /W4 declspec_restrict.c
#include <stdio.h>
#include <stdlib.h>

#define M 800
#define N 600
#define P 700

float * mempool, * memptr;

__declspec(restrict) float * ma(int size)
{
    float * retval;
    retval = memptr;
    memptr += size;
    return retval;
}

__declspec(restrict) float * init(int m, int n)
{
    float * a;
    int i, j;
    int k=1;

    a = ma(m * n);
    if (!a) exit(1);
    for (i=0; i<m; i++)
        for (j=0; j<n; j++)
            a[i*n+j] = 0.1f/k++;
    return a;
}

void multiply(float * a, float * b, float * c)
{
    int i, j, k;

    for (j=0; j<P; j++)
        for (i=0; i<M; i++)
            for (k=0; k<N; k++)
                c[i * P + j] =
                          a[i * N + k] *
                          b[k * P + j];
}

int main()
{
    float * a, * b, * c;

    mempool = (float *) malloc(sizeof(float) * (M*N + N*P + M*P));

    if (!mempool)
    {
        puts("ERROR: Malloc returned null");
        exit(1);
    }

    memptr = mempool;
    a = init(M, N);
    b = init(N, P);
    c = init(M, P);

    multiply(a, b, c);
}
```

**Microsoft 전용 종료**

## <a name="see-also"></a>참고 항목

[C++ 키워드](../cpp/keywords-cpp.md)<br/>
[__declspec](../cpp/declspec.md)<br/>
[__declspec(noalias)](../cpp/noalias.md)
