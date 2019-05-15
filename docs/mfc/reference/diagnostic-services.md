---
title: 진단 서비스
ms.date: 11/04/2016
helpviewer_keywords:
- diagnosi [MFC]s, diagnostic services
- diagnostic macros [MFC], list of general MFC
- services [MFC], diagnostic
- MFC, diagnostic services
- general diagnostic functions and variables [MFC]
- diagnostics [MFC], diagnostic functions and variables
- diagnostics [MFC], list of general MFC
- diagnosis [MFC], diagnostic functions and variables
- diagnosis [MFC], list of general MFC
- general diagnostic macros in MFC
- diagnostic macros [MFC]
- diagnostic services [MFC]
- object diagnostic functions in MFC
- diagnostics [MFC], diagnostic services
- diagnostic functions and variables [MFC]
ms.assetid: 8d78454f-9fae-49c2-88c9-d3fabd5393e8
ms.openlocfilehash: 682644dd84901e0f73a5fd43ca299d965476d759
ms.sourcegitcommit: 934cb53fa4cb59fea611bfeb9db110d8d6f7d165
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/14/2019
ms.locfileid: "65611448"
---
# <a name="diagnostic-services"></a>진단 서비스

MFC 라이브러리는 프로그램을 더 쉽게 디버그할 수 있는 많은 진단 서비스를 제공합니다. 이러한 진단 서비스에는 매크로 및 전역 함수가 포함되며, 이러한 함수를 통해 프로그램의 메모리 할당을 추적하고 런타임 중 개체의 내용을 덤프하고 런타임 중 디버깅 메시지를 인쇄할 수 있습니다. 진단 서비스의 매크로 및 전역 함수는 다음과 같은 범주로 그룹화됩니다.

- 일반 진단 매크로

- 일반 진단 함수 및 변수

- 개체 진단 함수

이러한 매크로 및 함수는 MFC 디버그 및 릴리스 버전의 `CObject` 에서 파생된 모든 클래스에서 사용할 수 있습니다. 그러나 DEBUG_NEW 및 확인을 제외 하 고 모든 릴리스 버전에서는 아무 작업도 수행합니다.

디버그 라이브러리에서, 할당된 모든 메모리 블록은 일련의 "보호 바이트"와 함께 묶입니다. 이러한 바이트가 잘못된 메모리 쓰기로 인해 교란되면 진단 루틴이 문제를 보고할 수 있습니다. 다음 줄을 포함하는 경우

