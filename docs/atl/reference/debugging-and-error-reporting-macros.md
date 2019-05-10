---
title: 디버깅 및 오류 보고 매크로
ms.date: 05/06/2019
f1_keywords:
- atldef/ATL::_ATL_DEBUG_INTERFACES
- atldef/ATL::_ATL_DEBUG_QI
- atldef/ATL::ATLASSERT
- afx/ATL::ATLENSURE
- atltrace/ATL::ATLTRACENOTIMPL
- atltrace/ATL::ATLTRACE
helpviewer_keywords:
- macros, error reporting
ms.assetid: 4da9b87f-ec5c-4a32-ab93-637780909b9d
ms.openlocfilehash: a243351ff337cb517f8a8231c18c495c8d2ca302
ms.sourcegitcommit: da32511dd5baebe27451c0458a95f345144bd439
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/07/2019
ms.locfileid: "65221083"
---
# <a name="debugging-and-error-reporting-macros"></a>디버깅 및 오류 보고 매크로

이러한 매크로 유용한 디버깅 및 추적 기능을 제공합니다.

|||
|-|-|
|[_ATL_DEBUG_INTERFACES](#_atl_debug_interfaces)|모든 인터페이스는 누수 출력 창에 씁니다 때 검색 된 `_Module.Term` 라고 합니다.|
|[_ATL_DEBUG_QI](#_atl_debug_qi)|에 대 한 모든 호출을 기록 `QueryInterface` 출력 합니다.|
|[ATLASSERT](#atlassert)|동일한 기능을 수행 합니다 [_ASSERTE](../../c-runtime-library/reference/assert-asserte-assert-expr-macros.md) 매크로 C 런타임 라이브러리에서 찾을 수 합니다.|
|[ATLENSURE](#atlensure)|매개 변수 유효성 검사를 수행합니다. 호출 `AtlThrow` 필요한 경우|
|[ATLTRACENOTIMPL](#atltracenotimpl)|지정된 된 함수 구현 되지 않았음을 덤프 장치에 메시지를 보냅니다.|
|[ATLTRACE](#atltrace)|지정 된 플래그 및 수준에 따라 디버거 창 같은 출력 장치에 경고를 보고합니다. 이전 버전과 호환성을 위해 포함 되어 있습니다.|
|[ATLTRACE2](#atltrace2)|지정 된 플래그 및 수준에 따라 디버거 창 같은 출력 장치에 경고를 보고합니다.|

##  <a name="_atl_debug_interfaces"></a>  _ATL_DEBUG_INTERFACES

모든 추적 하려면 모든 ATL 헤더 파일을 포함 하기 전에이 매크로 정의할 `AddRef` 및 `Release` 출력 창에 프로그램 구성 요소 인터페이스에서 호출 합니다.

```
#define _ATL_DEBUG_INTERFACES
```

### <a name="remarks"></a>설명

추적 출력은 아래와 같이 표시 됩니다.

`ATL: QIThunk - 2008         AddRef  :   Object = 0x00d81ba0   Refcount = 1   CBug - IBug`

첫 번째 부분은 각 추적은 항상 `ATL: QIThunk`합니다. 다음은 특정을 식별 하는 값 *썽크 인터페이스* 사용 합니다. 인터페이스 썽크는 참조 횟수를 유지 관리 하 고 여기에 추적 기능을 제공 하는 데는 개체입니다. 새 인터페이스 썽크를 호출할 때마다 만들어집니다 `QueryInterface` 에 대 한 요청 제외 하 고는 `IUnknown` 인터페이스 (이 경우 동일한 썽크 반환 됨 때마다 COM identity 규칙을 준수 하기 위해).

다음 보면 `AddRef` 또는 `Release` 호출 된 메서드를 나타내는입니다. 그런 다음, 해당 인터페이스 참조 횟수가 변경 된 개체를 식별 하는 값을 볼 수 있습니다. 추적 값을 **이** 개체의 포인터입니다.

추적 되는 참조 개수는 해당 썽크 후의 참조 횟수가 `AddRef` 또는 `Release` 호출 되었습니다. 참고가 참조 카운트는 개체에 대 한 참조 횟수를 일치 하지 않을 수 있습니다. 각 썽크 완전히 COM의 참조 횟수 규칙을 준수 하는 데 자체 참조 횟수를 유지 관리 합니다.

추적 정보의 마지막 부분이 개체와 영향을 받지 않도록 하는 인터페이스의 이름인 합니다 `AddRef` 또는 `Release` 호출 합니다.

누수 서버 종료 될 때 검색 되는 모든 인터페이스 및 `_Module.Term` 는 이라고 같이 기록:

`ATL: QIThunk - 2005         LEAK    :   Object = 0x00d81ca0   Refcount = 1   MaxRefCount = 1   CBug - IBug`

정보를 여기에 제공 된 이전 추적 문에 제공 하는 정보에 직접 매핑됩니다, 인터페이스 썽크를의 전체 수명 동안에 참조 횟수를 검사할 수 있도록 합니다. 또한 해당 인터페이스 썽크에서 최대 참조 횟수를 나타내는 값을 가져옵니다.

> [!NOTE]
> _ATL_DEBUG_INTERFACES 정품 빌드에 사용할 수 있습니다.

##  <a name="_atl_debug_qi"></a>  _ATL_DEBUG_QI

에 대 한 모든 호출을 기록 `QueryInterface` 출력 합니다.

```
#define _ATL_DEBUG_QI
```

### <a name="remarks"></a>설명

호출 하는 경우 `QueryInterface` 실패, 출력 창 표시 됩니다.

*인터페이스 이름* - `failed`

##  <a name="atlassert"></a>  ATLASSERT

ATLASSERT 매크로와 동일한 기능을 수행 합니다 [_ASSERTE](../../c-runtime-library/reference/assert-asserte-assert-expr-macros.md) 매크로 C 런타임 라이브러리에서 찾을 수 있습니다.

```
ATLASSERT(booleanExpression);
```

### <a name="parameters"></a>매개 변수

*booleanExpression*<br/>
0이 아닌 값 또는 0으로 계산되는 식(포인터 포함)입니다.

### <a name="remarks"></a>설명

디버그 빌드에서 ATLASSERT 평가 *booleanExpression* 결과가 false 인 경우 디버그 보고서를 생성 합니다.

## <a name="requirements"></a>요구 사항

**헤더:** atldef.h

##  <a name="atlensure"></a>  ATLENSURE

이 매크로 함수에 전달 하는 매개 변수 유효성 검사에 사용 됩니다.

```
ATLENSURE(booleanExpression);
ATLENSURE_THROW(booleanExpression, hr);
```

### <a name="parameters"></a>매개 변수

*booleanExpression*<br/>
테스트할 부울 식을 지정 합니다.

*hr*<br/>
반환할 오류 코드를 지정 합니다.

### <a name="remarks"></a>설명

이러한 매크로 검색 하 여 잘못 된 매개 변수 사용의 사용자에 게 알림 메커니즘을 제공 합니다.

매크로가 호출 ATLASSERT 및 호출의 조건이 실패 하는 경우 `AtlThrow`합니다.

ATLENSURE 경우에서 `AtlThrow` E_FAIL을 사용 하 여 호출 됩니다.

ATLENSURE_THROW 경우에서 `AtlThrow` 지정된 된 HRESULT를 사용 하 여 호출 됩니다.

ATLENSURE ATLASSERT 사이의 차이점은 ATLENSURE 빌드에서 릴리스도 디버그 빌드에서 같이 예외를 throw 합니다.

### <a name="example"></a>예제

[!code-cpp[NVC_ATL_Utilities#108](../../atl/codesnippet/cpp/debugging-and-error-reporting-macros_1.cpp)]

## <a name="requirements"></a>요구 사항

**헤더:** afx.h

##  <a name="atltracenotimpl"></a>  ATLTRACENOTIMPL

ATL의 디버그 빌드에서 문자열을 보내는 " *funcname* 구현 되지 않음" 덤프 장치 및 E_NOTIMPL 반환 합니다.

```
ATLTRACENOTIMPL(funcname);
```

### <a name="parameters"></a>매개 변수

*funcname*<br/>
[in] 구현 되지 않는 함수의 이름을 포함 하는 문자열입니다.

### <a name="remarks"></a>설명

릴리스 빌드에서 단순히 E_NOTIMPL을 반환합니다.

### <a name="example"></a>예제

[!code-cpp[NVC_ATL_Utilities#127](../../atl/codesnippet/cpp/debugging-and-error-reporting-macros_2.cpp)]

## <a name="requirements"></a>요구 사항

**헤더:** atltrace.h

##  <a name="atltrace"></a>  ATLTRACE

지정 된 플래그 및 수준에 따라 디버거 창 같은 출력 장치에 경고를 보고합니다. 이전 버전과 호환성을 위해 포함 되어 있습니다.

```
ATLTRACE(exp);

ATLTRACE(
    DWORD category,
    UINT  level,
    LPCSTR lpszFormat, ...);
```

### <a name="parameters"></a>매개 변수

*exp*<br/>
[in] 문자열 및 출력 창이 나 이러한 메시지를 트래핑 하는 모든 응용 프로그램에 보낼 변수입니다.

*category*<br/>
[in] 보고서에는 메서드 또는 이벤트의 형식입니다. 범주 목록에 대 한 설명을 참조 하세요.

*level*<br/>
[in] 보고서에 대 한 추적의 수준입니다. 자세한 내용은 설명 부분을 참조 하세요.

*lpszFormat*<br/>
[in] 덤프 장치에 보낼 서식이 지정 된 문자열입니다.

### <a name="remarks"></a>설명

참조 [ATLTRACE2](#atltrace2) ATLTRACE에 대 한 합니다. ATLTRACE 및 ATLTRACE2 동일 하 게 동작, ATLTRACE 이전 버전과 호환성을 위해 포함 되었습니다.

##  <a name="atltrace2"></a>  ATLTRACE2

지정 된 플래그 및 수준에 따라 디버거 창 같은 출력 장치에 경고를 보고합니다.

```
ATLTRACE2(exp);

ATLTRACE2(
    DWORD category,
    UINT level,
    LPCSTRlpszFormat,  ...);
```

### <a name="parameters"></a>매개 변수

*exp*<br/>
[in] 출력 창이 나 이러한 메시지를 트래핑 하는 모든 응용 프로그램에 보낼 문자열입니다.

*category*<br/>
[in] 보고서에는 메서드 또는 이벤트의 형식입니다. 범주 목록에 대 한 설명을 참조 하세요.

*level*<br/>
[in] 보고서에 대 한 추적의 수준입니다. 자세한 내용은 설명 부분을 참조 하세요.

*lpszFormat*<br/>
[in] `printf`-덤프 장치에 보낼 문자열을 만드는 데 사용할 형식 문자열 스타일입니다.

### <a name="remarks"></a>설명

ATLTRACE2의 약식 형태는 디버거의 출력 창에 문자열을 씁니다. ATLTRACE2의 두 번째 형태도 디버거의 출력 창에 출력 쓰기 이지만 ATL/MFC 추적 도구의 설정을 따릅니다 (참조 [ATLTraceTool 샘플](../../overview/visual-cpp-samples.md)). 예를 들어 설정한 *수준* 4를 수준 0으로 ATL/MFC 추적 도구가 표시 되지 것입니다 메시지입니다. *수준* 0, 1, 2, 3 또는 4 일 수 있습니다. 기본적으로 0의 가장 심각한 문제만 보고합니다.

합니다 *범주* 매개 변수는 설정 하는 추적 플래그를 나열 합니다. 이러한 플래그를 보고 하려는 메서드의 유형에 해당 합니다. 아래 표에 나열 되어 사용할 수 있습니다 올바른 추적 플래그를 *범주* 매개 변수입니다.

### <a name="atl-trace-flags"></a>ATL 추적 플래그

|ATL 범주|설명|
|------------------|-----------------|
|`atlTraceGeneral`|ATL에 대 한 응용 프로그램을 모두 보고 합니다. 기본값입니다.|
|`atlTraceCOM`|COM 메서드를 보고 합니다.|
|`atlTraceQI`|QueryInterface 호출을 보고 합니다.|
|`atlTraceRegistrar`|개체의 등록에 보고 합니다.|
|`atlTraceRefcount`|보고 참조 횟수를 변경 합니다.|
|`atlTraceWindowing`|Windows 메서드;에 대 한 보고서 예를 들어 잘못 된 메시지 맵 ID를 보고|
|`atlTraceControls`|컨트롤에 대 한 보고서 예를 들어, 컨트롤 또는 해당 창을 소멸 될 때 보고 합니다.|
|`atlTraceHosting`|메시지를 호스트 하는 보고서 예를 들어, 컨테이너에서 클라이언트가 활성화 될 때 보고 합니다.|
|`atlTraceDBClient`|OLE DB 소비자 템플릿;에 대 한 보고서 예를 들어, GetData 실패 호출, 출력 HRESULT를 포함할 수 있습니다.|
|`atlTraceDBProvider`|OLE DB 공급자 템플릿;에 대 한 보고서 예를 들어 열 생성에 실패 하는 경우 보고 합니다.|
|`atlTraceSnapin`|MMC 스냅인 응용 프로그램에 대해 보고 합니다.|
|`atlTraceNotImpl`|표시 된 함수 구현 되지 않았음을 보고 합니다.|
|`atlTraceAllocation`|디버깅 도구 atldbgmem.h에서 메모리에 의해 인쇄 되는 메시지를 보고 합니다.|

### <a name="mfc-trace-flags"></a>MFC 추적 플래그

|MFC 범주|설명|
|------------------|-----------------|
|`traceAppMsg`|범용, MFC 메시지입니다. 좋습니다.|
|`traceDumpContext`|메시지 [CDumpContext](../../mfc/reference/cdumpcontext-class.md)합니다.|
|`traceWinMsg`|코드를 처리 하는 MFC의 메시지에서 메시지입니다.|
|`traceMemory`|MFC의 메모리 관리 코드에서 메시지입니다.|
|`traceCmdRouting`|MFC의 Windows에서 메시지 라우팅 코드를 명령입니다.|
|`traceHtml`|MFC의 DHTML 대화 지원 메시지입니다.|
|`traceSocket`|MFC의 소켓 지원 메시지입니다.|
|`traceOle`|MFC의 OLE 지원에서 메시지입니다.|
|`traceDatabase`|MFC 데이터베이스 지원에서 메시지입니다.|
|`traceInternet`|MFC의 인터넷에서 메시지를 지원 합니다.|

사용자 지정 추적 범주를 선언 하려면의 전역 인스턴스를 선언 합니다 `CTraceCategory` 다음과 같이 클래스:

[!code-cpp[NVC_ATL_Utilities#109](../../atl/codesnippet/cpp/debugging-and-error-reporting-macros_3.cpp)]

이 예제에서는 MY_CATEGORY 범주 이름에 지정할 이름인 합니다 *범주* 매개 변수입니다. 첫 번째 매개 변수는 ATL/MFC 추적 도구에서 표시 되는 범주 이름입니다. 두 번째 매개 변수는 기본 추적 수준입니다. 이 매개 변수는 선택적 이며 기본 추적 수준을 0입니다.

사용 하려면 사용자 정의 범주:

[!code-cpp[NVC_ATL_Utilities#110](../../atl/codesnippet/cpp/debugging-and-error-reporting-macros_4.cpp)]

추적 메시지를 필터링 하려면를 지정 하려면 이러한 매크로 대 한 정의 하기 전에 Stdafx.h에 삽입 된 `#include <atlbase.h>` 문입니다.

또는의 전처리기 지시문에서 필터를 설정할 수 있습니다 합니다 **속성 페이지** 대화 상자. 클릭 합니다 **전처리기** 탭 한 다음에 전역를 삽입 합니다 **전처리기 정의** 편집 상자입니다.

ATLTRACE2 매크로의 기본 정의 포함 하는 Atlbase.h 및 atlbase.h가 처리 되기 전에 이러한 기호를 정의 하지 않으면 하는 경우 이러한 정의 사용 됩니다.

릴리스 빌드에서 ATLTRACE2 컴파일함으로써 `(void) 0`합니다.

ATLTRACE2 서식 지정 후 1,024 개 이상의 문자, 덤프 장치에 보낼 문자열의 내용을 제한 합니다.

ATLTRACE 및 ATLTRACE2 동일 하 게 동작, ATLTRACE 이전 버전과 호환성을 위해 포함 되었습니다.

### <a name="example"></a>예제

[!code-cpp[NVC_ATL_Utilities#111](../../atl/codesnippet/cpp/debugging-and-error-reporting-macros_5.cpp)]

## <a name="see-also"></a>참고자료

[매크로](../../atl/reference/atl-macros.md)<br/>
[디버깅 및 오류 보고 전역 함수](../../atl/reference/debugging-and-error-reporting-global-functions.md)
