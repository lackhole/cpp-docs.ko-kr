---
title: ARM64 예외 처리
ms.date: 11/19/2018
ms.openlocfilehash: 921029704e4bf5adabfbe0a82387dadc911b9036
ms.sourcegitcommit: 8105b7003b89b73b4359644ff4281e1595352dda
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/14/2019
ms.locfileid: "57816154"
---
# <a name="arm64-exception-handling"></a>ARM64 예외 처리

ARM64에서 Windows 동일한 구조적된 예외 처리 비동기 하드웨어에서 생성 된 예외와 동기 소프트웨어에서 생성 된 예외에 대 한 메커니즘을 사용 합니다. 언어별 예외 처리기가 언어 도우미 함수를 사용하여 Windows의 구조적 예외 처리를 기반으로 작성됩니다. 이 문서는 ARM64, Microsoft ARM 어셈블러 및 MSVC 컴파일러에서 생성 되는 코드에서 사용 하는 언어 도우미에는 Windows에서 처리 하는 예외를 설명 합니다.

## <a name="goals-and-motivation"></a>목표 및 동기

예외 해제 데이터 규칙 및이 설명 하고자 합니다.

1. 모든 경우에서 검색 하는 코드 없이 해제 수 있도록 충분 한 설명을 제공 합니다.

   - 코드 분석에서 페이징 하는 코드에 필요 합니다. 것이 유용한 일부 상황에서 해제 하는 것이 이렇게 (추적, 샘플링, 디버깅) 합니다.

   - 코드를 분석 하는 것은 복잡 합니다. 컴파일러만 해제기를 디코딩할 수는 지침을 생성 하도록 주의 해야 합니다.

   - 해제는 해제 코드를 사용 하 여 완전 하 게 설명할 수 없으면, 일부 경우에 해당 해야 하 여 다음 대체 명령 디코딩. 전체적인 복잡도 늘어나고 이상적으로 사용 하지 않아야 합니다.

1. 중간 프롤로그의 해제 및 중간 에필로그를 지원 합니다.

   - 예외 처리 보다 Windows는 해제, 수행 하는 일을 할 수는 중요 한 것 이므로 정확한 해제 프롤로그 또는 에필로그 코드 시퀀스를 중간도 합니다.

1. 최소한의 공간을 차지 합니다.

   - 해제 코드 이진 크기가 크게 증가 하는 집계 되지 해야 합니다.

   - 해제 코드는 메모리에서 잠글 수, 있으므로 적으며 각 로드 이진 파일에 대 한 최소한의 오버 헤드를 확인 합니다.

## <a name="assumptions"></a>Assumptions

예외 처리 설명의에서 가정은 다음과 같습니다.

1. 프롤로그와 에필로그는 다른 두 미러링 경향이 있습니다. 이 공통 특성 (trait) 기능을 활용 하 여 해제에 대해 설명 하는 데 필요한 메타 데이터의 크기를 크게 줄일 수 있습니다. 함수의 본문 내에서 중요 하지 않습니다는 프롤로그의 작업이 수행 되지 여부는 에필로그 작업 정방향 방식으로 수행 됩니다. 두 작업에서 모두 같은 결과가 생성됩니다.

1. 함수는 비교적 크기가 작은 경우가 전체적으로 볼 때 경향이 있습니다. 이 데이터의 가장 효율적인 압축을 달성 하기 위해 공간에 대 한 몇 가지 최적화를 사용 합니다.

1. 에필로그에서 조건부 코드가 없는 합니다.

1. 전용된 프레임 포인터 레지스터 합니다. 언제 든 지 원본 sp를 복구할 수 있도록 sp 프롤로그에 등록 하는 다른 레지스터 (r29)에 저장 된 경우 함수 전체에서 그대로 남아 있습니다.

1. Sp 다른 레지스터에 저장 하지 않으면 모든 조작 스택 포인터의 프롤로그 및 에필로그 내에서 엄격 하 게 발생 합니다.

1. 스택 프레임 레이아웃에는 다음 섹션에 설명 된 대로 구성 됩니다.

## <a name="arm64-stack-frame-layout"></a>ARM64 스택 프레임 레이아웃

![스택 프레임 레이아웃](media/arm64-exception-handling-stack-frame.png "스택 프레임 레이아웃")

연결 프레임 함수에 대 한 최적화 고려 사항에 따라 로컬 변수 영역에서 다른 위치에 있는 fp 및 lr 쌍을 저장할 수 있습니다. 목표는 프레임 포인터 (r29) 또는 스택 포인터 (sp)에 따라 하나의 단일 명령으로 연결할 수 있는 지역 수를 최대화 하는 것입니다. 그러나 한 `alloca` 함수 연결 되어야 합니다 및 r29 스택의 맨 아래를 가리켜야 합니다. 더 나은 레지스터 쌍-주소 지정-모드 검사를 허용 하려면 비휘발성 영역 로컬 영역 스택의 맨 위에 있는 놓이는 aave를 등록 합니다. 가장 효율적인 프롤로그 시퀀스의 몇 가지를 보여 주는 예제는 다음과 같습니다. 쉽게 구별할 수 있도록 캐시 효율 향상을 위해 모든 정식 프롤로그에서 호출 수신자 저장 레지스터를 저장 하는 순서는 "성장" 순서로 지정 됩니다. `#framesz` 아래 전체 스택 (alloca 영역 제외)의 크기를 나타냅니다. `#localsz` 및 `#outsz` 로컬 영역 크기를 나타냅니다 (저장을 포함 하 여 영역을 \<r29, lr > 쌍) 및 매개 변수 크기를 각각 나가는 합니다.

1. 연결, #localsz \<512 =

    ```asm
        stp    r19,r20,[sp,-96]!        // pre-indexed, save in 1st FP/INT pair
        stp    d8,d9,[sp,16]            // save in FP regs (optional)
        stp    r0,r1,[sp,32]            // home params (optional)
        stp    r2,r3,[sp, 48]
        stp    r4,r5,[sp,64]
        stp    r6,r7,[sp,72]
        stp    r29, lr, [sp, -#localsz]!    // save <r29,lr> at bottom of local area
        mov    r29,sp                   // r29 points to bottom of local
        sub    sp, #outsz               // (optional for #outsz != 0)
    ```

1. 연결 된, #localsz > 512

    ```asm
        stp    r19,r20,[sp,-96]!        // pre-indexed, save in 1st FP/INT pair
        stp    d8,d9,[sp,16]            // save in FP regs (optional)
        stp    r0,r1,[sp,32]            // home params (optional)
        stp    r2,r3,[sp, 48]
        stp    r4,r5,[sp,64]
        stp    r6,r7,[sp,72]
        sub    sp,#localsz+#outsz       // allocate remaining frame
        stp    r29, lr, [sp, #outsz]    // save <r29,lr> at bottom of local area
        add    r29,sp, #outsz           // setup r29 points to bottom of local area
    ```

