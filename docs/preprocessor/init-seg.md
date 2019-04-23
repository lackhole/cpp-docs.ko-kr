---
title: init_seg
ms.date: 11/04/2016
f1_keywords:
- vc-pragma.init_seg
- init_seg_CPP
helpviewer_keywords:
- pragmas, init_seg
- init_seg pragma
- data segment initializing [C++]
ms.assetid: 40a5898a-5c85-4aa9-8d73-3d967eb13610
ms.openlocfilehash: 801496739fd9bd2b8a14e699ca4da9fe79f3a28d
ms.sourcegitcommit: 72583d30170d6ef29ea5c6848dc00169f2c909aa
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/18/2019
ms.locfileid: "59026633"
---
# <a name="initseg"></a>init_seg

**C++특정**

시작 코드가 실행되는 순서에 영향을 주는 키워드 또는 코드 섹션을 지정합니다.

## <a name="syntax"></a>구문

```
#pragma init_seg({ compiler | lib | user | "section-name" [, func-name]} )
```

## <a name="remarks"></a>설명

의미 *세그먼트* 하 고 *섹션* 이 항목에서 서로 바꿀 수 있습니다.

전역 정적 개체의 초기화는 실행 코드를 포함할 수 있기 때문에 개체를 생성할 때 정의하는 키워드를 지정해야 합니다. 이 특히 사용 하는 **init_seg** pragma 동적 연결 라이브러리 (Dll)의 초기화가 필요한 라이브러리나.

옵션을 **init_seg** pragma는:

*compiler*<br/>
Microsoft C 런타임 라이브러리 초기화용으로 예약되어 있습니다. 이 그룹의 개체는 처음 생성됩니다.

*lib*<br/>
타사 클래스 라이브러리 공급업체의 초기화에 사용할 수 있습니다. 로 표시 된 후이 그룹의 개체 생성 됩니다 *컴파일러* , 다른 대체 이전 합니다.

*user*<br/>
모든 사용자가 사용할 수 있습니다. 이 그룹의 개체는 마지막에 생성됩니다.

*섹션 이름* 초기화 섹션의 명시적 지정을 허용 합니다. 그러나 개체에는 사용자 지정 *섹션 이름* 는 암시적으로 생성 되지 않으면 해당 주소에서 명명 된 섹션에 배치 됩니다 *섹션 이름*합니다.

제공된 섹션 이름은 pragma 뒤 해당 모듈에서 선언된 전역 개체를 생성할 도우미 함수에 대한 포인터를 포함합니다.

섹션을 만들 때 사용 하지 않아야 하는 이름의 목록을 보려면 참조 [/section](../build/reference/section-specify-section-attributes.md)합니다.

*함수 이름을* 대신 호출 될 함수를 지정 합니다 `atexit` 경우 프로그램이 종료 됩니다. 이 도우미 함수 호출 [atexit](../c-runtime-library/reference/atexit.md) 전역 개체 소멸자에 대 한 포인터를 사용 하 여 합니다. 다음 형식의 pragma에서 함수 식별자를 지정하면

```cpp
int __cdecl myexit (void (__cdecl *pf)(void))
```

C 런타임 라이브러리의 `atexit` 대신 해당 함수가 호출됩니다. 따라서 개체를 제거할 준비가 되면 호출되어야 할 소멸자 목록을 작성할 수 있습니다.

초기화를 지연해야 하는 경우(예: DLL에서) 섹션 이름을 명시적으로 지정할 수 있습니다. 그런 다음 각 정적 개체에 대한 생성자를 호출해야 합니다.

`atexit` 대체 식별자에는 따옴표가 없습니다.

개체는 여전히 다른 XXX_seg pragma가 정의하는 섹션에 배치됩니다.

모듈에 선언된 개체는 C 런타임으로 자동으로 초기화되지 않습니다. 해당 작업을 직접 수행해야 합니다.

기본적으로 `init_seg` 섹션은 읽기 전용입니다. 섹션 이름이 .CRT인 경우 컴파일러는 특성이 읽기/쓰기로 표시되어 있어도 해당 특성을 자동으로 읽기 전용으로 변경합니다.

지정할 수 없습니다 **init_seg** 변환 단위에서 두 번 이상.

코드에서 명시적으로 정의하지 않은 사용자 정의 생성자가 개체에 없어도 컴파일러에서 생성자를 만들 수 있습니다. 예를 들어 v-table 포인터를 바인딩하는 경우입니다. 따라서 코드가 컴파일러에서 생성된 생성자를 호출해야 합니다.

## <a name="example"></a>예제

```cpp
// pragma_directive_init_seg.cpp
#include <stdio.h>
#pragma warning(disable : 4075)

typedef void (__cdecl *PF)(void);
int cxpf = 0;   // number of destructors we need to call
PF pfx[200];    // pointers to destructors.

int myexit (PF pf) {
   pfx[cxpf++] = pf;
   return 0;
}

struct A {
   A() { puts("A()"); }
   ~A() { puts("~A()"); }
};

// ctor & dtor called by CRT startup code
// because this is before the pragma init_seg
A aaaa;

// The order here is important.
// Section names must be 8 characters or less.
// The sections with the same name before the $
// are merged into one section. The order that
// they are merged is determined by sorting
// the characters after the $.
// InitSegStart and InitSegEnd are used to set
// boundaries so we can find the real functions
// that we need to call for initialization.

#pragma section(".mine$a", read)
__declspec(allocate(".mine$a")) const PF InitSegStart = (PF)1;

#pragma section(".mine$z",read)
__declspec(allocate(".mine$z")) const PF InitSegEnd = (PF)1;

// The comparison for 0 is important.
// For now, each section is 256 bytes. When they
// are merged, they are padded with zeros. You
// can't depend on the section being 256 bytes, but
// you can depend on it being padded with zeros.

void InitializeObjects () {
   const PF *x = &InitSegStart;
   for (++x ; x < &InitSegEnd ; ++x)
      if (*x) (*x)();
}

void DestroyObjects () {
   while (cxpf>0) {
      --cxpf;
      (pfx[cxpf])();
   }
}

// by default, goes into a read only section
#pragma init_seg(".mine$m", myexit)

A bbbb;
A cccc;

int main () {
   InitializeObjects();
   DestroyObjects();
}
```

```Output
A()
A()
A()
~A()
~A()
~A()
```

## <a name="see-also"></a>참고자료

[Pragma 지시문 및 __Pragma 키워드](../preprocessor/pragma-directives-and-the-pragma-keyword.md)