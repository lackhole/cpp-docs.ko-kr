---
title: x64 예외 처리
ms.date: 10/14/2019
helpviewer_keywords:
- C++ exception handling, x64
- exception handling, x64
ms.assetid: 41fecd2d-3717-4643-b21c-65dcd2f18c93
ms.openlocfilehash: eff4f1a22512b597b5479dbcaabcc9d5fc93c940
ms.sourcegitcommit: 069e3833bd821e7d64f5c98d0ea41fc0c5d22e53
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2019
ms.locfileid: "74303207"
---
# <a name="x64-exception-handling"></a>x64 예외 처리

X64에서 구조화 된 예외 처리 및 C++ 예외 처리 코딩 규칙 및 동작에 대 한 개요입니다. 예외 처리에 대 한 일반적인 내용은 [시각적 개체 C++의 예외 처리 ](../cpp/exception-handling-in-visual-cpp.md)를 참조 하세요.

## <a name="unwind-data-for-exception-handling-debugger-support"></a>예외 처리를 위한 해제 데이터, 디버거 지원

예외 처리 및 디버깅 지원에는 몇 가지 데이터 구조가 필요 합니다.

### <a name="struct-runtime_function"></a>구조체 RUNTIME_FUNCTION

테이블 기반 예외 처리에는 스택 공간을 할당 하거나 다른 함수 (예: 리프가 아닌 함수)를 호출 하는 모든 함수에 대 한 테이블 항목이 필요 합니다. 함수 테이블 항목의 형식은 다음과 같습니다.

|||
|-|-|
|ULONG|함수 시작 주소|
|ULONG|함수 끝 주소|
|ULONG|해제 정보 주소|

RUNTIME_FUNCTION 구조는 메모리에서 DWORD로 정렬 되어야 합니다. 모든 주소는 이미지를 기준으로 합니다. 즉, 함수 테이블 항목을 포함 하는 이미지의 시작 주소에서 32 비트 오프셋입니다. 이러한 항목은 정렬 되어 PE32 + 이미지의 .pdata 섹션에 배치 됩니다. 동적으로 생성 된 함수 [JIT 컴파일러]의 경우 이러한 함수를 지 원하는 런타임에서는 RtlInstallFunctionTableCallback 또는 RtlAddFunctionTable을 사용 하 여이 정보를 운영 체제에 제공 해야 합니다. 이렇게 하지 않으면 프로세스의 예외 처리 및 디버깅이 불안정 해질 수 있습니다.

### <a name="struct-unwind_info"></a>구조체 UNWIND_INFO

해제 데이터 정보 구조는 함수에서 스택 포인터에 대 한 효과를 기록 하는 데 사용 되며, 비휘발성 레지스터가 스택에 저장 됩니다.

|||
|-|-|
|UBYTE: 3|버전|
|UBYTE: 5|플래그|
|UBYTE|프롤로그 크기|
|UBYTE|해제 코드 개수|
|UBYTE: 4|프레임 등록|
|UBYTE: 4|프레임 레지스터 오프셋 (크기 조정)|
|USHORT \* n|해제 코드 배열|
|변수|다음 형식 (1) 또는 (2) 중 하나를 사용할 수 있습니다.|

(1) 예외 처리기

|||
|-|-|
|ULONG|예외 처리기의 주소|
|변수|언어별 처리기 데이터 (선택 사항)|

(2) 연결 된 해제 정보

|||
|-|-|
|ULONG|함수 시작 주소|
|ULONG|함수 끝 주소|
|ULONG|해제 정보 주소|

UNWIND_INFO 구조는 메모리에서 DWORD로 정렬 되어야 합니다. 각 필드의 의미는 다음과 같습니다.

- **버전**

   해제 데이터의 버전 번호 (현재 1)입니다.

