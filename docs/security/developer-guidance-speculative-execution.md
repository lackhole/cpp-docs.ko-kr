---
title: C++투기적 실행 쪽 채널에 대 한 개발자 지침
ms.date: 07/10/2018
helpviewer_keywords:
- Visual C++, security
- security [C++]
- security [C++], best practices
- Spectre
- CVE-2017-5753
- Speculative Execution
ms.openlocfilehash: 20e6d45c088fe92fa736539e485d6807802b368a
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62179321"
---
# <a name="c-developer-guidance-for-speculative-execution-side-channels"></a>C++투기적 실행 쪽 채널에 대 한 개발자 지침

이 문서에는 식별 하 고에서 측면 채널 하드웨어 취약성 투기적 실행 완화에 도움이 되는 개발자를 위한 지침이 포함 되어 있습니다. C++ 소프트웨어입니다. 이러한 취약성 트러스트 경계에 걸쳐 중요 한 정보를 공개할 수 및 명령의 추측, 순서가의 실행을 지 원하는 프로세서에서 실행 되는 소프트웨어에 영향을 줄 수 있습니다. 이 클래스의 취약점으로 인 한이 2018 년 1 월에서에서 설명 하는 첫 번째 및 추가 배경 및에서 지침을 찾을 수 있습니다 [Microsoft 보안 권고](https://portal.msrc.microsoft.com/security-guidance/advisory/ADV180002)합니다.

이 문서에서 제공 하는 지침으로 표시 하는 취약성의 클래스는 관련이 있습니다.

1. CVE-2017-5753, Spectre variant 1 라고도 합니다. 이 하드웨어 취약점으로 인 한 클래스는 조건부 분기 오측의 결과로 발생 하는 투기적 실행으로 인해 발생할 수 있는 쪽 채널 관련이 있습니다. 시각적 개체 C++ Visual Studio 2017 (버전 15.5.5부터 시작)에서 컴파일러에 대 한 지원을 포함 합니다 `/Qspectre` CVE 2017-5753에 관련 된 잠재적으로 취약 한 코딩 패턴의 제한 된 집합에 대 한 컴파일 시간 완화 조치를 제공 하는 스위치입니다. 합니다 `/Qspectre` 스위치를 통해 Visual Studio 2015 업데이트 3에서 사용할 수 있는 이기도 [KB 4338871](https://support.microsoft.com/help/4338871)합니다. 에 대 한 설명서는 [/Qspectre](https://docs.microsoft.com/cpp/build/reference/qspectre) 플래그 효과 및 사용에 자세한 정보를 제공 합니다.

2. CVE-2018-3639, 라고도 [잘못 된 저장소 사용 안 함 (SSB)](https://aka.ms/sescsrdssb)합니다. 이 하드웨어 취약점으로 인 한 클래스는 메모리 액세스 오측 결과로 종속 저장소를 미리 로드의 투기적 실행으로 인해 발생할 수 있는 쪽 채널 관련이 있습니다.

투기적 실행 쪽 채널 취약성에 액세스할 수 있는 소개 라는 프레젠테이션에서 찾을 수 있습니다 [The 사례 스펙터와 멜트다운](https://www.youtube.com/watch?v=_4O0zMW-Zu4) 이러한 문제를 검색 하는 연구 팀 중 하나에서.

## <a name="what-are-speculative-execution-side-channel-hardware-vulnerabilities"></a>잘못 된 실행 쪽 채널 하드웨어 취약성은 무엇 인가요?

최신 Cpu 만들어 높은 수준의 성능 제공 활용 한 추측 및 순서가 명령 실행 합니다. 예를 들어,이 경우가 많습니다 추측을 통해 예측 된 분기 대상에 있는 지침을 실행 하려면 CPU 수 있도록 하는 대상 분기 (조건부 및 간접)를 예측 하 여 실제 분기 대상이 될 때까지 정지 방지 해결 합니다. 이벤트의 CPU를 오측 발생 했음을 나중에 검색 항목을 추측 계산 된 컴퓨터 상태가 모두 삭제 됩니다. 이렇게 하면 오측된 추론의 아키텍처 측면에서 볼 수 없는 효과 합니다.

투기적 실행을 구조적으로 표시 되는 상태는 영향을 주지 않습니다, 하지만 잔여 추적 CPU에서 사용 되는 다양 한 캐시 같은 아키텍처 되지 않은 상태로 그대로 둘 수 있습니다. 이러한 잔여 추적 쪽 채널 취약성을 증가 제공할 수 있는 투기적 실행의 경우 이 더 잘 이해 하려면 CVE-2017-5753 (범위 확인 사용 안 함)의 예제를 제공 하는 다음 코드 조각은 고려 합니다.

```cpp
// A pointer to a shared memory region of size 1MB (256 * 4096)
unsigned char *shared_buffer;

unsigned char ReadByte(unsigned char *buffer, unsigned int buffer_size, unsigned int untrusted_index) {
    if (untrusted_index < buffer_size) {
        unsigned char value = buffer[untrusted_index];
        return shared_buffer[value * 4096];
    }
}
```

이 예제에서는 `ReadByte` 가 해당 버퍼에 버퍼, 버퍼 크기와 인덱스를 제공 합니다. 인덱스 매개 변수에서 지정한 대로 `untrusted_index`, less에서 제공 하는 관리자가 아닌 프로세스와 같은 권한 있는 컨텍스트. 하는 경우 `untrusted_index` 는 보다 작은 `buffer_size`에서 해당 인덱스에 있는 문자를 읽은 다음 `buffer` 공유에서 참조 하는 메모리 영역에 인덱스를 사용 하 고 `shared_buffer`합니다.

아키텍처 관점에서이 코드 시퀀스는 안전 하다는 보장이 `untrusted_index` 은 항상 미만 `buffer_size`합니다. 그러나 투기적 실행 시 있기 CPU는 조건부 분기 예측 실패 하 고 if의 본문을 실행는 문의 경우에 `untrusted_index` 보다 크거나 같음 `buffer_size`합니다. 따라서 CPU의 범위에서 일어난 바이트 읽을 추측 수 있습니다 `buffer` (하는 암호를 사용 가능)를 통해 후속 부하의 주소를 계산 하는 바이트 값을 사용할 수 없습니다 및 `shared_buffer`합니다.

의도 하지 않은 남아 있는 CPU이이 오측 감지 최종적으로 동안 경계에서 읽은 바이트 값에 대 한 정보를 표시 하는 CPU 캐시에 남아 있을 수 있습니다 `buffer`합니다. 이러한 부작용 작음 하 여 검색할 수에서 얼마나 신속 하 게 검색 하 여 시스템에서 실행 되는 권한 있는 컨텍스트 각 캐시 줄 `shared_buffer` 액세스. 이 위해 수행할 수 있는 단계를 다음과 같습니다.

1. **호출할 `ReadByte` 으로 여러 번 `untrusted_index` 되 미만 `buffer_size`** 합니다. 공격 컨텍스트를 호출 하 여 컨텍스트를 발생할 수 있습니다 `ReadByte` (예: 통해 RPC)으로 not 수행 되도록 학습 분기 predictor는 되도록 `untrusted_index` 는 보다 작은 `buffer_size`합니다.

2. **모든 캐시 라인 플러시 `shared_buffer`** 합니다. 공격 컨텍스트 공유 지역에서 참조 하는 메모리에 캐시 줄을 모두 플러시해야 `shared_buffer`합니다. 메모리 영역을 공유 하므로이 간단 하며 같은 내장 함수를 사용 하 여 수행할 수 있습니다 `_mm_clflush`합니다.

3. **호출할 `ReadByte` 사용 하 여 `untrusted_index` 크거나 `buffer_size`** 합니다. 공격 컨텍스트를 호출 하 여 컨텍스트를 하면 `ReadByte` 는 올바르게 예측 하지 분기 수행 되지 것입니다. 블록 프로세서가 추측 경우 본문을 실행 하는이 원인 `untrusted_index` 보다 큰지 `buffer_size`범위를 벗어나는 읽기에 따라서 선행의 `buffer`합니다. 따라서 `shared_buffer` 읽은 범위를 벗어나는, CPU에서 로드할 각 캐시 라인이 발생 하는 잠재적으로 비밀 값을 사용 하 여 인덱싱됩니다.

4. **각 캐시 줄 읽기 `shared_buffer` 가장 빠르게 액세스 보려는**합니다. 공격 컨텍스트는 각 캐시 라인에 읽을 수 `shared_buffer` 하 고 다른 항목 보다 훨씬 더 빠르게 로드 하는 캐시 라인을 검색 합니다. 3 단계 가져온 후 발생할 수 있는 캐시 라인입니다. 이 예에서 바이트 값 및 캐시 줄 사이 1:1 관계 이므로 이렇게 하면 공격자가 범위를 벗어나는 읽은 바이트의 실제 값을 유추할 수 있습니다.

위의 단계를 플러시 + 다시 로드 CVE 2017-5753 인스턴스의 악용 함께에서 이라는 기술을 사용 하는 예제를 제공 합니다.

## <a name="what-software-scenarios-can-be-impacted"></a>어떤 소프트웨어 시나리오에 영향이 있을 수 있습니다.

과 같은 프로세스를 사용 하 여 보안 소프트웨어를 개발 합니다 [Security Development Lifecycle](https://www.microsoft.com/sdl/) (SDL)에 일반적으로 응용 프로그램에 존재 하는 신뢰 경계를 식별 하는 개발자가 필요 합니다. 트러스트 경계 경우 시스템에서 다른 프로세스 또는 커널 모드 장치 드라이버의 경우 관리자가 아닌 사용자 모드 프로세스와 같은 신뢰할 수 없는 context에서 제공 하는 데이터와 응용 프로그램 상호 작용할 수 있습니다 위치에 있습니다. 투기적 실행 쪽 채널 관련 된 취약점의 새 클래스 코드 및 장치에서 데이터를 격리 하는 기존 소프트웨어 보안 모델의 트러스트 경계 중 많은 부분에 관련이 있습니다.

다음 표에서 발생 하는 이러한 취약성에 대 한 고려 개발자가 해야 할 수 있는 소프트웨어 보안 모델의 요약을 제공 합니다.

|신뢰 경계|설명|
|----------------|----------------|
|가상 컴퓨터 경계|다른 가상 컴퓨터에서 신뢰할 수 없는 데이터를 수신 하는 별도 virtual machines에서 작업을 격리 하는 응용 프로그램은 위험할 수 있습니다.|
|커널 경계|관리자가 아닌 사용자 모드 프로세스에서 신뢰할 수 없는 데이터를 수신 하는 커널 모드 장치 드라이버는 위험할 수 있습니다.|
|프로세스 경계|위험에 노출 될 수 있습니다 메커니즘을 원격 프로시저 호출 (RPC), 공유 메모리 또는 다른 프로세스 간 통신 (IPC)을 통해 같은 로컬 시스템에서 실행 중인 다른 프로세스에서 신뢰할 수 없는 데이터를 수신 하는 응용 프로그램입니다.|
|Enclave 경계|Enclave 외부에서 신뢰할 수 없는 데이터를 수신 하는 (예: Intel SGX) 보안 enclave 내에서 실행 하는 응용 프로그램은 위험할 수 있습니다.|
|언어의 경계|해석 하는 응용 프로그램 또는 jit (JUST-IN-TIME) 컴파일 및 작성 하는 신뢰할 수 없는 코드를 실행 합니다. 상위 수준 언어를 위험에 노출 될 수 있습니다.|

응용 프로그램을 공격 노출 하려면 위 신뢰 경계에서 공격 노출 영역을 파악 및 완화할 수 인스턴스의 투기적 실행 쪽 채널 취약성에 대 한 코드를 검토 해야 합니다. 원격 네트워크 프로토콜과 같은 원격 공격에 노출 하는 신뢰 경계 투기적 실행 쪽 채널 취약성에 노출 되도록 설명 하지는 점에 유의 해야 합니다.

## <a name="potentially-vulnerable-coding-patterns"></a>잠재적으로 취약 한 코딩 패턴

투기적 실행 쪽 채널 취약성은 여러 코딩 패턴의 결과로 발생할 수 있습니다. 이 섹션에서는 잠재적으로 취약 한 코딩 패턴에 설명 하 고 각각에 대 한 예제를 제공 하지만 이러한 테마에서 각기 다르게 있을 인식 되도록 해야 합니다. 따라서 개발자가 모든 잠재적으로 취약 한 코딩 패턴의 전체 목록을 아니라 예제로 이러한 패턴을 사용 하는 것이 좋습니다. 지금 소프트웨어에 존재할 수 있는 메모리 안전성 취약점의 동일한 클래스 투기적 함께 존재할 수도 있습니다 및 버퍼 오버런에 국한 되지 않음 등 실행의 순서가 경로 범위를 벗어나는 액세스, 초기화 되지 않은 메모리 사용 형식 배열 혼동을 및 등입니다. 공격자가 아키텍처 경로 따라 메모리 안전성 취약점을 악용 하는 데 사용할 수 있는 동일한 기본 형식을 잘못 된 경로에 적용할 수 있습니다.

일반적으로 투기적 실행 쪽 채널 조건부 관련이 분기 오측 조건식 제어 하거나 신뢰할 수 없는 상황에 맞는 영향 수 있는 데이터에 작동 하는 경우 발생할 수 있습니다. 예를 들어,이에서 사용 되는 조건식 `if`, `for`, `while`, `switch`, 3 개로 구성 된 문 또는 합니다. 이러한 문은 각각에 대 한 컴파일러는 CPU 수 다음 런타임 시에 대 한 분기 대상이 예측 하는 조건부 분기를 생성할 수 있습니다.

각 예를 들어 개발자는 장벽 문제 완화를 얻는데 이러한 여기서 "추론 장벽을" 라는 문구를 사용 하 여 주석을 삽입 됩니다. 완화에 섹션에서 자세히 설명 되어 있습니다.

## <a name="speculative-out-of-bounds-load"></a>잘못 된 범위를 벗어나는 로드

이 범주의 코딩 패턴을 발생 시키는 잘못 된 범위를 벗어나는 조건부 분기 오측은 메모리 액세스 합니다.

### <a name="array-out-of-bounds-load-feeding-a-load"></a>배열 범위를 벗어나는 로드 부하를 제공 합니다.

이 코딩 패턴에는 CVE-2017-5753 (범위 확인 사용 안 함)에 대 한 원래 설명된 취약 한 코딩 패턴이입니다. 이 문서의 백그라운드 섹션에이 패턴을 자세히 설명합니다.

```cpp
// A pointer to a shared memory region of size 1MB (256 * 4096)
unsigned char *shared_buffer;

unsigned char ReadByte(unsigned char *buffer, unsigned int buffer_size, unsigned int untrusted_index) {
    if (untrusted_index < buffer_size) {
        // SPECULATION BARRIER
        unsigned char value = buffer[untrusted_index];
        return shared_buffer[value * 4096];
    }
}
```

마찬가지로 부하의 종료를 초과 하는 루프와 함께에서 나타날 수 있습니다 배열 범위를 벗어나는 오측 인해 조건입니다. 이 예에서 조건부 분기와 연결 합니다 `x < buffer_size` 식 예측 실패 하 고 추측의 본문을 실행할 수 있습니다를 `for` 때 루프 `x` 보다 크거나 같음 `buffer_size`, 따라서 결과 잘못 된 범위를 벗어나는 로드 합니다.

```cpp
// A pointer to a shared memory region of size 1MB (256 * 4096)
unsigned char *shared_buffer;

unsigned char ReadBytes(unsigned char *buffer, unsigned int buffer_size) {
    for (unsigned int x = 0; x < buffer_size; x++) {
        // SPECULATION BARRIER
        unsigned char value = buffer[x];
        return shared_buffer[value * 4096];
    }
}
```

### <a name="array-out-of-bounds-load-feeding-an-indirect-branch"></a>배열 범위를 벗어나는 로드 간접 분기를 제공 합니다.

이 코딩 패턴에서는 조건부 분기 오측 발생할 수 있는 대/소문자를 대상에는 간접 분기에는 다음 잠재 고객 문제를 해결 하는 함수 포인터의 배열에 대 한 액세스 범위를 벗어나는 읽은 범위를 벗어나는. 다음 코드 조각은이 보여 주는 예제를 제공 합니다.

이 예제에서는 신뢰할 수 없는 메시지 식별자 제공 되어 통해 DispatchMessage는 `untrusted_message_id` 매개 변수입니다. 하는 경우 `untrusted_message_id` 는 보다 작은 `MAX_MESSAGE_ID`, 함수 포인터의 배열로 인덱스 및 분기에 사용 됩니다 해당 분기 대상입니다. 아키텍처 측면에서이 코드는 안전 하지만 CPU mispredicts 조건부 분기를에서 될 수 있습니다 `DispatchTable` 에 의해 인덱싱되고 `untrusted_message_id` 해당 값 보다 크거나 같은 경우 `MAX_MESSAGE_ID`를 따라서는 범위를 벗어나는 액세스 합니다. 이 추측을 통해 실행 되는 코드에 따라 정보 공개 문제점는 배열의 범위를 넘어 파생 되는 분기 대상 주소에서 투기적 실행 될 수 있습니다.

```cpp
#define MAX_MESSAGE_ID 16

typedef void (*MESSAGE_ROUTINE)(unsigned char *buffer, unsigned int buffer_size);

const MESSAGE_ROUTINE DispatchTable[MAX_MESSAGE_ID];

void DispatchMessage(unsigned int untrusted_message_id, unsigned char *buffer, unsigned int buffer_size) {
    if (untrusted_message_id < MAX_MESSAGE_ID) {
        // SPECULATION BARRIER
        DispatchTable[untrusted_message_id](buffer, buffer_size);
    }
}
```

부하가 배열 범위를 벗어나는 대/소문자를 사용 하 여 다른 부하를 제공 하면이 문제는 오측 인해 종료 조건 초과 하는 루프와 함께에서 발생할 수 있습니다.

### <a name="array-out-of-bounds-store-feeding-an-indirect-branch"></a>배열 범위를 벗어나는 저장 간접 분기를 제공 합니다.

앞의 예제에 설명 했습니다는 잘못 된 범위를 벗어나는 방법을 부하를 간접 분기 대상에 영향을 줄 수는 것도 수는 함수 포인터 또는 반송 주소 등의 간접 분기 대상을 수정 하려면 범위를 벗어나는 저장 합니다. 이 잠재적으로 투기적 실행 공격자가 지정 된 주소에서 발생할 수 있습니다.

이 예제에서는 신뢰할 수 없는 인덱스를 통해 전달 됩니다는 `untrusted_index` 매개 변수입니다. 경우 `untrusted_index` 의 요소 수보다 작습니다 합니다 `pointers` 배열 (256 요소)를 다음에서 제공 된 포인터 값 `ptr` 에 기록 됩니다는 `pointers` 배열입니다. 이 코드는 아키텍처 측면에서 안전 하지만 CPU mispredicts 조건부 분기를에서 될 수 있습니다 `ptr` 스택에 할당의 경계를 벗어나 추측 쓰고 `pointers` 배열입니다. 이 대 한 반환 주소 투기적 손상을 초래할 수 `WriteSlot`입니다. 공격자의 값을 제어할 수 있는 경우 `ptr`, 임의의에서 투기적 실행 시킬 수 있습니다 때 주소 `WriteSlot` 잘못 된 경로 반환 합니다.

```cpp
unsigned char WriteSlot(unsigned int untrusted_index, void *ptr) {
    void *pointers[256];
    if (untrusted_index < 256) {
        // SPECULATION BARRIER
        pointers[untrusted_index] = ptr;
    }
}
```

마찬가지로, 명명 된 함수 포인터 로컬 변수가 `func` 추측 주소를 수정할 수 있습니다 다음 스택에 할당 된는 `func` 조건부 분기 오측 발생 하는 경우를 말합니다. 이 함수 포인터를 통해 호출 될 때 임의의 주소에서 투기적 실행 될 수 있습니다.

```cpp
unsigned char WriteSlot(unsigned int untrusted_index, void *ptr) {
    void *pointers[256];
    void (*func)() = &callback;
    if (untrusted_index < 256) {
        // SPECULATION BARRIER
        pointers[untrusted_index] = ptr;
    }
    func();
}
```

두이 예제 모두 잘못 된 스택 할당 간접 분기 포인터 수정 한다는 점에 유의 해야 합니다. 잘못 된 수정에도 읽기 전용 메모리 일부 Cpu에서 전역 변수, 힙 할당 메모리에 발생할 가능성이 있습니다. 스택 할당 된 메모리, 시각적 개체에 대 한 C++ 컴파일러에는 이미 추측 버퍼 보안에 인접 한 배치 되는 로컬 변수 다시 정렬 하 여 같은 간접 분기 스택 할당 대상을 수정 하기 더 어려운 확인 하는 단계는 쿠키의 일부로 합니다 [/GS](https://docs.microsoft.com/cpp/build/reference/gs-buffer-security-check) 컴파일러 보안 기능입니다.

## <a name="speculative-type-confusion"></a>잘못 된 형식 혼동

이 범주에 다룹니다 코딩 패턴을 잘못 된 형식 혼란이 발생할 수 있습니다. 이 아키텍처 패스를 따라는 잘못 된 문자를 사용 하 여 투기적 실행 하는 동안 메모리에 액세스할 때 발생 합니다. 조건부 분기 오측와 잘못 된 저장소 바이패스 잠재적으로 잘못 된 형식 혼란이 발생할 수 있습니다.

잘못 된 저장소 바이패스에 대 한이 시나리오는 컴파일러 다시 여러 종류의 변수에 대 한 스택 위치를 사용 하는 위치에서 발생할 수 있습니다. 왜냐하면 형식 변수의의 아키텍처 저장소 `A` 있으므로 다음 형식의 부하 우회 될 수 있습니다 `A` 드리는 변수에 할당 되기 전에 실행 하 합니다. 이전에 저장 된 변수의 다른 종류의 경우 잘못 된 형식 혼동 조건을 만들 수이.

조건부 분기 오측 다음 코드 조각 설명에 사용 됩니다 잘못 된 형식 혼동을 제공할 수 있는 다양 한 조건을 정상에 오 르다.

```cpp
enum TypeName {
    Type1,
    Type2
};

class CBaseType {
public:
    CBaseType(TypeName type) : type(type) {}
    TypeName type;
};

class CType1 : public CBaseType {
public:
    CType1() : CBaseType(Type1) {}
    char field1[256];
    unsigned char field2;
};

class CType2 : public CBaseType {
public:
    CType2() : CBaseType(Type2) {}
    void (*dispatch_routine)();
    unsigned char field2;
};

// A pointer to a shared memory region of size 1MB (256 * 4096)
unsigned char *shared_buffer;

unsigned char ProcessType(CBaseType *obj)
{
    if (obj->type == Type1) {
        // SPECULATION BARRIER
        CType1 *obj1 = static_cast<CType1 *>(obj);

        unsigned char value = obj1->field2;

        return shared_buffer[value * 4096];
    }
    else if (obj->type == Type2) {
        // SPECULATION BARRIER
        CType2 *obj2 = static_cast<CType2 *>(obj);

        obj2->dispatch_routine();

        return obj2->field2;
    }
}
```

### <a name="speculative-type-confusion-leading-to-an-out-of-bounds-load"></a>잘못 된 형식 혼동 하는 범위를 벗어나는 로드

이 코딩 패턴에서는 잘못 된 형식 혼동 될 수 있습니다 위치 하는 경우는 범위를 벗어나는 또는 로드 된 값 이후에 로드 주소를 피드 하는 위치 필드 형식 혼동 액세스 합니다. 이 배열 범위를 벗어나는 코딩 패턴 유사 하지만 위에 표시 된 대로 시퀀스를 코딩 하는 대신 통해 매니페스트 됩니다. 이 예제에서는 공격 컨텍스트를 실행을 위해 공격 대상 컨텍스트를 일으킬 수 있습니다 `ProcessType` 형식의 개체와 여러 번 `CType1` (`type` 필드 값과 같음 `Type1`). 첫 번째 조건부 분기를 학습의 효과 갖습니다이 `if` 문을 예측 수행 되지 않습니다. 공격 컨텍스트 실행을 위해 컨텍스트 교착 상태가 발생 하면 다음 `ProcessType` 형식의 개체를 사용 하 여 `CType2`입니다. 첫 번째 조건부 분기 하는 경우이 잘못 된 형식 혼동 될 수 있습니다 `if` mispredicts 문과의 본문을 실행 합니다 `if` 형식의 개체를 캐스팅 하므로 문을 `CType2` 에 `CType1`입니다. 하므로 `CType2` 보다 작습니다 `CType1`에 대 한 메모리 액세스 `CType1::field2` 는 결과에 잘못 된 범위를 벗어나는 로드 보안 되지 않은 데이터입니다. 이 값은 다음에서 로드 사용 `shared_buffer` 배열 마찬가지로 눈에 띄는 부작용을 만들 수 있는 범위를 벗어나는 예제에서는 앞에서 설명한 합니다.

### <a name="speculative-type-confusion-leading-to-an-indirect-branch"></a>간접 분기 앞에 잘못 된 형식 혼동

이 코딩 패턴에는 투기적 실행 하는 동안 안전 하지 않은 간접 분기의 잘못 된 형식 혼동 될 수 있습니다 위치 하는 경우 포함 됩니다. 이 예제에서는 공격 컨텍스트를 실행을 위해 공격 대상 컨텍스트를 일으킬 수 있습니다 `ProcessType` 형식의 개체와 여러 번 `CType2` (`type` 필드 값과 같음 `Type2`). 첫 번째 조건부 분기를 학습 효과 해야 `if` 수행할 문 및 `else if` 문을 수행 하지 않습니다. 공격 컨텍스트 실행을 위해 컨텍스트 교착 상태가 발생 하면 다음 `ProcessType` 형식의 개체를 사용 하 여 `CType1`입니다. 첫 번째 조건부 분기 하는 경우이 잘못 된 형식 혼동 될 수 있습니다 `if` 문은 예측 수행 및 `else if` 본문의 실행 문은 예측 하지 수행한는 `else if` 형식의개체를캐스팅하고`CType1` 에 `CType2`입니다. 이후를 `CType2::dispatch_routine` 필드와 겹치는 `char` 배열 `CType1::field1`,이 인해 잘못 된 간접 분기에서 의도 하지 않은 분기 대상입니다. 공격 상황에 맞는 경우 바이트 값을 제어할 수는 `CType1::field1` 배열 수 분기 대상 주소를 제어할 수 있습니다.

## <a name="speculative-uninitialized-use"></a>잘못 된 초기화 되지 않은 사용

이 범주의 코딩 패턴에는 투기적 실행 될 수 있습니다 초기화 되지 않은 메모리에 액세스 하 고 사용 하 여 이후 부하 또는 간접 분기 피드 시나리오 포함 됩니다. 악용 되도록 이러한 코딩 패턴을 공격자를 제어 하거나 맥락에서 사용 되는 컨텍스트별 초기화 되지 않은 상태로 사용 되는 메모리 내용을 영향을 줄 수 해야 합니다.

### <a name="speculative-uninitialized-use-leading-to-an-out-of-bounds-load"></a>투기적 초기화 되지 않은 사용 하는 범위를 벗어나는 로드

잘못 된 초기화 되지 않은 사용을 잠재적으로 발생 시킬 수는 범위를 벗어나는 공격자가 제어 값을 사용 하 여를 로드 합니다. 값 아래 예에서 `index` 할당 됩니다 `trusted_index` 아키텍처 모든 경로에 및 `trusted_index` 보다 작거나 같은 것으로 간주 됩니다 `buffer_size`. 그러나 컴파일러에서 생성 된 코드에 따라 있기 부하를 허용 하는 잘못 된 저장소 바이패스를 발생할 수 있습니다 `buffer[index]` 및 미리 할당을 실행 하는 종속 식 `index`합니다. 이 경우에 대 한 초기화 되지 않은 값 `index` 에 대 한 오프셋으로 사용할 `buffer` 공격자가 범위를 벗어나는 중요 한 정보를 읽고 종속 부하를 통해 쪽 채널을 통해이 전달할 수 있는 `shared_buffer` .

```cpp
// A pointer to a shared memory region of size 1MB (256 * 4096)
unsigned char *shared_buffer;

void InitializeIndex(unsigned int trusted_index, unsigned int *index) {
    *index = trusted_index;
}

unsigned char ReadByte(unsigned char *buffer, unsigned int buffer_size, unsigned int trusted_index) {
    unsigned int index;

    InitializeIndex(trusted_index, &index); // not inlined

    // SPECULATION BARRIER
    unsigned char value = buffer[index];
    return shared_buffer[value * 4096];
}
```

### <a name="speculative-uninitialized-use-leading-to-an-indirect-branch"></a>간접 분기 선행 투기적 초기화 되지 않은 사용

잘못 된 초기화 되지 않은 사용 될 수 있습니다 잠재적으로 간접 분기를 분기 대상이 공격자가 제어 하는 위치입니다. 아래 예에서 `routine` 중 하나에 할당 됩니다 `DefaultMessageRoutine1` 또는 `DefaultMessageRoutine` 값에 따라 `mode`합니다. 아키텍처 경로에서 이렇게 하면 `routine` 항상 간접 분기 미리 초기화 되 고 있습니다. 그러나 컴파일러에서 생성 된 코드에 따라 잘못 된 저장소 바이패스를 발생할 수 있습니다 통해 간접 분기 수 있도록 `routine` 할당을 사전 실행할 추측 `routine`합니다. 이 경우 공격자 할 수 있습니다는 임의의 주소에서 추측을 통해 실행 가정 공격자가 영향을 줄 수의 초기화 되지 않은 값을 제어 하 고 `routine`입니다.

```cpp
#define MAX_MESSAGE_ID 16

typedef void (*MESSAGE_ROUTINE)(unsigned char *buffer, unsigned int buffer_size);

const MESSAGE_ROUTINE DispatchTable[MAX_MESSAGE_ID];
extern unsigned int mode;

void InitializeRoutine(MESSAGE_ROUTINE *routine) {
    if (mode == 1) {
        *routine = &DefaultMessageRoutine1;
    }
    else {
        *routine = &DefaultMessageRoutine;
    }
}

void DispatchMessage(unsigned int untrusted_message_id, unsigned char *buffer, unsigned int buffer_size) {
    MESSAGE_ROUTINE routine;

    InitializeRoutine(&routine); // not inlined

    // SPECULATION BARRIER
    routine(buffer, buffer_size);
}
```

## <a name="mitigation-options"></a>완화 하는 방법

소스 코드를 변경 하 여 투기적 실행 쪽 채널 취약성을 완화할 수 있습니다. 이러한 변경 내용을 추가 하 여 같은 특정 인스턴스의 취약점을 완화 하는 포함 될 수 있습니다는 *추론 장벽을*, 또는 응용 프로그램의 중요 한 정보에 액세스할 수 없는 잘못 된 디자인을 변경 하 여 실행 합니다.

### <a name="speculation-barrier-via-manual-instrumentation"></a>수동 계측이 통해 추론 장벽

A *추론 장벽을* 아키텍처 경로 따라 계속에서 투기적 실행을 방지 하기 위해 개발자가 수동으로 삽입할 수 있습니다. 개발자가 조건부 분기) (이후에 블록의 시작 부분에서 조건부 블록의 본문에 위험한 코딩 패턴을 하기 전에 추론 장벽의 삽입할 수는 예를 들어, 또는 관련 된 첫 번째 로드 전에 합니다. 이 아키텍처 경로에서 실행을 직렬화 하 여 위험한 코드를 실행 하는 조건부 분기 오측을 못하게 됩니다. 추론 장벽을 시퀀스는 다음 표에 설명 된 대로 하드웨어 아키텍처에 따라 다릅니다.

|아키텍처|추론 장벽을 CVE 2017-5753에 대해 내장 함수|추론 장벽을 CVE-2018-3639 내장 함수|
|----------------|----------------|----------------|
|x86/x64|_mm_lfence()|_mm_lfence()|
|ARM|현재 사용할 수 없음|__dsb(0)|
|ARM64|현재 사용할 수 없음|__dsb(0)|

예를 들어, 사용 하 여 다음과 같은 코드 패턴을 완화할 수 있습니다는 `_mm_lfence` 아래와 같이 내장 함수입니다.

```cpp
// A pointer to a shared memory region of size 1MB (256 * 4096)
unsigned char *shared_buffer;

unsigned char ReadByte(unsigned char *buffer, unsigned int buffer_size, unsigned int untrusted_index) {
    if (untrusted_index < buffer_size) {
        _mm_lfence();
        unsigned char value = buffer[untrusted_index];
        return shared_buffer[value * 4096];
    }
}
```

### <a name="speculation-barrier-via-compiler-time-instrumentation"></a>추론 장벽을 컴파일러 타임 계측을 통해

시각적 개체 C++ Visual Studio 2017 (버전 15.5.5부터 시작)에서 컴파일러에 대 한 지원을 포함 합니다 `/Qspectre` 자동으로 제한 된 집합만 잠재적으로 취약 한 코딩 패턴에 대 한 추론 장벽을 삽입 하는 스위치와 관련 된 CVE-2017-5753 합니다. 에 대 한 설명서는 [/Qspectre](https://docs.microsoft.com/cpp/build/reference/qspectre) 플래그 효과 및 사용에 자세한 정보를 제공 합니다. 이 플래그는 모든 잠재적으로 취약 한 코딩 패턴은 다루지 않습니다을 같이 개발자에 의존 하지 않아야 하의 취약점으로 인 한이이 클래스에 대 한 포괄적인 완화 하는 것이 반드시 합니다.

### <a name="masking-array-indices"></a>마스킹 배열 인덱스

여기서는 잘못 된 범위를 벗어나는 로드 하는 경우에 발생할 수 있습니다, 배열 인덱스를 명시적으로 바인딩된 논리를 추가 하 여 아키텍처 및 아키텍처 경로에 배열 인덱스를 강력한 제한 될 수 있습니다. 예를 들어, 배열 2의 거듭제곱에 맞춰진 크기를 할당할 경우 다음 간단한 마스크를 도입할 수 있습니다. 이 나와 있는 것으로 가정 하는 아래 샘플에서 `buffer_size` 2의 거듭제곱에 맞춥니다. 이렇게 `untrusted_index` 는 항상 미만 `buffer_size`조건부 분기 오측 발생 하는 경우에, 및 `untrusted_index` 보다 크거나 같은 값을 사용 하 여 전달 된 `buffer_size`합니다.

컴파일러에서 생성 되는 코드에 따라 잘못 된 저장소 바이패스를 여기서 수행할 인덱스 마스킹 발생할 수 있습니다는 점에 유의 해야 합니다.

```cpp
// A pointer to a shared memory region of size 1MB (256 * 4096)
unsigned char *shared_buffer;

unsigned char ReadByte(unsigned char *buffer, unsigned int buffer_size, unsigned int untrusted_index) {
    if (untrusted_index < buffer_size) {
        untrusted_index &= (buffer_size - 1);
        unsigned char value = buffer[untrusted_index];
        return shared_buffer[value * 4096];
    }
}
```

### <a name="removing-sensitive-information-from-memory"></a>메모리에서 중요 한 정보를 제거합니다.

투기적 실행 쪽 채널 취약성을 완화 하기 위해 사용할 수 있는 또 다른 방법은 메모리에서 중요 한 정보를 제거 하는 것입니다. 소프트웨어 개발자는 투기적 실행 하는 동안 중요 한 정보에 액세스할 수 없는 응용 프로그램을 리팩터링 하는 기회 찾을 수 있습니다. 이 별도 프로세스에 중요 한 정보를 격리 하는 응용 프로그램의 디자인을 리팩터링에서 수행할 수 있습니다. 예를 들어, 웹 브라우저 응용 프로그램을 하나의 프로세스 투기적 실행을 통해 크로스-원본 데이터에 액세스할 수 없도록 방지 하는 별도 프로세스에 사용 하 여 각 웹 연결 된 데이터를 격리 하려고 할 수 있습니다.

## <a name="see-also"></a>참고자료

[투기적 실행 사이드 채널 취약성을 완화 하기 위한 지침](https://portal.msrc.microsoft.com/security-guidance/advisory/ADV180002)<br/>
[투기적 실행 쪽 채널 하드웨어 취약성을 완화 하기](https://blogs.technet.microsoft.com/srd/2018/03/15/mitigating-speculative-execution-side-channel-hardware-vulnerabilities/)
