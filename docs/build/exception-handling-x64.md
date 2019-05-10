---
title: x64 예외 처리
ms.date: 12/17/2018
helpviewer_keywords:
- C++ exception handling, x64
- exception handling, x64
ms.assetid: 41fecd2d-3717-4643-b21c-65dcd2f18c93
ms.openlocfilehash: 7dab7f3b6593bf4eaed1b8c804deb915677ccf5b
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62195207"
---
# <a name="x64-exception-handling"></a>x64 예외 처리

구조적된 예외 처리 개요 및 C++ 규칙 및 x64에는 동작을 코딩 하는 예외 처리 합니다. 예외 처리에 대 한 일반적인 내용은 참조 하세요. [시각적 개체의 예외 처리 C++ ](../cpp/exception-handling-in-visual-cpp.md)합니다.

## <a name="unwind-data-for-exception-handling-debugger-support"></a>예외 처리, 디버거 지원에 대 한 데이터를 해제 합니다.

여러 데이터 구조는 예외 처리 및 디버깅 지원에 필요 합니다.

### <a name="struct-runtimefunction"></a>구조체 RUNTIME_FUNCTION

테이블 기반 예외 처리 스택 공간을 할당 하거나 다른 함수 (예를 들어, 리프가 아닌 함수)를 호출 하는 모든 함수에 대 한 테이블 항목을 필요 합니다. 형식이 함수 테이블 항목:

|||
|-|-|
|ULONG|함수 시작 주소|
|ULONG|함수 끝 주소|
|ULONG|정보 주소를 해제 합니다.|

RUNTIME_FUNCTION 구조 DWORD 메모리에 정렬 해야 합니다. 모든 주소는 상대 이미지, 즉, 이러한은 함수 테이블 항목을 포함 하는 이미지의 시작 주소에서 32 비트 오프셋입니다. 이러한 항목은 정렬 되며 PE32 + 이미지의.pdata 섹션에 놓여집니다. 동적으로 생성 된 함수 [JIT 컴파일러]에 대 한 이러한 기능을 지 원하는 런타임 운영 체제에이 정보를 제공할 RtlInstallFunctionTableCallback 또는 RtlAddFunctionTable를 사용 하거나 해야 합니다. 이렇게 하지 않으면 안정적이 지 않은 예외 처리 및 프로세스 디버깅 됩니다.

### <a name="struct-unwindinfo"></a>구조체 UNWIND_INFO

해제 데이터 정보 구조 함수 스택 포인터 및 비휘발성 레지스터 스택에 저장 되는 위치에 결과 기록 하는 합니다.

|||
|-|-|
|UBYTE: 3|버전|
|UBYTE: 5|플래그|
|UBYTE|프롤로그의 크기|
|UBYTE|해제 코드 수|
|UBYTE: 4|프레임 등록|
|UBYTE: 4|프레임 등록 오프셋 (확장)|
|USHORT \* n|해제 코드 배열|
|변수|폼의 (1) 또는 (2) 아래 중일 수 있습니다|

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
|ULONG|정보 주소를 해제 합니다.|

UNWIND_INFO 구조 DWORD 메모리에 정렬 해야 합니다. 각 필드의 의미 다음과 같습니다.

- **Version**

   현재 1 해제 데이터의 버전 번호입니다.