- **플래그**

   현재 세 개의 플래그가 정의 되어 있습니다.

   |플래그|설명|
   |-|-|
   |`UNW_FLAG_EHANDLER`| 함수에는 예외를 검사 해야 하는 함수를 찾을 때 호출 해야 하는 예외 처리기가 있습니다.|
   |`UNW_FLAG_UHANDLER`| 함수에는 예외를 해제할 때 호출 해야 하는 종료 처리기가 있습니다.|
   |`UNW_FLAG_CHAININFO`| 이 해제 정보 구조는 프로시저에 대 한 기본 구조가 아닙니다. 대신, 연결 된 해제 정보 항목은 이전 RUNTIME_FUNCTION 항목의 내용입니다. 자세한 내용은 연결 된 [해제 정보 구조체](#chained-unwind-info-structures)를 참조 하세요. 이 플래그가 설정 되 면 UNW_FLAG_EHANDLER 및 UNW_FLAG_UHANDLER 플래그를 지워야 합니다. 또한 프레임 레지스터 및 고정 스택 할당 필드의 값은 기본 해제 정보의 값과 같아야 합니다.|

- **프롤로그 크기**

   함수 프롤로그의 길이 (바이트)입니다.

- **해제 코드 개수**

   해제 코드 배열의 슬롯 수입니다. UWOP_SAVE_NONVOL와 같은 일부 해제 코드에는 배열에 둘 이상의 슬롯이 필요 합니다.

- **프레임 등록**

   0이 아닌 경우 함수는 프레임 포인터 (FP)를 사용 하 고이 필드는 UNWIND_CODE 노드의 작업 정보 필드에 대해 동일한 인코딩을 사용 하 여 프레임 포인터로 사용 되는 비휘발성 레지스터의 번호입니다.

- **프레임 레지스터 오프셋 (크기 조정)**

   Frame register 필드가 0이 아닌 경우이 필드는 설정 시 FP 레지스터에 적용 되는 RSP에서 크기가 조정 된 오프셋입니다. 실제 FP 레지스터는 0에서 240 까지의 오프셋을 허용 하는이 숫자 \* RSP + 16으로 설정 됩니다. 이 오프셋을 사용 하면 동적 스택 프레임에 대 한 로컬 스택 할당 중간에 FP 레지스터를 가리키면 보다 짧은 지침을 통해 더 나은 코드 밀도를 사용할 수 있습니다. 즉, 더 많은 지침이 8 비트 부호 있는 오프셋 형식을 사용할 수 있습니다.

- **해제 코드 배열**

   비휘발성 레지스터 및 RSP에서 프롤로그의 효과를 설명 하는 항목의 배열입니다. 개별 항목의 의미는 UNWIND_CODE에 대 한 섹션을 참조 하세요. 정렬 목적으로이 배열에는 항상 짝수 개의 항목이 있으며 최종 항목이 사용 되지 않을 수 있습니다. 이 경우 배열은 해제 코드 수 필드 수에 지정 된 것 보다 더 깁니다.

- **예외 처리기의 주소**

   UNW_FLAG_CHAININFO 플래그를 명확 하 게 지정 하 고 UNW_FLAG_EHANDLER 또는 UNW_FLAG_UHANDLER 플래그 중 하나를 설정 하는 경우 함수의 언어별 예외 또는 종료 처리기에 대 한 이미지 상대 포인터입니다.

- **언어별 처리기 데이터**

   함수의 언어별 예외 처리기 데이터입니다. 이 데이터의 형식은 사용 중인 특정 예외 처리기에 의해 지정 되지 않고 완전히 결정 됩니다.

- **연결 된 해제 정보**

   플래그가 UNW_FLAG_CHAININFO 설정 된 경우 UNWIND_INFO 구조는 세 개의 UWORDs로 끝납니다.  이러한 UWORDs는 연결 된 해제의 함수에 대 한 RUNTIME_FUNCTION 정보를 나타냅니다.

### <a name="struct-unwind_code"></a>구조체 UNWIND_CODE

해제 코드 배열은 비휘발성 레지스터 및 RSP에 영향을 주는 프롤로그의 작업 시퀀스를 기록 하는 데 사용 됩니다. 각 코드 항목의 형식은 다음과 같습니다.

|||
|-|-|
|UBYTE|프롤로그의 오프셋|
|UBYTE: 4|해제 작업 코드|
|UBYTE: 4|작업 정보|

배열은 프롤로그에서 내림차순으로 정렬 됩니다.

#### <a name="offset-in-prolog"></a>프롤로그의 오프셋

이 작업을 수행 하는 명령의 끝에 대 한 오프셋 (프롤로그의 시작)과 1 (다음 명령의 시작 오프셋)을 더한 값입니다.

#### <a name="unwind-operation-code"></a>해제 작업 코드

참고: 특정 작업 코드에는 로컬 스택 프레임의 값에 대 한 부호 없는 오프셋이 필요 합니다. 이 오프셋은 시작, 즉 고정 스택 할당의 가장 낮은 주소에서 가져온 것입니다. UNWIND_INFO의 프레임 등록 필드가 0 인 경우이 오프셋은 RSP에서 가져온 것입니다. 프레임 레지스터 필드가 0이 아닌 경우이 오프셋은 FP 레지스터가 설정 되었을 때 RSP가 있는 위치에서 발생 합니다. Fp 레지스터에서 FP 레지스터 오프셋을 뺀 값과 동일 합니다 (16 \* UNWIND_INFO 크기 조정 된 프레임 레지스터 오프셋). FP 레지스터가 사용 되는 경우에는 프롤로그에서 FP 레지스터가 설정 된 후에만 오프셋을 사용 하는 해제 코드를 사용 해야 합니다.

`UWOP_SAVE_XMM128` 및 `UWOP_SAVE_XMM128_FAR`를 제외한 모든 opcode에 대해, 모든 스택 값은 8 바이트 경계에 저장 되므로 (스택 자체는 항상 16 바이트로 정렬 됨) 오프셋은 항상 8의 배수입니다. Short 오프셋 (512K 미만)을 사용 하는 작업 코드의 경우이 코드의 노드에 있는 최종 USHORT는 오프셋을 8로 나눈 값을 포함 합니다. Long 오프셋 (512Kb < = 오프셋 < 4GB)을 사용 하는 작업 코드의 경우이 코드에 대 한 최종 두 개의 USHORT 노드에는 오프셋 (거의 endian 형식)이 포함 됩니다.

Opcode `UWOP_SAVE_XMM128` 및 `UWOP_SAVE_XMM128_FAR`의 경우 모든 128 비트 XMM 작업이 16 바이트 정렬 메모리에서 발생 해야 하므로 오프셋은 항상 16의 배수입니다. 따라서 크기 조정 인수 16은 1M 미만의 오프셋을 허용 하는 `UWOP_SAVE_XMM128`에 사용 됩니다.

해제 작업 코드는 다음 값 중 하나입니다.

- `UWOP_PUSH_NONVOL` (0) 노드 1 개

  비 volatile 정수 레지스터를 푸시합니다. 여기서는 RSP를 8 씩 감소 합니다. 작업 정보는 레지스터의 번호입니다. `UWOP_PUSH_NONVOL` 에필로그에 대 한 제약 조건 때문에 해제 코드는 처음에는 해제 코드 배열에서 마지막에 표시 되어야 합니다. 이 상대 순서 지정은 `UWOP_PUSH_MACHFRAME`를 제외 하 고 다른 모든 해제 코드에 적용 됩니다.

- `UWOP_ALLOC_LARGE` (1) 2 또는 3 개 노드

  스택에서 크기가 큰 영역을 할당 합니다. 두 가지 형식이 있습니다. 작업 정보가 0 인 경우 할당의 크기를 8로 나눈 값이 다음 슬롯에 기록 됩니다 .이 경우 512Kb까지 할당할 수 있습니다. 작업 정보가 1 이면 크기가 지정 되지 않은 할당의 크기가 작은 endian 형식으로 다음 두 슬롯에 기록 되므로 4GB까지 할당할 수 있습니다.

- `UWOP_ALLOC_SMALL` (2) 1 노드

  스택에서 작은 크기의 영역을 할당 합니다. 할당의 크기는 \* 8 + 128 8 바이트의 작업 정보 필드입니다.

  스택 할당에 대 한 해제 코드는 항상 가능한 가장 짧은 인코딩을 사용 해야 합니다.

  |**할당 크기**|**해제 코드**|
  |-|-|
  |8 ~ 128 바이트|`UWOP_ALLOC_SMALL`|
  |136 ~ 512K-8 바이트|`UWOP_ALLOC_LARGE`, 작업 정보 = 0|
  |4G ~ 8 바이트|`UWOP_ALLOC_LARGE`, 작업 정보 = 1|

- `UWOP_SET_FPREG` (3) 노드 1 개

  레지스터를 현재 RSP의 일부 오프셋으로 설정 하 여 프레임 포인터 등록을 설정 합니다. 오프셋은 UNWIND_INFO \* 16의 프레임 레지스터 오프셋 (배율) 필드와 같으며 0에서 240 사이의 오프셋을 허용 합니다. 오프셋을 사용 하면 고정 스택 할당의 중간을 가리키는 프레임 포인터를 설정할 수 있습니다 .이를 통해 더 많은 액세스를 통해 짧은 명령 폼을 사용 하 여 코드 밀도를 도울 수 있습니다. 작업 정보 필드는 예약 되어 있으므로 사용할 수 없습니다.

- `UWOP_SAVE_NONVOL` (4) 노드 2 개

  푸시 대신 MOV를 사용 하 여 스택에 비휘발성 정수 레지스터를 저장 합니다. 이 코드는 주로 비휘발성 레지스터가 이전에 할당 된 위치에서 스택에 저장 되는 *축소 래핑*에 사용 됩니다. 작업 정보는 레지스터의 번호입니다. 위의 참고 사항에 설명 된 대로, 다음 해제 작업 코드 슬롯에 확장 된 8 차원 스택 오프셋이 기록 됩니다.

- `UWOP_SAVE_NONVOL_FAR` (5) 3 개 노드

  푸시 대신 MOV를 사용 하 여 스택에 비휘발성 정수 레지스터를 저장 합니다. 이 코드는 주로 비휘발성 레지스터가 이전에 할당 된 위치에서 스택에 저장 되는 *축소 래핑*에 사용 됩니다. 작업 정보는 레지스터의 번호입니다. 크기 조정 된 스택 오프셋은 위의 참고 사항에 설명 된 대로 다음 두 해제 작업 코드 슬롯에 기록 됩니다.

- `UWOP_SAVE_XMM128` (8) 노드 2 개

  스택에 비휘발성 XMM 레지스터의 모든 128 비트를 저장 합니다. 작업 정보는 레지스터의 번호입니다. 16으로 확장 된 스택 오프셋은 다음 슬롯에 기록 됩니다.

- `UWOP_SAVE_XMM128_FAR` (9) 3 개 노드

  Long 오프셋을 사용 하 여 스택에 비휘발성 XMM 레지스터의 모든 128 비트를 저장 합니다. 작업 정보는 레지스터의 번호입니다. 크기 조정 된 스택 오프셋은 다음 두 슬롯에 기록 됩니다.

- `UWOP_PUSH_MACHFRAME` (10) 1 노드

  컴퓨터 프레임을 푸시합니다.  이 해제 코드는 하드웨어 인터럽트 또는 예외의 효과를 기록 하는 데 사용 됩니다. 두 가지 형식이 있습니다. 작업 정보가 0 인 경우 해당 프레임 중 하나가 스택으로 푸시됩니다.

  |||
  |-|-|
  |RSP+32|SS|
  |RSP+24|이전 RSP|
  |RSP+16|EFLAGS|
  |RSP+8|CS|
  |RSP|리핑하|

  작업 정보가 1 이면 다음 프레임 중 하나가 푸시됩니다.

  |||
  |-|-|
  |RSP+40|SS|
  |RSP+32|이전 RSP|
  |RSP+24|EFLAGS|
  |RSP+16|CS|
  |RSP+8|리핑하|
  |RSP|오류 코드|

  이 해제 코드는 실제로 실행 되지 않는 더미 프롤로그에 항상 표시 되지만 대신 중단 루틴의 실제 진입점 앞에 표시 되며 컴퓨터 프레임의 푸시를 시뮬레이트하는 위치를 제공 하기 위해서만 존재 합니다. `UWOP_PUSH_MACHFRAME`는 컴퓨터가 개념적으로이 작업을 수행 했음을 나타내는 시뮬레이션을 기록 합니다.

  1. 스택 맨 위에서 *Temp* 로 반환 주소를 팝 합니다.
  
  1. 밀어넣기 SS

  1. 이전 RSP 푸시

  1. 밀어넣기 EFLAGS

  1. 푸시 CS

  1. *임시* 푸시

  1. 푸시 오류 코드 (op 정보가 1 인 경우)

  시뮬레이션 된 `UWOP_PUSH_MACHFRAME` 연산은 40 (op 정보는 0) 또는 48 (op 정보는 1)으로 RSP를 감소 시킵니다.

#### <a name="operation-info"></a>작업 정보

작업 정보 비트의 의미는 작업 코드에 따라 달라 집니다. 범용 (정수) 레지스터를 인코딩하려면 다음 매핑이 사용 됩니다.

|||
|-|-|
|0|RAX|
|1|RCX|
|2|RDX|
|3|RBX|
|4|RSP|
|5|RBP|
|6|RSI|
|7|RDI|
|8-15|R15에 대 한 R8|

### <a name="chained-unwind-info-structures"></a>연결 된 해제 정보 구조체

UNW_FLAG_CHAININFO 플래그가 설정 되 면 해제 정보 구조가 보조 데이터베이스가 되 고 공유 된 예외-처리기/연결 된 정보 주소 필드에 기본 해제 정보가 포함 됩니다. 이 샘플 코드는 `unwindInfo`이 UNW_FLAG_CHAININFO 플래그가 설정 된 구조인 경우 기본 해제 정보를 검색 합니다.

```cpp
PRUNTIME_FUNCTION primaryUwindInfo = (PRUNTIME_FUNCTION)&(unwindInfo->UnwindCode[( unwindInfo->CountOfCodes + 1 ) & ~1]);
```

연결 된 정보는 두 가지 상황에서 유용 합니다. 첫째, 연속 되지 않은 코드 세그먼트에 사용할 수 있습니다. 연결 된 정보를 사용 하면 기본 해제 정보에서 해제 코드 배열을 복제할 필요가 없기 때문에 필요한 해제 정보의 크기를 줄일 수 있습니다.

또한 연결 된 정보를 사용 하 여 휘발성 레지스터 저장을 그룹화 할 수 있습니다. 컴파일러는 함수 엔트리 프롤로그 외부에 있을 때까지 일시적 레지스터의 저장을 연기할 수 있습니다. 그룹화 된 코드 앞의 함수 부분에 대 한 기본 해제 정보를 사용 하 여이를 기록한 다음 연결 된 정보의 해제 코드에서 비휘발성 레지스터의 저장을 반영 하는 연결 된 정보를 0이 아닌 크기의 프롤로그로 설정할 수 있습니다. 이 경우 해제 코드는 UWOP_SAVE_NONVOL의 모든 인스턴스입니다. 푸시를 사용 하 여 비휘발성 레지스터를 저장 하거나 추가 고정 스택 할당을 사용 하 여 RSP 레지스터를 수정 하는 그룹화는 지원 되지 않습니다.

UNW_FLAG_CHAININFO 집합이 설정 된 UNWIND_INFO 항목에는 UNWIND_INFO 항목에도 *여러 개의 축소 래핑*이 라고도 하는 UNW_FLAG_CHAININFO 집합이 있는 RUNTIME_FUNCTION 항목이 포함 될 수 있습니다. 결국에는 연결 된 해제 정보 포인터가 UNW_FLAG_CHAININFO 지워진 UNWIND_INFO 항목에 도착 합니다. 이 항목은 실제 프로시저 진입점을 가리키는 기본 UNWIND_INFO 항목입니다.

## <a name="unwind-procedure"></a>해제 프로시저

해제 코드 배열은 내림차순으로 정렬 됩니다. 예외가 발생 하는 경우 전체 컨텍스트는 운영 체제에 의해 컨텍스트 레코드에 저장 됩니다. 그런 다음 예외 디스패치 논리를 호출 하 여 예외 처리기를 찾기 위해 이러한 단계를 반복적으로 실행 합니다.

1. 컨텍스트 레코드에 저장 된 현재 RIP를 사용 하 여 현재 함수 (또는 연결 된 UNWIND_INFO 항목에 대 한 함수 부분)를 설명 하는 RUNTIME_FUNCTION 테이블 항목을 검색 합니다.

1. 함수 테이블 항목을 찾을 수 없는 경우이 항목은 리프 함수에 있으며, RSP는 반환 포인터의 주소를 직접 처리 합니다. [RSP]에 있는 반환 포인터는 업데이트 된 컨텍스트에 저장 되 고, 시뮬레이션 된 RSP는 8 씩 증가 하며, 1 단계를 반복 합니다.

1. 함수 테이블 항목이 발견 되 면 RIP는 예외 처리기에서 적용 될 수 있는 코드에서, b의 에필로그, b)에 있는 세 지역에 있을 수 있습니다.

   - Case a) RIP가 에필로그 내에 있으면 제어가 함수를 종료 하 고,이 함수에 대해이 예외와 연결 된 예외 처리기가 없을 수 있으며, 에필로그의 효과를 계속 하 여 호출자 함수의 컨텍스트를 계산 해야 합니다. RIP가 에필로그 내에 있는지 확인 하기 위해 RIP 이후부터 코드 스트림을 검사 합니다. 해당 코드 스트림을 합법적인 에필로그의 후행 부분과 일치 시킬 수 있는 경우 에필로그에 있고 에필로그의 나머지 부분이 시뮬레이션 되며, 각 명령이 처리 될 때마다 컨텍스트 레코드가 업데이트 됩니다. 이 처리 후 1 단계가 반복 됩니다.

   - 사례 b) RIP가 프롤로그 내에 있는 경우이 함수에 대 한이 예외와 연결 된 예외 처리기가 없을 수 있으며, 프롤로그의 영향을 취소 하 여 호출자 함수의 컨텍스트를 계산 해야 합니다. 함수에서 RIP로 시작 하는 거리가 해제 정보로 인코딩된 프롤로그 크기 보다 작거나 같은 경우에는 RIP가 프롤로그 내에 있습니다. 함수에서 RIP의 오프셋 보다 작거나 같은 오프셋을 가진 첫 번째 항목에 대 한 해제 코드 배열에서 앞으로 검색 한 다음 해제 코드 배열에서 나머지 항목의 영향을 취소 하 여 프롤로그의 효과를 해제 합니다. 그런 다음 1 단계를 반복 합니다.

   - Case c) RIP가 프롤로그 또는 에필로그 내에 있지 않고 함수에 예외 처리기가 있는 경우 (UNW_FLAG_EHANDLER 설정 됨) 언어별 처리기가 호출 됩니다. 처리기는 해당 데이터를 검색 하 고 필터 함수를 적절 하 게 호출 합니다. 언어별 처리기는 예외가 처리 되었거나 검색을 계속 하는 것으로 돌아갈 수 있습니다. 또한 해제를 직접 시작할 수 있습니다.

