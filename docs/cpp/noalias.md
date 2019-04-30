---
title: noalias
ms.date: 02/09/2018
f1_keywords:
- noalias_cpp
helpviewer_keywords:
- noalias __declspec keyword
- __declspec keyword [C++], noalias
ms.assetid: efafa8b0-7f39-4edc-a81e-d287ae882c9b
ms.openlocfilehash: 2eceffd10f97615859918991320ceebf577d094c
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62377441"
---
# <a name="noalias"></a>noalias

**Microsoft 전용**

**noalias** 함수 호출을 수정 하거나 표시 되는 전역 상태를 참조 하지 않는 것을 의미를 메모리에만 수정 하 고 *직접* 포인터 매개 변수가 (첫 번째 수준의 간접 참조).

함수는 주석이 달린 경우 **noalias**, 최적화 프로그램에는 자체 매개 변수 외에도 포인터 매개 변수의 첫 번째 수준의 간접 참조 참조 되거나 수정 되는 함수 내에서 가정할 수 있습니다. 표시되는 전역 상태는 컴파일 범위 외부에서 정의되거나 참조되지 않는 모든 데이터의 집합이며 해당 주소는 사용되지 않습니다. 컴파일 범위는 모든 소스 파일 ([/LTCG (링크 타임 코드 생성)](../build/reference/ltcg-link-time-code-generation.md) 빌드) 또는 단일 원본 파일 (비 **/LTCG** 빌드).

합니다 **noalias** 주석은 주석이 추가 된 함수 본문에만 적용 됩니다. 함수로 표시 **__declspec(noalias)** 함수로 반환 된 포인터의 별칭을 지정 하는 데 영향을 주지 않습니다.

별칭 지정에 영향을 줄 수 있는 다른 주석을 참조 하세요 [__declspec(restrict)](../cpp/restrict.md)합니다.

## <a name="example"></a>예제

다음 샘플의 사용법을 보여 줍니다 **__declspec(noalias)** 합니다.

때 함수 `multiply` 메모리 액세스에 주석이 지정 되어 있는지 **__declspec(noalias)**, 컴파일러에 알려 준다는이 함수는 매개 변수 목록의 포인터를 통해 제외 하 고 전역 상태를 수정 하지 않습니다.

```C
// declspec_noalias.c
#include <stdio.h>
#include <stdlib.h>

#define M 800
#define N 600
#define P 700

float * mempool, * memptr;

float * ma(int size)
{
    float * retval;
    retval = memptr;
    memptr += size;
    return retval;
}

float * init(int m, int n)
{
    float * a;
    int i, j;
    int k=1;

    a = ma(m * n);
    if (!a) exit(1);
    for (i=0; i<m; i++)
        for (j=0; j<n; j++)
            a[i*n+j] = 0.1/k++;
    return a;
}

__declspec(noalias) void multiply(float * a, float * b, float * c)
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

## <a name="see-also"></a>참고자료

[__declspec](../cpp/declspec.md)<br/>
[C++ 키워드](../cpp/keywords-cpp.md)<br/>
[__declspec(restrict)](../cpp/restrict.md)