- **플래그**

   세 가지 플래그 현재 정의 됩니다.

   |플래그|설명|
   |-|-|
   |`UNW_FLAG_EHANDLER`| 함수는 예외를 검사 해야 하는 함수를 찾을 때 호출 해야 하는 예외 처리기를 있습니다.|
   |`UNW_FLAG_UHANDLER`| 함수는 예외를 해제 하는 경우를 호출 해야 하는 종료 처리기를 있습니다.|
   |`UNW_FLAG_CHAININFO`| 이 구조 아닌 기본 프로시저에 대 한 정보를 해제 합니다. 대신 연결 된 해제 정보 항목을 이전 RUNTIME_FUNCTION 항목의 내용입니다. 정보를 참조 하세요 [Chained 해제 정보 구조체](#chained-unwind-info-structures)합니다. 이 플래그를 설정 하는 경우 다음 UNW_FLAG_EHANDLER 및 UNW_FLAG_UHANDLER 플래그를 지워야 합니다. 또한 프레임 등록 및 고정 스택 할당 필드 해제 정보 주 데이터베이스와 같이 동일한 값을 가져야 합니다.|

- **프롤로그의 크기**

   길이 (바이트)는 함수 프롤로그입니다.

- **해제 코드 수**

   해제 코드 배열에서 슬롯의 수입니다. 일부는 해제 코드, 예를 들어 UWOP_SAVE_NONVOL 배열에서 둘 이상의 슬롯이 필요 합니다.

- **프레임 등록**

   0이 아니면 함수는 프레임 포인터 (FP)를 사용 하는 다음 하 고이 필드는 UNWIND_CODE 노드 작업 정보 필드에 대 한 동일한 인코딩을 사용 하 여 프레임 포인터로 사용 비휘발성 레지스터의 번호입니다.

- **프레임 오프셋 (확장)를 등록 합니다.**

   이 필드는 크기 조정 된 오프셋 RSP FP에 적용 되는 프레임 등록 필드가 0이 아닌 경우 설정 되 면 등록 합니다. 실제 FP 레지스터 RSP + 16으로 설정 됩니다 \* 이 숫자를 오프셋 0에서 240 허용 합니다. 이 오프셋은 짧은 지침 (자세한 내용은 8 비트 부호 있는 오프셋된 폼을 사용할 수 있음)를 통해 더 나은 코드 밀도 허용 하는 동적 스택 프레임에 대 한 로컬 스택 할당의 중간에 FP 레지스터를 가리키는 허용 합니다.

- **해제 코드 배열**

   비휘발성 레지스터 및 RSP 프롤로그의 결과 설명 하는 항목의 배열입니다. 개별 항목의 의미 UNWIND_CODE에서 섹션을 참조 하십시오. 맞춤을 위해이 배열에는 항상 짝수 개의 항목에 및 최종 항목은 잠재적으로 사용 되지 않습니다. 이 경우 배열이 해제 코드 필드의 수를 나타내는 이상 하나입니다.

- **예외 처리기의 주소**

   함수의 언어별 예외 나 종료 처리기, 플래그가 UNW_FLAG_CHAININFO의 선택을 취소 하 고 UNW_FLAG_EHANDLER 또는 UNW_FLAG_UHANDLER 플래그 설정 된 경우에 이미지에 상대적인 포인터입니다.

- **언어별 처리기 데이터**

   함수의 언어별 예외 처리기 데이터입니다. 이 데이터의 형식은 지정 하지 않으면 이며 사용 중인 특정 예외 처리기에 의해 완전히 결정 됩니다.

- **연결 된 해제 정보**

   UNW_FLAG_CHAININFO 플래그가 설정 되어 있으면 UNWIND_INFO 구조 세 UWORDs로 끝납니다.  이러한 UWORDs RUNTIME_FUNCTION 정보를 함수에 대 한 연결된 해제를 나타냅니다.

### <a name="struct-unwindcode"></a>구조체 UNWIND_CODE

해제 코드 배열은 비휘발성 레지스터 및 RSP 영향을 주는 프롤로그에 작업 시퀀스를 기록 하는 데 사용 됩니다. 각 코드 항목에는이 형식에 있습니다.

|||
|-|-|
|UBYTE|프롤로그의 오프셋된|
|UBYTE: 4|작업 코드를 해제 합니다.|
|UBYTE: 4|작업 정보|

배열은 프롤로그의 오프셋의 내림차순으로 정렬 됩니다.

#### <a name="offset-in-prolog"></a>프롤로그의 오프셋된

이 작업의 경우 + 1 (즉, 다음 명령의 시작 오프셋)를 수행 하는 명령의 끝 프롤로그의 시작 부분에서 오프셋입니다.

#### <a name="unwind-operation-code"></a>작업 코드를 해제 합니다.

참고: 특정 작업 코드는 로컬 스택 프레임의 값에 대 한 부호 없는 오프셋을 필요합니다. 고정 된 스택 할당의 가장 낮은 주소 즉, 처음부터이 오프셋이입니다. UNWIND_INFO 프레임 등록 필드 0 인 경우이 오프셋에서 RSP입니다. 프레임 등록 필드가 0이 아닌 경우 이것이 RSP 있었던 FP 레지스터 설정 되었을 때의 오프셋입니다. FP 레지스터 FP 레지스터 오프셋을 뺀 값이 같음 (16 \* 확장 된 프레임을 UNWIND_INFO 오프셋 등록). FP 레지스터를 사용 하는 경우 다음 모든 해제 코드 오프셋만 사용 되어야 합니다는 FP 레지스터는 프롤로그에 설정 된 후.

제외한 모든 opcode에 대 한 `UWOP_SAVE_XMM128` 및 `UWOP_SAVE_XMM128_FAR`오프셋은 항상 8의 배수가, 값을 8 바이트 경계 (자체 스택은 항상 16 바이트 정렬)에 저장 된 모든 스택 때문입니다. 짧은 오프셋 (512k 미만)을 사용 하는 코드를 작업에 대 한이 코드에 대 한 노드의 마지막 USHORT 8로 나눈 값 오프셋을 포함 합니다. 시간 오프셋을 사용 하는 작업 코드에 대 한 (512k < = < 4GB 오프셋),이 코드의 마지막 두 USHORT 노드 (형태로 little endian) 오프셋을 저장 합니다.

Opcode에 대 한 `UWOP_SAVE_XMM128` 고 `UWOP_SAVE_XMM128_FAR`, 오프셋 항상의 배수가 16 이므로 16 바이트 정렬 된 메모리에서 모든 128 비트 XMM 작업을 수행 해야 합니다. 따라서 16 배율 인수는 `UWOP_SAVE_XMM128`, 보다 작거나 1m의 오프셋을 허용 합니다.

해제 작업 코드를 다음이 값 중 하나입니다.

- `UWOP_PUSH_NONVOL` (0) 노드 1 개

  정수 비휘발성 레지스터를 8로 감소 RSP 푸시하십시오. 작업 정보에는 레지스터의 수입니다. 에필로그에 대 한 제약 조건으로 인해 `UWOP_PUSH_NONVOL` 해제 코드를 프롤로그에서 첫 번째로 표시 되어야 하며 마지막 해제 코드 배열은에 있습니다. 제외한 기타 모든 해제 코드에 적용이 상대적 순서 `UWOP_PUSH_MACHFRAME`합니다.

- `UWOP_ALLOC_LARGE` (1) 2 또는 3 노드

  스택에 큰 영역을 할당 합니다. 다음과 같은 두 가지 있습니다. 작업 정보가 0 이면로 나눈 값 할당의 크기 8 K-8 512 최대 할당 다음 슬롯에 기록 됩니다. 작업 정보가 1 이면 할당의 실제 크기 크기 할당을 허용 하 고 little endian 형식으로 다음 두 슬롯에 기록 됩니다 최대 4GB-8입니다.

- `UWOP_ALLOC_SMALL` (노드 1 개 2)

  스택에 크기가 작은 영역을 할당 합니다. 할당의 크기는 작업 정보 필드 \* 8 + 8, 128 바이트를 8에서 할당을 허용 합니다.

  스택 할당에 대 한 해제 코드는 항상 가능한 가장 짧은 인코딩을 사용 해야 합니다.

  |**할당 크기**|**해제 코드**|
  |-|-|
  |8 ~ 128 바이트|`UWOP_ALLOC_SMALL`|
  |136에서 512k-8 바이트|`UWOP_ALLOC_LARGE`에서 작업 정보 = 0|
  |512k ~ 4 G-8 바이트|`UWOP_ALLOC_LARGE`에서 작업 정보 = 1|

- `UWOP_SET_FPREG` (노드 1 개 3)

  현재 RSP의 일부 오프셋으로 레지스터를 설정 하 여 프레임 포인터 레지스터를 설정 합니다. 오프셋은 같은 프레임 등록 오프셋된 (확장된) 필드에는 UNWIND_INFO \* 16, 오프셋 0에서 240 허용 합니다. 오프셋을 사용 하는 짧은 명령 폼 사용 하 여 더 많은 액세스를 허용 하 여 코드 밀도 지원 하면 고정된 스택 할당의 중간으로 가리키는 프레임 포인터를 설정할 수 있습니다. 작업 정보 필드는 예약어 이므로 사용할 수 없습니다.

- `UWOP_SAVE_NONVOL` (노드 4) 2 개

  MOV 푸시를 대신 사용 하 여 스택에 정수 비휘발성 레지스터를 저장 합니다. 이 코드는 주로 *래핑*, 이전에 할당 된 위치에 있는 스택에 비휘발성 레지스터를 저장 합니다. 작업 정보에는 레지스터의 수입니다. 크기를 조정 하 여 8 스택에서 오프셋은 다음에 기록 됩니다. 위 참고 사항에 설명 된 대로 작업 코드 슬롯을 해제 합니다.

- `UWOP_SAVE_NONVOL_FAR` (5) 3 노드

  시간 오프셋을 사용 하 여 스택에 정수 비휘발성 레지스터 저장을 MOV 푸시를 대신 사용합니다. 이 코드는 주로 *래핑*, 이전에 할당 된 위치에 있는 스택에 비휘발성 레지스터를 저장 합니다. 작업 정보에는 레지스터의 수입니다. 소수 자릿수가 없는 스택 오프셋은 다음에 기록 됩니다. 위 참고 사항에 설명 된 대로 작업 코드 슬롯 두 해제 합니다.

- `UWOP_SAVE_XMM128` (노드 8) 2 개

  스택에 XMM 등록 비휘발성의 모든 128 비트를 저장 합니다. 작업 정보에는 레지스터의 수입니다. 스택 크기를 조정 하 여 16 오프셋 다음 슬롯에 기록 됩니다.

- `UWOP_SAVE_XMM128_FAR` (9) 3 노드

  시간 오프셋을 사용 하 여 스택에 XMM 등록 비휘발성의 모든 128 비트를 저장 합니다. 작업 정보에는 레지스터의 수입니다. 소수 자릿수가 없는 스택 오프셋은 다음 두 슬롯에 기록 됩니다.

- `UWOP_PUSH_MACHFRAME` (노드 1 개 10)

  시스템 프레임을 푸시하십시오.  이 효과 하드웨어 인터럽트 또는 예외를 기록에 사용 됩니다. 다음과 같은 두 가지 있습니다. 작업 정보를 0 이면 이러한 프레임 중 하나 스택에 푸시 되었습니다.

  |||
  |-|-|
  |RSP+32|SS|
  |RSP+24|이전 RSP|
  |RSP+16|EFLAGS|
  |RSP+8|CS|
  |RSP|RIP|

  작업 정보가 1 인 경우 다음 이러한 프레임 중 푸시 되었습니다.

  |||
  |-|-|
  |RSP+40|SS|
  |RSP+32|이전 RSP|
  |RSP+24|EFLAGS|
  |RSP+16|CS|
  |RSP+8|RIP|
  |RSP|오류 코드|

  이 해제 코드는 다르지만 대신는 인터럽트 루틴의 실제 진입점 보다 먼저 나타납니다 및 컴퓨터 프레임의 푸시 시뮬레이션 하는 위치를 제공 하기 위해서만 존재 더미 프롤로그에 항상 표시 됩니다. `UWOP_PUSH_MACHFRAME` 컴퓨터에이 작업을 수행할 개념적으로 나타내는 해당 시뮬레이션을 기록 합니다.

  1. 에 스택 맨 위에서 반환 주소 RIP 팝 *Temp*
  
  1. SS 푸시

  1. 이전 RSP 푸시

  1. EFLAGS 푸시

  1. CS 푸시

  1. 푸시 *Temp*

  1. (Op 정보에는 1과 같음) 하는 경우 오류 코드를 푸시

  Simulated `UWOP_PUSH_MACHFRAME` 40 여 작업 감소 RSP (op 정보가 0) 또는 48 (op 정보가 1).

#### <a name="operation-info"></a>작업 정보

작업 정보 비트의 의미는 작업 코드에 따라 달라 집니다. 범용 (정수) 레지스터를 인코딩하려면이 매핑이 사용 됩니다.

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
|8 ~ 15|R 15 R8|

### <a name="chained-unwind-info-structures"></a>연결 된 해제 정보 구조체

UNW_FLAG_CHAININFO 플래그가 설정 된 경우에 해제 정보 구조체는 보조 단일 되 고 기본 해제 정보를 포함 하는 공유 되는 예외 처리기/연결-정보 주소 필드 이 샘플 코드는 기본 검색 정보를 가정 하 고 해제 `unwindInfo` 구조는 UNW_FLAG_CHAININFO 있는 플래그가 설정 됩니다.

```cpp
PRUNTIME_FUNCTION primaryUwindInfo = (PRUNTIME_FUNCTION)&(unwindInfo->UnwindCode[( unwindInfo->CountOfCodes + 1 ) & ~1]);
```

연결 된 정보는 두 가지 상황에서 유용 합니다. 첫째, 불연속 코드 세그먼트에 사용할 수 있습니다. 연결 된 정보를 사용 하 여 기본 해제 정보에서 해제 코드 배열은 중복 없기 때문에 필요한 해제 정보의 크기를 줄일 수 있습니다.

또한 휘발성 레지스터 저장을 그룹에 연결 된 정보를 사용할 수 있습니다. 컴파일러는 함수 진입점 프롤로그 외부에서 될 때까지 일부 휘발성 레지스터 저장 지연 될 수 있습니다. 그룹화 된 코드가 전에 함수 부분에 대 한 정보를 주 해제 함으로써이 기록할 수 있습니다 하 고 프롤로그에 있는 연결 된 정보는 해제 코드 비휘발성 레지스터의 0이 아닌 크기를 사용 하는 정보를 연결로 설정 합니다. 이 경우 해제 코드는 UWOP_SAVE_NONVOL의 모든 인스턴스입니다. 푸시를 사용 하 여 비휘발성 레지스터를 저장 하거나 추가 고정된 스택 할당을 사용 하 여 RSP 레지스터를 수정 하는 그룹화가 지원 되지 않습니다.

UNW_FLAG_CHAININFO 집합 수 UNWIND_INFO 항목이 역시 설정 UNW_FLAG_CHAININFO RUNTIME_FUNCTION 항목이 포함 된 UNWIND_INFO 항목이 라고도 *여러 래핑*합니다. 결과적으로 연결 된 해제 정보 포인터 UNW_FLAG_CHAININFO;의 선택을 취소 된 UNWIND_INFO 항목이 도착 이것이 실제 프로시저 진입점을 가리키는 주 UNWIND_INFO 항목입니다.

## <a name="unwind-procedure"></a>해제 절차

해제 코드 배열은 내림차순으로 정렬 됩니다. 예외가 발생 하는 컨텍스트 레코드의 운영 체제에서 전체 컨텍스트에 저장 됩니다. 예외 디스패치 논리 호출 되는 예외 처리기를 찾으려면 다음이 단계를 반복 해 서 실행:

1. 현재 함수 (또는 연결 된 UNWIND_INFO 항목에 대 한 함수 부분)를 설명 하는 RUNTIME_FUNCTION 테이블 항목을 검색할 컨텍스트 레코드에 저장 된 현재 RIP를 사용 합니다.

1. 함수 테이블 항목이 있으면 리프 함수에서 것 및 RSP 직접 주소를 포인터를 반환 합니다. [Rsp] 반환 포인터는 업데이트 된 컨텍스트에 저장 됩니다 하 고 시뮬레이트된 RSP 8 씩 증가 1 단계를 반복 합니다.

1. RIP 세 지역 내에서 상태로 남아 있을 수 있으면 함수 테이블 항목: a) 에필로그, b)에서 프롤로그 또는 c) 예외 처리기로 보호 되어야 하는 코드입니다.

   - 사례는) 경우 RIP가 에필로그 내에서 다음 함수 실행이 종료 된,이 함수에 대 한이 예외와 관련 된 예외 처리기 있을 수 있으며 에필로그의 효과가 호출자 함수의의 컨텍스트에서 계산을 계속 해야 합니다. RIP 켜져 있는지 RIP에서 코드 스트림 에필로그 내에서 확인 하려면이 검사 됩니다. 뒤에 오는 부분을 합법적인 에필로그 코드 스트림에 있는 일치 시킬 수 있습니다 하 고 에필로그에 에필로그의 나머지 부분을 시뮬레이션 하는, 하는 경우 각 명령으로 업데이트 된 컨텍스트 레코드를 사용 하 여 처리 됩니다. 그런 다음 1 단계를 반복 합니다.

   - 사례 b) 제어 되지 않은 다음 RIP 프롤로그 내에 않았으면 함수,이 함수에 대 한이 예외와 관련 된 예외 처리기 있을 수 있습니다 및 프롤로그의 결과 계산 컨텍스트의 호출자 함수를 실행 취소 해야 합니다. RIP은 프롤로그 내 경우 RIP 함수 시작에서 까지의 거리 보다 작거나 해제 정보를 인코딩된 프롤로그 크기와 동일 합니다. 프롤로그의 결과 오프셋과 함께 작거나 같거나 RIP의 오프셋을 함수 시작부터 첫 번째 항목에 대 한 해제 코드 배열은 통해 앞으로 검색 한 다음 해제 코드 배열에서 나머지 모든 항목의 효과 취소 하 여 해제 되었습니다. 1 단계를 반복 합니다.

   - 사례 c) RIP 프롤로그 또는 에필로그와 함수 안에 없을 경우에 예외 처리기 (UNW_FLAG_EHANDLER 설정 됨) 다음 언어별 처리기가 호출 됩니다. 처리기의 데이터를 검색 하 고 필터 함수를 적절 한 호출 합니다. 언어별 처리기는 예외가 처리 되었는지 또는 검색을 계속할 수를 반환할 수 있습니다. 해제를 직접 시작할 수도 있습니다.