1. 언어별 처리기가 처리 된 상태를 반환 하는 경우 원래 컨텍스트 레코드를 사용 하 여 실행이 계속 됩니다.

1. 언어별 처리기가 없거나 처리기가 "검색 계속" 상태를 반환 하는 경우 컨텍스트 레코드를 호출자의 상태로 해제 해야 합니다. 모든 해제 코드 배열 요소를 처리 하 고 각각의 효과를 취소 하 여 수행 됩니다. 그런 다음 1 단계를 반복 합니다.

연결 된 해제 정보를 포함 하는 경우에는 이러한 기본 단계를 계속 진행 합니다. 유일한 차이점은, 배열의 끝에 도달한 후에는 해제 코드 배열을 탐색 하 여 프롤로그의 효과를 해제 하는 반면, 배열의 끝에 도달 하면 부모 해제 정보 및 여기에 있는 전체 해제 코드 배열에 연결 됩니다. 이러한 연결은 UNW_CHAINED_INFO 플래그 없이 해제 정보에 도착 하기 전까지 계속 되며, 해제 코드 배열에서 실행을 완료 합니다.

해제 데이터의 가장 작은 집합은 8 바이트입니다. 이는 128 바이트의 스택 이하로만 할당 되 고 비휘발성 레지스터 하나를 저장할 수 있는 함수를 나타냅니다. 또한 해제 코드 없이 길이가 0 인 프롤로그에 대 한 연결 된 해제 정보 구조의 크기 이기도 합니다.

