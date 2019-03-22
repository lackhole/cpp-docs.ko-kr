---
title: _InterlockedCompareExchange 내장 함수
ms.date: 12/17/2018
f1_keywords:
- _InterlockedCompareExchange_HLERelease
- _InterlockedCompareExchange8_nf
- _InterlockedCompareExchange16_acq_cpp
- _InterlockedCompareExchange_acq_cpp
- _InterlockedCompareExchange16_rel_cpp
- _InterlockedCompareExchange64_rel_cpp
- _InterlockedCompareExchange_cpp
- _InterlockedCompareExchange16_cpp
- _InterlockedCompareExchange64_acq_cpp
- _InterlockedCompareExchange_acq
- _InterlockedCompareExchange64_rel
- _InterlockedCompareExchange64_nf
- _InterlockedCompareExchange_rel_cpp
- _InterlockedCompareExchange16_nf
- _InterlockedCompareExchange8
- _InterlockedCompareExchange64_np
- _InterlockedCompareExchange16_rel
- _InterlockedCompareExchange64_acq
- _InterlockedCompareExchange8_rel
- _InterlockedCompareExchange_HLEAcquire
- _InterlockedCompareExchange64_HLERelease
- _InterlockedCompareExchange64_cpp
- _InterlockedCompareExchange_np
- _InterlockedCompareExchange8_acq
- _InterlockedCompareExchange16_acq
- _InterlockedCompareExchange_rel
- _InterlockedCompareExchange64_HLEAcquire
- _InterlockedCompareExchange64
- _InterlockedCompareExchange16
- _InterlockedCompareExchange
helpviewer_keywords:
- _InterlockedCompareExchange16 intrinsic
- _InterlockedCompareExchange_acq intrinsic
- InterlockedCompareExchange_acq intrinsic
- _InterlockedCompareExchange intrinsic
- InterlockedCompareExchange64 intrinsic
- _InterlockedCompareExchange64_acq intrinsic
- InterlockedCompareExchange16 intrinsic
- _InterlockedCompareExchange_rel intrinsic
- InterlockedCompareExchange intrinsic
- InterlockedCompareExchange64_acq intrinsic
- InterlockedCompareExchange_rel intrinsic
- _InterlockedCompareExchange64 intrinsic
- InterlockedCompareExchange64_rel intrinsic
- _InterlockedCompareExchange64_rel intrinsic
ms.assetid: c3ad79c0-a523-4930-a3a4-69a65d7d5c81
ms.openlocfilehash: 840a7e63bb9b98cfb46ea36e30b3439168688c87
ms.sourcegitcommit: c1f646c8b72f330fa8cf5ddb0f8f261ba10d16f0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/21/2019
ms.locfileid: "58328314"
---
# <a name="interlockedcompareexchange-intrinsic-functions"></a>_InterlockedCompareExchange 내장 함수

**Microsoft 전용**

연관 비교 및 교환을 수행합니다.

## <a name="syntax"></a>구문