1. 언어별 처리기 처리 상태를 반환할 경우 실행을 계속할 경우 원래 컨텍스트 레코드를 사용 하 여 합니다.

1. 언어별 처리기 없거나 "검색을 계속 합니다." 상태를 반환 하는 처리기를 다음 컨텍스트 레코드 없어야 스택이 호출자의 상태입니다. 이 모든 해제 코드 배열 요소를 각각의 효과 실행 취소를 처리 하 여 이루어집니다. 1 단계를 반복 합니다.

연결 하는 경우 해제 정보 관련 된, 이러한 기본 단계를 계속 수행 합니다. 유일한 차이점은 walking 해제 코드 배열은 배열의 끝에 도달 하면 프롤로그의 효과 해제 하려면 다음 연결 된 부모 해제 정보를 찾을 수 없으면 전체 해제 코드 배열은 안내 하는 동안입니다. UNW_CHAINED_INFO 플래그 없이 해제 정보에 도착 될 때까지 계속이 연결 하 고 해당 해제 코드 배열은 walking 완료 한 다음 키를 누릅니다.

최소한의 해제 데이터는 8 바이트입니다. 만 스택의 이하의 128 바이트를 할당 하 고 가능한 한 비휘발성 레지스터를 저장 하는 함수를 나타냅니다. 이 연결 된 크기인 이기도 없습니다 해제 코드를 사용 하 여 길이가 0 인 프롤로그에 대 한 정보 구조를 해제 합니다.