## <a name="language-specific-handler"></a>언어별 처리기

UNW_FLAG_EHANDLER 또는 UNW_FLAG_UHANDLER 플래그가 설정 될 때마다 UNWIND_INFO에 언어별 처리기의 상대 주소가 표시 됩니다. 이전 섹션에서 설명한 것 처럼 언어별 처리기는 예외 처리기 검색의 일부로 호출 되거나 해제의 일부로 호출 됩니다. 다음 프로토타입이 있습니다.

```cpp
typedef EXCEPTION_DISPOSITION (*PEXCEPTION_ROUTINE) (
    IN PEXCEPTION_RECORD ExceptionRecord,
    IN ULONG64 EstablisherFrame,
    IN OUT PCONTEXT ContextRecord,
    IN OUT PDISPATCHER_CONTEXT DispatcherContext
);
```

**Exceptionrecord** 는 표준 Win64 정의를 포함 하는 예외 레코드에 대 한 포인터를 제공 합니다.

**EstablisherFrame** 는이 함수에 대 한 고정 스택 할당의 기준 주소입니다.

**Contextrecord** 는 예외가 발생 한 시점의 예외 컨텍스트 (예외 처리기의 경우) 또는 현재 "해제" 컨텍스트 (종료 처리기의 경우)를 가리킵니다.

