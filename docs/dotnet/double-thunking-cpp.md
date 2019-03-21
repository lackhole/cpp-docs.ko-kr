---
title: 이중 썽킹(C++)
ms.date: 11/04/2016
helpviewer_keywords:
- double thunks
- interop [C++], double thunking
- mixed assemblies [C++], double thunking
- /clr compiler option [C++], double thunking
- interoperability [C++], double thunking
ms.assetid: a85090b2-dc3c-498a-b40c-340db229dd6f
ms.openlocfilehash: f34af20ed3dd2c48659bdbf7794c443920dbb4e9
ms.sourcegitcommit: 90817d9d78fbaed8ffacde63f3add334842e596f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/20/2019
ms.locfileid: "58278400"
---
# <a name="double-thunking-c"></a>이중 썽킹(C++)

이중 썽킹 Visual c + + 함수를 관리 하 고는 프로그램 실행을 관리 되는 상황에 맞는 호출에서 함수 호출을 관리 되는 함수를 호출 하려면 네이티브 진입점 함수를 호출할 때 발생할 수 있는 성능 저하를 가리킵니다. 이 항목에서는 이중 썽킹 발생 하 고 성능을 향상 시키기 위해이 방지 하는 방법을 설명 합니다.

## <a name="remarks"></a>설명

기본적으로 사용 하 여 컴파일하면 **/clr**, 관리 되는 함수 정의 사용 하면 컴파일러가 네이티브 진입점 및 관리 되는 진입점을 생성 합니다. 이 관리 되는 기능을 네이티브 및 관리 호출 사이트에서 호출할 수 있습니다. 그러나 네이티브 진입점이 있으면이 함수에 대 한 모든 호출에 대 한 진입점을 수 있습니다. 호출 함수의 경우 관리 되는 경우 네이티브 진입점 관리 되는 진입점을 호출 됩니다. 두 번의 호출 함수를 호출 하는 데 필요한 실제로 (하므로 이중 썽킹). 예를 들어, 가상 함수는 항상 네이티브 진입점을 통해 호출 됩니다.

하나의 해결 함수를 사용 하 여 관리 되는 컨텍스트를 호출 되는 관리 되는 함수에 대 한 기본 진입점을 생성 하지 않도록 컴파일러에 지시 하는 것은 [__clrcall](../cpp/clrcall.md) 호출 규칙입니다.

마찬가지로, 내보내는 경우 ([dllexport, dllimport](../cpp/dllexport-dllimport.md)) 관리 되는 함수 네이티브 진입점이 생성 되 고 네이티브 진입점을 통해를 가져오고 해당 함수를 호출 하는 모든 함수를 호출 합니다. 이 경우 이중 썽킹를 방지 하려면 기본 내보내기/가져오기 의미 체계를 사용 하지 마십시오 통해 메타 데이터를 간단히 참조할 `#using` (참조 [#using 지시문](../preprocessor/hash-using-directive-cpp.md)).

불필요 한 이중 썽킹 줄이기 위해 컴파일러 업데이트 되었습니다. 으로 모든 함수는 시그니처 (반환 형식 포함)에서 관리 되는 유형으로 암시적으로 표시 됩니다 예를 들어 `__clrcall`합니다.

## <a name="example"></a>예제

### <a name="description"></a>설명

다음 샘플에서는 이중 썽킹 하는 방법을 보여 줍니다. 네이티브 컴파일된 경우 (없이 **/clr**), 가상 함수에 대 한 호출 `main` 호출을 생성 `T`의 복사 생성자 및 소멸자를 한 번 호출 합니다. 사용 된 가상 함수를 선언 하는 경우 비슷한 동작이 이루어집니다 **/clr** 및 `__clrcall`합니다. 그러나 사용 하 여 컴파일하는 경우 **/clr**복사 생성자에 대 한 호출을 생성 하는 함수 호출 되지만 네이티브-관리 되는 썽크 인해 복사 생성자에 대 한 호출이 있습니다.

### <a name="code"></a>코드

```
// double_thunking.cpp
// compile with: /clr
#include <stdio.h>
struct T {
   T() {
      puts(__FUNCSIG__);
   }

   T(const T&) {
      puts(__FUNCSIG__);
   }

   ~T() {
      puts(__FUNCSIG__);
   }

   T& operator=(const T&) {
      puts(__FUNCSIG__);
      return *this;
   }
};

struct S {
   virtual void /* __clrcall */ f(T t) {};
} s;

int main() {
   S* pS = &s;
   T t;

   printf("calling struct S\n");
   pS->f(t);
   printf("after calling struct S\n");
}
```

### <a name="sample-output"></a>샘플 출력

```
__thiscall T::T(void)
calling struct S
__thiscall T::T(const struct T &)
__thiscall T::T(const struct T &)
__thiscall T::~T(void)
__thiscall T::~T(void)
after calling struct S
__thiscall T::~T(void)
```

## <a name="example"></a>예제

### <a name="description"></a>설명

앞의 예제에는 이중 썽킹 있는지 보여 줍니다. 이 샘플에서는 효과 보여 줍니다. `for` 루프는 가상 함수를 호출 하 고 프로그램은 실행 시간을 보고 합니다. 실행 시간이 가장 느린 프로그램으로 컴파일될 때 보고 됩니다 **/clr**합니다. 가장 빠른 시간 없이 컴파일하는 경우 보고 됩니다 **/clr** 사용 하 여 가상 함수를 선언 하는 경우 또는 `__clrcall`합니다.

### <a name="code"></a>코드

```
// double_thunking_2.cpp
// compile with: /clr
#include <time.h>
#include <stdio.h>

#pragma unmanaged
struct T {
   T() {}
   T(const T&) {}
   ~T() {}
   T& operator=(const T&) { return *this; }
};

struct S {
   virtual void /* __clrcall */ f(T t) {};
} s;

int main() {
   S* pS = &s;
   T t;
   clock_t start, finish;
   double  duration;
   start = clock();

   for ( int i = 0 ; i < 1000000 ; i++ )
      pS->f(t);

   finish = clock();
   duration = (double)(finish - start) / (CLOCKS_PER_SEC);
   printf( "%2.1f seconds\n", duration );
   printf("after calling struct S\n");
}
```

### <a name="sample-output"></a>샘플 출력

```
4.2 seconds
after calling struct S
```

## <a name="see-also"></a>참고자료

[혼합형(네이티브 및 관리) 어셈블리](../dotnet/mixed-native-and-managed-assemblies.md)