```
long _InterlockedCompareExchange(
   long volatile * Destination,
   long Exchange,
   long Comparand
);
long _InterlockedCompareExchange_acq(
   long volatile * Destination,
   long Exchange,
   long Comparand
);
long _InterlockedCompareExchange_HLEAcquire(
   long volatile * Destination,
   long Exchange,
   long Comparand
);
long _InterlockedCompareExchange_HLERelease(
   long volatile * Destination,
   long Exchange,
   long Comparand
);
long _InterlockedCompareExchange_np(
   long volatile * Destination,
   long Exchange,
   long Comparand
);
long _InterlockedCompareExchange_rel(
   long volatile * Destination,
   long Exchange,
   long Comparand
);
char _InterlockedCompareExchange8(
   char volatile * Destination,
   char Exchange,
   char Comparand
);
char _InterlockedCompareExchange8_acq(
   char volatile * Destination,
   char Exchange,
   char Comparand
);
char _InterlockedCompareExchange8_nf(
   char volatile * Destination,
   char Exchange,
   char Comparand
);
char _InterlockedCompareExchange8_rel(
   char volatile * Destination,
   char Exchange,
   char Comparand
);
short _InterlockedCompareExchange16(
   short volatile * Destination,
   short Exchange,
   short Comparand
);
short _InterlockedCompareExchange16_acq(
   short volatile * Destination,
   short Exchange,
   short Comparand
);
short _InterlockedCompareExchange16_nf(
   short volatile * Destination,
   short Exchange,
   short Comparand
);
short _InterlockedCompareExchange16_np(
   short volatile * Destination,
   short Exchange,
   short Comparand
);
short _InterlockedCompareExchange16_rel(
   short volatile * Destination,
   short Exchange,
   short Comparand
);
__int64 _InterlockedCompareExchange64(
   __int64 volatile * Destination,
   __int64 Exchange,
   __int64 Comparand
);
__int64 _InterlockedCompareExchange64_acq(
   __int64 volatile * Destination,
   __int64 Exchange,
   __int64 Comparand
);
__int64 _InterlockedCompareExchange64_HLEAcquire (
   __int64 volatile * Destination,
   __int64 Exchange,
   __int64 Comparand
);
__int64 _InterlockedCompareExchange64_HLERelease(
   __int64 volatile * Destination,
   __int64 Exchange,
   __int64 Comparand
);
__int64 _InterlockedCompareExchange64_nf(
   __int64 volatile * Destination,
   __int64 Exchange,
   __int64 Comparand
);
__int64 _InterlockedCompareExchange64_np(
   __int64 volatile * Destination,
   __int64 Exchange,
   __int64 Comparand
);
__int64 _InterlockedCompareExchange64_rel(
   __int64 volatile * Destination,
   __int64 Exchange,
   __int64 Comparand
);
```

#### <a name="parameters"></a>매개 변수

*대상*<br/>
[out에서] 대상 값에 대 한 포인터입니다. 부호는 무시됩니다.

*Exchange*<br/>
[in] 값을 교환 합니다. 부호는 무시됩니다.

*비교 피연산자*<br/>
[in] 대상과 비교할 값입니다. 부호는 무시됩니다.

## <a name="return-value"></a>반환 값

반환 값은 `Destination` 포인터의 초기 값입니다.

## <a name="requirements"></a>요구 사항

|내장 함수|아키텍처|헤더|
|---------------|------------------|------------|
|`_InterlockedCompareExchange`, `_InterlockedCompareExchange8`, `_InterlockedCompareExchange16`, `_InterlockedCompareExchange64`|x86, ARM, x64|\<intrin.h>|
|`_InterlockedCompareExchange_acq`, `_InterlockedCompareExchange_rel`, `_InterlockedCompareExchange8_acq`, `_InterlockedCompareExchange8_nf`, `_InterlockedCompareExchange8_rel`,`_InterlockedCompareExchange16_acq`, `_InterlockedCompareExchange16_nf`, `_InterlockedCompareExchange16_rel`, `_InterlockedCompareExchange64_acq`, `_InterlockedCompareExchange64_nf`, `_InterlockedCompareExchange64_rel`,|ARM|\<intrin.h>|
|`_InterlockedCompareExchange_np`, `_InterlockedCompareExchange16_np`, `_InterlockedCompareExchange64_np`|X64|\<intrin.h>|
|`_InterlockedCompareExchange_HLEAcquire`, `_InterlockedCompareExchange_HLERelease`, `_InterlockedCompareExchange64_HLEAcquire`, `_InterlockedCompareExchange64_HLERelease`|x86, x64|\<immintrin.h>|

## <a name="remarks"></a>설명

`_InterlockedCompareExchange`는 `Destination` 값과 `Comparand` 값의 원자성 비교를 수행합니다. 
  `Destination` 값이 `Comparand` 값과 같으면 `Exchange`으로 지정된 주소에 `Destination` 값이 저장됩니다. 그렇지 않으면 작업이 수행되지 않습니다.