**Dispatchercontext** 는이 함수에 대 한 디스패처 컨텍스트를 가리킵니다. 이 정의는 다음과 같습니다.

```cpp
typedef struct _DISPATCHER_CONTEXT {
    ULONG64 ControlPc;
    ULONG64 ImageBase;
    PRUNTIME_FUNCTION FunctionEntry;
    ULONG64 EstablisherFrame;
    ULONG64 TargetIp;
    PCONTEXT ContextRecord;
    PEXCEPTION_ROUTINE LanguageHandler;
    PVOID HandlerData;
} DISPATCHER_CONTEXT, *PDISPATCHER_CONTEXT;
```

**Controlpc** 는이 함수 내의 RIP 값입니다. 이 값은 예외 주소 이거나 제어가 설정 함수를 떠난 주소입니다. RIP는 컨트롤이이 함수 내의 일부 보호 된 구문 내에 있는지 확인 하는 데 사용 됩니다 (예: `__try`/`__except` 또는 `__try`/`__finally`에 대 한 `__try` 블록).

**.Imagebase** 는 함수 항목에서 사용 되는 32 비트 오프셋에 추가 되 고 상대 주소를 기록 하는 해제 정보에 추가 될이 함수가 포함 된 모듈의 이미지 기반 (로드 주소)입니다.

