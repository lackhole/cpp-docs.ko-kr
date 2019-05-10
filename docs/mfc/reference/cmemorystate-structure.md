---
title: CMemoryState 구조체
ms.date: 11/04/2016
f1_keywords:
- CMemoryState
helpviewer_keywords:
- CMemoryState structure [MFC]
- memory leaks [MFC], detecting
- detecting memory leaks [MFC]
ms.assetid: 229d9de7-a6f3-4cc6-805b-5a9d9b1bfe1d
ms.openlocfilehash: a110e1345cb970c117de125bd8105e1bc86eaf94
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62163756"
---
# <a name="cmemorystate-structure"></a>CMemoryState 구조체

프로그램에서 메모리 누수 문제를 감지 하는 편리한 방법을 제공 합니다.

## <a name="syntax"></a>구문

```
struct CMemoryState
```

## <a name="members"></a>멤버

### <a name="public-constructors"></a>Public 생성자

|이름|설명|
|----------|-----------------|
|[CMemoryState::CMemoryState](#cmemorystate)|메모리 검사점을 제어 하는 클래스 같은 구조를 생성 합니다.|

### <a name="public-methods"></a>Public 메서드

|이름|설명|
|----------|-----------------|
|[CMemoryState::Checkpoint](#checkpoint)|현재 메모리 상태의 스냅숏으로 (검사점)을 가져옵니다.|
|[CMemoryState::Difference](#difference)|형식의 두 개체 간의 차이 계산 `CMemoryState`합니다.|
|[CMemoryState::DumpAllObjectsSince](#dumpallobjectssince)|이전 검사점 이후의 모든 현재 할당 된 개체의 요약을 덤프합니다.|
|[CMemoryState::DumpStatistics](#dumpstatistics)|에 대 한 메모리 할당 통계 출력을 `CMemoryState` 개체입니다.|

## <a name="remarks"></a>설명

`CMemoryState` 구조 이며 기본 클래스를 포함 하지 않습니다.

"메모리 누수" 개체의 메모리가 힙에 할당 되었지만 더 이상 필요한 경우 할당 취소 되지 않은 경우 발생 합니다. 이러한 메모리 누수 결국 메모리 부족 오류가 발생할 수 있습니다. 할당 하 고 프로그램에서 메모리 할당을 취소 하는 방법은 여러 가지가 있습니다.

- 사용 하는 `malloc` /  `free` 런타임 라이브러리에서 함수 패밀리입니다.

- Windows API 메모리 관리 함수를 사용 하 여 `LocalAlloc` /  `LocalFree` 하 고 `GlobalAlloc` /  `GlobalFree`합니다.

- 사용 하는 C++ **새** 하 고 **삭제** 연산자입니다.

합니다 `CMemoryState` 진단만 메모리를 찾아내는 데 도움이 누수를 사용 하 여 메모리를 할당할 때 발생 합니다 **새** 연산자를 사용 하 여 할당이 해제 되지 않습니다 **삭제**합니다. 에 대 한 메모리 관리 함수는 다른 두 개의 그룹을 비-C++ 프로그램 및 사용 하 여 혼합 **새** 하 고 **삭제** 동일한 프로그램에서 권장 되지 않습니다. DEBUG_NEW, 추가 매크로 대체 하기 위해 제공 됩니다는 **새** 파일 및 메모리 할당의 줄 번호 추적 해야 하는 경우 연산자입니다. DEBUG_NEW 일반적으로 사용 될 때마다 사용 되는 **새** 연산자입니다.

다른 진단 마찬가지로 `CMemoryState` 진단 프로그램의 디버그 버전에서 에서만 사용할 수 있습니다. 디버그 버전에 정의 된 _DEBUG 상수가 있어야 합니다.

프로그램에 메모리 누수가 의심 되는 경우 사용할 수는 `Checkpoint`, `Difference`, 및 `DumpStatistics` 프로그램 실행의 두 가지 다른 지점에서 메모리 상태 (할당 된 개체) 간의 차이 검색 하는 함수입니다. 이 정보는 함수를 정리 하 고 할당 한 모든 개체 있는지 여부를 결정 하는 데 유용할 수 있습니다.

단순히 할당 및 할당 취소에서 않으므로 이러한 불균형은 발생 한 위치를 알면 충분 한 정보를 제공 하지 않습니다, 경우 사용할 수 있습니다 합니다 `DumpAllObjectsSince` 함수에 대 한 이전 호출 이후 할당 된 모든 개체를 덤프 하는 데 `Checkpoint`합니다. 이 덤프 할당, 소스 파일 및 개체 할당 된 위치 (DEBUG_NEW에 사용할 할당) 하는 경우, 줄의 순서를 표시 하 고 개체, 해당 주소 및 해당 크기의 파생입니다. `DumpAllObjectsSince` 또한 각 개체의 호출 `Dump` 현재 상태에 대 한 정보를 제공 하는 함수입니다.

사용 하는 방법에 대 한 자세한 내용은 `CMemoryState` 기타 진단 내용과 [MFC 응용 프로그램 디버깅](/visualstudio/debugger/mfc-debugging-techniques)합니다.

> [!NOTE]
>  형식 개체의 선언을 `CMemoryState` 멤버 함수를 호출 하 여 대괄호로 묶어야 합니다 및 `#if defined(_DEBUG)/#endif` 지시문입니다. 그러면 메모리 진단 프로그램의 빌드를 디버깅에 사용할 수 있습니다.

## <a name="inheritance-hierarchy"></a>상속 계층 구조

`CMemoryState`

## <a name="requirements"></a>요구 사항

**헤더:** afx.h

##  <a name="checkpoint"></a>  CMemoryState::Checkpoint

스냅숏을 메모리 요약 하 고이 저장 `CMemoryState` 개체입니다.

```
void Checkpoint();
```

### <a name="remarks"></a>설명

`CMemoryState` 멤버 함수 [차이](#difference) 하 고 [DumpAllObjectsSince](#dumpallobjectssince) 이 스냅숏 데이터를 사용 합니다.

### <a name="example"></a>예제

  예제를 참조 합니다 [CMemoryState](#cmemorystate) 생성자입니다.

##  <a name="cmemorystate"></a>  CMemoryState::CMemoryState

빈 생성 `CMemoryState` 은 입력 해야 하는 개체를 [검사점](#checkpoint) 하거나 [차이](#difference) 멤버 함수입니다.

```
CMemoryState();
```

### <a name="example"></a>예제

[!code-cpp[NVC_MFC_Utilities#18](../../mfc/codesnippet/cpp/cmemorystate-structure_1.cpp)]

##  <a name="difference"></a>  CMemoryState::Difference

두 `CMemoryState` 개체를이 차이 저장 합니다 `CMemoryState` 개체입니다.

```
BOOL Difference(
    const CMemoryState& oldState,
    const CMemoryState& newState);
```

### <a name="parameters"></a>매개 변수

*oldState*<br/>
정의 된 대로 초기 메모리 상태를 `CMemoryState` 검사점입니다.

*newState*<br/>
에 의해 정의 된 새 메모리 상태를 `CMemoryState` 검사점입니다.

### <a name="return-value"></a>반환 값

두 메모리 상태가 서로 다른 경우 0이 아닌 값 그렇지 않으면 0입니다.

### <a name="remarks"></a>설명

[검사점](#checkpoint) 각 두 메모리 상태 매개 변수에 대해 호출 합니다.

### <a name="example"></a>예제

  예제를 참조 합니다 [CMemoryState](#cmemorystate) 생성자입니다.

##  <a name="dumpallobjectssince"></a>  CMemoryState::DumpAllObjectsSince

호출 된 `Dump` 클래스에서 파생 된 형식의 모든 개체에 대 한 함수 `CObject` 는 할당 된와 여전히 할당 된 마지막 [검사점](#checkpoint) 이 호출 `CMemoryState` 개체입니다.

```
void DumpAllObjectsSince() const;
```

### <a name="remarks"></a>설명

호출 `DumpAllObjectsSince` 초기화 되지 않은 사용 하 여 `CMemoryState` 개체 현재 메모리에 있는 모든 개체를 덤프 합니다.

### <a name="example"></a>예제

  예제를 참조 합니다 [CMemoryState](#cmemorystate) 생성자입니다.

##  <a name="dumpstatistics"></a>  CMemoryState::DumpStatistics

간결한 메모리 통계 보고서를 인쇄를 `CMemoryState` 개체에서 채워진 합니다 [차이](#difference) 멤버 함수입니다.

```
void DumpStatistics() const;
```

### <a name="remarks"></a>설명

에 인쇄 된 보고서를 [afxDump](diagnostic-services.md#afxdump) 장치에서는 다음을 보여 줍니다.

샘플 보고서의 수 (또는 크기)에 대 한 정보를 제공합니다.

- 사용 가능한 블록

- 일반 블록

- CRT 블록

- 무시 블록

- 클라이언트 블록

- 프로그램에서 사용 하는 바이트 단위로 한 번에 최대 메모리

- 총 메모리 (메가바이트) 프로그램에서 현재 사용

Free 블록은 해당 할당 취소 하는 경우 지연 된 블록 수가 `afxMemDF` 로 설정 된 `delayFreeMemDF`합니다. 자세한 내용은 [afxMemDF](diagnostic-services.md#afxmemdf), "MFC 매크로 및 전역 변수" 섹션에 있습니다.

### <a name="example"></a>예제

  다음 코드를 배치할 *projname*App.cpp 합니다. 다음 전역 변수를 정의 합니다.

[!code-cpp[NVC_MFC_Utilities#40](../../mfc/codesnippet/cpp/cmemorystate-structure_2.cpp)]

에 `InitInstance` 함수, 줄을 추가 합니다.

[!code-cpp[NVC_MFC_Utilities#41](../../mfc/codesnippet/cpp/cmemorystate-structure_3.cpp)]

에 대 한 처리기를 추가 합니다 `ExitInstance` 함수를 다음 코드를 사용 합니다.

[!code-cpp[NVC_MFC_Utilities#42](../../mfc/codesnippet/cpp/cmemorystate-structure_4.cpp)]

이제 프로그램의 출력을 확인 하려면 디버그 모드에서 실행할 수 있습니다는 `DumpStatistics` 함수입니다.

## <a name="see-also"></a>참고자료

[계층 구조 차트](../../mfc/hierarchy-chart.md)