`_InterlockedCompareExchange` Win32 Windows SDK에 대 한 컴파일러 내장 지원을 제공 [InterlockedCompareExchange](/windows/desktop/api/winnt/nf-winnt-interlockedcompareexchange) 함수입니다.

사용되는 데이터 형식과 프로세서별 획득 또는 해제 의미 체계에 따라 다른 `_InterlockedCompareExchange`의 여러 변형이 있습니다.


  `_InterlockedCompareExchange` 함수는 long 정수 값에 대해 작동하는 반면 `_InterlockedCompareExchange8`은 8비트 정수 값에 대해, `_InterlockedCompareExchange16`은 short 정수 값에 대해 그리고 `_InterlockedCompareExchange64`는 64비트 정수 값에 대해 작동합니다.

ARM 플랫폼에서는 임계 영역의 시작 및 끝과 같은 위치에서 의미 체계를 획득하고 해제하려면 `_acq` 및 `_rel` 접미사가 포함된 내장 함수를 사용합니다. 
  `_nf`("no fence"의 약어) 접미사가 포함된 ARM 내장 함수는 메모리 장벽으로 작동하지 않습니다.


  `_np`("no prefetch"의 약어) 접미사가 포함된 내장 함수는 컴파일러가 가능한 프리페치 연산을 삽입하지 못하도록 차단합니다.

HLE(Hardware Lock Elision) 명령을 지원하는 Intel 플랫폼에서 `_HLEAcquire` 및 `_HLERelease` 접미사가 포함된 내장 함수는 하드웨어에서 잠금 쓰기 단계를 제거하여 성능을 향상시킬 수 있는 힌트를 프로세서에 포함합니다. HLE를 지원하지 않는 플랫폼에서 이러한 내장 함수를 호출하면 힌트는 무시됩니다.

이러한 루틴은 내장 함수로만 사용할 수 있습니다.

## <a name="example"></a>예제

다음 예제에서는 간단한 하위 수준 스레드 동기화에 `_InterlockedCompareExchange`를 사용합니다. 이 방식은 다중 스레드 프로그래밍의 기준으로 사용하기에는 한계가 있으며, 일반적인 연관 내장 함수 사용 방법을 보여 주기 위한 용도로 제공됩니다. 최상의 결과를 얻으려면 Windows API를 사용합니다. 다중 스레드 프로그래밍에 대 한 자세한 내용은 참조 하세요. [다중 스레드 Win32 프로그램 작성](../parallel/writing-a-multithreaded-win32-program.md)합니다.