1. 체인화, 리프 함수 (lr 저장 되지 않은)

    ```asm
        stp    r19,r20,[sp, -72]!       // pre-indexed, save in 1st FP/INT reg-pair
        stp    r21,r22,[sp, 16]
        str    r23 [sp,32]
        stp    d8,d9,[sp,40]            // save FP regs (optional)
        stp    d10,d11,[sp,56]
        sub    sp,#framesz-72           // allocate the remaining local area
    ```

   SP.에 따라 모든 지역에 액세스 하는 \<r29, lr > 이전 프레임을 가리킵니다. 프레임 크기에 대 한 \<512 =는 "sub sp,..." 최적화 될 수 있는 저장 regs 영역 스택의 맨 이동 합니다. 위의 다른 레이아웃을 사용 하 여 일치 하지 않습니다 하 고 저장 된 regs 쌍 regs 및 사전 및 사후 인덱싱된 오프셋된 주소 지정 모드에 대 한 범위의 참여의 단점은입니다.

1. 체인화, 비-리프 함수 (lr 저장 Int 영역에 저장 됩니다.)

    ```asm
        stp    r19,r20,[sp,-80]!        // pre-indexed, save in 1st FP/INT reg-pair
        stp    r21,r22,[sp,16]          // ...
        stp    r23, lr,[sp, 32]         // save last Int reg and lr
        stp    d8,d9,[sp, 48]           // save FP reg-pair (optional)
        stp    d10,d11,[sp,64]          // ...
        sub    sp,#framesz-80           // allocate the remaining local area
    ```

   짝수를 사용 하 여 Int 레지스터를 저장 또는

    ```asm
        stp    r19,r20,[sp,-72]!        // pre-indexed, save in 1st FP/INT reg-pair
        stp    r21,r22,[sp,16]          // ...
        str    lr,[sp, 32]              // save lr
        stp    d8,d9,[sp, 40]           // save FP reg-pair (optional)
        stp    d10,d11,[sp,56]          // ...
        sub    sp,#framesz-72           // allocate the remaining local area
    ```

   저장 r19만:

    ```asm
        sub    sp, sp, #16              // reg save area allocation*
        stp    r19,lr,[sp,0]            // save r19, lr
        sub    sp,#framesz-16           // allocate the remaining local area
    ```

   \* 영역 할당 저장 reg은 stp에 폴딩 되지 않습니다 미리 인덱싱된 reg lr stp 해제 코드를 사용 하 여 표현할 수 없기 때문에 합니다.

   SP.에 따라 모든 지역에 액세스 하는 \<r29 > 이전 프레임을 가리킵니다.

1. 연결, #framesz \<#outsz 512 = = 0

    ```asm
        stp    r29, lr, [sp, -#framesz]!    // pre-indexed, save <r29,lr>
        mov    r29,sp                       // r29 points to bottom of stack
        stp    r19,r20,[sp, #framesz -32]   // save INT pair
        stp    d8,d9,[sp, #framesz -16]     // save FP pair
    ```

   위의 #1 프롤로그를 비교 장점은 모든 등록 지침 저장 명령 할당 하나만 스택 직후 실행 될 준비가입니다. 따라서 명령 수준 병렬 처리를 방지 하는 sp에서 백신 종속 하지 않습니다.

1. 연결을 프레임 크기 > 512 (alloca 없이 함수에 대 한 선택 사항)

    ```asm
        stp    r29, lr, [sp, -80]!          // pre-indexed, save <r29,lr>
        stp    r19,r20,[sp,16]              // save in INT regs
        stp    r21,r22,[sp,32]              // ...
        stp    d8,d9,[sp,48]                // save in FP regs
        stp    d10,d11,[sp,64]
        mov    r29,sp                       // r29 points to top of local area
        sub    sp,#framesz-80               // allocate the remaining local area
    ```

   최적화를 위해 r29 "reg 쌍" 및 사전/사후-indexed 오프셋 모드 주소 지정에 대 한 더 나은 검사를 제공 하는 지역에서의 임의 위치에 배치할 수 있습니다. SP. 기반 프레임 포인터 아래 지역에 액세스할 수 있습니다.