## <a name="language-specific-handler"></a>언어별 처리기

언어별 처리기의 상대 주소에에서 있으면는 UNWIND_INFO 때마다 UNW_FLAG_EHANDLER 또는 UNW_FLAG_UHANDLER 플래그를 설정 합니다. 이전 섹션에서 설명한 대로, 예외 처리기 검색의 일부로 또는 해제의 일부로 언어별 처리기가 호출 됩니다. 이 프로토타입은 다음과 같습니다.

```cpp
typedef EXCEPTION_DISPOSITION (*PEXCEPTION_ROUTINE) (
    IN PEXCEPTION_RECORD ExceptionRecord,
    IN ULONG64 EstablisherFrame,
    IN OUT PCONTEXT ContextRecord,
    IN OUT PDISPATCHER_CONTEXT DispatcherContext
);
```

**ExceptionRecord** 표준 Win64 정의는 예외 레코드에 대 한 포인터를 제공 합니다.

**EstablisherFrame** 의이 함수에 대 한 고정된 스택 할당의 기본 주소입니다.

**ContextRecord** 예외 컨텍스트 (에서 예외 처리기) 예외가 발생 하는 경우 또는 현재 가리키는 "해제" 컨텍스트 (종료 처리기의 경우).

**DispatcherContext** 이 함수에 대 한 디스패처 컨텍스트를 가리킵니다. 이 정의 있습니다.

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