**Functionentry** 는 함수를 포함 하는 RUNTIME_FUNCTION 함수 항목에 대 한 포인터 및이 함수에 대 한 해제 정보 이미지-기본 상대 주소를 제공 합니다.

**EstablisherFrame** 는이 함수에 대 한 고정 스택 할당의 기준 주소입니다.

**TargetIp** 해제의 연속 주소를 지정 하는 선택적 명령 주소를 제공 합니다. **EstablisherFrame** 가 지정 되지 않은 경우이 주소는 무시 됩니다.

**Contextrecord** 는 시스템 예외 디스패치/해제 코드에 사용 되는 예외 컨텍스트를 가리킵니다.

**LanguageHandler** 은 호출 되는 언어별 언어 처리기 루틴을 가리킵니다.

**Handlerdata** 는이 함수에 대 한 언어별 처리기 데이터를 가리킵니다.

## <a name="unwind-helpers-for-masm"></a>MASM에 대 한 해제 도우미

적절 한 어셈블리 루틴을 작성 하기 위해 실제 어셈블리 명령과 병렬로 사용 하 여 적절 한 .pdata 및. .xdata를 만들 수 있는 의사 (pseudo) 작업 집합이 있습니다. 그리고 가장 일반적으로 사용 되는 의사 작업을 간단 하 게 사용할 때 사용 하는 매크로 집합이 있습니다.

### <a name="raw-pseudo-operations"></a>원시 의사 (pseudo) 작업