1. 연결을 프레임 크기 > (4k, alloca(), 유무

    ```asm
        stp    r29, lr, [sp, -80]!          // pre-indexed, save <r29,lr>
        stp    r19,r20,[sp,16]              // save in INT regs
        stp    r21,r22,[sp,32]              // ...
        stp    d8,d9,[sp,48]                // save in FP regs
        stp    d10,d11,[sp,64]
        mov    r29,sp                       // r29 points to top of local area
        mov    r8, #framesz/16
        bl     chkstk
        sub    sp, r8*16                    // allocate remaining frame
                                            // end of prolog
        ...
        sp = alloca                         // more alloca() in body
        ...
                                            // beginning of epilog
        mov    sp,r29                       // sp points to top of local area
        ldp    d10,d11, [sp,64],
        ...
        ldp    r29, lr, [sp], -80           // post-indexed, reload <r29,lr>
    ```

## <a name="arm64-exception-handling-information"></a>ARM64 예외 처리 정보

### <a name="pdata-records"></a>.pdata 레코드

.Pdata 레코드는 PE 이진 파일에 모든 스택 조작 함수를 설명 하는 고정 길이 항목의 순서 있는 배열입니다. 구 "스택 조작" 신중 하 게 확인: 리프 함수 로컬 저장소가 필요 하지 않은 되었으며 저장 또는 복원할 비휘발성 레지스터에 필요 하지 않습니다는.pdata 레코드를 필요 하지 않습니다 이 공간 절약을 위해 명시적으로 생략 해야 합니다. 이러한 함수 중 하나에서 해제 하기만 하면 호출자에 게 위로 이동 하려면 LR에서 반환 주소를 가져올 수 있습니다.

ARM64 용 각.pdata 레코드는 길이가 8 바이트입니다. 각 함수의 32 비트 RVA를 잠시 뒤, 첫 번째 단어의 시작 레코드 위치의 일반 형식은 가변 길이.xdata 블록에 대 한 포인터 또는 정식 함수 해제 시퀀스를 설명 하는 압축 된 단어를 포함 합니다.

![.pdata 레코드 레이아웃](media/arm64-exception-handling-pdata-record.png ".pdata 레코드 레이아웃")

필드는 다음과 같습니다.

- **함수 시작 RVA** 는 함수 시작의 32 비트 RVA입니다.

- **플래그** 두 번째.pdata 단어의 나머지 30 비트를 해석 하는 방법을 나타내는 2 비트 필드입니다. 하는 경우 **플래그** 가 0 이면 나머지 비트는 **예외 정보 RVA** (하위 2 비트를 사용 하 여 암시적으로 0). 하는 경우 **플래그** 나머지 비트는 0이 아닌이 **압축 된 해제 데이터** 구조입니다.

- **예외 정보 RVA** .xdata 섹션에 저장 된 가변 길이 예외 정보 구조의 주소입니다. 이 데이터는 4비트 단위로 정렬되어야 합니다.

- **압축 해제 데이터** 정규형으로 간주 하는 함수에서 해제 하는 데 필요한 작업에 대 한 압축 된 설명입니다. 이 경우에는 .xdata 레코드가 필요하지 않습니다.

### <a name="xdata-records"></a>.xdata 레코드

압축된 해제 형식만으로는 함수 해제를 설명하는 데 부족한 경우에는 가변 길이 .xdata 레코드를 만들어야 합니다. 이 레코드의 주소는 .pdata 레코드의 두 번째 단어에 저장됩니다. .Xdata의 형식은 압축 된 가변 길이 단어 집합으로 다음과 같습니다.

![.xdata 레코드 레이아웃](media/arm64-exception-handling-xdata-record.png ".xdata 레코드 레이아웃")

이 데이터는 네 개의 섹션으로 나뉩니다.

1. 1 또는 2 word 헤더는 구조의 전체 크기를 설명 하 고 주요 함수 데이터를 제공 합니다. 두 번째 단어는 모두에 있는 합니다 **에필로그 수** 하 고 **코드 단어** 필드가 0으로 설정 됩니다. 다음은 헤더에 있는 비트 필드입니다.

   a. **함수 길이** 총 길이 (바이트)를 4로 나눈 값의 함수를 나타내는 18 비트 필드입니다. 함수 1m 보다 큰 경우 여러 pdata 및 xdata 레코드 함수를 설명 하기 위해 사용 되어야 합니다. 참조 된 [큰 함수](#large-functions) 대 한 자세한 내용은 섹션입니다.

   b. **Vers** 나머지 xdata의 버전을 설명 하는 2 비트 필드입니다. 이 문서의 작성 시점 현재 버전 0만 정의 됩니다 하 고 있으므로 1-3 값 허용 되지 않습니다.

   c. **X** 합니다 (1)의 존재 여부 (0) 예외 데이터를 나타내는 1 비트 필드입니다.

   d. **E** 은 1 비트 필드는 이상 (0) 단어 추가 범위를 요구 하는 대신 단일 에필로그는 (1) 헤더에 압축을 설명 하는 정보를 나타냅니다.

   e. **에필로그 수** 상태에 따라 두 가지 의미 있는 5 비트 필드가 **E** 비트:

      1. 하는 경우 **E** 0으로 설정 됩니다: 2 단원에서 설명한 예외 범위의 총 수를 지정 하는 것입니다. 31 개 이상의 범위 함수에 존재 하는 경우 해당 **코드 단어** 여 확장명 단어가 필요 함을 나타내기에 필드를 0으로 설정 해야 합니다.

      2. 하는 경우 **E** 및 에필로그만을 설명 하는 첫 번째 해제 코드의 인덱스를 지정 하는이 필드를 1로 설정 됩니다.

   f. **코드 단어** 4 단원의 해제 코드를 모두 포함 하는 데 필요한 32 비트 단어 수를 지정 하는 5 비트 필드입니다. 31 개 이상의 단어 필요한 경우 (즉, 둘 124 해제 코드 바이트), 여 확장명 단어가 필요 함을 나타내기에이 필드를 0으로 설정 해야 합니다.

   g. **에필로그 수를 확장** 하 고 **확장 코드 단어** 16 비트 및 8 비트 필드는 각각, 에필로그 많은 인코딩에 대 한 더 많은 공간을 제공 하는 또는 비정상적으로 많은 수의 해제 코드 단어입니다. 이러한 필드를 포함 하 여 확장명 단어가 있으면만 모두를 **에필로그 수** 하 고 **코드 단어** 첫 번째 헤더 단어의 필드는 0으로 설정 됩니다.

1. 예외 데이터 다음 경우 **에필로그 수** 0이 아닌, 단어에 하나로 압축 및 작은 시작 오프셋부터 순서 대로 저장 에필로그 범위에 대 한 정보의 목록입니다. 각 범위에는 다음 비트를 포함 합니다.

   a. **에필로그 시작 오프셋** 오프셋 (바이트)를 함수 시작에 상대적인 에필로그의 4로 나눈 값을 설명 하는 18 비트 필드

   b. **Res** 향후 확장에 대 한 예약 된 4 비트 필드입니다. 해당 값은 0이어야 합니다.

   c. **에필로그 시작 인덱스** 10 비트 (보다 더 많은 2 비트가 **확장 코드 단어**) 첫 번째 바이트 인덱스를 나타내는 필드는이 에필로그를 설명 하는 코드를 해제 합니다.

1. 에필로그 범위 목록에는 해제 코드를 포함 하는 바이트 배열을 상태가 되 면 후 이후 섹션에서 자세히 설명 합니다. 이 배열은 가장 가까운 전체 단어 경계 끝에 채워집니다. 바이트는 little endian 모드에서 직접 가져올 수 있도록 쉽게 little endian 순서로 저장됩니다.

1. 해제 코드 바이트 뒤에 마지막으로, (경우에 **X** 헤더에 대 한 비트가 1로 설정 된) 예외 처리기 정보가 제공 됩니다. 이 개로만 이루어진 **예외 처리기 RVA** 가변 길이 양의 예외 처리기에 필요한 데이터를 바로 뒤 자체 예외 처리기의 주소를 제공 합니다.

위의.xdata 레코드는 처음 8 바이트를 가져와는 (길이 뺀 값 뒤에 오는 가변 크기 예외 데이터의) 레코드의 전체 크기를 계산 하는 데 수 있도록 설계 되었습니다. 다음 코드 조각은 레코드 크기를 계산 합니다.

```cpp
ULONG ComputeXdataSize(PULONG *Xdata)
{
    ULONG EpilogScopes;
    ULONG Size;
    ULONG UnwindWords;

    if ((Xdata[0] >> 27) != 0) {
        Size = 4;
        EpilogScopes = (Xdata[0] >> 22) & 0x1f;
        UnwindWords = (Xdata[0] >> 27) & 0x0f;
    } else {
        Size = 8;
        EpilogScopes = Xdata[1] & 0xffff;
        UnwindWords = (Xdata[1] >> 16) & 0xff;
    }

    Size += 4 * EpilogScopes;
    Size += 4 * UnwindWords;
    if (Xdata[0] & (1 << 20)) {
        Size += 4;        // exception handler RVA
    }
    return Size;
}
```

프롤로그와 각 에필로그에 해제 코드로 자체 인덱스가 있지만 테이블 간의 공유 하는 가능 (완전히 흥미롭지만) 유의 해야 하는 공유할 수 있습니다 (아래 부록 A에서에서 예 2 참조)과 동일한 코드입니다. 컴파일러 작성자 최적화 해야이 사례에 대 한 특히 지정할 수 있는 가장 큰 인덱스는 255 이므로 특정 함수에 대 한 해제 코드의 총 수를 제한 합니다.

### <a name="unwind-codes"></a>해제 코드

해제 코드의 배열에 있는 작업을 취소할 필요가 순서 대로 프롤로그의 결과 실행 취소 하는 방법을 정확히 설명 하는 시퀀스 풀입니다. 해제 코드 바이트 문자열로 인코딩된 미니 명령 집합으로 생각할 수 있습니다. 실행 완료 되 면 호출 함수로 반환 주소 lr 레지스터에 포함 되며 모든 비휘발성 레지스터는이 함수가 호출 시 해당 값으로 복원 됩니다.

예외는 함수 본문 내에서 (및 프롤로그 또는 에필로그 모든 사용 되지 않습니다)만 발생 하도록 보장 된다면, 필요한으로 단일 순서를 것입니다. 그러나 Windows 해제 모델을 부분적으로 실행 된 프롤로그 또는 에필로그 내에서 해제할 수는 필요 합니다. 이 요구를 수용 하기 위해 프롤로그 및 에필로그의 각 관련 opcode에 1:1 명확 하 게 매핑하는 해제 코드를 신중 하 게 설계. 여기에는 다음과 같은 의미가 있습니다.

1. 해제 코드 수를 세어 프롤로그 및 에필로그의 길이 계산 하는 것이 같습니다.

1. 에필로그 범위를 시작 또는 끝 명령의 수를 계산, 해당 해제 코드 수를 건너뛰고 나머지 부분적으로 실행을 완료 하는 순서를 실행할 수 있기 에필로그가 수행 중이 해제 합니다.

1. 프롤로그 종료 되기 전에 명령의 수를 계산 하 여 해당 해제 코드 수를 건너뛰고 나머지 실행이 완료 된 프롤로그의 부분에만 실행 취소 하는 순서를 실행 하는 것이 같습니다.

해제 코드는 아래 표에 따라 인코딩됩니다. 모든 해제 코드는 엄청난 스택을 할당 하는 것을 제외 하 고는 단일/더블 바이트입니다. 완전히 21 해제 코드가 있습니다. 각 해제 코드 맵 하나만 명령 프롤로그/에필로그 부분적으로 실행 된 프롤로그 및 에필로그 해제를 허용 하기 위해입니다.

|해제 코드|Bits 및 해석|
|-|-|
|`alloc_s`|000xxxxx: 크기를 사용 하 여 작은 스택 할당 \< 512 (2 ^5 * 16).|
|`save_r19r20_x`|    001zzzzz: 저장 \<r19, r20 > 쌍 [sp-#Z * 8]!, 미리 인덱싱된 오프셋 >-248 = |
|`save_fplr`|        01zzzzzz: 저장할 \<r29, lr > 쌍에서 [sp + #Z * 8], 오프셋 \<504 =. |
|`save_fplr_x`|        10zzzzzz: 저장 \<r29, lr > 쌍에서 [sp-(#Z + 1) * 8]!, 미리 인덱싱된 오프셋 >-512 = |
|`alloc_m`|        11000xxx'xxxxxxxx: 크기를 사용 하 여 큰 스택 할당 \< 16k (2 ^11 * 16). |
|`save_regp`|        110010xx'xxzzzzzz: r(19+#X) 쌍에 저장 [sp + #Z * 8], 오프셋 \<504 = |
|`save_regp_x`|        110011xx'xxzzzzzz:에서 쌍 r(19+#X) 저장 [sp-(#Z + 1) * 8]!, 미리 인덱싱된 오프셋 >-512 = |
|`save_reg`|        110100xx'xxzzzzzz:에서 reg r(19+#X) 저장 [sp + #Z * 8], 오프셋 \<504 = |
|`save_reg_x`|        1101010 x'xxxzzzzz:에서 reg r(19+#X) 저장 [sp-(#Z + 1) * 8]!, 미리 인덱싱된 오프셋 >-256 = |
|`save_lrpair`|         1101011 x'xxzzzzzz: 쌍을 저장할 \<r19 + 2 *#X, lr >에서 [sp + #Z*8], 오프셋 \<504 = |
|`save_fregp`|        1101100 x'xxzzzzzz:에서 쌍 d(8+#X) 저장 [sp + #Z * 8], 오프셋 \<504 = |
|`save_fregp_x`|        1101101 x'xxzzzzzz:에서 쌍 d(8+#X) 저장 [sp-(#Z + 1) * 8]!, 미리 인덱싱된 오프셋 >-512 = |
|`save_freg`|        1101110 x'xxzzzzzz:에서 reg d(8+#X) 저장 [sp + #Z * 8], 오프셋 \<504 = |
|`save_freg_x`|        11011110' xxxzzzzz:에서 reg d(8+#X) 저장 [sp-(#Z + 1) * 8]!, 미리 인덱싱된 오프셋 >-256 = |
|`alloc_l`|         11100000' xxxxxxxx 'xxxxxxxx' xxxxxxxx: 크기를 사용 하 여 큰 스택 할당 \< 256m (2 ^24 * 16) |
|`set_fp`|        11100001: r29 설정: 사용 하 여: mov r29 sp |
|`add_fp`|        11100010' xxxxxxxx: 사용 하 여 r29 설정: r29, sp, #x 추가 * 8 |
|`nop`|            11100011: 없습니다 해제 작업이 필요 합니다. |
|`end`|            11100100: 해제 코드의 끝입니다. 의미 에필로그에 만료 됩니다. |
|`end_c`|        11100101: 현재 연결 된 범위에서 해제 코드의 끝입니다. |
|`save_next`|        11100110: 다음 비휘발성 Int를 저장 하거나 FP 쌍을 등록 합니다. |
|`arithmetic(add)`|    11100111'000zxxxx: add cookie reg(z) to lr (0=x28, 1=sp); add lr, lr, reg(z) |
|`arithmetic(sub)`|    11100111'001zxxxx: sub cookie reg(z) from lr (0=x28, 1=sp); sub lr, lr, reg(z) |
|`arithmetic(eor)`|    11100111'010zxxxx: eor lr with cookie reg(z) (0=x28, 1=sp); eor lr, lr, reg(z) |
|`arithmetic(rol)`|    11100111' 0110xxxx: 쿠키 reg (x28);를 사용 하 여 lr의 시뮬레이션 된 rol xip0 neg x28; = lr ror xip0 |
|`arithmetic(ror)`|    11100111'100zxxxx: ror lr with cookie reg(z) (0=x28, 1=sp); ror lr, lr, reg(z) |
| |            11100111: xxxz----: ---- reserved |
| |              11101xxx: asm 루틴에 대해서만 생성 사용자 지정 스택 사례에 대 한 예약 |
| |              11101001: 사용자 지정 MSFT_OP_TRAP_FRAME 스택 |
| |              11101010: 사용자 지정 MSFT_OP_MACHINE_FRAME 스택 |
| |              11101011: 사용자 지정 MSFT_OP_CONTEXT 스택 |
| |              1111xxxx: reserved |

여러 바이트를 포함 하는 큰 값을 사용 하 여 지침, 가장 중요 한 비트가 먼저 저장 됩니다. 위의 해제 코드는 코드의 첫 번째 바이트를 단순히 조회 하 여 해제 코드의 바이트의 총 크기를 알 수 있기 되도록 설계 되었습니다. 각 해제 코드 프롤로그/에필로그의 명령에 매핑된 정확히는 프롤로그 또는 에필로그의 크기를 계산을 수행 해야 하는 조회 테이블 또는 유사한 장치를 사용 하 여 확인을 끝으로 시퀀스의 시작 부분에서 설명 시간 cor 응답 opcode 값이 있습니다.

프롤로그의 오프셋 주소 인덱싱된 후에 허용 되지 않습니다. 모든 오프셋된 범위 (#Z) 제외 하 고 STP/STR 주소 지정의 인코딩과 일치 `save_r19r20_x` 는 248는 충분 한 모든 영역 (10 Int 레지스터 + 8 FP 레지스터 + 8 입력된 레지스터)를 저장 합니다.

`save_next` Int에 대 한 저장을 수행 하거나 FP volatile 쌍을 등록 해야 합니다. `save_regp`, `save_regp_x`, `save_fregp`, `save_fregp_x`, `save_r19r20_x`, 또는 다른 `save_next`합니다. 다음으로 16 바이트 슬롯에서 다음 레지스터 쌍 "증가" 순서로 저장 됩니다. `save-next` 다음을 `save_next` 마지막 Int 레지스터 쌍 첫 번째 FP 레지스터 쌍 참조를 나타내는입니다.

없기 때문에 일반 크기 반환와 동일한 지침을 이동의 구분을 하지 않아도 `end` 마무리 호출 시나리오에 대 한 코드를 해제 합니다.

`end_c` 최적화를 위해 연속 되지 않은 함수 조각을 처리 하도록 설계 되었습니다. A `end_c` 현재 범위에서 해제 코드의 끝을 나타내는 뒤에 야를 실시간으로 종료 하는 해제 코드의 다른 계열 `end`합니다. 해제 코드 간의 `end_c` 고 `end` 부모 영역 ("가상" 프롤로그)의 프롤로그 연산을 나타냅니다.  자세한 내용 및 예제는 아래 섹션에 설명 되어 있습니다.

### <a name="packed-unwind-data"></a>압축 된 해제 데이터

함수 아래에 설명 된 정규 형식이 해당 프롤로그와 에필로그 따라 압축 해제에 대 한 데이터를 사용할 수 있습니다, 그리고 해제 데이터는.xdata 레코드에 대 한 필요성을 완전히 제거 하 고 현저 하 게 제공 하는 비용을 절감 합니다. 정식 프롤로그 및 에필로그는 예외 처리기가 필요 하지는 않으며 표준 순서로 설정 및 정리 작업을 수행 하는 단순 함수의 일반적인 요구 사항을 충족 하도록 설계 되었습니다.

압축된.pdata 레코드의 형식은 다음과 같은 데이터가 해제:

![.pdata 레코드 압축 된 해제 데이터](media/arm64-exception-handling-packed-unwind-data.png ".pdata 레코드 압축 된 해제 데이터")

필드는 다음과 같습니다.

- **함수 시작 RVA** 는 함수 시작의 32 비트 RVA입니다.
- **플래그** 의미를 사용 하 여 위에서 설명한 대로 2 비트 필드입니다.
  - 00 = 압축 된 해제 데이터 사용 되지 않습니다. 아래 나머지 비트.xdata 레코드를 가리키도록
  - 01 = 압축 된 해제 데이터를 단일 프롤로그 및 에필로그 시작 및 끝 범위를 사용 하 여 아래 설명 된 대로 사용
  - 10 = 압축 된 해제 데이터 모든 프롤로그 및 에필로그; 없이 코드에 대 한 아래 설명 된 대로 사용 분리 된 함수 세그먼트를 설명 하는 데 유용 합니다.
  - 11 = 예약 되었습니다.
- **함수 길이** 길이 (바이트)를 4로 나눈 값의 전체 함수를 제공 하는 11 비트 필드입니다. 함수 8k 보다 크면 전체.xdata 레코드를 대신 사용 되어야 합니다.
- **프레임 크기가** 16로 나눈 값이 함수에 대해 할당 된 스택 바이트 수를 나타내는 9 비트 필드입니다. 스택의 (8k-16) 바이트 보다 큰 할당 하는 함수는 전체.xdata 레코드를 사용 해야 합니다. 로컬 변수 영역에서 동적 할당 영역을 제외한 매개 변수 영역, 호출 수신자 저장 Int 및 FP 영역 및 홈 매개 변수 영역을 나가는 포함 됩니다.
- **CR** 함수에 반환 하는 링크를 프레임 체인을 설정 하는 추가 명령을 포함 하는지 여부를 나타내는 2 비트 플래그:
  - 00 = 체인화 함수 \<r29, lr > 쌍 스택에 저장 되지 않습니다.
  - 01 = 체인화 함수 \<lr > 스택에 저장 됩니다
  - 10 = 예약 되었습니다.
  - 11 = 연결 된 함수 프롤로그/에필로그에는 저장소/로드 쌍 명령을 사용 하는 \<r29, lr >
- **H** 함수의 처음에 저장 하 여 함수에 정수 매개 변수가 호 밍 여부를 나타내는 1 비트 플래그 (r0-r7)에 등록 됩니다. (0 = 1 레지스터를 홈지 않습니다 집 레지스터 =) 합니다.
- **RegI** 정식 스택 위치에 저장 된 비휘발성 INT 레지스터 (r19 r28)의 수를 나타내는 4 비트 필드입니다.
- **RegF** 정식 스택 위치에 저장 된 비휘발성 FP 레지스터 (d8-d15)의 수를 나타내는 3 비트 필드입니다. (0 = 없음 FP 레지스터 저장은 m > 0: m + 1 FP 레지스터에 저장 됩니다). FP 레지스터를 압축 해제 하나만 저장 하는 함수에 대 한 데이터를 적용할 수 없습니다.

위의 섹션에서 1, 2 (하지 않고 나가는 매개 변수 영역), 3 및 4 범주에 속하는 정식 프롤로그는 압축 된 해제 형식으로 나타낼 수 있습니다.  에필로그 정식 함수에 따라 매우 유사한 폼에 대 한 제외 **H** 해도 아무런 영향이 없습니다는 `set_fp` 명령은 생략 하 고 에필로그의 각 단계에 대 한 지침 뿐만 아니라 단계 순서가 바뀝니다. 압축된 xdata 알고리즘을 다음 표에서 자세히 설명 하는 이러한 단계를 따릅니다.

0 단계: 각 영역의 크기를 사전 계산을 수행 합니다.

1단계: Int 호출 수신자 저장 레지스터를 저장 합니다.

2단계: 이 단계는 초기 섹션의 4 형식에 대 한 특정입니다. lr은 Int 영역의 끝에 저장 됩니다.

3단계: FP 호출 수신자 저장 레지스터를 저장 합니다.

4단계: 홈 매개 변수 영역의 입력된 인수를 저장 합니다.

5단계: 로컬 영역을 비롯 한 나머지 스택에 할당 \<r29, lr > 쌍 및 나가는 매개 변수 영역입니다. 5a 정식 유형 1에 해당합니다. 5b 5c와 정식 유형 2에 대 한입니다. 5d 및 5e 두 유형 3에 대 한 4를 입력 합니다.

단계 #|플래그 값|# 명령|Opcode|해제 코드
-|-|-|-|-
0|||`#intsz = RegI * 8;`<br/>`if (CR==01) #intsz += 8; // lr`<br/>`#fpsz = RegF * 8;`<br/>`if(RegF) #fpsz += 8;`<br/>`#savsz=((#intsz+#fpsz+8*H)+0xf)&~0xf)`<br/>`#locsz = #famsz - #savsz`|
1|0 < **RegI** <= 10|RegI / 2 + **RegI** %2|`stp r19,r20,[sp,#savsz]!`<br/>`stp r21,r22,[sp,16]`<br/>`...`|`save_regp_x`<br/>`save_regp`<br/>`...`
2|**CR**==01*|1|`str lr,[sp, #intsz-8]`\*|`save_reg`
3|0 < **RegF** <=7|(RegF + 1) / 2 +<br/>(RegF + 1) % 2)|`stp d8,d9,[sp, #intsz]`\*\*<br/>`stp d10,d11,[sp, #intsz+16]`<br/>`...`<br/>`str d(8+RegF),[sp, #intsz+#fpsz-8]`|`save_fregp`<br/>`...`<br/>`save_freg`
4|**H** == 1|4|`stp r0,r1,[sp, #intsz+#fpsz]`<br/>`stp r2,r3,[sp, #intsz+#fpsz+16]`<br/>`stp r4,r5,[sp, #intsz+#fpsz+32]`<br/>`stp r6,r7,[sp, #intsz+#fpsz+48]`|`nop`<br/>`nop`<br/>`nop`<br/>`nop`
5a|**CR** == 11 && #locsz<br/> <= 512|2|`stp r29,lr,[sp,-#locsz]!`<br/>`mov r29,sp`\*\*\*|`save_fplr_x`<br/>`set_fp`
5b|**CR** == 11 &&<br/>512 < #locsz <= 4088|3|`sub sp,sp, #locsz`<br/>`stp r29,lr,[sp,0]`<br/>`add r29, sp, 0`|`alloc_m`<br/>`save_fplr`<br/>`set_fp`
5c|**CR** == 11 && #locsz > 4088|4|`sub sp,sp,4088`<br/>`sub sp,sp, (#locsz-4088)`<br/>`stp r29,lr,[sp,0]`<br/>`add r29, sp, 0`|`alloc_m`<br/>`alloc_s`/`alloc_m`<br/>`save_fplr`<br/>`set_fp`
5d|(**CR** == 00 \|\| **CR**==01) &&<br/>#locsz <= 4088|1|`sub sp,sp, #locsz`|`alloc_s`/`alloc_m`
5e|(**CR** == 00 \|\| **CR**==01) &&<br/>#locsz > 4088|2|`sub sp,sp,4088`<br/>`sub sp,sp, (#locsz-4088)`|`alloc_m`<br/>`alloc_s`/`alloc_m`

\* 하는 경우 **CR** 01 = = 및 **RegI** 홀수가, 2 단계 및 1 단계의 마지막 save_rep 하나 save_regp에 병합 됩니다.

\*\* 하는 경우 **RegI** == **CR** = = 0, 및 **RegF** ! = 0, 첫 번째 stp 부동 소수점있지 않습니다는 사전 감소 합니다.

\*\*\* 에 해당 하 없습니다 명령 `mov r29, sp` 에필로그에 합니다. 함수를 사용할 수 없습니다 r29에서 sp 복원을 요구 하는 경우 압축 된 해제 데이터입니다.

### <a name="unwinding-partial-prologs-and-epilogs"></a>해제 부분 프롤로그 및 에필로그

가장 일반적인 해제 상황은 하나는 예외 또는 통화를 프롤로그 및 모든 에필로그 벗어난 함수 본문에 발생 합니다. 이 경우 해제 간단: 해제기 단순히 인덱스 0부터 시작 하 고 종료 opcode가 검색 될 때까지 계속 해제 배열의 코드 실행을 시작 합니다.

더 프롤로그 또는 에필로그를 실행 하는 동안 예외 나 인터럽트가 발생 하는 위치에서는 올바르게 해제 하는 것이 어렵습니다. 이러한 상황에서 스택 프레임을 부분적 으로만 생성 및 정확히 어떤 저희 올바르게 실행 취소 하기 위해 결정을 합니다.

예를 들어이 프롤로그 및 에필로그 시퀀스를 수행 합니다.

```asm
0000:    stp    r29, lr, [sp, -256]!        // save_fplr_x  256 (pre-indexed store)
0004:    stp    d8,d9,[sp,224]              // save_fregp 0, 224
0008:    stp    r19,r20,[sp,240]            // save_regp 0, 240
000c:    mov    r29,sp                      // set_fp
         ...
0100:    mov    sp,r29                      // set_fp
0104:    ldp    r19,r20,[sp,240]            // save_regp 0, 240
0108:    ldp    d8,d9,[sp,224]              // save_fregp 0, 224
010c:    ldp    r29, lr, [sp, -256]!        // save_fplr_x  256 (post-indexed load)
0110:    ret     lr                         // end
```

각 opcode 옆에 있는이 작업을 설명 하는 적절 한 해제 코드입니다. 먼저 참고 점 일련의 프롤로그에 대 한 해제 코드는 에필로그 (에필로그의 최종 명령은 제외)에 대 한 해제 코드의 정확한 미러 이미지입니다. 일반적인 상황에서는 이며이 따라서 해제 프롤로그에 대 한 코드 항상 프롤로그의 실행 순서를 역순으로 저장 될 간주 됩니다.

따라서 프롤로그와 에필로그를 실행 하는 것에 대 한 왼쪽 공통 해제 코드 집합을 사용 하 여:

`set_fp`, `save_regp 0,240`, `save_fregp,0,224`, `save_fplr_x_256`, `end`

부터 시작 하 여 더 간단 이므로 일반 순서, 에필로그에서는 에필로그 (시작 하는 함수에서 0x100 오프셋) 내의 오프셋 0에서 예상할 수는 전체 해제 시퀀스를 실행 하려면 정리를 아직 수행 하는 대로 합니다. 발견 되는 경우 직접 명령 하나 (오프셋 2 에필로그에), 첫 번째 해제 코드를 건너뛰어 해제 성공적으로 했습니다. 이 상황을 일반화 하 고 opcode 간에 1:1 매핑이 가정 되는 해제 코드는 명령 n 에필로그에 해제 됩니다 것를 하는 경우는 첫 번째 n 해제 코드를 건너뛸 하 고 여기에서의 실행을 시작할 상태 수 것입니다.

그런데 유사한 논리 작동 하는지 프롤로그에 대 한 제외 하 고 반대 방향. 프롤로그의 오프셋 0에서에서 해제 된 것을 하는 경우 아무 것도 실행 하려고 합니다. 2, 오프셋에서 위치에서는 하는 경우, 하나의 명령에는 다음 끝 에서부터 해제 시퀀스 한 해제 코드 실행을 시작 하려고 (기억에 코드를 역순으로 저장 됩니다). 및 여기 너무 우리를 일반화할 수는 프롤로그의 명령 n에서 해제 됩니다 것을 하는 경우 코드 목록 끝에서 n 해제 코드 실행을 시작 해야 했습니다.

이제 것 항상 프롤로그 및 에필로그 코드를 정확히 일치 하는 경우입니다. 따라서 해제 배열은 여러 코드 시퀀스를 포함 해야 합니다. 코드 처리를 시작할 위치의 오프셋을 확인 하려면 다음 논리를 사용 합니다.

1. 내에서 해제 하는 경우 함수 본문 단순히 인덱스 0에서 해제 코드의 실행을 시작할 및이 "end" opcode 도달 될 때까지 계속 합니다.

1. 에필로그 내에서 해제를 시작 지점으로 사용 하 여 에필로그 별 시작 인덱스 에필로그 범위를 사용 하 여 제공 합니다. 에필로그의 시작 부분에서 바이트 수에 해당 PC가 계산 합니다. 다음은 이미 실행 명령의 모든 처리 될 때까지 해제 코드를 건너뛰는 중 해제 코드를 통해 앞으로 이동 합니다. 해당 시점 에서부터 실행 합니다.

1. 프롤로그 내에서 해제를 하는 경우 인덱스 0을 시작 지점으로 사용 합니다. 프롤로그의 끝에서 바이트 수에 해당 PC가 계산를 시퀀스에서 프롤로그 코드의 길이 계산 합니다. 다음은 아직 실행 되지 않음 지침의 모든 처리 될 때까지 해제 코드를 건너뛰는 중 해제 코드를 통해 앞으로 이동 합니다. 해당 시점 에서부터 실행 합니다.

결과적으로 이러한 규칙의 프롤로그 해제 코드 여야 배열의 첫 번째 및 본문 내에서 해제의 경우 일반에서 해제를 사용 하는 코드 이기도 합니다. 모든 에필로그 별 코드 시퀀스 바로 뒤에 따라야 합니다.

### <a name="function-fragments"></a>함수 조각

코드 최적화 목적 및 기타 이유로 함수 (지역) 분리 된 조각으로 분할 하는 것이 좋습니다 수도 있습니다. 각 결과 함수 조각 필요한 자체 별도.pdata (및.xdata)이 완료 되 면 레코드입니다.

자체 프롤로그에 있는 분리 된 보조 조각에 대해 스택 조정이 없음을 해당 프롤로그에서 수행 되도록 예상 됩니다. 모든 보조 복제본에 필요한 공간을 스택 지역 해당 부모 영역 (또는 호출된 호스트 지역)가 미리 할당 해야 합니다. 이렇게 하면 스택 포인터 조작이 엄격 하 게 함수의 원래 프롤로그에 있습니다.

함수 조각의 일반적인 사례는 "코드 분리" 해당 컴파일러를 사용 하 여 해당 호스트 함수에서 코드 영역을 이동할 수 있습니다. 코드 분리 하 여 발생 될 수 있습니다 하는 세 가지 예외적인 경우가 있습니다.

#### <a name="example"></a>예제:

- (영역 1: 시작)

    ```asm
        stp     r29, lr, [sp, -256]!    // save_fplr_x  256 (pre-indexed store)
        stp     r19,r20,[sp,240]        // save_regp 0, 240
        mov     r29,sp                  // set_fp
        ...
    ```

- (영역 1: 끝)
- (영역 3: 시작)

    ```asm
        ...
    ```

- (영역 3: 끝)
- (영역 2: 시작)

    ```asm
    ...
        mov     sp,r29                  // set_fp
        ldp     r19,r20,[sp,240]        // save_regp 0, 240
        ldp     r29, lr, [sp, -256]!    // save_fplr_x  256 (post-indexed load)
        ret     lr                      // end
    ```

- (영역 2: 끝)

1. 프롤로그만 (영역 1: 모든 에필로그가 별도 지역에 있는):

   프롤로그만 설명 해야 합니다. 이 압축.pdata 형식으로 나타낼 수 없습니다. 전체.xdata 경우에서 에필로그 수를 설정 하 여 나타낼 수 있습니다 = 0. 위의 예에서 지역 1을 참조 하세요.

   해제 코드: `set_fp`, `save_regp 0,240`를 `save_fplr_x_256`, `end`합니다.

1. 에필로그만 (영역 2: 프롤로그는 호스트 지역)

   이 영역으로 이동 시간 컨트롤에 의해 모든 프롤로그 코드 실행 된 것으로 가정 합니다. 부분 해제와 일반 함수와 똑같은 에필로그에서 발생할 수 있습니다. 이 유형의 영역 압축.pdata로 나타낼 수 없습니다. 전체 xdata 레코드의 묶은 "가상" 프롤로그를 사용 하 여 인코드할 수 있습니다는 `end_c` 고 `end` 코드 쌍을 해제 합니다.  앞에 오는 `end_c` 프롤로그의 크기는 0을 나타냅니다. 에필로그 시작 인덱스는 단일 에필로그 요소의 `set_fp`합니다.

   해제 코드 2 영역에 대 한: `end_c`, `set_fp`, `save_regp 0,240`합니다 `save_fplr_x_256`, `end`합니다.

1. 프롤로그 또는 에필로그 없음 (영역 3: 프롤로그 및 모든 에필로그는 다른 조각에).

   압축.pdata 형식 플래그를 설정를 통해 적용할 수 = 10입니다. 전체.xdata 레코드를 에필로그 수를 사용 하 여 = 1입니다. 해제 코드는 위의 2 영역에 대 한 것과 동일 하지만 에필로그 시작 인덱스 가리킵니다 `end_c`합니다. 코드의이 영역에서 부분 해제 되지 발생 합니다.

함수 조각의 더 복잡 한 경우 다른 함수 진입점 프롤로그 외부에서 될 때까지 일부 호출 수신자 저장 레지스터 저장을 지연 하도록 선택할 수 "는 컴파일러를 사용 하 여" 래핑 축소 됩니다.

- (영역 1: 시작)

    ```asm
        stp     r29, lr, [sp, -256]!    // save_fplr_x  256 (pre-indexed store)
        stp     r19,r20,[sp,240]        // save_regp 0, 240
        mov     r29,sp                  // set_fp
        ...
    ```

- (영역 2: 시작)

    ```asm
        stp     r21,r22,[sp,224]        // save_regp 2, 224
        ...
        ldp     r21,r22,[sp,224]        // save_regp 2, 224
    ```

- (영역 2: 끝)

    ```asm
        ...
        mov     sp,r29                  // set_fp
        ldp     r19,r20,[sp,240]        // save_regp 0, 240
        ldp     r29, lr, [sp, -256]!    // save_fplr_x  256 (post-indexed load)
        ret     lr                      // end
    ```

- (영역 1: 끝)

영역 1의 프롤로그에 스택 공간이 미리 할당 됩니다. 참고 2 해당 지역 코딩 하는 경우에 동일한 해제 해야 합니다. 해당 호스트 함수 외부로 이동 됩니다.

영역 1: `set_fp`, `save_regp 0,240`를 `save_fplr_x_256`를 `end` 가리키는 에필로그 시작 인덱스를 사용 하 여 `set_fp` 일반적으로 합니다.

영역 2: `save_regp 2, 224`, `end_c`, `set_fp`, `save_regp 0,240`합니다 `save_fplr_x_256`, `end`합니다. 에필로그 시작 인덱스를 먼저 해제 코드 가리키는 `save_regp 2, 224`합니다.

### <a name="large-functions"></a>큰 함수

조각은.xdata 헤더의 비트 필드에 따른 1백만 개 제한 보다 큰 함수를 설명 하기 위해 활용할 수 있습니다. 다음과 같이 매우 큰 함수를 설명 하기 위해 단순히 1백만 개 더 작은 조각으로 나눌 수 해야 합니다. 각 조각은 에필로그를 여러 부분으로 분할 하지 않도록 조정 되어야 합니다.

함수의 첫 조각에만 프롤로그;에 포함 됩니다. 나머지 모든 조각은 프롤로그 없는 것으로 표시 됩니다. 에필로그 있는 개수에 따라 각 조각은 에필로그를 0 개 이상의 포함할 수 있습니다. 조각의 각 에필로그 범위 시작 함수 시작과 조각 부분에 상대적인 시작 오프셋을 지정 하는지 염두에 두어야 합니다.

조각 없습니다 프롤로그 및 에필로그 없습니다 있으면 계속 필요는 자체.pdata (및.xdata) 레코드를 함수의 본문 내에서 해제 하는 방법에 설명 합니다.

## <a name="examples"></a>예제

### <a name="example-1-frame-chained-compact-form"></a>예제 1: 프레임 체인, compact 형식

```asm
|Foo|     PROC
|$LN19|
    str     x19,[sp,#-0x10]!        // save_reg_x
    sub     sp,sp,#0x810            // alloc_m
    stp     fp,lr,[sp]              // save_fplr
    mov     fp,sp                   // set_fp
                                    //  end of prolog
    ...

|$pdata$Foo|
    DCD     imagerel     |$LN19|
    DCD     0x416101ed
    ;Flags[SingleProEpi] functionLength[492] RegF[0] RegI[1] H[0] frameChainReturn[Chained] frameSize[2080]
```

### <a name="example-2-frame-chained-full-form-with-mirror-prolog--epilog"></a>예제 2: 프레임 체인, 미러 프롤로그 및 에필로그를 사용 하 여 전체 형식

```asm
|Bar|     PROC
|$LN19|
    stp     x19,x20,[sp,#-0x10]!    // save_regp_x
    stp     fp,lr,[sp,#-0x90]!      // save_fplr_x
    mov     fp,sp                   // set_fp
                                    // end of prolog
    ...
                                    // begin of epilog, a mirror sequence of Prolog
    mov     sp,fp
    ldp     fp,lr,[sp],#0x90
    ldp     x19,x20,[sp],#0x10
    ret     lr

|$pdata$Bar|
    DCD     imagerel     |$LN19|
    DCD     imagerel     |$unwind$cse2|
|$unwind$Bar|
    DCD     0x1040003d
    DCD     0x1000038
    DCD     0xe42291e1
    DCD     0xe42291e1
    ;Code Words[2], Epilog Count[1], E[0], X[0], Function Length[6660]
    ;Epilog Start Index[0], Epilog Start Offset[56]
    ;set_fp
    ;save_fplr_x
    ;save_r19r20_x
    ;end
```

프롤로그 해제 코드의 순서를 가리키는 EpilogStart 인덱스 [0] 참고 합니다.

### <a name="example-3-variadic-unchained-function"></a>예제 3: Variadic 체인화 함수

```asm
|Delegate| PROC
|$LN4|
    sub     sp,sp,#0x50
    stp     x19,lr,[sp]
    stp     x0,x1,[sp,#0x10]        // save incoming register to home area
    stp     x2,x3,[sp,#0x20]        // ...
    stp     x4,x5,[sp,#0x30]
    stp     x6,x7,[sp,#0x40]        // end of prolog
    ...
    ldp     x19,lr,[sp]             // beginning of epilog
    add     sp,sp,#0x50
    ret     lr

    AREA    |.pdata|, PDATA
|$pdata$Delegate|
    DCD     imagerel |$LN4|
    DCD     imagerel |$unwind$Delegate|

    AREA    |.xdata|, DATA
|$unwind$Delegate|
    DCD     0x18400012
    DCD     0x200000f
    DCD     0xe3e3e3e3
    DCD     0xe40500d6
    DCD     0xe40500d6
    ;Code Words[3], Epilog Count[1], E[0], X[0], Function Length[18]
    ;Epilog Start Index[4], Epilog Start Offset[15]
    ;nop        // nop for saving in home area
    ;nop        // ditto
    ;nop        // ditto
    ;nop        // ditto
    ;save_lrpair
    ;alloc_s
    ;end
```

참고: EpilogStart 인덱스 [4] 프롤로그 해제 코드 (부분적으로 다시 사용할 수 있도록 해제 배열)의 중간을 가리킵니다.

## <a name="see-also"></a>참고자료

[ARM64 ABI 규칙 개요](arm64-windows-abi-conventions.md)<br/>
[ARM 예외 처리](arm-exception-handling.md)