[!code-cpp[NVC_MFCCObjectSample#14](../../mfc/codesnippet/cpp/diagnostic-services_1.cpp)]

구현 파일에서 **new** 에 대한 모든 호출은 파일 이름 및 메모리 할당이 발생한 줄 번호를 저장합니다. [CMemoryState::DumpAllObjectsSince](cmemorystate-structure.md#dumpallobjectssince) 함수는 이 추가 정보를 표시하여 메모리 누수를 확인할 수 있도록 합니다. 또한 진단 출력에 대한 자세한 내용은 [CDumpContext](../../mfc/reference/cdumpcontext-class.md) 클래스를 참조하세요.

또한 C 런타임 라이브러리는 애플리케이션을 디버그하는 데 사용할 수 있는 진단 함수 집합도 지원합니다. 자세한 내용은 런타임 라이브러리 참조에서 [루틴 디버그](../../c-runtime-library/debug-routines.md) 를 참조하세요.

### <a name="mfc-general-diagnostic-macros"></a>MFC 일반 진단 매크로

|||
|-|-|
|[ASSERT](#assert)|메시지를 출력 한 후 라이브러리의 디버그 버전에서 FALSE로 지정 된 식이 평가 되 면 프로그램을 중단 합니다.|
|[ASSERT_KINDOF](#assert_kindof)|개체가 지정된 클래스의 개체인지 아니면 지정된 클래스에서 파생된 클래스의 개체인지 테스트합니다.|
|[ASSERT_VALID](#assert_valid)|해당 `AssertValid` 멤버 함수를 호출하여 개체의 내부 유효성을 테스트합니다. 일반적으로 `CObject`에서 재정의됩니다.|
|[DEBUG_NEW](#debug_new)|메모리 누수를 쉽게 찾을 수 있도록 디버그 모드에서 모든 개체 할당에 파일 이름과 줄 번호를 제공합니다.|
|[DEBUG_ONLY](#debug_only)|ASSERT 비슷합니다, 식의 값을 테스트 하지는 않습니다 디버그 모드 에서만에서 실행 해야 하는 코드에 유용 합니다.|
|[확인 및 ENSURE_VALID](#ensure)|데이터 정확성의 유효성을 검사 하려면 사용 합니다.|
|[THIS_FILE](#this_file)|컴파일 중인 파일의 이름으로 확장 합니다.|
|[TRACE](#trace)|라이브러리의 디버그 버전에서 `printf`와 유사한 기능을 제공합니다.|
|[VERIFY](#verify)|ASSERT 유사 하지만 디버그 버전도 라이브러리의 릴리스 버전 에서도 식을 평가합니다.|

### <a name="mfc-general-diagnostic-variables-and-functions"></a>MFC 일반 진단 변수 및 함수

|||
|-|-|
|[afxDump](#afxdump)|[CDumpContext](../../mfc/reference/cdumpcontext-class.md) 정보를 디버거 출력 창 또는 디버그 터미널에 보내는 전역 변수입니다.|
|[afxMemDF](#afxmemdf)|디버깅 메모리 할당자의 동작을 제어하는 전역 변수입니다.|
|[AfxCheckError](#afxcheckerror)|오류가 발생 하는 경우 및 그렇다면 전달된 SCODE를 테스트 하는 데 사용 되는 전역 변수를 적절 한 오류를 throw 합니다.|
|[AfxCheckMemory](#afxcheckmemory)|현재 할당된 모든 메모리의 무결성을 검사합니다.|
|[AfxDebugBreak](#afxdebugbreak)|실행에서을 중단을 하면 됩니다.|
|[AfxDump](#cdumpcontext_in_mfc)|디버거 내에 있는 동안 호출되는 경우 디버그하는 동안 개체의 상태를 덤프합니다.|
|[AfxDump](#afxdump)|디버깅 하는 동안 개체의 상태를 덤프 하는 내부 함수입니다.|
|[AfxDumpStack](#afxdumpstack)|현재 스택의 이미지를 생성합니다. 이 함수는 항상 정적으로 연결됩니다.|
|[AfxEnableMemoryLeakDump](#afxenablememoryleakdump)|메모리 누수 덤프를 사용하도록 설정합니다.|
|[AfxEnableMemoryTracking](#afxenablememorytracking)|메모리 추적을 켜고 끕니다.|
|[AfxIsMemoryBlock](#afxismemoryblock)|메모리 블록이 제대로 할당되었는지 확인합니다.|
|[AfxIsValidAddress](#afxisvalidaddress)|메모리 주소 범위가 프로그램의 경계 내에 있는지 확인합니다.|
|[AfxIsValidString](#afxisvalidstring)|문자열에 대한 포인터가 유효한지 여부를 결정합니다.|
|[AfxSetAllocHook](#afxsetallochook)|각 메모리 할당에서 함수 호출을 사용하도록 설정합니다.|

### <a name="mfc-object-diagnostic-functions"></a>MFC 개체 진단 함수

|||
|-|-|
|[AfxDoForAllClasses](#afxdoforallclasses)|런타임 형식 검사를 지원하는 모든 `CObject`파생 클래스에서 지정된 함수를 실행합니다.|
|[AfxDoForAllObjects](#afxdoforallobjects)|`CObject`new **와 함께 할당된 모든**파생 개체에서 지정된 함수를 실행합니다.|

### <a name="mfc-compilation-macros"></a>MFC 컴파일 매크로

|||
|-|-|
|[_AFX_SECURE_NO_WARNINGS](#afx_secure_no_warnings)|사용 되지 않는 MFC 함수 사용에 대 한 컴파일러 경고를 표시 하지 않습니다.|

## <a name="afx_secure_no_warnings"></a> _AFX_SECURE_NO_WARNINGS

사용 되지 않는 MFC 함수 사용에 대 한 컴파일러 경고를 표시 하지 않습니다.

### <a name="syntax"></a>구문

```
_AFX_SECURE_NO_WARNINGS
```

### <a name="example"></a>예제

이 코드 샘플 _AFX_SECURE_NO_WARNINGS 정의 되지 않은 경우 컴파일러 경고가 발생 됩니다.

```cpp
// define this before including any afx files in stdafx.h
#define _AFX_SECURE_NO_WARNINGS
```
```cpp
CRichEditCtrl* pRichEdit = new CRichEditCtrl;
pRichEdit->Create(WS_CHILD|WS_VISIBLE|WS_BORDER|ES_MULTILINE,
   CRect(10,10,100,200), pParentWnd, 1);
char sz[256];
pRichEdit->GetSelText(sz);
```

## <a name="afxdebugbreak"></a> AfxDebugBreak

중단 하려면이 함수를 호출 (위치에 대 한 호출에서 `AfxDebugBreak`) MFC 응용 프로그램의 디버그 버전을 실행 합니다.

### <a name="syntax"></a>구문

```
void AfxDebugBreak( );
```

### <a name="remarks"></a>설명

`AfxDebugBreak` MFC 응용 프로그램의 릴리스 버전에 적용 되지 않습니다 하 고 제거 해야 합니다. 이 함수는 MFC 응용 프로그램에서 에서만 사용 해야 합니다. Win32 API 버전을 사용 하 여 `DebugBreak`를 비 MFC 응용 프로그램에서 중단 합니다.

### <a name="requirements"></a>요구 사항

**헤더:** afxver_.h

##  <a name="assert"></a>  ASSERT

해당 인수를 평가합니다.

```
ASSERT(booleanExpression)
```

### <a name="parameters"></a>매개 변수

*booleanExpression*<br/>
0이 아닌 값 또는 0으로 계산 되는 식 (포인터 값 포함)을 지정 합니다.

### <a name="remarks"></a>설명

결과가 0 인 경우 매크로가 진단 메시지를 출력 한 프로그램을 중단 합니다. 조건 0이 아닌 경우 아무 작업도 수행 하지 것입니다.

진단 메시지의 형식은 다음과 같습니다.

`assertion failed in file <name> in line <num>`

여기서 *이름을* 원본 파일의 이름 및 *num* 는 소스 파일에서 실패 한 어설션의 줄 번호입니다.

릴리스 버전의 MFC에서 ASSERT 식을 평가 하지 않습니다 하 고 따라서 프로그램을 방해 하지 않습니다. 식은 반드시 환경에 관계 없이 평가 되어야 하는 경우 ASSERT 대신 VERIFY 매크로 사용 합니다.

> [!NOTE]
>  이 함수는 MFC의 디버그 버전 에서만 사용할 수 있습니다.

### <a name="example"></a>예제

[!code-cpp[NVC_MFC_Utilities#44](../../mfc/codesnippet/cpp/diagnostic-services_2.cpp)]

### <a name="requirements"></a>요구 사항

**헤더:** afx.h

##  <a name="assert_kindof"></a>  ASSERT_KINDOF

이 매크로 가리키는 개체는 지정된 된 클래스의 개체 또는 지정된 된 클래스에서 파생 된 클래스의 개체를 어설션 합니다.

```
ASSERT_KINDOF(classname, pobject)
```

### <a name="parameters"></a>매개 변수

*classname*<br/>
이름을 `CObject`-클래스를 파생 합니다.

*pobject*<br/>
클래스 개체에 대 한 포인터입니다.

### <a name="remarks"></a>설명

합니다 *pobject* 매개 변수 개체에 대 한 포인터 여야 하며 수 **const**합니다. 개체를 가리키는 및 클래스를 지원 해야 합니다 `CObject` 런타임 클래스 정보입니다. 예를 들어, 되도록 `pDocument` 의 개체에 대 한 포인터를 `CMyDoc` 클래스 또는 해당 파생 항목을 코딩할 수 있습니다.

[!code-cpp[NVC_MFCDocView#194](../../mfc/codesnippet/cpp/diagnostic-services_3.cpp)]

사용 하는 `ASSERT_KINDOF` 매크로 정확 하 게 코딩와 동일 합니다.

[!code-cpp[NVC_MFCDocView#195](../../mfc/codesnippet/cpp/diagnostic-services_4.cpp)]

이 함수를 사용 하 여 선언 된 클래스에 대해서만 작동 합니다 [DECLARE_DYNAMIC] (#declare_dynamic 실행-시간-개체-모델-services.md 또는 [DECLARE_SERIAL](run-time-object-model-services.md#declare_serial) 매크로입니다.

> [!NOTE]
>  이 함수는 MFC의 디버그 버전 에서만 사용할 수 있습니다.

### <a name="requirements"></a>요구 사항

**헤더:** afx.h

##  <a name="assert_valid"></a>  ASSERT_VALID

사용 하 여 개체의 내부 상태의 유효성에 대 한 가정을 테스트할 수 있습니다.

```
ASSERT_VALID(pObject)
```

### <a name="parameters"></a>매개 변수

*pObject*<br/>
파생 된 클래스의 개체를 지정 `CObject` 의 재정의 버전을 보유 하는 `AssertValid` 멤버 함수입니다.

### <a name="remarks"></a>설명

ASSERT_VALID 호출을 `AssertValid` 개체의 멤버 함수는 인수로 전달 합니다.

MFC의 릴리스 버전에서는 ASSERT_VALID 일어나지 않습니다. 디버그 버전에서 포인터의 유효성을 검사, NULL에 대해 확인 하 고 호출 개체의 고유 `AssertValid` 멤버 함수입니다. 이러한 테스트 실패를 동일한 방식으로에 경고 메시지가 표시 됩니다 [ASSERT](#assert)합니다.

> [!NOTE]
>  이 함수는 MFC의 디버그 버전 에서만 사용할 수 있습니다.

자세한 내용 및 예제를 참조 하세요 [MFC 응용 프로그램 디버깅](/visualstudio/debugger/mfc-debugging-techniques)합니다.

### <a name="example"></a>예제

[!code-cpp[NVC_MFCCObjectSample#19](../../mfc/codesnippet/cpp/diagnostic-services_5.cpp)]

### <a name="requirements"></a>요구 사항

**헤더:** afx.h

##  <a name="debug_new"></a>  DEBUG_NEW

메모리 누수를 찾는 데 유용 합니다.

```
#define  new DEBUG_NEW
```

### <a name="remarks"></a>설명

일반적으로 사용 하는 프로그램에서 DEBUG_NEW을 어디에서 나 사용할 수 있습니다 합니다 **새** 힙 저장소를 할당 하는 연산자입니다.

디버그 모드에서 (때 합니다 **_DEBUG** 기호가 정의 된), DEBUG_NEW 할당 된 각 개체에 대 한 파일 이름과 줄 번호는 추적 합니다. 그런 다음 사용 하는 경우는 [cmemorystate:: Dumpallobjectssince](cmemorystate-structure.md#dumpallobjectssince) 멤버 함수를 DEBUG_NEW를 사용 하 여 할당 된 각 개체는 표시 파일 이름과 줄 번호를 사용 하 여 할당 된 위치입니다.

DEBUG_NEW를 사용 하려면 소스 파일에 다음 지시문을 삽입 합니다.

[!code-cpp[NVC_MFCCObjectSample#14](../../mfc/codesnippet/cpp/diagnostic-services_1.cpp)]

이 지시문을 삽입 하면 전처리기 삽입 DEBUG_NEW 사용할 때마다 **새**, MFC 나머지 작업을 수행 하 고 있습니다. DEBUG_NEW 간단한 확인 프로그램의 릴리스 버전을 컴파일할 때 **새** 작업 및 파일 이름 및 줄 번호 정보가 생성 되지 않습니다.

> [!NOTE]
>  이전 버전의 MFC (4.1 및 이전 버전)에 배치 해야 합니다 `#define` IMPLEMENT_DYNCREATE 또는 IMPLEMENT_SERIAL 매크로 호출 하는 모든 문은 뒤의 문으로 합니다. 이것이 더 이상 필요 합니다.

### <a name="requirements"></a>요구 사항

**헤더:** afx.h

##  <a name="debug_only"></a>  DEBUG_ONLY

디버그 모드에서 (때 합니다 **_DEBUG** 기호가 정의 된), DEBUG_ONLY 해당 인수를 계산 합니다.

```
DEBUG_ONLY(expression)
```

### <a name="remarks"></a>설명

릴리스 빌드에서 DEBUG_ONLY 해당 인수를 계산 하지 않습니다. 디버그 빌드에서만에서 실행 되어야 하는 코드가 있는 경우에 유용 합니다.

DEBUG_ONLY 매크로 주변 *식* 사용 하 여 `#ifdef _DEBUG` 고 `#endif`입니다.

### <a name="example"></a>예제

[!code-cpp[NVC_MFC_Utilities#32](../../mfc/codesnippet/cpp/diagnostic-services_6.cpp)]

### <a name="requirements"></a>요구 사항

**헤더:** afx.h

### <a name="ensure"></a>  확인 및 ENSURE_VALID

데이터 정확성의 유효성을 검사 하려면 사용 합니다.

### <a name="syntax"></a>구문

```
ENSURE(  booleanExpression )
ENSURE_VALID( booleanExpression  )
```

### <a name="parameters"></a>매개 변수

*booleanExpression*<br/>
테스트할 부울 식을 지정 합니다.

### <a name="remarks"></a>설명

이러한 매크로의 목적은 매개 변수 유효성 검사를 개선 하는 것입니다. 매크로 코드에서 잘못 된 매개 변수 추가 처리를 방지 합니다. ASSERT 매크로 달리 확인 매크로 어설션을 생성 하는 것 외에도 예외를 throw 합니다.

매크로는 프로젝트 구성에 따라 두 가지 방법으로 작동합니다. 매크로는 ASSERT 호출 및 어설션이 실패 하는 경우 다음 예외를 throw 합니다. 따라서 디버그 구성에서 (즉, 여기서 _DEBUG이 정의) 매크로 어설션 및 생성 릴리스 구성에서는 매크로 생성 하는 동안 예외 (ASSERT는 식을 평가할 릴리스 구성에서) 예외에만 합니다.

매크로 ENSURE_ARG 확인 매크로 처럼 작동합니다.

ENSURE_VALID (디버그 빌드에서만에서 효과가)는 ASSERT_VALID 매크로 호출 합니다. 또한 ENSURE_VALID 포인터가 null 인 경우 예외를 throw 합니다. NULL 테스트 디버그 및 릴리스 구성에서 수행 됩니다.

이러한 테스트 중 하나라도 실패 하면 ASSERT와 동일 하 게에 경고 메시지가 표시 됩니다. 필요한 경우 잘못 된 인수 예외를 throw 하는 매크로입니다.
### <a name="requirements"></a>요구 사항

**헤더:** afx.h

## <a name="this_file"></a> THIS_FILE

컴파일 중인 파일의 이름으로 확장 합니다.

### <a name="syntax"></a>구문

```
THIS_FILE
```

### <a name="remarks"></a>설명

정보를 확인 및 ASSERT 매크로에서 사용 됩니다. 응용 프로그램 마법사 및 코드 마법사 생성 되는 소스 코드 파일에 매크로 배치 합니다.

### <a name="example"></a>예제

```cpp
#ifdef _DEBUG
#undef THIS_FILE
static char THIS_FILE[] = __FILE__;
#endif

// __FILE__ is one of the six predefined ANSI C macros that the
// compiler recognizes.
```

### <a name="requirements"></a>요구 사항

**헤더:** afx.h

##  <a name="trace"></a>  TRACE

현재 응용 프로그램의 디버거를 지정된 된 문자열을 보냅니다.

```
TRACE(exp)
TRACE(DWORD  category,  UINT  level, LPCSTR lpszFormat, ...)
```

### <a name="remarks"></a>설명

참조 [ATLTRACE2](../../atl/reference/debugging-and-error-reporting-macros.md#atltrace2) 추적에 대 한 합니다. 추적 및 ATLTRACE2 동일 하 게 동작 합니다.

MFC의 디버그 버전을이 매크로 현재 응용 프로그램의 디버거를 지정된 된 문자열을 보냅니다. 릴리스 빌드에서이 매크로 (코드 없음 전혀 생성) nothing으로 컴파일합니다.

자세한 내용은 [MFC 응용 프로그램 디버깅](/visualstudio/debugger/mfc-debugging-techniques)합니다.

### <a name="requirements"></a>요구 사항

**헤더:** afx.h

##  <a name="verify"></a>  VERIFY

MFC의 디버그 버전에서는 해당 인수를 계산 합니다.

```
VERIFY(booleanExpression)
```

### <a name="parameters"></a>매개 변수

*booleanExpression*<br/>
0이 아닌 값 또는 0으로 계산 되는 식 (포인터 값 포함)을 지정 합니다.

### <a name="remarks"></a>설명

결과가 0 인 경우 매크로가 진단 메시지를 출력 한 프로그램을 중단 합니다. 조건 0이 아닌 경우 아무 작업도 수행 하지 것입니다.

진단 메시지의 형식은 다음과 같습니다.

`assertion failed in file <name> in line <num>`

여기서 *이름을* 소스 파일의 이름 및 *num* 는 소스 파일에서 실패 한 어설션의 줄 번호입니다.

MFC의 릴리스 버전에서는 확인 식을 평가 합니다. 하지만 인쇄 되지 않거나에 프로그램을 중단 합니다. 예를 들어 식 함수를 호출할 경우는 전화를 걸 수 있습니다.

### <a name="example"></a>예제

[!code-cpp[NVC_MFCDocView#198](../../mfc/codesnippet/cpp/diagnostic-services_7.cpp)]

### <a name="requirements"></a>요구 사항

**헤더:** afx.h

##  <a name="cdumpcontext_in_mfc"></a>  afxDump (MFC의 CDumpContext)

응용 프로그램에서 기본 개체를 덤프 하는 기능을 제공합니다.

```
CDumpContext  afxDump;
```

### <a name="remarks"></a>설명

`afxDump` 미리 정의 된 [CDumpContext](../../mfc/reference/cdumpcontext-class.md) 보낼 수 있는 개체 `CDumpContext` 정보를 디버거 출력 창 또는 디버그 터미널. 일반적으로 제공 `afxDump` 매개 변수로 `CObject::Dump`합니다.

Windows NT 및 Windows에서의 모든 버전에서 `afxDump` 출력은 다음과 같은 시각적 개체의 디버그 출력 창에 전송 됩니다. C++ 응용 프로그램을 디버깅 하는 경우.

이 변수는 MFC의 디버그 버전에만 정의 됩니다. 에 대 한 자세한 `afxDump`를 참조 하세요 [MFC 응용 프로그램 디버깅](/visualstudio/debugger/mfc-debugging-techniques)합니다.

### <a name="example"></a>예제

[!code-cpp[NVC_MFC_Utilities#23](../../mfc/codesnippet/cpp/diagnostic-services_8.cpp)]

### <a name="requirements"></a>요구 사항

**헤더:** afx.h

## <a name="afxdump"></a> AfxDump (내부)

MFC 디버깅 하는 동안 개체의 상태를 덤프 하는 데 사용 하는 내부 함수입니다.

### <a name="syntax"></a>구문

```
void AfxDump(const CObject* pOb);
```

### <a name="parameters"></a>매개 변수

*pOb*<br/>
파생 된 클래스의 개체에 대 한 포인터 `CObject`합니다.

### <a name="remarks"></a>설명

`AfxDump` 개체의 호출 `Dump` 멤버 함수 및으로 지정 된 위치 정보를 보냅니다는 `afxDump` 변수입니다. `AfxDump` MFC의 디버그 버전 에서만 제공 됩니다.

프로그램 코드를 호출 하지 않아야 `AfxDump`를 대신 호출 해야 하지만 `Dump` 적절 한 개체의 멤버 함수입니다.

### <a name="requirements"></a>요구 사항

**헤더:** afx.h

##  <a name="afxmemdf"></a>  afxMemDF

이 변수는 디버거 또는 프로그램에서 액세스할 수 있습니다 및 할당 진단 튜닝할 수 있습니다.

```
int  afxMemDF;
```

### <a name="remarks"></a>설명

`afxMemDF` 열거에 의해 지정 된 대로 다음 값을 가질 수 `afxMemDF`:

- `allocMemDF` 디버깅 할당자 (디버그 라이브러리의 기본 설정)을 설정합니다.

- `delayFreeMemDF` 지연 메모리를 해제 합니다. 메모리 블록을 해제 하는 프로그램을 하는 동안 할당자는 기본 운영 체제 메모리를 반환 하지 않습니다. 이 최대 메모리 내 스트레스 프로그램에 배치할 수 있습니다.

- `checkAlwaysMemDF` 호출 `AfxCheckMemory` 될 때마다 메모리를 할당 하거나 해제 합니다. 크게 메모리 할당 및 할당 취소 속도가 느려집니다.

### <a name="example"></a>예제

[!code-cpp[NVC_MFC_Utilities#30](../../mfc/codesnippet/cpp/diagnostic-services_9.cpp)]

### <a name="requirements"></a>요구 사항

**헤더:** afx.h

##  <a name="afxcheckerror"></a>  AfxCheckError

이 함수는 오류가 있는지 확인 하려면 전달 된 SCODE를 테스트 합니다.

```
void AFXAPI AfxCheckError(SCODE sc);
throw CMemoryException*
throw COleException*
```

### <a name="remarks"></a>설명

오류가 있으면 함수는 예외가 throw 됩니다. 이 함수가 throw 하는 전달 된 SCODE E_OUTOFMEMORY 인 경우는 [CMemoryException](../../mfc/reference/cmemoryexception-class.md) 를 호출 하 여 [AfxThrowMemoryException](exception-processing.md#afxthrowmemoryexception)합니다. 그렇지 않으면 throw 함수는 [COleException](../../mfc/reference/coleexception-class.md) 를 호출 하 여 [AfxThrowOleException](exception-processing.md#afxthrowoleexception)합니다.

응용 프로그램에서 OLE 함수 호출의 반환 값을 확인 하려면이 함수를 사용할 수 있습니다. 응용 프로그램에서이 함수를 사용 하 여 반환 값을 테스트 하 여 올바르게 사용 하 여 최소한의 코드 오류 조건에 대응할 수 있습니다.

> [!NOTE]
>  이 함수는과 동일한 효과가 디버그에서 하 고 디버그 이외 빌드합니다.

### <a name="example"></a>예제

[!code-cpp[NVC_MFCOleContainer#33](../../mfc/codesnippet/cpp/diagnostic-services_10.cpp)]

### <a name="requirements"></a>요구 사항

**헤더:** afx.h

##  <a name="afxcheckmemory"></a>  AfxCheckMemory

이 함수는 사용 가능한 메모리 풀의 유효성을 검사 하 고 필요에 따라 오류 메시지를 인쇄 합니다.

```
BOOL  AfxCheckMemory();
```

### <a name="return-value"></a>반환 값

0이 아닌 메모리 오류가 없습니다. 그렇지 않으면 0입니다.

### <a name="remarks"></a>설명

함수에서 메모리 손상이 없는지를 발견 하면 아무 것도 표시 됩니다.

힙에 현재 할당 된 모든 메모리 블록에 의해 할당 포함 하 여 확인 되 **새** 는 없음 같은 기본 메모리 할당자를 직접 호출 하 여 할당 합니다 **malloc** 함수 또는 `GlobalAlloc` Windows 함수입니다. 손상 된 것으로 모든 블록 없으면 메시지를 디버거 출력에 출력 됩니다.

줄을 포함 하는 경우

[!code-cpp[NVC_MFCCObjectSample#14](../../mfc/codesnippet/cpp/diagnostic-services_1.cpp)]

프로그램 모듈에 대 한 다음 후속 호출에서 `AfxCheckMemory` 메모리가 할당 된 위치에 파일 이름과 줄 번호를 표시 합니다.

> [!NOTE]
>  모듈에는 serializable 클래스의 하나 이상의 구현이 포함 되어 있습니다. 다음 배치 해야 하는 경우는 `#define` IMPLEMENT_SERIAL 매크로 대 한 마지막 호출 뒤에 줄.

이 함수는 MFC의 디버그 버전 에서만에서 작동합니다.

### <a name="example"></a>예제

[!code-cpp[NVC_MFCCObjectSample#26](../../mfc/codesnippet/cpp/diagnostic-services_11.cpp)]

### <a name="requirements"></a>요구 사항

**헤더:** afx.h

##  <a name="afxdump"></a>  AfxDump (MFC)

디버깅 하는 동안 개체의 상태를 덤프 하는 데 디버거 내에서이 함수를 호출 합니다.

```
void AfxDump(const CObject* pOb);
```

### <a name="parameters"></a>매개 변수

*pOb*<br/>
파생 된 클래스의 개체에 대 한 포인터 `CObject`합니다.

### <a name="remarks"></a>설명

`AfxDump` 개체의 호출 `Dump` 멤버 함수 및으로 지정 된 위치 정보를 보냅니다는 `afxDump` 변수입니다. `AfxDump` MFC의 디버그 버전 에서만 제공 됩니다.

프로그램 코드를 호출 하지 않아야 `AfxDump`를 대신 호출 해야 하지만 `Dump` 적절 한 개체의 멤버 함수입니다.

### <a name="requirements"></a>요구 사항

**헤더:** afx.h

##  <a name="afxdumpstack"></a>  AfxDumpStack

현재 스택의 이미지를 생성 하려면이 전역 함수를 사용할 수 있습니다.

```
void AFXAPI AfxDumpStack(DWORD dwTarget = AFX_STACK_DUMP_TARGET_DEFAULT);
```

### <a name="parameters"></a>매개 변수

*dwTarget*<br/>
덤프 출력의 대상을 나타냅니다. 비트 OR를 사용 하 여 결합할 수 있는 가능한 값 ( **&#124;**) 연산자는 다음과 같습니다.

- 출력을 이용 하 여 AFX_STACK_DUMP_TARGET_TRACE 보냅니다 합니다 [추적](#trace) 매크로입니다. TRACE 매크로 디버그 빌드에서만;에서 출력을 생성합니다. 릴리스 빌드에서 출력이 생성합니다. 또한 추적 디버거 외에도 다른 대상으로 리디렉션할 수 있습니다.

- 기본 대상 덤프 출력 AFX_STACK_DUMP_TARGET_DEFAULT 보냅니다. 디버그 빌드에 대 한 출력 TRACE 매크로로 이동합니다. 릴리스 빌드에서 출력 클립보드로 이동합니다.

- AFX_STACK_DUMP_TARGET_CLIPBOARD만 클립보드에 출력을 보냅니다. 데이터를 일반 텍스트로 CF_TEXT 클립보드 형식을 사용 하 여 클립보드에 배치 됩니다.

- AFX_STACK_DUMP_TARGET_BOTH 클립보드에 TRACE 매크로 동시에 출력을 보냅니다.

- Win32 함수를 사용 하 여 디버거를 직접 출력 AFX_STACK_DUMP_TARGET_ODS 보냅니다 `OutputDebugString()`합니다. 이 옵션은 모두 디버그에서 디버거 출력을 생성 하 고 릴리스 빌드 프로세스에 디버거가 연결 되어 있는 경우. (연결)가 있는 경우 항상 디버거를 도달 AFX_STACK_DUMP_TARGET_ODS 리디렉션될 수 없습니다.

### <a name="remarks"></a>설명

아래 예제에서는 호출에서 생성 된 출력을 전혀 반영 `AfxDumpStack` MFC 대화 상자 응용 프로그램에서 단추 처리기에서:

```Output
=== begin AfxDumpStack output ===
00427D55: DUMP2\DEBUG\DUMP2.EXE! void AfxDumpStack(unsigned long) + 181 bytes
0040160B: DUMP2\DEBUG\DUMP2.EXE! void CDump2Dlg::OnClipboard(void) + 14 bytes
0044F884: DUMP2\DEBUG\DUMP2.EXE! int _AfxDispatchCmdMsg(class CCmdTarget *,
unsigned int,int,void ( CCmdTarget::*)(void),void *,unsigned int,struct
AFX_CMDHANDLE
0044FF7B: DUMP2\DEBUG\DUMP2.EXE! virtual int CCmdTarget::OnCmdMsg(unsigned
int,int,void *,struct AFX_CMDHANDLERINFO *) + 626 bytes
00450C71: DUMP2\DEBUG\DUMP2.EXE! virtual int CDialog::OnCmdMsg(unsigned
int,int,void *,struct AFX_CMDHANDLERINFO *) + 36 bytes
00455B27: DUMP2\DEBUG\DUMP2.EXE! virtual int CWnd::OnCommand(unsigned
int,long) + 312 bytes
00454D3D: DUMP2\DEBUG\DUMP2.EXE! virtual int CWnd::OnWndMsg(unsigned
int,unsigned int,long,long *) + 83 bytes
00454CC0: DUMP2\DEBUG\DUMP2.EXE! virtual long CWnd::WindowProc(unsigned
int,unsigned int,long) + 46 bytes
004528D9: DUMP2\DEBUG\DUMP2.EXE! long AfxCallWndProc(class CWnd *,struct
HWND__ *,unsigned int,unsigned int,long) + 237 bytes
00452D34: DUMP2\DEBUG\DUMP2.EXE! long AfxWndProc(struct HWND__ *,unsigned
int,unsigned int,long) + 129 bytes
BFF73663: WINDOWS\SYSTEM\KERNEL32.DLL! ThunkConnect32 + 2148 bytes
BFF928E0: WINDOWS\SYSTEM\KERNEL32.DLL! UTUnRegister + 2492 bytes
=== end AfxDumpStack() output ===
```

위의 출력에서 각 줄의 마지막 함수 호출을 함수 호출 및 호출 함수 프로토타입이 포함 된 모듈의 전체 경로 이름 주소를 나타냅니다. 함수 호출 스택에 있는 함수의 정확한 주소의 작업이 발생 하지 않습니다, 바이트 오프셋 표시 됩니다.

예를 들어, 다음 표에서 위의 출력의 첫 번째 줄을 설명합니다.

|출력|설명|
|------------|-----------------|
|`00427D55:`|마지막 함수 호출의 반환 주소입니다.|
|`DUMP2\DEBUG\DUMP2.EXE!`|함수 호출을 포함 하는 모듈의 전체 경로 이름입니다.|
|`void AfxDumpStack(unsigned long)`|함수 프로토타입 호출 됩니다.|
|`+ 181 bytes`|함수 프로토타입의 주소에서에서 바이트 오프셋 (이 예에서 `void AfxDumpStack(unsigned long)`) 반송 주소로 (이 예제의 경우 `00427D55`).|

`AfxDumpStack` 디버그 빌드와 버전의 MFC 라이브러리;에서 사용할 수 있습니다. 그러나 함수는 항상 정적으로 연결, 실행 파일 공유 DLL에서 MFC를 사용 하는 경우에 합니다. 공유 라이브러리 구현에서는 함수를 MFCS42에서 발견 됩니다. LIB 라이브러리 (및 해당 변형)입니다.

성공적으로이 함수를 사용 합니다.

- IMAGEHLP 파일입니다. DLL 경로에 있어야 합니다. 이 DLL이 없으면 함수는 오류 메시지가 표시 됩니다. 참조 [이미지 도움말 라이브러리](/windows/desktop/Debug/image-help-library) IMAGEHLP에서 제공 하는 함수 집합에 대 한 정보에 대 한 합니다.

- 스택 프레임에 있는 모듈 디버깅 정보를 포함 해야 합니다. 디버깅 정보를 포함 하지 않습니다 하는 경우 상태는 함수에서 스택 추적을 생성 하지만 추적 덜 자세하게 표시 됩니다.
  ### <a name="requirements"></a>요구 사항

**헤더:** afx.h

##  <a name="afxenablememoryleakdump"></a>  AfxEnableMemoryLeakDump

사용 하도록 설정 하 고 AFX_DEBUG_STATE 소멸자에서 메모리 누수 덤프를 사용 하지 않도록 설정 합니다.

```
BOOL AFXAPI AfxEnableMemoryLeakDump(BOOL bDump);
```

### <a name="parameters"></a>매개 변수

*bDump*<br/>
[in] TRUE 이면 메모리 누수 덤프를 활성화 됩니다. FALSE 이면 메모리 누수 덤프를 사용할 수 없습니다.

### <a name="return-value"></a>반환 값

이 플래그에 대한 이전 값입니다.

### <a name="remarks"></a>설명

애플리케이션이 MFC 라이브러리를 언로드하면 MFC 라이브러리는 메모리 누수를 확인합니다. 이 시점에서 모든 메모리 누수가 통해 사용자에 게 보고 합니다 **디버그** Visual Studio의 창.

애플리케이션이 MFC 라이브러리 전에 다른 라이브러리를 로드하는 경우, 해당 라이브러리의 일부 메모리 할당이 메모리 누수로 잘못 보고됩니다. 거짓 메모리 누수가 발생하면 MFC 라이브러리에서 이를 보고하므로 애플리케이션이 느리게 종료될 수 있습니다. 이 경우 메모리 누수 덤프를 사용하지 않으려면 `AfxEnableMemoryLeakDump` 를 사용합니다.

> [!NOTE]
>  이 방법을 사용하여 메모리 누수 덤프를 끄는 경우, 애플리케이션에서 발생하는 유효한 메모리 누수의 보고서를 받지 못합니다. 메모리 누수 보고서에 거짓 메모리 누수가 포함되어 있다고 확신하는 경우에만 이 방법을 사용해야 합니다.

### <a name="requirements"></a>요구 사항

**헤더:** afx.h

##  <a name="afxenablememorytracking"></a>  AfxEnableMemoryTracking

MFC의 디버그 버전 진단 메모리 추적이 일반적으로 사용 됩니다.

```
BOOL AfxEnableMemoryTracking(BOOL bTrack);
```

### <a name="parameters"></a>매개 변수

*bTrack*<br/>
메모리 추적;을 TRUE으로 설정 하면이이 값으로 설정 FALSE 이면이 해제 됩니다.

### <a name="return-value"></a>반환 값

추적 사용 플래그의 이전 설정입니다.

### <a name="remarks"></a>설명

이 함수를 사용 하 여 요소를 올바르게 할당 되는 것이 알고 있는 코드의 섹션에는 추적을 사용 하지 않도록 설정 합니다.

에 대 한 자세한 `AfxEnableMemoryTracking`를 참조 하세요 [MFC 응용 프로그램 디버깅](/visualstudio/debugger/mfc-debugging-techniques)합니다.

> [!NOTE]
>  이 함수는 MFC의 디버그 버전 에서만에서 작동합니다.

### <a name="example"></a>예제

[!code-cpp[NVC_MFC_Utilities#24](../../mfc/codesnippet/cpp/diagnostic-services_12.cpp)]

### <a name="requirements"></a>요구 사항

**헤더:** afx.h

##  <a name="afxismemoryblock"></a>  AfxIsMemoryBlock

진단 버전에서 할당 된 현재 메모리 블록을 나타내므로 되도록 메모리 주소를 테스트 **새**합니다.

```
BOOL AfxIsMemoryBlock(
    const void* p,
    UINT nBytes,
    LONG* plRequestNumber = NULL);
```

### <a name="parameters"></a>매개 변수

*p*<br/>
테스트할 메모리 블록을 가리킵니다.

*nBytes*<br/>
바이트의 메모리 블록의 길이 포함합니다.

*plRequestNumber*<br/>
가리키는 **긴** 정수 메모리 블록의 할당 순서 번호 채워집니다 또는 현재 활성 메모리 블록을 나타내지 않는 경우 0입니다.

### <a name="return-value"></a>반환 값

현재 할당 된 메모리 블록은 길이가 올바른; 경우 0이 아닌 값 그렇지 않으면 0입니다.

### <a name="remarks"></a>설명

또한 원래 할당 된 크기에 대해 지정된 된 크기를 확인합니다. 함수는 0이 아닌 반환 하는 경우에 할당 순서 번호가 반환 됩니다 *plRequestNumber*합니다. 이 숫자는 블록은 다른 모든 기준으로 할당 된 순서를 나타내는 **새** 할당 합니다.

### <a name="example"></a>예제

[!code-cpp[NVC_MFC_Utilities#27](../../mfc/codesnippet/cpp/diagnostic-services_13.cpp)]

### <a name="requirements"></a>요구 사항

**헤더:** afx.h

##  <a name="afxisvalidaddress"></a>  AfxIsValidAddress

프로그램의 메모리 공간 내에 완전히 포함 되어 있는지 확인 하려면 원하는 메모리 주소를 테스트 합니다.

```
BOOL AfxIsValidAddress(
    const void* lp,
    UINT nBytes,
    BOOL bReadWrite = TRUE);
```

### <a name="parameters"></a>매개 변수

*lp*<br/>
테스트할 메모리 주소를 가리킵니다.

*nBytes*<br/>
테스트할 메모리의 바이트 수가 포함 되어 있습니다.

*bReadWrite*<br/>
메모리 읽기 및 쓰기 (TRUE) 또는 (FALSE)을 읽어서 모두 인지를 지정 합니다.

### <a name="return-value"></a>반환 값

디버그 빌드에서 지정된 된 메모리를 차단 하는 경우 0이 아닌 포함 된 프로그램의 메모리 공간 내에 완전히 그렇지 않으면 0입니다.

디버그가 아닌 빌드에서 0이 아닌 경우 *lp* 0이 고, 그렇지 않으면 NULL입니다.

### <a name="remarks"></a>설명

주소에서 할당 된 블록 제한 되지 않습니다 **새**합니다.

### <a name="example"></a>예제

[!code-cpp[NVC_MFC_Utilities#28](../../mfc/codesnippet/cpp/diagnostic-services_14.cpp)]

### <a name="requirements"></a>요구 사항

**헤더:** afx.h

##  <a name="afxisvalidstring"></a>  AfxIsValidString

이 함수를 사용 하 여 문자열에 대 한 포인터 올바른지 여부를 확인 합니다.

```
BOOL  AfxIsValidString(
    LPCSTR lpsz,
    int nLength = -1);
```

### <a name="parameters"></a>매개 변수

*lpsz*<br/>
테스트에 대 한 포인터입니다.

*nLength*<br/>
테스트할 바이트에서 문자열의 길이 지정 합니다. 값이-1 문자열을 null로 끝나는 된다는 것을 나타냅니다.

### <a name="return-value"></a>반환 값

지정된 된 포인터가; 지정된 된 크기의 문자열을 가리키는 경우 0이 아닌 디버그 빌드에서 그렇지 않으면 0입니다.

디버그가 아닌 빌드에서 0이 아닌 경우 *lpsz* 0이 고, 그렇지 않으면 NULL입니다.

### <a name="example"></a>예제

[!code-cpp[NVC_MFC_Utilities#29](../../mfc/codesnippet/cpp/diagnostic-services_15.cpp)]

### <a name="requirements"></a>요구 사항

**헤더:** afx.h

##  <a name="afxsetallochook"></a>  AfxSetAllocHook

각 메모리 블록 할당 하기 전에 지정 된 함수 호출 수 있도록 하는 후크를 설정 합니다.

```
AFX_ALLOC_HOOK AfxSetAllocHook(AFX_ALLOC_HOOK pfnAllocHook);
```

### <a name="parameters"></a>매개 변수

*pfnAllocHook*<br/>
호출할 함수의 이름을 지정 합니다. 할당 함수 프로토타입에 대 한 설명을 참조 하세요.

### <a name="return-value"></a>반환 값

할당을 허용 하려는 경우 0이 아닌 값 그렇지 않으면 0입니다.

### <a name="remarks"></a>설명

Microsoft Foundation Class 라이브러리 디버그 메모리 할당자는 메모리 할당을 모니터링 하 고 할당 허용 되는지 여부를 제어 하는 사용자를 허용 하는 사용자 정의 후크 함수를 호출할 수 있습니다. 할당 후크 함수는 프로토타입 다음과 같습니다.

**BOOL AFXAPI AllocHook( size_t** `nSize`**, BOOL** `bObject`**, LONG** `lRequestNumber` **);**

*nSize*<br/>
제안 된 메모리 할당의 크기입니다.

*bObject*<br/>
할당에 대 한 경우 TRUE를 `CObject`-파생된 개체가; 그렇지 않으면 FALSE입니다.

*lRequestNumber*<br/>
메모리 할당의 시퀀스 번호입니다.

호출 규칙 AFXAPI 호출 수신자가 스택에서 매개 변수를 제거 해야 의미는 note 합니다.

### <a name="requirements"></a>요구 사항

**헤더:** afx.h

##  <a name="afxdoforallclasses"></a>  AfxDoForAllClasses

지정 된 반복 함수에 대 한 모든 직렬화 가능 호출 `CObject`-응용 프로그램의 메모리 공간에서 클래스를 파생 합니다.

```
void
AFXAPI AfxDoForAllClasses(
    void (* pfn)(const CRuntimeClass* pClass, void* pContext),
    void* pContext);
```

### <a name="parameters"></a>매개 변수

*pfn*<br/>
각 클래스에 대해 호출 되는 반복 함수를 가리킵니다. 함수 인수는에 대 한 포인터를 `CRuntimeClass` 개체 및 함수에 호출자에 게 제공 하는 추가 데이터에 대 한 void 포인터입니다.

*pContext*<br/>
반복 함수 호출자에 게 제공할 수 있는 선택적 데이터를 가리킵니다. 이 포인터는 NULL 일 수 있습니다.

### <a name="remarks"></a>설명

Serializable `CObject`-파생된 클래스는 DECLARE_SERIAL 매크로 사용 하 여 파생 된 클래스입니다. 에 전달 되는 포인터 `AfxDoForAllClasses` 에 *pContext* 를 호출할 때마다 지정 된 반복 함수에 전달 됩니다.

> [!NOTE]
>  이 함수는 MFC의 디버그 버전 에서만에서 작동합니다.

### <a name="example"></a>예제

[!code-cpp[NVC_MFCCollections#113](../../mfc/codesnippet/cpp/diagnostic-services_16.cpp)]

[!code-cpp[NVC_MFCCollections#114](../../mfc/codesnippet/cpp/diagnostic-services_17.cpp)]

### <a name="requirements"></a>요구 사항

**헤더:** afx.h

##  <a name="afxdoforallobjects"></a>  AfxDoForAllObjects

파생 된 모든 개체에 대 한 지정 된 반복 함수를 실행 `CObject` 사용 하 여 할당 된 **새**합니다.

```
void AfxDoForAllObjects(
    void (* pfn)(CObject* pObject, void* pContext),
    void* pContext);
```

### <a name="parameters"></a>매개 변수

*pfn*<br/>
각 개체에 대해 실행 하는 반복 함수를 가리킵니다. 함수 인수는에 대 한 포인터를 `CObject` 및 함수에 호출자에 게 제공 하는 추가 데이터에 대 한 void 포인터입니다.

*pContext*<br/>
반복 함수 호출자에 게 제공할 수 있는 선택적 데이터를 가리킵니다. 이 포인터는 NULL 일 수 있습니다.

### <a name="remarks"></a>설명

전역 스택 또는 포함 된 개체가 열거 되지 않습니다. 에 전달 된 포인터 `AfxDoForAllObjects` 에 *pContext* 를 호출할 때마다 지정 된 반복 함수에 전달 됩니다.

> [!NOTE]
>  이 함수는 MFC의 디버그 버전 에서만에서 작동합니다.

### <a name="example"></a>예제

[!code-cpp[NVC_MFCCollections#115](../../mfc/codesnippet/cpp/diagnostic-services_18.cpp)]

[!code-cpp[NVC_MFCCollections#116](../../mfc/codesnippet/cpp/diagnostic-services_19.cpp)]

## <a name="see-also"></a>참고자료

[매크로 및 전역](mfc-macros-and-globals.md)<br/>
[CObject::Dump](cobject-class.md#dump)