|의사 작업|설명|
|-|-|
|PROC 프레임 \[:*ehandler*]|MASM에서 함수의 구조화 된 예외 처리 해제 동작에 대 한 .xdata에서 함수 테이블 항목을 생성 하도록 합니다.  *Ehandler* 가 있는 경우이 프로시저는 언어별 처리기로 .xdata에 입력 됩니다.<br /><br /> FRAME 특성을 사용 하는 경우 뒤에가와 야 합니다. ENDPROLOG 지시문입니다.  함수가 리프 함수 ( [함수 형식](../build/stack-usage.md#function-types)에 정의 된 대로) 인 경우에는 이러한 의사 연산의 나머지와 마찬가지로 FRAME 특성이 필요 하지 않습니다.|
|. PUSHREG *등록*|프롤로그의 현재 오프셋을 사용 하 여 지정 된 레지스터 번호에 대 한 UWOP_PUSH_NONVOL 해제 코드 항목을 생성 합니다.<br /><br /> 비휘발성 정수 레지스터 에서만 사용 합니다.  Volatile 레지스터를 푸시하는 경우를 사용 합니다. ALLOCSTACK 8, 대신|
|.SETFRAME *register*, *offset*|지정 된 레지스터 및 오프셋을 사용 하 여 해제 정보에서 프레임 레지스터 필드와 오프셋을 채웁니다. 오프셋은 16의 배수 여야 하며 240 보다 작거나 같아야 합니다. 이 지시문은 현재 프롤로그 오프셋을 사용 하 여 지정 된 레지스터에 대 한 UWOP_SET_FPREG 해제 코드 항목도 생성 합니다.|
|. ALLOCSTACK *크기*|프롤로그에서 현재 오프셋의 지정 된 크기를 사용 하 여 UWOP_ALLOC_SMALL 또는 UWOP_ALLOC_LARGE을 생성 합니다.<br /><br /> *크기* 피연산자는 8의 배수 여야 합니다.|
|.SAVEREG *register*, *offset*|현재 프롤로그 오프셋을 사용 하 여 지정 된 레지스터 및 오프셋에 대 한 UWOP_SAVE_NONVOL 또는 UWOP_SAVE_NONVOL_FAR 해제 코드 항목을 생성 합니다. MASM은 가장 효율적인 인코딩을 선택 합니다.<br /><br /> *오프셋* 은 양수 여야 하며 8의 배수 여야 합니다. *offset* 은 일반적으로 RSP에 있는 프로시저 프레임의 밑을 기준으로 하며, 프레임 포인터를 사용 하는 경우에는 크기 조정 프레임 포인터를 사용 합니다.|
|.SAVEXMM128 *register*, *offset*|현재 프롤로그 오프셋을 사용 하 여 지정 된 XMM 레지스터 및 오프셋에 대 한 UWOP_SAVE_XMM128 또는 UWOP_SAVE_XMM128_FAR 해제 코드 항목을 생성 합니다. MASM은 가장 효율적인 인코딩을 선택 합니다.<br /><br /> *오프셋* 은 양수 여야 하며 16의 배수 여야 합니다.  *offset* 은 일반적으로 RSP에 있는 프로시저 프레임의 밑을 기준으로 하며, 프레임 포인터를 사용 하는 경우에는 크기 조정 프레임 포인터를 사용 합니다.|
|. PUSHFRAME \[*코드*]|UWOP_PUSH_MACHFRAME 해제 코드 항목을 생성 합니다. 선택적 *코드가* 지정 된 경우 해제 코드 항목에는 한정자 1이 지정 됩니다. 그렇지 않으면 한정자가 0입니다.|
|.ENDPROLOG|프롤로그 선언의 끝을 신호로 보냅니다.  함수의 처음 255 바이트에서 발생 해야 합니다.|

대부분의 opcode를 적절 하 게 사용 하는 샘플 함수 프롤로그는 다음과 같습니다.

```MASM
sample PROC FRAME
    db      048h; emit a REX prefix, to enable hot-patching
    push rbp
    .pushreg rbp
    sub rsp, 040h
    .allocstack 040h
    lea rbp, [rsp+020h]
    .setframe rbp, 020h
    movdqa [rbp], xmm7
    .savexmm128 xmm7, 020h ;the offset is from the base of the frame
                           ;not the scaled offset of the frame
    mov [rbp+018h], rsi
    .savereg rsi, 038h
    mov [rsp+010h], rdi
    .savereg rdi, 010h ; you can still use RSP as the base of the frame
                       ; or any other register you choose
    .endprolog

; you can modify the stack pointer outside of the prologue (similar to alloca)
; because we have a frame pointer.
; if we didn't have a frame pointer, this would be illegal
; if we didn't make this modification,
; there would be no need for a frame pointer

    sub rsp, 060h

; we can unwind from the next AV because of the frame pointer

    mov rax, 0
    mov rax, [rax] ; AV!

; restore the registers that weren't saved with a push
; this isn't part of the official epilog, as described in section 2.5

    movdqa xmm7, [rbp]
    mov rsi, [rbp+018h]
    mov rdi, [rbp-010h]

; Here's the official epilog

    lea rsp, [rbp+020h] ; deallocate both fixed and dynamic portions of the frame
    pop rbp
    ret
sample ENDP
```

에필로그 예제에 대 한 자세한 내용은 [x64 프롤로그 및 에필로그](prolog-and-epilog.md)의 [에필로그 코드](prolog-and-epilog.md#epilog-code) 를 참조 하세요.

### <a name="masm-macros"></a>MASM 매크로

[원시 의사 (pseudo) 작업](#raw-pseudo-operations)의 사용을 간소화 하기 위해 ksamd64에 정의 된 매크로 집합을 사용 하 여 일반적인 프로시저 프롤로그 및 에필로그를 만들 수 있습니다.

|매크로|설명|
|-|-|
|alloc_stack(n)|`sub rsp, n`를 사용 하 여 n 바이트의 스택 프레임을 할당 하 고 적절 한 해제 정보 (allocstack n)를 내보냅니다.|
|save_reg *reg*, *loc*|스택에 있는 비휘발성 레지스터 *reg* 를 RSP offset *loc*에 저장 하 고 적절 한 해제 정보를 내보냅니다. (. savereg reg, loc)|
|push_reg *reg*|스택에 비휘발성 레지스터 *reg* 를 푸시하고 적절 한 해제 정보를 내보냅니다. (. pushreg reg)|
|rex_push_reg *reg*|2 바이트 푸시를 사용 하 여 스택에 비휘발성 레지스터를 저장 하 고 적절 한 해제 정보 (.reg .reg reg)를 내보냅니다.  함수가 핫 패치 가능한이 되도록 push가 함수의 첫 번째 명령인 경우이 매크로를 사용 합니다.|
|save_xmm128 *reg*, *loc*|스택에 있는 비휘발성 XMM 레지스터 *reg* 를 RSP offset *loc*에 저장 하 고 적절 한 해제 정보 (. savexmm128 reg, loc)를 내보냅니다.|
|set_frame *reg*, *offset*|`mov`또는 `lea`를 사용 하 여 프레임 레지스터 *reg* 를 RSP + *offset* 으로 설정 하 고 적절 한 해제 정보 (. set_frame reg, offset)를 내보냅니다.|
|push_eflags|`pushfq` 명령으로 eflags를 푸시하고 적절 한 해제 정보 (. alloc_stack 8)를 내보냅니다.|

매크로를 적절 하 게 사용 하는 샘플 함수 프롤로그는 다음과 같습니다.

```MASM
sampleFrame struct
    Fill     dq ?; fill to 8 mod 16
    SavedRdi dq ?; Saved Register RDI
    SavedRsi dq ?; Saved Register RSI
sampleFrame ends

sample2 PROC FRAME
    alloc_stack(sizeof sampleFrame)
    save_reg rdi, sampleFrame.SavedRdi
    save_reg rsi, sampleFrame.SavedRsi
    .end_prolog

; function body

    mov rsi, sampleFrame.SavedRsi[rsp]
    mov rdi, sampleFrame.SavedRdi[rsp]

; Here's the official epilog

    add rsp, (sizeof sampleFrame)
    ret
sample2 ENDP
```

## <a name="unwind-data-definitions-in-c"></a>C의 해제 데이터 정의

다음은 해제 데이터에 대 한 C 설명입니다.

```C
typedef enum _UNWIND_OP_CODES {
    UWOP_PUSH_NONVOL = 0, /* info == register number */
    UWOP_ALLOC_LARGE,     /* no info, alloc size in next 2 slots */
    UWOP_ALLOC_SMALL,     /* info == size of allocation / 8 - 1 */
    UWOP_SET_FPREG,       /* no info, FP = RSP + UNWIND_INFO.FPRegOffset*16 */
    UWOP_SAVE_NONVOL,     /* info == register number, offset in next slot */
    UWOP_SAVE_NONVOL_FAR, /* info == register number, offset in next 2 slots */
    UWOP_SAVE_XMM128 = 8, /* info == XMM reg number, offset in next slot */
    UWOP_SAVE_XMM128_FAR, /* info == XMM reg number, offset in next 2 slots */
    UWOP_PUSH_MACHFRAME   /* info == 0: no error-code, 1: error-code */
} UNWIND_CODE_OPS;

typedef union _UNWIND_CODE {
    struct {
        UBYTE CodeOffset;
        UBYTE UnwindOp : 4;
        UBYTE OpInfo   : 4;
    };
    USHORT FrameOffset;
} UNWIND_CODE, *PUNWIND_CODE;

#define UNW_FLAG_EHANDLER  0x01
#define UNW_FLAG_UHANDLER  0x02
#define UNW_FLAG_CHAININFO 0x04

typedef struct _UNWIND_INFO {
    UBYTE Version       : 3;
    UBYTE Flags         : 5;
    UBYTE SizeOfProlog;
    UBYTE CountOfCodes;
    UBYTE FrameRegister : 4;
    UBYTE FrameOffset   : 4;
    UNWIND_CODE UnwindCode[1];
/*  UNWIND_CODE MoreUnwindCode[((CountOfCodes + 1) & ~1) - 1];
*   union {
*       OPTIONAL ULONG ExceptionHandler;
*       OPTIONAL ULONG FunctionEntry;
*   };
*   OPTIONAL ULONG ExceptionData[]; */
} UNWIND_INFO, *PUNWIND_INFO;

typedef struct _RUNTIME_FUNCTION {
    ULONG BeginAddress;
    ULONG EndAddress;
    ULONG UnwindData;
} RUNTIME_FUNCTION, *PRUNTIME_FUNCTION;

#define GetUnwindCodeEntry(info, index) \
    ((info)->UnwindCode[index])

#define GetLanguageSpecificDataPtr(info) \
    ((PVOID)&GetUnwindCodeEntry((info),((info)->CountOfCodes + 1) & ~1))

#define GetExceptionHandler(base, info) \
    ((PEXCEPTION_HANDLER)((base) + *(PULONG)GetLanguageSpecificDataPtr(info)))

#define GetChainedFunctionEntry(base, info) \
    ((PRUNTIME_FUNCTION)((base) + *(PULONG)GetLanguageSpecificDataPtr(info)))

#define GetExceptionDataPtr(info) \
    ((PVOID)((PULONG)GetLanguageSpecificData(info) + 1)
```

## <a name="see-also"></a>참고 항목

[x64 소프트웨어 규칙](../build/x64-software-conventions.md)