```
// intrinExample.cpp
// compile with: /EHsc /O2
// Simple example of using _Interlocked* intrinsics to
// do manual synchronization
//
// Add [-DSKIP_LOCKING] to the command line to disable
// the locking. This will cause the threads to execute out
// of sequence.

#define _CRT_RAND_S

#include "windows.h"

#include <iostream>
#include <queue>
#include <intrin.h>

using namespace std;

// --------------------------------------------------------------------

// if defined, will not do any locking on shared data
//#define SKIP_LOCKING

// A common way of locking using _InterlockedCompareExchange.
// Please refer to other sources for a discussion of the many issues
// involved. For example, this particular locking scheme performs well
// when lock contention is low, as the while loop overhead is small and
// locks are acquired very quickly, but degrades as many callers want
// the lock and most threads are doing a lot of interlocked spinning.
// There are also no guarantees that a caller will ever acquire the
// lock.
namespace MyInterlockedIntrinsicLock
{
    typedef unsigned LOCK, *PLOCK;

#pragma intrinsic(_InterlockedCompareExchange, _InterlockedExchange)

    enum {LOCK_IS_FREE = 0, LOCK_IS_TAKEN = 1};

    void Lock(PLOCK pl)
    {
#if !defined(SKIP_LOCKING)
        // If *pl == LOCK_IS_FREE, it is set to LOCK_IS_TAKEN
        // atomically, so only 1 caller gets the lock.
        // If *pl == LOCK_IS_TAKEN,
        // the result is LOCK_IS_TAKEN, and the while loop keeps spinning.
        while (_InterlockedCompareExchange((long *)pl,
                                           LOCK_IS_TAKEN, // exchange
                                           LOCK_IS_FREE)  // comparand
               == LOCK_IS_TAKEN)
        {
            // spin!
        }
        // This will also work.
        //while (_InterlockedExchange(pl, LOCK_IS_TAKEN) ==
        //                             LOCK_IS_TAKEN)
        //{
        //    // spin!
        //}

        // At this point, the lock is acquired.
#endif
    }

    void Unlock(PLOCK pl) {
#if !defined(SKIP_LOCKING)
        _InterlockedExchange((long *)pl, LOCK_IS_FREE);
#endif
    }
}

// ------------------------------------------------------------------

// Data shared by threads

queue<int> SharedQueue;
MyInterlockedIntrinsicLock::LOCK SharedLock;
int TicketNumber;

// ------------------------------------------------------------------

DWORD WINAPI
ProducerThread(
    LPVOID unused
    )
{
    unsigned int randValue;
    while (1) {
        // Acquire shared data. Enter critical section.
        MyInterlockedIntrinsicLock::Lock(&SharedLock);

        //cout << ">" << TicketNumber << endl;
        SharedQueue.push(TicketNumber++);

        // Release shared data. Leave critical section.
        MyInterlockedIntrinsicLock::Unlock(&SharedLock);

        rand_s(&randValue);
        Sleep(randValue % 20);
    }

    return 0;
}

DWORD WINAPI
ConsumerThread(
    LPVOID unused
    )
{
    while (1) {
        // Acquire shared data. Enter critical section
        MyInterlockedIntrinsicLock::Lock(&SharedLock);

        if (!SharedQueue.empty()) {
            int x = SharedQueue.front();
            cout << "<" << x << endl;
            SharedQueue.pop();
        }

        // Release shared data. Leave critical section
        MyInterlockedIntrinsicLock::Unlock(&SharedLock);

        unsigned int randValue;
        rand_s(&randValue);
        Sleep(randValue % 20);
    }
    return 0;
}

int main(
    void
    )
{
    const int timeoutTime = 500;
    int unused1, unused2;
    HANDLE threads[4];

    // The program creates 4 threads:
    // two producer threads adding to the queue
    // and two consumers taking data out and printing it.
    threads[0] = CreateThread(NULL,
                              0,
                              ProducerThread,
                              &unused1,
                              0,
                              (LPDWORD)&unused2);

    threads[1] = CreateThread(NULL,
                              0,
                              ConsumerThread,
                              &unused1,
                              0,
                              (LPDWORD)&unused2);

    threads[2] = CreateThread(NULL,
                              0,
                              ProducerThread,
                              &unused1,
                              0,
                              (LPDWORD)&unused2);

    threads[3] = CreateThread(NULL,
                              0,
                              ConsumerThread,
                              &unused1,
                              0,
                              (LPDWORD)&unused2);

    WaitForMultipleObjects(4, threads, TRUE, timeoutTime);

    return 0;
}
```

```Output
<0
<1
<2
<3
<4
<5
<6
<7
<8
<9
<10
<11
<12
<13
<14
<15
<16
<17
<18
<19
<20
<21
<22
<23
<24
<25
<26
<27
<28
<29
```

**Microsoft 전용 종료**

## <a name="see-also"></a>참고 항목

[_InterlockedCompareExchange128](../intrinsics/interlockedcompareexchange128.md)<br/>
[_InterlockedCompareExchangePointer 내장 함수](../intrinsics/interlockedcompareexchangepointer-intrinsic-functions.md)<br/>
[컴파일러 내장 함수](../intrinsics/compiler-intrinsics.md)<br/>
[C++ 키워드](../cpp/keywords-cpp.md)<br/>
[x86 컴파일러와 충돌](../build/x64-software-conventions.md#conflicts-with-the-x86-compiler)