**ControlPc** 이 함수 내에서 RIP의 값입니다. 이 값은 예외 주소 또는 주소는 컨트롤 왼쪽 설정 함수입니다. RIP 경우 컨트롤은이 함수에서 일부 보호 된 구문에 예를 들어 확인 되는 `__try` 에 대 한 차단 `__try` / `__except` 또는 `__try` / `__finally`합니다.

**ImageBase** 이미지 기본 (로드 주소)이이 함수를 함수 항목에서 사용 되는 32 비트 오프셋에 추가 되 고 해제 상대 주소를 기록 하는 정보를 포함 하는 모듈입니다.

**FunctionEntry** 는 RUNTIME_FUNCTION에 대 한 포인터를 제공 함수 진입 함수를 보유 하 고이 함수에 대 한 정보 이미지 기반 상대 주소를 해제 합니다.

**EstablisherFrame** 의이 함수에 대 한 고정된 스택 할당의 기본 주소입니다.

**TargetIp** 해제의 연속 주소를 지정 하는 선택적 명령 주소를 제공 합니다. 이 주소는 무시 됩니다 **EstablisherFrame** 지정 하지 않으면.

**ContextRecord** 시스템 예외 디스패치/해제 코드 사용에 대 한 예외 컨텍스트를 가리킵니다.

