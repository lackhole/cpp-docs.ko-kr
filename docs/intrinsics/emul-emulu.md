---
title: __emul, __emulu
ms.date: 11/04/2016
f1_keywords:
- __emulu_cpp
- __emul
- __emul_cpp
- __emulu
helpviewer_keywords:
- __emul intrinsic
- __emulu intrinsic
ms.assetid: 79545236-cca2-40b8-a4e1-8abce9b26311
ms.openlocfilehash: 8657c0fb034ac6bbcfbebb946e059ad08d9e7046
ms.sourcegitcommit: 72583d30170d6ef29ea5c6848dc00169f2c909aa
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/18/2019
ms.locfileid: "59030052"
---
# <a name="emul-emulu"></a>__emul, __emulu

**Microsoft 전용**

32 비트 정수를 보유할 수 있는 항목을 오버플로 하는 곱하기를 수행 합니다.

## <a name="syntax"></a>구문

```
__int64 __emul(
   int a,
   int b
);
unsigned __int64 __emulu(
   unsigned int a,
   unsigned int b
);
```

#### <a name="parameters"></a>매개 변수

*a*<br/>
[in] 곱하기의 첫 번째 정수 피연산자입니다.

*b*<br/>
[in] 곱하기의 두 번째 정수 피연산자입니다.

## <a name="return-value"></a>반환 값

곱하기의 결과입니다.

## <a name="requirements"></a>요구 사항

|내장 함수|아키텍처|
|---------------|------------------|
|`__emul`|x86, x64|
|`__emulu`|x86, x64|

**헤더 파일** \<intrin.h >

## <a name="remarks"></a>설명

`__emul` 두 개의 32 비트 부호 있는 값을 사용 하 고 64 비트 부호 있는 정수 값으로 곱하기의 결과 반환 합니다.

`__emulu` 두 개의 32 비트 부호 없는 정수 값을 사용 하 고 64 비트 부호 없는 정수 값으로 곱하기의 결과 반환 합니다.

## <a name="example"></a>예제

```
// emul.cpp
// compile with: /EHsc
// processor: x86, x64
#include <iostream>
#include <intrin.h>
using namespace std;

#pragma intrinsic(__emul)
#pragma intrinsic(__emulu)

int main()
{
   int a = -268435456;
   int b = 2;

   __int64 result = __emul(a, b);

   cout << a << " * " << b << " = " << result << endl;

   unsigned int ua = 0xFFFFFFFF; // Dec value: 4294967295
   unsigned int ub = 0xF000000;  // Dec value: 251658240

   unsigned __int64 uresult = __emulu(ua, ub);

   cout << ua << " * " << ub << " = " << uresult << endl;

}
```

## <a name="output"></a>출력

```
-268435456 * 2 = -536870912
4294967295 * 251658240 = 1080863910317260800
```

**Microsoft 전용 종료**

## <a name="see-also"></a>참고자료

[컴파일러 내장 함수](../intrinsics/compiler-intrinsics.md)