**LanguageHandler** 호출할 언어별 언어 처리기 루틴을 가리킵니다.

**HandlerData** 이 함수에 대 한 언어별 처리기 데이터를 가리킵니다.

## <a name="unwind-helpers-for-masm"></a>MASM에 대 한 도우미를 해제 합니다.

적절 한 어셈블리 루틴을 작성 하기 위해 적절 한.pdata 및.xdata 만들려면 실제 어셈블리 명령 함께에서 사용할 수 있는 의사 (pseudo) 작업 집합이 있습니다. 매크로 제공 하는 가장 일반적인 용도 대 한 의사 (pseudo) 작업의 사용을 간소화 하는 수도 있습니다.

### <a name="raw-pseudo-operations"></a>원시 의사 작업

|의사 작업|설명|
|-|-|
|PROC 프레임 \[:*ehandler*]|함수를 생성 하는 MASM 원인.pdata에 항목을 테이블 및 함수의 구조적에 대 한.xdata에서 정보를 해제 예외 처리 동작을 해제 합니다.  하는 경우 *ehandler* 가 있는 경우이 프로시저는.xdata 언어별 처리기로 입력 합니다.<br /><br /> 프레임 특성을 사용 하는 경우 그 뒤에 야를 합니다. 프롤로그 끝 지시문입니다.  함수는 리프 함수 이면 (에 정의 된 대로 [함수 형식을](../build/stack-usage.md#function-types)) 프레임 특성으로 이러한 의사 (pseudo)이 작업의 나머지 부분에는 필요 하지 않습니다.|
|. PUSHREG *등록*|현재 프롤로그의 오프셋을 사용 하 여 지정 된 레지스터 번호가 UWOP_PUSH_NONVOL 해제 코드 항목을 생성 합니다.<br /><br /> 이 정수 비휘발성 레지스터를 사용 하 여 사용 해야 합니다.  휘발성 레지스터의 푸시를 사용 하 여를 합니다. ALLOCSTACK 8 대신|
|.SETFRAME *register*, *offset*|지정 된 등록 및 오프셋을 사용 하 여 해제 정보에서 필드 및 오프셋을 등록 하는 프레임을 채웁니다. 오프셋은 16의 배수 여야 합니다. 240 보다 작거나 같음. 또한이 지시문은 현재 프롤로그 오프셋을 사용 하 여 지정된 된 레지스터의 uwop_set_fpreg 해제 코드를 생성 합니다.|
|. ALLOCSTACK *크기*|프롤로그에는 UWOP_ALLOC_SMALL 또는 현재 오프셋에 대 한 지정된 된 크기를 사용 하 여 UWOP_ALLOC_LARGE를 생성합니다.<br /><br /> 합니다 *크기* 피연산자를 8의 배수 여야 합니다.|
|.SAVEREG *register*, *offset*|UWOP_SAVE_NONVOL 또는 지정 된 등록 및 현재 프롤로그 오프셋을 사용 하 여 오프셋 UWOP_SAVE_NONVOL_FAR 해제 코드 항목을 생성 합니다. MASM 가장 효율적인 인코딩 선택합니다.<br /><br /> *오프셋* 양수와 8의 배수 여야 합니다. *오프셋* 하단에 일반적으로 RSP 프로시저의 프레임을 기준으로 또는 소수 자릿수가 없는 프레임 포인터 프레임 포인터를 사용 하는 경우.|
|.SAVEXMM128 *register*, *offset*|UWOP_SAVE_XMM128 또는 지정 된 XMM 레지스터 및 현재 프롤로그 오프셋을 사용 하 여 오프셋 UWOP_SAVE_XMM128_FAR 해제 코드 항목을 생성 합니다. MASM 가장 효율적인 인코딩 선택합니다.<br /><br /> *오프셋* 양수와 16의 배수 여야 합니다.  *오프셋* 하단에 일반적으로 RSP 프로시저의 프레임을 기준으로 또는 소수 자릿수가 없는 프레임 포인터 프레임 포인터를 사용 하는 경우.|
|. PUSHFRAME \[ *코드*]|UWOP_PUSH_MACHFRAME 해제 코드 항목을 생성합니다. 경우 선택적 *코드* 지정 된 경우 해제 코드 항목 1의 한정자를 지정 합니다. 그렇지 않은 경우 한정자는 0입니다.|
|.ENDPROLOG|프롤로그 선언의 끝 신호를 보냅니다.  함수의 첫 번째 255 바이트에서 수행 되어야 합니다.|

적절 한 대부분의 opcode 사용 하 여 샘플 함수 프롤로그는 다음과 같습니다.

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
; if we didn’t have a frame pointer, this would be illegal
; if we didn’t make this modification,
; there would be no need for a frame pointer

    sub rsp, 060h

; we can unwind from the next AV because of the frame pointer

    mov rax, 0
    mov rax, [rax] ; AV!

; restore the registers that weren’t saved with a push
; this isn’t part of the official epilog, as described in section 2.5

    movdqa xmm7, [rbp]
    mov rsi, [rbp+018h]
    mov rdi, [rbp-010h]

; Here’s the official epilog

    lea rsp, [rbp-020h]
    pop rbp
    ret
sample ENDP
```

### <a name="masm-macros"></a>MASM 매크로

사용을 간소화 하기 위해 합니다 [원시 의사 작업](#raw-pseudo-operations), 일반적인 프로시저 프롤로그 및 에필로그를 만드는 데 사용할 수 있습니다 ksamd64.inc에 정의 된 매크로 집합이 있습니다.

|매크로|설명|
|-|-|
|alloc_stack(n)|N 바이트의 스택 프레임 할당 (사용 하 여 `sub rsp, n`)를 내보내고 적절 한 해제 정보 (.allocstack n)|
|save_reg *reg*, *loc*|비휘발성 레지스터 저장 *reg* RSP 스택에 오프셋 *loc*를 내보내고 적절 한 정보를 해제 합니다. (.savereg reg, loc)|
|push_reg *reg*|비휘발성 레지스터를 푸시 *reg* 스택에 내보내고 적절 한 정보를 해제 합니다. 생성 합니다.|
|rex_push_reg *reg*|2 바이트 푸시를 사용 하 여 스택에 비휘발성 레지스터를 저장 하 고 내보내는 적절 한 해제 정보 생성 합니다. 푸시는 함수에서 첫 번째 명령을 핫 패치 가능한 함수 인지 확인 하는 경우 사용 해야 합니다.|
|save_xmm128 *reg*, *loc*|비휘발성 XMM 레지스터를 저장 *reg* RSP 스택에 오프셋 *loc*를 내보내고 적절 한 정보 (. savexmm128 reg, loc) 해제|
|set_frame *reg*, *offset*|프레임 등록 설정 *reg* 는 RSP 되도록 + *오프셋* (사용 하 여를 `mov`, 또는 `lea`)를 내보내고 적절 한 정보 (.set_frame reg, 오프셋)를 해제|
|push_eflags|사용 하 여 eflags 푸시를 `pushfq` 명령 내보내고 적절 한 해제 정보 (.alloc_stack 8)|

적절 한 매크로 사용 하 여 샘플 함수 프롤로그는 다음과 같습니다.

```MASM
SkFrame struct
    Fill    dq ?; fill to 8 mod 16
    SavedRdi dq ?; saved register RDI
    SavedRsi dq ?; saved register RSI
SkFrame ends

sampleFrame struct
    Filldq?; fill to 8 mod 16
    SavedRdidq?; Saved Register RDI
    SavedRsi  dq?; Saved Register RSI
sampleFrame ends

sample2 PROC FRAME
    alloc_stack(sizeof sampleFrame)
    save_reg rdi, sampleFrame.SavedRdi
    save_reg rsi, sampleFrame.SavedRsi
    .end_prolog

; function body

    mov rsi, sampleFrame.SavedRsi[rsp]
    mov rdi, sampleFrame.SavedRdi[rsp]

; Here’s the official epilog

    add rsp, (sizeof sampleFrame)
    ret
sample2 ENDP
```

## <a name="unwind-data-definitions-in-c"></a>C의 해제 데이터 정의

C의 해제 데이터 설명은 다음과 같습니다.

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

## <a name="see-also"></a>참고자료

[x64 소프트웨어 규칙](../build/x64-software-conventions.md)
