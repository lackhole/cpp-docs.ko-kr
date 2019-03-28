---
title: CStringT 클래스
ms.date: 03/27/2019
f1_keywords:
- CStringT
- ATLSTR/ATL::CStringT
- ATLSTR/ATL::CStringT::CStringT
- ATLSTR/ATL::CStringT::AllocSysString
- ATLSTR/ATL::CStringT::AnsiToOem
- ATLSTR/ATL::CStringT::AppendFormat
- ATLSTR/ATL::CStringT::Collate
- ATLSTR/ATL::CStringT::CollateNoCase
- ATLSTR/ATL::CStringT::Compare
- ATLSTR/ATL::CStringT::CompareNoCase
- ATLSTR/ATL::CStringT::Delete
- ATLSTR/ATL::CStringT::Find
- ATLSTR/ATL::CStringT::FindOneOf
- ATLSTR/ATL::CStringT::Format
- ATLSTR/ATL::CStringT::FormatMessage
- ATLSTR/ATL::CStringT::FormatMessageV
- ATLSTR/ATL::CStringT::FormatV
- ATLSTR/ATL::CStringT::GetEnvironmentVariable
- ATLSTR/ATL::CStringT::Insert
- ATLSTR/ATL::CStringT::Left
- ATLSTR/ATL::CStringT::LoadString
- ATLSTR/ATL::CStringT::MakeLower
- ATLSTR/ATL::CStringT::MakeReverse
- ATLSTR/ATL::CStringT::MakeUpper
- ATLSTR/ATL::CStringT::Mid
- ATLSTR/ATL::CStringT::OemToAnsi
- ATLSTR/ATL::CStringT::Remove
- ATLSTR/ATL::CStringT::Replace
- ATLSTR/ATL::CStringT::ReverseFind
- ATLSTR/ATL::CStringT::Right
- ATLSTR/ATL::CStringT::SetSysString
- ATLSTR/ATL::CStringT::SpanExcluding
- ATLSTR/ATL::CStringT::SpanIncluding
- ATLSTR/ATL::CStringT::Tokenize
- ATLSTR/ATL::CStringT::Trim
- ATLSTR/ATL::CStringT::TrimLeft
- ATLSTR/ATL::CStringT::TrimRight
- CSTRINGT/CStringT
- CSTRINGT/CStringT::CStringT
- CSTRINGT/CStringT::AllocSysString
- CSTRINGT/CStringT::AnsiToOem
- CSTRINGT/CStringT::AppendFormat
- CSTRINGT/CStringT::Collate
- CSTRINGT/CStringT::CollateNoCase
- CSTRINGT/CStringT::Compare
- CSTRINGT/CStringT::CompareNoCase
- CSTRINGT/CStringT::Delete
- CSTRINGT/CStringT::Find
- CSTRINGT/CStringT::FindOneOf
- CSTRINGT/CStringT::Format
- CSTRINGT/CStringT::FormatMessage
- CSTRINGT/CStringT::FormatMessageV
- CSTRINGT/CStringT::FormatV
- CSTRINGT/CStringT::GetEnvironmentVariable
- CSTRINGT/CStringT::Insert
- CSTRINGT/CStringT::Left
- CSTRINGT/CStringT::LoadString
- CSTRINGT/CStringT::MakeLower
- CSTRINGT/CStringT::MakeReverse
- CSTRINGT/CStringT::MakeUpper
- CSTRINGT/CStringT::Mid
- CSTRINGT/CStringT::OemToAnsi
- CSTRINGT/CStringT::Remove
- CSTRINGT/CStringT::Replace
- CSTRINGT/CStringT::ReverseFind
- CSTRINGT/CStringT::Right
- CSTRINGT/CStringT::SetSysString
- CSTRINGT/CStringT::SpanExcluding
- CSTRINGT/CStringT::SpanIncluding
- CSTRINGT/CStringT::Tokenize
- CSTRINGT/CStringT::Trim
- CSTRINGT/CStringT::TrimLeft
- CSTRINGT/CStringT::TrimRight
helpviewer_keywords:
- strings [C++], in ATL
- shared classes, CStringT
- CStringT class
ms.assetid: 7cacc59c-425f-40f1-8f5b-6db921318ec9
ms.openlocfilehash: 327ffc40a9b7e41004bc5aac7ecc320076de537f
ms.sourcegitcommit: 309dc532f13242854b47759cef846de59bb807f1
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/28/2019
ms.locfileid: "58565820"
---
# <a name="cstringt-class"></a>CStringT 클래스

이 클래스를 나타냅니다는 `CStringT` 개체입니다.

## <a name="syntax"></a>구문

```
template<typename BaseType, class StringTraits>
class CStringT :
    public CSimpleStringT<BaseType,
        _CSTRING_IMPL_::_MFCDLLTraitsCheck<BaseType, StringTraits>::c_bIsMFCDLLTraits>
```

#### <a name="parameters"></a>매개 변수

*BaseType*<br/>
String 클래스의 문자 형식입니다. 다음 중 하나일 수 있습니다.

- **char** (용 ANSI 문자열)입니다.

- **wchar_t** (용 유니코드 문자열)입니다.

- TCHAR (ANSI 및 유니코드 문자열)에 대 한 합니다.

*StringTraits*<br/>
String 클래스 C 런타임 (CRT) 라이브러리 지원 및 문자열 리소스가 있는 경우 결정 합니다. 다음 중 하나일 수 있습니다.

- **StrTraitATL< wchar_t** &#124; **char** &#124; **TCHAR, ChTraitsCRT< wchar_t** &#124; **char** &#124; **TCHAR > >**

   클래스에 필요한 CRT 지원 및 리소스 문자열에 지정 된 모듈에 대해 검색 `m_hInstResource` (응용 프로그램의 모듈 클래스의 멤버).

- **StrTraitATL < wchar_t** &#124; **char** &#124; **TCHAR, ChTraitsOS < wchar_t** &#124; **char** &#124;  **TCHAR >>**

   클래스에는 CRT 지원 및 리소스 문자열에 지정 된 모듈에 대해 검색 않아도 `m_hInstResource` (응용 프로그램의 모듈 클래스의 멤버).

- **StrTraitMFC< wchar_t** &#124; **char** &#124; **TCHAR, ChTraitsCRT< wchar_t** &#124; **char** &#124; **TCHAR > >**

   클래스는 CRT 지원 및 표준 MFC 검색 알고리즘을 사용 하 여 리소스 문자열을 검색 해야 합니다.

- **StrTraitMFC < wchar_t** &#124; **char** &#124; **TCHAR, ChTraitsOS < wchar_t** &#124; **char** &#124;  **TCHAR >>**

   클래스에는 CRT 지원 및 표준 MFC 검색 알고리즘을 사용 하 여 리소스 문자열을 검색 필요 하지 않습니다.

## <a name="members"></a>멤버

### <a name="public-constructors"></a>Public 생성자

|이름|설명|
|----------|-----------------|
|[CStringT::CStringT](#cstringt)|생성 된 `CStringT` 다양 한 방법으로 개체입니다.|
|[CStringT::~CStringT](#_dtorcstringt)|`CStringT` 개체를 제거합니다.|

### <a name="public-methods"></a>Public 메서드

|이름|설명|
|----------|-----------------|
|[CStringT::AllocSysString](#allocsysstring)|BSTR에서 할당 `CStringT` 데이터입니다.|
|[CStringT::AnsiToOem](#ansitooem)|ANSI 문자를 OEM 문자 집합에는 전체 변환할 수 있습니다.|
|[CStringT::AppendFormat](#appendformat)|서식이 지정 된 데이터를 기존 추가 `CStringT` 개체입니다.|
|[CStringT::Collate](#collate)|(대 소문자를 구분을 사용 하 여 로캘별 정보)에 두 문자열을 비교 합니다.|
|[CStringT::CollateNoCase](#collatenocase)|(대/소문자 구분 안 함, 사용 하 여 로캘별 정보)에 두 문자열을 비교 합니다.|
|[CStringT::Compare](#compare)|(대/소문자 구분) 두 문자열을 비교 합니다.|
|[CStringT::CompareNoCase](#comparenocase)|(대/소문자 구분) 두 문자열을 비교 합니다.|
|[CStringT::Delete](#delete)|문자열에서 문자 또는 문자를 삭제합니다.|
|[CStringT::Find](#find)|문자 또는 더 큰 문자열 내에서 부분 문자열을 찾습니다.|
|[CStringT::FindOneOf](#findoneof)|집합에서 일치 하는 첫 번째 문자를 찾습니다.|
|[CStringT::Format](#format)|문자열 형식 `sprintf` 않습니다.|
|[CStringT::FormatMessage](#formatmessage)|메시지 문자열의 서식을 지정합니다.|
|[CStringT::FormatMessageV](#formatmessagev)|가변 인수 목록을 사용 하 여 메시지 문자열의 서식을 지정 합니다.|
|[CStringT::FormatV](#formatv)|변수 인수 목록을 사용 하 여 문자열의 형식을 지정 합니다.|
|[CStringT::GetEnvironmentVariable](#getenvironmentvariable)|지정 된 환경 변수의 값으로 문자열을 설정합니다.|
|[CStringT::Insert](#insert)|문자열 내에서 지정된 된 인덱스에 단일 문자 또는 부분 문자열을 삽입합니다.|
|[CStringT::Left](#left)|문자열의 왼쪽된 부분을 추출합니다.|
|[CStringT::LoadString](#loadstring)|기존 로드 `CStringT` Windows 리소스 개체입니다.|
|[CStringT::MakeLower](#makelower)|모든는이 문자열의에서 문자를 소문자로 변환 합니다.|
|[CStringT::MakeReverse](#makereverse)|문자열을 반대로 바꿉니다.|
|[CStringT::MakeUpper](#makeupper)|이 문자열을 대문자로의 모든 문자를 변환 합니다.|
|[CStringT::Mid](#mid)|문자열의 가운데 부분을 추출합니다.|
|[CStringT::OemToAnsi](#oemtoansi)|OEM 문자 집합을 ANSI 문자 집합으로 전체도 변환할 수 있습니다.|
|[CStringT::Remove](#remove)|제거는 문자열에서 문자를 표시 합니다.|
|[CStringT::Replace](#replace)|대체 다른 문자를 사용 하 여 문자를 표시 합니다.|
|[CStringT::ReverseFind](#reversefind)|더 큰 문자열; 내에서 문자를 찾습니다. 끝에서 시작 됩니다.|
|[CStringT::Right](#right)|문자열의 오른쪽 부분을 추출합니다.|
|[CStringT::SetSysString](#setsysstring)|설정에서 데이터를 사용 하 여 기존 BSTR 개체는 `CStringT` 개체입니다.|
|[CStringT::SpanExcluding](#spanexcluding)|로 식별 되는 문자 집합에 있지 않은 첫 번째 문자부터 문자열에서 문자를 추출 `pszCharSet`합니다.|
|[CStringT::SpanIncluding](#spanincluding)|집합의 문자만 포함 된 하위 문자열을 추출 합니다.|
|[CStringT::Tokenize](#tokenize)|추출 대상 문자열에 토큰을 지정 합니다.|
|[CStringT::Trim](#trim)|문자열에서 모든 선행 및 후행 공백 문자를 삭제합니다.|
|[CStringT::TrimLeft](#trimleft)|문자열에서 선행 공백 문자를 삭제 합니다.|
|[CStringT::TrimRight](#trimright)|후행 공백 문자는 문자열에서 삭제 합니다.|

### <a name="operators"></a>연산자

|||
|-|-|
|[CStringT::operator =](#operator_eq)|새 값을 할당 한 `CStringT` 개체입니다.|
|[CStringT::operator +](#operator_add)|두 문자열 또는 문자 및 문자열을 연결합니다.|
|[CStringT::operator + =](#operator_add_eq)|기존 문자열의 끝에 새 문자열을 연결합니다.|
|[CStringT::operator = =](#operator_eq_eq)|두 문자열이 논리적으로 같은지 여부를 결정 합니다.|
|[CStringT::operator !=](#operator_neq)|두 문자열이 없는 경우 논리적으로 같은지 확인 합니다.|
|[CStringT::operator &lt;](#operator_lt)|연산자의 좌 변에 있는 문자열 미만 있는지 여부를 결정 오른쪽에 있는 문자열입니다.|
|[CStringT::operator &gt;](#operator_gt)|연산자의 좌 변에 있는 문자열은 오른쪽에 문자열 보다 큰 경우를 결정 합니다.|
|[CStringT::operator &lt;=](#operator_lt_eq)|연산자의 좌 변에 있는 문자열 오른쪽에 문자열 보다 작거나 인지 확인 합니다.|
|[CStringT::operator &gt;=](#operator_gt_eq)|연산자의 좌 변에 있는 문자열 오른쪽에 문자열 보다 크거나 같은 경우 인지 확인 합니다.|

## <a name="remarks"></a>설명

`CStringT` 상속 [CSimpleStringT 클래스](../../atl-mfc-shared/reference/csimplestringt-class.md)합니다. 문자 조작, 정렬 및 검색 등의 고급 기능에서 구현 됩니다 `CStringT`합니다.

> [!NOTE]
> `CStringT` 개체는 예외를 throw 할 수 있습니다. 이런 경우는 `CStringT` 개체 어떤 이유로 메모리가 부족 합니다.

`CStringT` 문자의 가변 길이 시퀀스 개체를 구성 합니다. `CStringT` 함수 및 연산자는 Basic와 유사한 구문을 사용 하 여 제공 합니다. 연결 및 간소화 된 메모리 관리와 함께 비교 연산자를 사용 하면 `CStringT` 개체 일반 문자 배열 보다 사용 하기 쉽습니다.

> [!NOTE]
>  만들 수는 있지만 `CStringT` 에 대해 권장 인스턴스가 포함 된 null 문자를 포함 합니다. 메서드 및 연산자를 호출 `CStringT` 포함 된 null 문자를 포함 하는 개체에 의도 하지 않은 결과가 발생할 수 있습니다.

다양 한 조합을 사용 하 여는 `BaseType` 하 고 `StringTraits` 매개 변수를 `CStringT` 수는 다음 형식에서 돌아와가 미리 정의한 ATL 라이브러리 개체입니다.

ATL 응용 프로그램에서 사용 하 여 하는 경우:

`CString`하십시오 `CStringA`, 및 `CStringW` (MFC90 MFC DLL에서 내보낸. DLL), 사용자 Dll에서 하지 않습니다. 방지 하기 위해 이렇게 `CStringT` 에서 여러 번 정의 되 고 있습니다.

> [!NOTE]
>  코드에 설명 된 링커 오류에 대 한 해결 방법을 포함 하는 경우 [CStringT를 사용 하 여 문자열 클래스 내보내기](../../atl-mfc-shared/exporting-string-classes-using-cstringt.md), 해당 코드를 제거 해야 합니다. 필요 하지 않습니다.

MFC 기반 응용 프로그램 내에서 사용 가능한 다음 문자열 형식은 다음과 같습니다.

|CStringT 형식|선언|
|-------------------|-----------------|
|`CStringA`|ANSI 문자 CRT 지원 포함 된 문자열을 입력 합니다.|
|`CStringW`|유니코드 문자 CRT 지원 포함 된 문자열을 입력 합니다.|
|`CString`|Crt 사용 하 여 ANSI 및 유니코드 문자 형식입니다.|

다음 문자열 형식은 다음과 같습니다. 프로젝트에서 사용할 수 있는 ATL_CSTRING_NO_CRT 정의 되어 있는

|CStringT 형식|선언|
|-------------------|-----------------|
|`CAtlStringA`|ANSI 문자 CRT 지원 하지 않는 문자열을 입력 합니다.|
|`CAtlStringW`|유니코드 문자는 CRT 지원 하지 않는 문자열을 입력 합니다.|
|`CAtlString`|CRT 지원 하지 않는 ANSI 및 유니코드 문자 형식입니다.|

문자열은 프로젝트에서 사용할 수 ATL_CSTRING_NO_CRT 정의 되어 있지 않습니다.

|CStringT 형식|선언|
|-------------------|-----------------|
|`CAtlStringA`|ANSI 문자 CRT 지원 포함 된 문자열을 입력 합니다.|
|`CAtlStringW`|유니코드 문자 CRT 지원 포함 된 문자열을 입력 합니다.|
|`CAtlString`|Crt 사용 하 여 ANSI 및 유니코드 문자 형식입니다.|

`CString` 개체의 수도 특징이 있습니다.

- `CStringT` 개체는 연결 작업의 결과로 증가할 수 있습니다.

- `CStringT` 개체에 따라 "의미 체계를 값입니다." 생각할는 `CStringT` 는 실제 문자열로, 문자열로 포인터가 아니라 개체입니다.

- 자유롭게 대체할 수 있습니다 `CStringT` 에 대 한 개체 `PCXSTR` 함수 인수입니다.

- 문자열 버퍼에 대 한 사용자 지정 메모리 관리 합니다. 자세한 내용은 [메모리 관리 및 CStringT](../../atl-mfc-shared/memory-management-with-cstringt.md)합니다.

## <a name="cstringt-predefined-types"></a>CStringT 미리 정의 된 형식

때문에 `CStringT` 문자 형식을 정의 하는 템플릿 인수를 사용 하 여 (중 하나 [wchar_t](../../c-runtime-library/standard-types.md) 또는 [char](../../c-runtime-library/standard-types.md)) 지원 메서드 매개 변수 형식 복잡할 수에 합니다. 이 문제를 단순화 하기 위해 미리 정의 된 형식 집합이 정의 되 고 전체에서 사용 된 `CStringT` 클래스입니다. 다음 표에서 다양 한 유형을 나열합니다.

|이름|설명|
|----------|-----------------|
|`XCHAR`|단일 문자 (하거나 **wchar_t** 또는 **char**) 같은 문자 유형으로 `CStringT` 개체입니다.|
|`YCHAR`|단일 문자 (하거나 **wchar_t** 또는 **char**)으로 반대 문자 형식을 사용 하 여는 `CStringT` 개체입니다.|
|`PXSTR`|문자열에 대 한 포인터 (하거나 **wchar_t** 또는 **char**) 같은 문자 유형으로 `CStringT` 개체입니다.|
|`PYSTR`|문자열에 대 한 포인터 (하거나 **wchar_t** 또는 **char**)으로 반대 문자 형식을 사용 하 여는 `CStringT` 개체입니다.|
|`PCXSTR`|에 대 한 포인터를 **const** 문자열 (하거나 **wchar_t** 또는 **char**) 같은 문자 유형으로 `CStringT` 개체입니다.|
|`PCYSTR`|에 대 한 포인터를 **const** 문자열 (하거나 **wchar_t** 또는 **char**) 반대 문자 유형으로 `CStringT` 개체입니다.|

> [!NOTE]
>  이전에 문서화 되지 않은 메서드를 사용 하는 코드 `CString` (같은 `AssignCopy`)의 문서화 된 다음 메서드를 사용 하는 코드를 사용 하 여 바꾸어야 `CStringT` (같은 `GetBuffer` 또는 `ReleaseBuffer`). 이러한 메서드는 상속 `CSimpleStringT`합니다.

## <a name="inheritance-hierarchy"></a>상속 계층 구조

[CSimpleStringT](../../atl-mfc-shared/reference/csimplestringt-class.md)

`CStringT`

## <a name="requirements"></a>요구 사항

|헤더|에 대 한 사용|
|------------|-------------|
|cstringt.h|MFC 전용 string 개체|
|atlstr.h|비 MFC 문자열 개체|

##  <a name="allocsysstring"></a>  CStringT::AllocSysString

Automation 호환 문자열을 BSTR 형식를 할당 하 고의 내용을 복사는 `CStringT` 개체로, null 종결 문자를 포함 하 여 합니다.

```
BSTR AllocSysString() const;
```

### <a name="return-value"></a>반환 값

새로 할당 된 문자열입니다.

### <a name="remarks"></a>설명

MFC 프로그램에는 [CMemoryException 클래스](../../mfc/reference/cmemoryexception-class.md) 메모리가 부족 하 여 없으면 throw 됩니다. ATL 프로그램에서을 [CAtlException](../../atl/reference/catlexception-class.md) throw 됩니다. 이 함수는 Automation에 대 한 문자열을 반환 하려면 일반적으로 사용 됩니다.

일반적으로이 문자열은 COM 함수에 전달 하는 경우 [in] 매개 변수를 다음이 필요 호출자가 해제할 문자열입니다. 사용 하 여 이렇게 [SysFreeString](/windows/desktop/api/oleauto/nf-oleauto-sysfreestring)Windows SDK에 설명 된 대로 합니다. 자세한 내용은 [Allocating 및 BSTR에 대해 메모리를 해제](../../atl-mfc-shared/allocating-and-releasing-memory-for-a-bstr.md)합니다.

Windows에서 OLE 할당 함수에 대 한 자세한 내용은 참조 하세요. [SysAllocString](/windows/desktop/api/oleauto/nf-oleauto-sysallocstring) Windows SDK에 있습니다.

### <a name="example"></a>예제

다음 예에서는 `CStringT::AllocSysString`의 사용법을 보여줍니다.

[!code-cpp[NVC_ATLMFC_Utilities#105](../../atl-mfc-shared/codesnippet/cpp/cstringt-class_1.cpp)]

##  <a name="ansitooem"></a>  CStringT::AnsiToOem

이 모든 문자가 변환 `CStringT` ANSI 문자를 OEM 문자 집합에는 개체입니다.

```
void AnsiToOem();
```

### <a name="remarks"></a>설명

함수는 _UNICODE가 정의 된 경우에 사용할 수 없는 경우

### <a name="example"></a>예제

[!code-cpp[NVC_ATLMFC_Utilities#106](../../atl-mfc-shared/codesnippet/cpp/cstringt-class_2.cpp)]

##  <a name="appendformat"></a>  CStringT::AppendFormat

서식이 지정 된 데이터를 기존 추가 `CStringT` 개체입니다.

```
void __cdecl AppendFormat(PCXSTR pszFormat, [, argument] ...);
void __cdecl AppendFormat(UINT nFormatID, [, argument] ...);
```

### <a name="parameters"></a>매개 변수

*pszFormat*<br/>
형식 컨트롤 문자열입니다.

*nFormatID*<br/>
형식 컨트롤 문자열을 포함 하는 문자열 리소스 식별자입니다.

*argument*<br/>
선택적 인수입니다.

### <a name="remarks"></a>설명

이 함수는 형식 및 일련의 문자 및 값에 추가 된 `CStringT`합니다. 각 선택적 인수 (있는 경우) 변환 되 고 해당 형식 사양에 따라 추가 *pszFormat* 식별 되는 문자열 리소스의 들어오거나 *nFormatID*합니다.

### <a name="example"></a>예제

[!code-cpp[NVC_ATLMFC_Utilities#107](../../atl-mfc-shared/codesnippet/cpp/cstringt-class_3.cpp)]

##  <a name="collate"></a>  CStringT::Collate

일반 텍스트 함수를 사용 하 여 두 문자열을 비교 `_tcscoll`합니다.

```
int Collate(PCXSTR psz) const throw();
```

### <a name="parameters"></a>매개 변수

*psz*<br/>
다른 문자열 비교에 사용 됩니다.

### <a name="return-value"></a>반환 값

문자열이 동일한 경우 0이 고, < 0이 `CStringT` 개체가 보다 작거나 *psz*, 또는 > 0이 `CStringT` 개체 보다 크면 *psz*합니다.

### <a name="remarks"></a>설명

제네릭 텍스트 함수인 `_tcscoll`, TCHAR에서 정의 됩니다. H, 중 하나에 매핑됩니다 `strcoll`, `wcscoll`, 또는 `_mbscoll`컴파일 타임에 정의 된 문자 집합에 따라 합니다. 각 함수에 따라 사용 중인 코드 페이지에 따라 문자열의 대/소문자 구분 비교를 수행 하는 현재 합니다. 자세한 내용은 [strcoll, wcscoll, _mbscoll, _strcoll_l, _wcscoll_l, _mbscoll_l](../../c-runtime-library/reference/strcoll-wcscoll-mbscoll-strcoll-l-wcscoll-l-mbscoll-l.md)합니다.

##  <a name="collatenocase"></a>  CStringT::CollateNoCase

일반 텍스트 함수를 사용 하 여 두 문자열을 비교 `_tcscoll`합니다.

```
int CollateNoCase(PCXSTR psz) const throw();
```

### <a name="parameters"></a>매개 변수

*psz*<br/>
다른 문자열 비교에 사용 됩니다.

### <a name="return-value"></a>반환 값

문자열이 없으면 0 동일 (대/소문자 무시), < 0이 `CStringT` 개체가 보다 작거나 *psz* (대/소문자 무시) > 0이 `CStringT` 개체 보다 크면 *psz* (대/소문자 무시).

### <a name="remarks"></a>설명

제네릭 텍스트 함수인 `_tcscoll`, TCHAR에서 정의 됩니다. H, 중 하나에 매핑됩니다 `stricoll`, `wcsicoll`, 또는 `_mbsicoll`컴파일 타임에 정의 된 문자 집합에 따라 합니다. 각 함수에서 현재 사용 중인 코드 페이지에 따라 문자열을 대/소문자 구분 비교를 수행 합니다. 자세한 내용은 [strcoll, wcscoll, _mbscoll, _strcoll_l, _wcscoll_l, _mbscoll_l](../../c-runtime-library/reference/strcoll-wcscoll-mbscoll-strcoll-l-wcscoll-l-mbscoll-l.md)합니다.

### <a name="example"></a>예제

[!code-cpp[NVC_ATLMFC_Utilities#109](../../atl-mfc-shared/codesnippet/cpp/cstringt-class_4.cpp)]

##  <a name="compare"></a>  CStringT::Compare

(대/소문자 구분) 두 문자열을 비교 합니다.

```
int Compare(PCXSTR psz) const;
```

### <a name="parameters"></a>매개 변수

*psz*<br/>
다른 문자열 비교에 사용 됩니다.

### <a name="return-value"></a>반환 값

문자열이 동일한 경우 0이 고, < 0이 `CStringT` 개체가 보다 작거나 *psz*, 또는 > 0이 `CStringT` 개체 보다 크면 *psz*합니다.

### <a name="remarks"></a>설명

제네릭 텍스트 함수인 `_tcscmp`, TCHAR에서 정의 됩니다. H, 중 하나에 매핑됩니다 `strcmp`, `wcscmp`, 또는 `_mbscmp`컴파일 타임에 정의 된 문자 집합에 따라 합니다. 각 함수는 문자열의 대/소문자 구분 비교를 수행 하 고 로캘의 영향을 받지 않습니다. 자세한 내용은 [strcmp, wcscmp, _mbscmp](../../c-runtime-library/reference/strcmp-wcscmp-mbscmp.md)합니다.

문자열에 내장된 된 null이 포함 하는 경우 비교의 목적을 위해 문자열에서 첫 번째 포함 된 null 문자가 잘립니다으로 간주 됩니다.

### <a name="example"></a>예제

다음 예에서는 `CStringT::Compare`의 사용법을 보여줍니다.

[!code-cpp[NVC_ATLMFC_Utilities#110](../../atl-mfc-shared/codesnippet/cpp/cstringt-class_5.cpp)]

##  <a name="comparenocase"></a>  CStringT::CompareNoCase

(대/소문자 구분) 두 문자열을 비교 합니다.

```
int CompareNoCase(PCXSTR psz) const throw();
```

### <a name="parameters"></a>매개 변수

*psz*<br/>
다른 문자열 비교에 사용 됩니다.

### <a name="return-value"></a>반환 값

문자열이 동일한 경우 0 (대/소문자 무시) < 0이 `CStringT` 개체가 보다 작거나 *psz* (대/소문자 무시) 또는 > 0이 `CStringT` 개체 보다 크면 *psz* (대/소문자 무시).

### <a name="remarks"></a>설명

제네릭 텍스트 함수인 `_tcsicmp`, TCHAR에서 정의 됩니다. H, 중 하나에 매핑됩니다 `_stricmp`, `_wcsicmp` 또는 `_mbsicmp`컴파일 타임에 정의 된 문자 집합에 따라 합니다. 각 함수는 문자열의 대/소문자 구분 비교를 수행합니다. 비교는 로캘 하지만 하지 LC_COLLATE LC_CTYPE 측면에 따라 달라 집니다. 자세한 내용은 [_stricmp, _wcsicmp, _mbsicmp, _stricmp_l, _wcsicmp_l, _mbsicmp_l](../../c-runtime-library/reference/stricmp-wcsicmp-mbsicmp-stricmp-l-wcsicmp-l-mbsicmp-l.md)합니다.

### <a name="example"></a>예제

[!code-cpp[NVC_ATLMFC_Utilities#111](../../atl-mfc-shared/codesnippet/cpp/cstringt-class_6.cpp)]

##  <a name="cstringt"></a>  CStringT::CStringT

`CStringT` 개체를 생성합니다.

```
CStringT() throw() :
    CThisSimpleString(StringTraits::GetDefaultManager());

explicit CStringT(IAtlStringMgr* pStringMgr) throw() :
    CThisSimpleString( pStringMgr);

CStringT(const VARIANT& varSrc);

CStringT(const VARIANT& varSrc, IAtlStringMgr* pStringMgr);

CStringT(const CStringT& strSrc) :
    CThisSimpleString( strSrc);

operator CSimpleStringT<
                    BaseType,
                    !_CSTRING_IMPL_::_MFCDLLTraitsCheck<BaseType, StringTraits>
                    :: c_bIsMFCDLLTraits> &()

template <bool bMFCDLL>
CStringT(const CSimpleStringT<BaseType, bMFCDLL>& strSrc) :
    CThisSimpleString( strSrc);

template <class SystemString>
CStringT(SystemString^ pString) :
    CThisSimpleString( StringTraits::GetDefaultManager());

CStringT(const XCHAR* pszSrc) :
    CThisSimpleString( StringTraits::GetDefaultManager());

CSTRING_EXPLICIT CStringT(const YCHAR* pszSrc) :
    CThisSimpleString( StringTraits::GetDefaultManager());

CStringT(LPCSTR pszSrc, IAtlStringMgr* pStringMgr) :
    CThisSimpleString( pStringMgr);

CStringT(LPCWSTR pszSrc, IAtlStringMgr* pStringMgr) :
    CThisSimpleString( pStringMgr);

CSTRING_EXPLICIT CStringT(const unsigned char* pszSrc) :
    CThisSimpleString( StringTraits::GetDefaultManager());

/*CSTRING_EXPLICIT*/ CStringT(char* pszSrc) :
    CThisSimpleString( StringTraits::GetDefaultManager());

CSTRING_EXPLICIT CStringT(unsigned char* pszSrc) :
    CThisSimpleString( StringTraits::GetDefaultManager());

CSTRING_EXPLICIT CStringT(wchar_t* pszSrc) :
    CThisSimpleString( StringTraits::GetDefaultManager());

CStringT(const unsigned char* pszSrc, IAtlStringMgr* pStringMgr) :
    CThisSimpleString( pStringMgr);

CSTRING_EXPLICIT CStringT(char ch, int nLength = 1) :
    CThisSimpleString( StringTraits::GetDefaultManager());

CSTRING_EXPLICIT CStringT(wchar_t ch, int nLength = 1) :
    CThisSimpleString( StringTraits::GetDefaultManager());

CStringT(const XCHAR* pch, int nLength) :
    CThisSimpleString( pch, nLength, StringTraits::GetDefaultManager());

CStringT(const YCHAR* pch, int nLength) :
    CThisSimpleString( StringTraits::GetDefaultManager());

CStringT(const XCHAR* pch, int nLength, AtlStringMgr* pStringMgr) :
    CThisSimpleString( pch, nLength, pStringMgr);

CStringT(const YCHAR* pch, int nLength, IAtlStringMgr* pStringMgr) :
    CThisSimpleString( pStringMgr);
```

### <a name="parameters"></a>매개 변수

*pch*<br/>
길이 문자 배열에 대 한 포인터 *nLength*null로 끝나는 없습니다.

*nLength*<br/>
문자 수가 *pch*합니다.

*ch*<br/>
단일 문자입니다.

*pszSrc*<br/>
복사할이 null로 끝나는 문자열을 `CStringT` 개체입니다.

*pStringMgr*<br/>
Memory manager에 대 한 포인터를 `CStringT` 개체입니다. 에 대 한 자세한 `IAtlStringMgr` 및 메모리 관리에 대 한 `CStringT`를 참조 하십시오 [CStringT 사용한 메모리 관리](../../atl-mfc-shared/memory-management-with-cstringt.md)합니다.

*strSrc*<br/>
기존 `CStringT` 에이 복사 될 개체 `CStringT` 개체입니다. 에 대 한 자세한 `CThisString` 고 `CThisSimpleString`, 주의 섹션을 참조 합니다.

*varSrc*<br/>
이에 복사할 variant 개체 `CStringT` 개체입니다.

*BaseType*<br/>
String 클래스의 문자 형식입니다. 다음 중 하나일 수 있습니다.

**char** (용 ANSI 문자열)입니다.

**wchar_t** (용 유니코드 문자열)입니다.

TCHAR (ANSI 및 유니코드 문자열)에 대 한 합니다.

*bMFCDLL*<br/>
프로젝트는 MFC DLL (TRUE) 인지 여부를 지정 하는 부울 값 (FALSE)입니다.

*SystemString*<br/>
해야 `System::String`, 및 /clr을 사용 하 여 프로젝트를 컴파일해야 합니다.

*pString*<br/>
에 대 한 핸들을 `CStringT` 개체입니다.

### <a name="remarks"></a>설명

알고 있어야 생성자에 할당 된 새 저장소를 입력된 데이터를 복사 하기 때문에 메모리 예외가 발생할 수 있습니다. 이러한 생성자 중 일부 프록시로 변환 함수를 참고 합니다. 예를 들어, LPTSTR를 대신할 수 있습니다 위치는 `CStringT` 개체가 필요한 합니다.

- `CStringT`( `LPCSTR` `lpsz` ): 유니코드 생성 `CStringT` ANSI 문자열에서. 또한 아래 예제와 같이 문자열 리소스를 로드 하려면이 생성자를 사용할 수 있습니다.

- `CStringT(` `LPCWSTR` `lpsz` ): 생성 된 `CStringT` 유니코드 문자열에서입니다.

- `CStringT`( `const unsigned char*` `psz` ): 생성할 수는 `CStringT` 에 대 한 포인터에서 **unsigned char**합니다.

> [!NOTE]
>  ANSI 및 유니코드 문자열 간의 암시적 문자열 변환 하지 않으려면 _CSTRING_DISABLE_NARROW_WIDE_CONVERSION 매크로 정의 합니다. 매크로 변환을 지 컴파일 생성자에서 제외 합니다.

합니다 *strSrc* 수 매개 변수 중 하나는 `CStringT` 또는 `CThisSimpleString` 개체입니다. 에 대 한 `CStringT`, 해당 기본 인스턴스화 중 하나를 사용 하 여 (`CString`, `CStringA`, 또는 `CStringW`);에 대 한 `CThisSimpleString`를 사용 하 여를 **이** 포인터입니다. `CThisSimpleString` 인스턴스를 선언 합니다 [CSimpleStringT 클래스](../../atl-mfc-shared/reference/csimplestringt-class.md), 보다 작은 기본 제공 기능을 사용 하 여 더 작은 문자열 클래스인는 `CStringT` 클래스입니다.

연산자를 오버 로드 `CSimpleStringT<>&()` 생성을 `CStringT` 에서 개체를 `CSimpleStringT` 선언 합니다.

> [!NOTE]
>  만들 수는 있지만 `CStringT` 에 대해 권장 인스턴스가 포함 된 null 문자를 포함 합니다. 메서드 및 연산자를 호출 `CStringT` 포함 된 null 문자를 포함 하는 개체에 의도 하지 않은 결과가 발생할 수 있습니다.

### <a name="example"></a>예제

[!code-cpp[NVC_ATLMFC_Utilities#112](../../atl-mfc-shared/codesnippet/cpp/cstringt-class_7.cpp)]

##  <a name="_dtorcstringt"></a>  CStringT::~CStringT

제거 된 `CStringT` 개체입니다.

```
~CStringT() throw();
```

### <a name="remarks"></a>설명

제거 된 `CStringT` 개체입니다.

##  <a name="delete"></a>  CStringT::Delete

지정된 된 인덱스에 있는 문자를 사용 하 여 시작 하는 문자열에서 문자 또는 문자를 삭제 합니다.

```
int Delete(int iIndex, int nCount = 1);
```

### <a name="parameters"></a>매개 변수

*iIndex*<br/>
첫 번째 문자의 인덱스를 `CStringT` 삭제할 개체입니다.

*nCount*<br/>
제거할 문자 수입니다.

### <a name="return-value"></a>반환 값

변경 된 문자열의 길이입니다.

### <a name="remarks"></a>설명

하는 경우 *nCount* 제거할 문자열의 나머지 부분 문자열 보다 깁니다.

### <a name="example"></a>예제

[!code-cpp[NVC_ATLMFC_Utilities#113](../../atl-mfc-shared/codesnippet/cpp/cstringt-class_8.cpp)]

```Output
Before: Soccer is best,
    but hockey is quicker!
After: Soccer best,
    but hockey is quicker!
```

##  <a name="find"></a>  CStringT::Find

문자나 부분 문자열의 첫 번째 일치 항목에 대 한이 문자열을 검색합니다.

```
int Find(PCXSTR pszSub, int iStart=0) const throw();
int Find(XCHAR ch, int iStart=0) const throw();
```

### <a name="parameters"></a>매개 변수

*pszSub*<br/>
검색할 부분 문자열입니다.

*iStart*<br/>
인덱스, 검색을 시작 하는 문자열의 0부터에서 시작 하는 문자입니다.

*ch*<br/>
단일 문자에 대 한 검색입니다.

### <a name="return-value"></a>반환 값

이 첫 번째 문자의 인덱스 `CStringT` 요청 된 부분 문자열 또는 문자를 일치 하는 개체 이거나, 부분 문자열 또는 문자를 찾을 수 없으면-1입니다.

### <a name="remarks"></a>설명

함수는 모두 단일 문자를 허용 하도록 오버 로드 (런타임 함수와 비슷합니다 `strchr`) 및 문자열 (비슷합니다 `strstr`).

### <a name="example"></a>예제

[!code-cpp[NVC_ATLMFC_Utilities#114](../../atl-mfc-shared/codesnippet/cpp/cstringt-class_9.cpp)]

##  <a name="findoneof"></a>  CStringT::FindOneOf

이 문자열에 포함 된 모든 문자를 일치 하는 첫 번째 문자에 대 한 검색 *pszCharSet*합니다.

```
int FindOneOf(PCXSTR pszCharSet) const throw();
```

### <a name="parameters"></a>매개 변수

*pszCharSet*<br/>
일치 하는 문자를 포함 하는 문자열입니다.

### <a name="return-value"></a>반환 값

또한는이 문자열의 첫 번째 문자의 인덱스 *pszCharSet*; 일치 하는 항목이 없으면-1입니다.

### <a name="remarks"></a>설명

처음에는 문자를 찾습니다 *pszCharSet*합니다.

### <a name="example"></a>예제

[!code-cpp[NVC_ATLMFC_Utilities#115](../../atl-mfc-shared/codesnippet/cpp/cstringt-class_10.cpp)]

##  <a name="format"></a>  CStringT::Format

형식이 지정 된 데이터를 씁니다를 `CStringT` 동일한 방식으로 [sprintf_s](../../c-runtime-library/reference/sprintf-s-sprintf-s-l-swprintf-s-swprintf-s-l.md) C 스타일 문자 배열로 데이터의 형식을 지정 합니다.

```
void __cdecl Format(UINT nFormatID, [, argument]...);
void __cdecl Format(PCXSTR pszFormat,  [, argument] ...);
```

### <a name="parameters"></a>매개 변수

*nFormatID*<br/>
형식 컨트롤 문자열을 포함 하는 문자열 리소스 식별자입니다.

*pszFormat*<br/>
형식 컨트롤 문자열입니다.

*argument*<br/>
선택적 인수입니다.

### <a name="remarks"></a>설명

포맷 하 고 일련의 문자 및 값을 저장 하는이 함수는 `CStringT`합니다. 각 선택적 인수 (있는 경우) 변환 되 고 해당 형식 사양에 따라 출력 *pszFormat* 식별 되는 문자열 리소스의 들어오거나 *nFormatID*합니다.

문자열 개체 자체를 매개 변수로 제공 하는 경우 호출 실패 `Format`합니다. 예를 들어, 다음 코드를 사용 하면 예기치 않은 결과.

[!code-cpp[NVC_ATLMFC_Utilities#116](../../atl-mfc-shared/codesnippet/cpp/cstringt-class_11.cpp)]

자세한 내용은 [형식 사양 구문: printf 및 wprintf 함수](../../c-runtime-library/format-specification-syntax-printf-and-wprintf-functions.md)를 참조하세요.

### <a name="example"></a>예제

[!code-cpp[NVC_ATLMFC_Utilities#117](../../atl-mfc-shared/codesnippet/cpp/cstringt-class_12.cpp)]

##  <a name="formatmessage"></a>  CStringT::FormatMessage

메시지 문자열의 서식을 지정합니다.

```
void __cdecl FormatMessage(UINT nFormatID, [, argument]...);
void __cdecl FormatMessage(PCXSTR pszFormat, [, argument]...);
```

### <a name="parameters"></a>매개 변수

*nFormatID*<br/>
형식이 지정 되지 않은 메시지 텍스트가 포함 된 문자열 리소스 식별자입니다.

*pszFormat*<br/>
형식 컨트롤 문자열을 가리킵니다. 수 삽입에 대 한 검색 하 고 그에 따라 서식이 지정 합니다. 서식 문자열은 실행 시간 함수와 비슷합니다 *printf*-매개 변수는 임의의 순서로 삽입할 수 있도록 점을 제외 하 고 형식 문자열 스타일입니다.

*argument*<br/>
선택적 인수입니다.

### <a name="remarks"></a>설명

함수에는 입력으로는 메시지 정의가 필요합니다. 메시지 정의 의해 결정 됩니다 *pszFormat* 식별 되는 문자열 리소스의 들어오거나 *nFormatID*합니다. 서식이 지정 된 메시지 텍스트를 복사 하는 함수는 `CStringT` 처리 포함 된 모든 개체를 요청 하는 경우 시퀀스를 삽입 합니다.

> [!NOTE]
> `FormatMessage` 형식이 새로 지정 된 문자열에 대 한 시스템 메모리를 할당 하려고 시도 합니다. 이 시도가 실패 하면 메모리 예외를 자동으로 throw 됩니다.

각 삽입을 해당 매개 변수 다음이 있어야 합니다.는 *pszFormat* 하거나 *nFormatID* 매개 변수입니다. 메시지 텍스트 내에서 동적으로 메시지의 서식을 지정 하는 것에 대 한 몇 가지 이스케이프 시퀀스는 지원 됩니다. 자세한 내용은 참조는 Windows [FormatMessage](/windows/desktop/api/winbase/nf-winbase-formatmessage) Windows SDK에는 함수입니다.

### <a name="example"></a>예제

[!code-cpp[NVC_ATLMFC_Utilities#118](../../atl-mfc-shared/codesnippet/cpp/cstringt-class_13.cpp)]

##  <a name="formatmessagev"></a>  CStringT::FormatMessageV

가변 인수 목록을 사용 하 여 메시지 문자열의 서식을 지정 합니다.

```
void FormatMessageV(PCXSTR pszFormat, va_list* pArgList);
```

### <a name="parameters"></a>매개 변수

*pszFormat*<br/>
형식 컨트롤 문자열을 가리킵니다. 수 삽입에 대 한 검색 하 고 그에 따라 서식이 지정 합니다. 서식 문자열은 런타임 함수와 유사한 `printf`-매개 변수는 임의의 순서로 삽입할 수 있도록 점을 제외 하 고 형식 문자열 스타일입니다.

*pArgList*<br/>
인수 목록에 대 한 포인터입니다.

### <a name="remarks"></a>설명

함수에 입력으로 메시지 정의 필요에 따라 결정 *pszFormat*합니다. 함수에 인수의 변수 목록과 서식이 지정 된 메시지 텍스트를 복사 합니다 `CStringT` 포함 하나를 처리 하는 개체를 요청 하는 경우 시퀀스를 삽입 합니다.

> [!NOTE]
> `FormatMessageV` 호출 [CStringT::FormatMessage](#formatmessage), 형식이 새로 지정 된 문자열에 대 한 시스템 메모리를 할당 하려고 하는 합니다. 이 시도가 실패 하면 메모리 예외를 자동으로 throw 됩니다.

자세한 내용은 참조는 Windows [FormatMessage](/windows/desktop/api/winbase/nf-winbase-formatmessage) Windows SDK에는 함수입니다.

##  <a name="formatv"></a>  CStringT::FormatV

가변 인수 목록을 사용 하 여 메시지 문자열의 서식을 지정 합니다.

```
void FormatV(PCXSTR pszFormat, va_list args);
```

### <a name="parameters"></a>매개 변수

*pszFormat*<br/>
형식 컨트롤 문자열을 가리킵니다. 수 삽입에 대 한 검색 하 고 그에 따라 서식이 지정 합니다. 서식 문자열은 런타임 함수와 유사한 `printf`-매개 변수는 임의의 순서로 삽입할 수 있도록 점을 제외 하 고 형식 문자열 스타일입니다.

*args*<br/>
인수 목록에 대 한 포인터입니다.

### <a name="remarks"></a>설명

서식이 지정 된 문자열 및 가변 인수 목록 작성을 `CStringT` 동일한 문자열 방식으로 `vsprintf_s` C 스타일 문자 배열로 데이터의 형식을 지정 합니다.

### <a name="example"></a>예제

[!code-cpp[NVC_ATLMFC_Utilities#119](../../atl-mfc-shared/codesnippet/cpp/cstringt-class_14.cpp)]

[!code-cpp[NVC_ATLMFC_Utilities#120](../../atl-mfc-shared/codesnippet/cpp/cstringt-class_15.cpp)]

##  <a name="getenvironmentvariable"></a>  CStringT::GetEnvironmentVariable

지정 된 환경 변수의 값으로 문자열을 설정합니다.

```
BOOL GetEnvironmentVariable(PCXSTR pszVar);
```

### <a name="parameters"></a>매개 변수

*pszVar*<br/>
환경 변수를 지정 하는 null로 끝나는 문자열에 대 한 포인터입니다.

### <a name="return-value"></a>반환 값

성공하면 0이 아니고, 그렇지 않으면 0입니다.

### <a name="remarks"></a>설명

호출 프로세스의 환경 블록에서 지정 된 변수의 값을 검색합니다. 값이 문자의 null로 끝나는 문자열의 형식에서입니다.

### <a name="example"></a>예제

[!code-cpp[NVC_ATLMFC_Utilities#121](../../atl-mfc-shared/codesnippet/cpp/cstringt-class_16.cpp)]

##  <a name="insert"></a>  CStringT::Insert

문자열 내에서 지정된 된 인덱스에 단일 문자 또는 부분 문자열을 삽입합니다.

```
int Insert(int iIndex, PCXSTR psz);
int Insert(int iIndex, XCHAR ch);
```

### <a name="parameters"></a>매개 변수

*iIndex*<br/>
되기까지의 삽입 수행 되는 문자의 인덱스입니다.

*psz*<br/>
삽입할 하위 문자열 포인터입니다.

*ch*<br/>
삽입할 문자입니다.

### <a name="return-value"></a>반환 값

변경 된 문자열의 길이입니다.

### <a name="remarks"></a>설명

합니다 *iIndex* 이동할 문자나 부분 문자열에 대 한 공간을 확보 하는 첫 번째 문자를 식별 하는 매개 변수입니다. 하는 경우 *nIndex* 가 0 이면 전체 문자열 앞에 삽입 발생 합니다. 하는 경우 *nIndex* 함수 문자열의 길이 있는 문자열을 연결 하 고 새 자료 중 하나에서 제공 하는 보다 높은 *ch* 하거나 *psz*합니다.

### <a name="example"></a>예제

[!code-cpp[NVC_ATLMFC_Utilities#122](../../atl-mfc-shared/codesnippet/cpp/cstringt-class_17.cpp)]

##  <a name="left"></a>  CStringT::Left

가장 왼쪽에 있는 추출 *nCount* 에서 문자 `CStringT` 개체 및 추출된 된 부분 문자열의 복사본을 반환 합니다.

```
CStringT Left(int nCount) const;
```

### <a name="parameters"></a>매개 변수

*nCount*<br/>
이 `CStringT` 개체에서 추출할 문자의 수입니다.

### <a name="return-value"></a>반환 값

지정된 문자 범위의 복사본을 포함하는 `CStringT` 개체입니다. 반환된 `CStringT` 개체가 비어 있을 수 있습니다.

### <a name="remarks"></a>설명

하는 경우 *nCount* 문자열 길이 초과 하면 다음 전체 문자열이 추출 됩니다. `Left`는 기본 `Left` 함수와 유사합니다.

멀티 바이트 문자 집합 (MBCS)에 대 한 *nCount* 각 8 비트 시퀀스를 문자로 처리 되도록 *nCount* 2를 곱하여 멀티 바이트 문자의 수를 반환 합니다.

### <a name="example"></a>예제

[!code-cpp[NVC_ATLMFC_Utilities#123](../../atl-mfc-shared/codesnippet/cpp/cstringt-class_18.cpp)]

##  <a name="loadstring"></a>  CStringT::LoadString

로 식별 되는 Windows 문자열 리소스를 읽고 *nID*를 기존 `CStringT` 개체입니다.

```
BOOL LoadString(HINSTANCE hInstance, UINT nID, WORD wLanguageID);
BOOL LoadString(HINSTANCE hInstance, UINT nID);
BOOL LoadString(UINT nID);
```

### <a name="parameters"></a>매개 변수

*hInstance*<br/>
모듈의 인스턴스 핸들입니다.

*nID*<br/>
Windows 문자열 리소스 id입니다.

*wLanguageID*<br/>
문자열 리소스의 언어입니다.

### <a name="return-value"></a>반환 값

리소스 로드에 성공 하면 0이 아닌 값 그렇지 않으면 0입니다.

### <a name="remarks"></a>설명

문자열 리소스를 로드 (*nID*) 지정 된 모듈에서 (*hInstance*) 지정된 된 언어를 사용 하 여 (*wLanguage*).

### <a name="example"></a>예제

[!code-cpp[NVC_ATLMFC_Utilities#124](../../atl-mfc-shared/codesnippet/cpp/cstringt-class_19.cpp)]

##  <a name="makelower"></a>  CStringT::MakeLower

변환 된 `CStringT` 개체를 소문자 문자열로 합니다.

```
CStringT& MakeLower();
```

### <a name="return-value"></a>반환 값

결과 소문자 문자열입니다.

### <a name="example"></a>예제

[!code-cpp[NVC_ATLMFC_Utilities#125](../../atl-mfc-shared/codesnippet/cpp/cstringt-class_20.cpp)]

##  <a name="makereverse"></a>  CStringT::MakeReverse

에 있는 문자의 순서를 반대로 바꿉니다는 `CStringT` 개체입니다.

```
CStringT& MakeReverse();
```

### <a name="return-value"></a>반환 값

결과 문자열을 반대로 합니다.

### <a name="example"></a>예제

[!code-cpp[NVC_ATLMFC_Utilities#126](../../atl-mfc-shared/codesnippet/cpp/cstringt-class_21.cpp)]

##  <a name="makeupper"></a>  CStringT::MakeUpper

변환 된 `CStringT` 대문자 문자열 개체입니다.

```
CStringT& MakeUpper();
```

### <a name="return-value"></a>반환 값

결과 대문자 문자열입니다.

### <a name="remarks"></a>설명

### <a name="example"></a>예제

[!code-cpp[NVC_ATLMFC_Utilities#127](../../atl-mfc-shared/codesnippet/cpp/cstringt-class_22.cpp)]

##  <a name="mid"></a>  CStringT::Mid

길이의 부분 문자열 추출 *nCount* 에서 문자 `CStringT` 위치에서 시작 하는 개체 *iFirst* (0부터 시작)입니다.

```
CStringT Mid(int iFirst, int nCount) const;
CStringT Mid(int iFirst) const;
```

### <a name="parameters"></a>매개 변수

*iFirst*<br/>
이 첫 번째 문자의 인덱스 `CStringT` 추출된 된 부분 문자열에 포함 되어야 하는 개체입니다.

*nCount*<br/>
이 `CStringT` 개체에서 추출할 문자의 수입니다. 이 매개 변수를 제공 하지 않으면 문자열의 나머지 부분 추출 됩니다.

### <a name="return-value"></a>반환 값

지정된 문자 범위의 복사본을 포함하는 `CStringT` 개체입니다. 반환 된 `CStringT` 개체는 비어 있을 수 있습니다.

### <a name="remarks"></a>설명

함수 추출된 된 부분 문자열의 복사본을 반환 합니다. `Mid` 비슷합니다 기본 Mid 함수 (점을 제외 하 고 기본 인덱스는 1부터 시작)입니다.

멀티 바이트 문자 집합 (MBCS)에 대 한 *nCount* 멀티 바이트 문자를 두 개의 문자로 계산 됩니다 하나에 각 8 비트 문자, 즉, 한 선행 및 후행 바이트를 가리킵니다.

### <a name="example"></a>예제

[!code-cpp[NVC_ATLMFC_Utilities#128](../../atl-mfc-shared/codesnippet/cpp/cstringt-class_23.cpp)]

##  <a name="oemtoansi"></a>  CStringT::OemToAnsi

이 모든 문자가 변환 `CStringT` OEM 문자 집합을 ANSI 문자 집합의에서 개체입니다.

```
void OemToAnsi();
```

### <a name="remarks"></a>설명

이 함수는 _UNICODE가 정의 된 경우에 사용할 수 없습니다.

### <a name="example"></a>예제

예를 참조 하세요 [CStringT::AnsiToOem](#ansitooem)합니다.

##  <a name="operator_eq"></a>  CStringT::operator =

문자열에 새 값을 할당 합니다.

```
CStringT& operator=(const CStringT& strSrc);

template<bool bMFCDLL>
CStringT& operator=(const CSimpleStringT<BaseType, bMFCDLL>& str);

CStringT& operator=(PCXSTR pszSrc);
CStringT& operator=(PCYSTR pszSrc);
CStringT& operator=(const unsigned char* pszSrc);
CStringT& operator=(XCHAR ch);
CStringT& operator=(YCHAR ch);
CStringT& operator=(const VARIANT& var);
```

### <a name="parameters"></a>매개 변수

*strSrc*<br/>
`CStringT` 이 문자열을 할당 합니다.

*str*<br/>
`CThisSimpleString` 개체에 대한 참조입니다.

*bMFCDLL*<br/>
프로젝트는 MFC DLL 인지 여부를 지정 하는 부울입니다.

*BaseType*<br/>
문자열 기본 형식입니다.

*var*<br/>
이 문자열에 할당할 variant 개체입니다.

*ch*<br/>
문자열에 할당할 ANSI 또는 유니코드 문자입니다.

*pszSrc*<br/>
할당 되는 원래 문자열에 대 한 포인터입니다.

### <a name="remarks"></a>설명

대입 연산자를 허용 다른 `CStringT` 개체, 문자에 대 한 포인터 또는 단일 문자입니다. 알아야 할 메모리가이 연산자를 사용 하 여 새 저장소를 할당할 수 있으므로 때마다 예외가 발생할 수 있습니다.

에 대 한 내용은 `CThisSimpleString`의 설명 섹션을 참조 하세요 [CStringT::CStringT](#cstringt)합니다.

> [!NOTE]
> 만들 수는 있지만 `CStringT` 에 대해 권장 인스턴스가 포함 된 null 문자를 포함 합니다. 메서드 및 연산자를 호출 `CStringT` 포함 된 null 문자를 포함 하는 개체에 의도 하지 않은 결과가 발생할 수 있습니다.

##  <a name="operator_add"></a>  CStringT::operator +

두 문자열 또는 문자 및 문자열을 연결합니다.

```
friend CStringT operator+(const CStringT& str1, const CStringT& str2);
friend CStringT operator+(const CStringT& str1, PCXSTR psz2);
friend CStringT operator+(PCXSTR psz1, const CStringT& str2,);
friend CStringT operator+(char ch1, const CStringT& str2,);
friend CStringT operator+(const CStringT& str1, char ch2);
friend CStringT operator+(const CStringT& str1, wchar_t ch2);
friend CStringT operator+(wchar_t ch1, const CStringT& str2,);
```

### <a name="parameters"></a>매개 변수

*ch1*<br/>
연결 문자열을 사용 하 여 ANSI 또는 유니코드 문자입니다.

*ch2*<br/>
연결 문자열을 사용 하 여 ANSI 또는 유니코드 문자입니다.

*str1*<br/>
`CStringT` 문자열 또는 문자를 사용 하 여 연결 합니다.

*str2*<br/>
`CStringT` 문자열 또는 문자를 사용 하 여 연결 합니다.

*psz1*<br/>
문자열 또는 문자를 사용 하 여 연결 하는 null로 끝나는 문자열에 대 한 포인터입니다.

*psz2*<br/>
문자열 또는 문자를 사용 하 여 연결 문자열에 대 한 포인터입니다.

### <a name="remarks"></a>설명

7 개의 오버 로드 형태를 가지는 `CStringT::operator+` 함수입니다. 첫 번째 버전을 두 개의 기존 연결 `CStringT` 개체입니다. 다음 두 개의 연결을 `CStringT` 개체 및 null로 끝나는 문자열입니다. 다음 두 개의 연결을 `CStringT` 개체와는 ANSI 문자입니다. 마지막 두 연결을 `CStringT` 개체 및 유니코드 문자입니다.

> [!NOTE]
>  만들 수는 있지만 `CStringT` 에 대해 권장 인스턴스가 포함 된 null 문자를 포함 합니다. 메서드 및 연산자를 호출 `CStringT` 포함 된 null 문자를 포함 하는 개체에 의도 하지 않은 결과가 발생할 수 있습니다.

### <a name="example"></a>예제

[!code-cpp[NVC_ATLMFC_Utilities#140](../../atl-mfc-shared/codesnippet/cpp/cstringt-class_24.cpp)]

##  <a name="operator_add_eq"></a>  CStringT::operator +=

문자열의 끝에 문자를 연결합니다.

```
CStringT& operator+=(const CThisSimpleString& str);

template<bool bMFCDLL>
CStringT& operator+=(const const CSimpleStringT<BaseType, bMFCDLL>& str);

template<int t_nSize>
CStringT& operator+=(const CStaticString<XCHAR, t_nSize>& strSrc);
CStringT& operator+=(PCXSTR pszSrc);
CStringT& operator+=(PCYSTR pszSrc);
CStringT& operator+=(char ch);
CStringT& operator+=(unsigned char ch);
CStringT& operator+=(wchar_t ch);
CStringT& operator+=(const VARIANT& var);
```

### <a name="parameters"></a>매개 변수

*str*<br/>
`CThisSimpleString` 개체에 대한 참조입니다.

*bMFCDLL*<br/>
프로젝트는 MFC DLL 인지 여부를 지정 하는 부울입니다.

*BaseType*<br/>
문자열 기본 형식입니다.

*var*<br/>
이 문자열을 연결 하는 variant 개체입니다.

*ch*<br/>
연결 문자열을 사용 하 여 ANSI 또는 유니코드 문자입니다.

*pszSrc*<br/>
연결 되 고 원래 문자열에 대 한 포인터입니다.

*strSrc*<br/>
`CStringT` 이 문자열을 연결 합니다.

### <a name="remarks"></a>설명

다른 연산자를 허용 `CStringT` 개체, 문자에 대 한 포인터 또는 단일 문자입니다. 알아야 할 추가 문자에 대 한 새 저장소를 할당할 수 있으므로이 연결 연산자를 사용할 때마다 예외가 발생할 수 있습니다 하는 메모리 `CStringT` 개체입니다.

에 대 한 내용은 `CThisSimpleString`의 설명 섹션을 참조 하세요 [CStringT::CStringT](#cstringt)합니다.

> [!NOTE]
>  만들 수는 있지만 `CStringT` 에 대해 권장 인스턴스가 포함 된 null 문자를 포함 합니다. 메서드 및 연산자를 호출 `CStringT` 포함 된 null 문자를 포함 하는 개체에 의도 하지 않은 결과가 발생할 수 있습니다.

### <a name="example"></a>예제

[!code-cpp[NVC_ATLMFC_Utilities#141](../../atl-mfc-shared/codesnippet/cpp/cstringt-class_25.cpp)]

##  <a name="operator_eq_eq"></a>  CStringT::operator ==

두 문자열은 논리적으로 동일한 지 여부를 결정 합니다.

```
friend bool operator==(const CStringT& str1, const CStringT& str2) throw();
friend bool operator==(const CStringT& str1, PCXSTR psz2) throw();
friend bool operator==(const CStringT& str1, PCYSTR psz2) throw();
friend bool operator==(const CStringT& str1, XCHAR ch2) throw();
friend bool operator==(PCXSTR psz1, const CStringT& str2) throw();
friend bool operator==(PCYSTR psz1, const CStringT& str2,) throw();
friend bool operator==(XCHAR ch1, const CStringT& str2,) throw();
```

### <a name="parameters"></a>매개 변수

*ch1*<br/>
비교에 대 한 ANSI 또는 유니코드 문자입니다.

*ch2*<br/>
비교에 대 한 ANSI 또는 유니코드 문자입니다.

*str1*<br/>
`CStringT` 비교 합니다.

*str2*<br/>
`CStringT` 비교 합니다.

*psz1*<br/>
Null로 끝나는 문자열 비교에 대 한 포인터입니다.

*psz2*<br/>
Null로 끝나는 문자열 비교에 대 한 포인터입니다.

### <a name="remarks"></a>설명

문자열 또는 왼쪽에 문자를 문자열 또는 오른쪽에 있는 문자 이며 따라 TRUE 또는 FALSE를 반환 하는지 여부를 테스트 합니다.

### <a name="example"></a>예제

[!code-cpp[NVC_ATLMFC_Utilities#142](../../atl-mfc-shared/codesnippet/cpp/cstringt-class_26.cpp)]

##  <a name="operator_neq"></a>  CStringT::operator !=

논리적으로 없습니다 두 문자열이 같은지 확인 합니다.

```
friend bool operator!=(const CStringT& str1, const CStringT& str2) throw();
friend bool operator!=(const CStringT& str1, PCXSTR psz2) throw();
friend bool operator!=(const CStringT& str1, PCYSTR psz2) throw();
friend bool operator!=(const CStringT& str1, XCHAR ch2) throw();
friend bool operator!=(PCXSTR psz1, const CStringT& str2) throw();
friend bool operator!=(PCYSTR psz1, const CStringT& str2,) throw();
friend bool operator!=(XCHAR ch1, const CStringT& str2,) throw();
```

### <a name="parameters"></a>매개 변수

*ch1*<br/>
연결 문자열을 사용 하 여 ANSI 또는 유니코드 문자입니다.

*ch2*<br/>
연결 문자열을 사용 하 여 ANSI 또는 유니코드 문자입니다.

*str1*<br/>
`CStringT` 비교 합니다.

*str2*<br/>
`CStringT` 비교 합니다.

*psz1*<br/>
Null로 끝나는 문자열 비교에 대 한 포인터입니다.

*psz2*<br/>
Null로 끝나는 문자열 비교에 대 한 포인터입니다.

### <a name="remarks"></a>설명

문자열 또는 왼쪽에 문자를 문자열 또는 오른쪽에 있는 문자 인지 테스트 합니다.

### <a name="example"></a>예제

[!code-cpp[NVC_ATLMFC_Utilities#143](../../atl-mfc-shared/codesnippet/cpp/cstringt-class_27.cpp)]

##  <a name="operator_lt"></a>  CStringT::operator &lt;

연산자의 좌 변에 있는 문자열 오른쪽에 문자열 보다 작은지 여부를 결정 합니다.

```
friend bool operator<(const CStringT& str1, const CStringT& str2) throw();
friend bool operator<(const CStringT& str1, PCXSTR psz2) throw();
friend bool operator<(PCXSTR psz1, const CStringT& str2) throw();
```

### <a name="parameters"></a>매개 변수

*str1*<br/>
`CStringT` 비교 합니다.

*str2*<br/>
`CStringT` 비교 합니다.

*psz1*<br/>
Null로 끝나는 문자열 비교에 대 한 포인터입니다.

*psz2*<br/>
Null로 끝나는 문자열 비교에 대 한 포인터입니다.

### <a name="remarks"></a>설명

될 때까지 문자별으로 문자열 간의 어휘 비교:

- 해당하는 두 문자가 같지 않음이 확인될 때까지. 이 경우 해당 비교 결과를 문자열 간의 비교 결과로 가져옵니다.

- 같지 않은 문자는 없으나 한 문자열의 문자 수가 다른 문자열보다 많음이 확인될 때까지. 이 경우 더 짧은 문자열이 더 긴 문자열보다 작은 것으로 간주합니다.

- 같지 않은 문자가 없으며 문자열의 문자 수도 같음이 확인될 때까지. 이 경우 두 문자열은 동일한 것으로 간주합니다.

### <a name="example"></a>예제

[!code-cpp[NVC_ATLMFC_Utilities#144](../../atl-mfc-shared/codesnippet/cpp/cstringt-class_28.cpp)]

##  <a name="operator_gt"></a>  CStringT::operator &gt;

연산자의 좌 변에 있는 문자열 오른쪽에 문자열 보다 큰지 여부를 결정 합니다.

```
friend bool operator>(const CStringT& str1, const CStringT& str2) throw();
friend bool operator>(const CStringT& str1, PCXSTR psz2) throw();
friend bool operator>(PCXSTR psz1, const CStringT& str2) throw();
```

### <a name="parameters"></a>매개 변수

*str1*<br/>
`CStringT` 비교 합니다.

*str2*<br/>
`CStringT` 비교 합니다.

*psz1*<br/>
Null로 끝나는 문자열 비교에 대 한 포인터입니다.

*psz2*<br/>
Null로 끝나는 문자열 비교에 대 한 포인터입니다.

### <a name="remarks"></a>설명

될 때까지 문자별으로 문자열 간의 어휘 비교:

- 해당하는 두 문자가 같지 않음이 확인될 때까지. 이 경우 해당 비교 결과를 문자열 간의 비교 결과로 가져옵니다.

- 같지 않은 문자는 없으나 한 문자열의 문자 수가 다른 문자열보다 많음이 확인될 때까지. 이 경우 더 짧은 문자열이 더 긴 문자열보다 작은 것으로 간주합니다.

- 같지 않은 문자가 없으며 문자열의 문자 수도 같음이 확인될 때까지. 이 경우 두 문자열은 동일한 것으로 간주합니다.

### <a name="example"></a>예제

[!code-cpp[NVC_ATLMFC_Utilities#145](../../atl-mfc-shared/codesnippet/cpp/cstringt-class_29.cpp)]

##  <a name="operator_lt_eq"></a>  CStringT::operator &lt;=

연산자의 좌 변에 있는 문자열 오른쪽에 문자열 보다 작거나 인지 확인 합니다.

```
friend bool operator<=(const CStringT& str1, const CStringT& str2) throw();
friend bool operator<=(const CStringT& str1, PCXSTR psz2) throw();
friend bool operator<=(PCXSTR psz1, const CStringT& str2) throw();
```

### <a name="parameters"></a>매개 변수

*str1*<br/>
`CStringT` 비교 합니다.

*str2*<br/>
`CStringT` 비교 합니다.

*psz1*<br/>
Null로 끝나는 문자열 비교에 대 한 포인터입니다.

*psz2*<br/>
Null로 끝나는 문자열 비교에 대 한 포인터입니다.

### <a name="remarks"></a>설명

될 때까지 문자별으로 문자열 간의 어휘 비교:

- 해당하는 두 문자가 같지 않음이 확인될 때까지. 이 경우 해당 비교 결과를 문자열 간의 비교 결과로 가져옵니다.

- 같지 않은 문자는 없으나 한 문자열의 문자 수가 다른 문자열보다 많음이 확인될 때까지. 이 경우 더 짧은 문자열이 더 긴 문자열보다 작은 것으로 간주합니다.

- 같지 않은 문자가 없으며 문자열의 문자 수도 같음이 확인될 때까지. 이 경우 두 문자열은 동일한 것으로 간주합니다.

### <a name="example"></a>예제

[!code-cpp[NVC_ATLMFC_Utilities#146](../../atl-mfc-shared/codesnippet/cpp/cstringt-class_30.cpp)]

##  <a name="operator_gt_eq"></a>  CStringT::operator &gt;=

연산자의 좌 변에 있는 문자열 오른쪽에 문자열 보다 크거나 같은 경우 인지 확인 합니다.

```
friend bool operator>=(const CStringT& str1, const CStringT& str2) throw();
friend bool operator>=(const CStringT& str1, PCXSTR psz2) throw();
friend bool operator>=(PCXSTR psz1, const CStringT& str2) throw();
```

### <a name="parameters"></a>매개 변수

*str1*<br/>
`CStringT` 비교 합니다.

*str2*<br/>
`CStringT` 비교 합니다.

*psz1*<br/>
문자열 비교에 대 한 포인터입니다.

*psz2*<br/>
문자열 비교에 대 한 포인터입니다.

### <a name="remarks"></a>설명

될 때까지 문자별으로 문자열 간의 어휘 비교:

- 해당하는 두 문자가 같지 않음이 확인될 때까지. 이 경우 해당 비교 결과를 문자열 간의 비교 결과로 가져옵니다.

- 같지 않은 문자는 없으나 한 문자열의 문자 수가 다른 문자열보다 많음이 확인될 때까지. 이 경우 더 짧은 문자열이 더 긴 문자열보다 작은 것으로 간주합니다.

- 같지 않은 문자가 없으며 문자열의 문자 수도 같음이 확인될 때까지. 이 경우 두 문자열은 동일한 것으로 간주합니다.

### <a name="example"></a>예제

[!code-cpp[NVC_ATLMFC_Utilities#147](../../atl-mfc-shared/codesnippet/cpp/cstringt-class_31.cpp)]

##  <a name="remove"></a>  CStringT::Remove

문자열에서 지정 된 문자의 모든 인스턴스를 제거합니다.

```
int Remove(XCHAR chRemove);
```

### <a name="parameters"></a>매개 변수

*chRemove*<br/>
문자열에서 제거할 문자입니다.

### <a name="return-value"></a>반환 값

문자열에서 제거 되는 문자의 수입니다. 문자열 변경 되지 않으면 0입니다.

### <a name="remarks"></a>설명

문자에 대 한 비교는 대/소문자 구분 합니다.

### <a name="example"></a>예제

[!code-cpp[NVC_ATLMFC_Utilities#129](../../atl-mfc-shared/codesnippet/cpp/cstringt-class_32.cpp)]

##  <a name="replace"></a>  CStringT::Replace

두 가지 버전의 `Replace`합니다. 부분 문자열의 복사본을 하나 이상의 다른 부분 문자열을 사용 하 여 대체 하는 첫 번째 버전입니다. 두 부분 문자열은 null로 끝납니다. 두 번째 버전은 다른 문자를 사용 하 여 하나 이상의 문자 복사본을 대체 합니다. 두 버전 모두에 저장 하는 문자 데이터에서 작동 `CStringT`합니다.

```
int Replace(PCXSTR pszOld, PCXSTR pszNew);
int Replace(XCHAR chOld, XCHAR chNew);
```

### <a name="parameters"></a>매개 변수

*pszOld*<br/>
교체는 null로 끝나는 문자열에 대 한 포인터 *pszNew*합니다.

*pszNew*<br/>
대체 하는 null로 끝나는 문자열에 대 한 포인터 *pszOld*합니다.

*chOld*<br/>
교체 문자 *chNew*합니다.

*chNew*<br/>
문자 대체 *chOld*합니다.

### <a name="return-value"></a>반환 값

문자열 변경 되지 않으면 0 문자 또는 부분 문자열의 대체 인스턴스 수를 반환 합니다.

### <a name="remarks"></a>설명

`Replace` 때문에 문자열 길이 변경할 수 있습니다 *pszNew* 하 고 *pszOld* 동일한 길이 수 없고 새 이전 부분 문자열의 여러 복사본을 변경할 수 있습니다. 함수는 대/소문자 구분 일치를 수행합니다.

예가 `CStringT` 인스턴스가 `CString`를 `CStringA`, 및 `CStringW`합니다.

에 대 한 `CStringA`, `Replace` ANSI 또는 멀티 바이트 (MBCS) 문자를 사용 하 여 작동 합니다. 에 대 한 `CStringW`, `Replace` 와이드 문자를 사용 하 여 작동 합니다.

에 대 한 `CString`, 문자 데이터 형식이 다음 표에 상수를 정의 하는 여부에 따라 컴파일 타임에 선택 됩니다.

|정의 된 상수|문자 데이터 형식|
|----------------------|-------------------------|
|_UNICODE|와이드 문자|
|_MBCS|멀티 바이트 문자|
|모두|단일 바이트 문자|
|Both|Undefined|

### <a name="example"></a>예제

[!code-cpp[NVC_ATLMFC_Utilities#200](../../atl-mfc-shared/codesnippet/cpp/cstringt-class_33.cpp)]

##  <a name="reversefind"></a>  CStringT::ReverseFind

이 검색 `CStringT` 문자의 마지막 일치 항목에 대 한 개체입니다.

```
int ReverseFind(XCHAR ch) const throw();
```

### <a name="parameters"></a>매개 변수

*ch*<br/>
검색할 문자입니다.

### <a name="return-value"></a>반환 값

이 마지막 문자의 인덱스 `CStringT` 문자가 없는 경우 요청 된 문자 또는-1과 일치 하는 개체입니다.

### <a name="remarks"></a>설명

함수는 런타임 함수와 비슷합니다 `strrchr`합니다.

### <a name="example"></a>예제

[!code-cpp[NVC_ATLMFC_Utilities#130](../../atl-mfc-shared/codesnippet/cpp/cstringt-class_34.cpp)]

##  <a name="right"></a>  CStringT::Right

마지막 추출 (즉, 오른쪽에 있는) *nCount* 에서 문자 `CStringT` 개체 및 추출된 된 부분 문자열의 복사본을 반환 합니다.

```
CStringT Right(int nCount) const;
```

### <a name="parameters"></a>매개 변수

*nCount*<br/>
이 `CStringT` 개체에서 추출할 문자의 수입니다.

### <a name="return-value"></a>반환 값

지정된 문자 범위의 복사본을 포함하는 `CStringT` 개체입니다. 반환 된 `CStringT` 개체는 비어 있을 수 있습니다.

### <a name="remarks"></a>설명

하는 경우 *nCount* 문자열 길이 초과 하면 다음 전체 문자열이 추출 됩니다. `Right` 기본 비슷합니다 `Right` 함수와 (점을 제외 하 고 기본 인덱스는 0부터 시작)입니다.

멀티 바이트 문자 집합 (MBCS)에 대 한 *nCount* 멀티 바이트 문자를 두 개의 문자로 계산 됩니다 하나에 각 8 비트 문자, 즉, 한 선행 및 후행 바이트를 가리킵니다.

### <a name="example"></a>예제

[!code-cpp[NVC_ATLMFC_Utilities#131](../../atl-mfc-shared/codesnippet/cpp/cstringt-class_35.cpp)]

##  <a name="setsysstring"></a>  CStringT::SetSysString

가리키는 BSTR 다시 할당 *pbstr* 의 내용을 복사 하 고는 `CStringT` 개체로, NULL 문자를 포함 합니다.

```
BSTR SetSysString(BSTR* pbstr) const;
```

### <a name="parameters"></a>매개 변수

*pbstr*<br/>
문자열 포인터입니다.

### <a name="return-value"></a>반환 값

새 문자열입니다.

### <a name="remarks"></a>설명

내용에 따라 합니다 `CStringT` 개체, 값에서 참조 하는 BSTR *pbstr* 변경할 수 있습니다. 함수가 throw를 `CMemoryException` 메모리가 부족 하 여 존재 하는 경우.

이 함수는 Automation에 대 한 참조로 전달 된 문자열의 값을 변경 하려면 일반적으로 사용 됩니다.

### <a name="example"></a>예제

[!code-cpp[NVC_ATLMFC_Utilities#132](../../atl-mfc-shared/codesnippet/cpp/cstringt-class_36.cpp)]

##  <a name="spanexcluding"></a>  CStringT::SpanExcluding

로 식별 되는 문자 집합에 있지 않은 첫 번째 문자부터 문자열에서 문자를 추출 *pszCharSet*합니다.

```
CStringT SpanExcluding(PCXSTR pszCharSet) const;
```

### <a name="parameters"></a>매개 변수

*pszCharSet*<br/>
문자열로 문자 집합으로 해석 합니다.

### <a name="return-value"></a>반환 값

에 없는 문자열의 문자를 포함 하는 부분 문자열 *pszCharSet*, 문자열의 첫 번째 문자로 시작 하 고 또한 문자열에서 찾은 첫 번째 문자로 끝나는 *pszCharSet* (즉, 문자열의 최대 하며 발견 된 문자열의 첫 번째 문자를 제외 하 고 첫 번째 문자부터 *pszCharSet*). 에 문자가 없는 경우에 전체 문자열을 반환 *pszCharSet* 문자열에서 발견 됩니다.

### <a name="remarks"></a>설명

`SpanExcluding` 추출 하 고 앞에서 문자의 첫 번째 발생 하는 모든 문자를 반환 *pszCharSet* (즉,에서 문자 *pszCharSet* 문자열에 따라 모든 문자가 없는 이 반환 됨). 문자가 없는 경우 *pszCharSet* 그런 다음 문자열에 있는 `SpanExcluding` 전체 문자열을 반환 합니다.

### <a name="example"></a>예제

[!code-cpp[NVC_ATLMFC_Utilities#133](../../atl-mfc-shared/codesnippet/cpp/cstringt-class_37.cpp)]

##  <a name="spanincluding"></a>  CStringT::SpanIncluding

로 식별 되는 문자 집합에 있는 첫 번째 문자부터 문자열에서 문자를 추출 *pszCharSet*합니다.

```
CStringT SpanIncluding(PCXSTR pszCharSet) const;
```

### <a name="parameters"></a>매개 변수

*pszCharSet*<br/>
문자열로 문자 집합으로 해석 합니다.

### <a name="return-value"></a>반환 값

에 있는 문자열의 문자를 포함 하는 부분 문자열 *pszCharSet*, 문자열의 첫 번째 문자로 시작 하 고이 아닌 문자열의 문자가 발견 되 면 끝나는 *pszCharSet*합니다. `SpanIncluding` 문자열의 첫 번째 문자에 지정한 집합에 없는 경우 빈 부분 문자열을 반환 합니다.

### <a name="remarks"></a>설명

문자열의 첫 번째 문자에에서 없는 경우 문자 집합을 다음 `SpanIncluding` 빈 문자열을 반환 합니다. 그렇지 않은 경우 집합에 있는 연속 된 문자 시퀀스를 반환 합니다.

### <a name="example"></a>예제

[!code-cpp[NVC_ATLMFC_Utilities#134](../../atl-mfc-shared/codesnippet/cpp/cstringt-class_38.cpp)]

##  <a name="tokenize"></a>  CStringT::Tokenize

대상 문자열에서 다음 토큰을 찾습니다.

```
CStringT Tokenize(PCXSTR pszTokens, int& iStart) const;
```

### <a name="parameters"></a>매개 변수

*pszTokens*<br/>
토큰 구분 기호를 포함 하는 문자열입니다. 이러한 구분 기호 순서가 중요 합니다.

*iStart*<br/>
검색을 시작할 0부터 시작 하는 인덱스입니다.

### <a name="return-value"></a>반환 값

`CStringT` 현재 토큰 값을 포함 하는 개체입니다.

### <a name="remarks"></a>설명

`Tokenize` 함수는 대상 문자열에서 다음 토큰을 찾습니다. 문자 집합이 *pszTokens* 찾을 토큰의 사용 가능한 구분 기호를 지정 합니다. 호출할 때마다 `Tokenize` 함수에서 시작 *iStart*선행 구분 기호를 건너뛰고 반환을 `CStringT` 다음 구분 기호 문자 까지의 문자 문자열인 현재 토큰을 포함 하는 개체입니다. 변수의 *iStart* 문자열의 끝에 도달한 경우 끝 구분 기호 또는-1을 다음 위치에 업데이트 됩니다. 토큰이 더 이상는 일련의 호출 하 여 대상 문자열의 나머지 분할할 수 있습니다 `Tokenize`를 사용 하 여 *iStart* 다음 토큰이 읽어야 하는 문자열의 위치를 추적 하기 위해. 함수는 빈 문자열을 반환 토큰이 더 이상 없으면 경우 및 *iStart* -1로 설정 됩니다.

CRT 달리와 같은 함수를 토큰화 [strtok_s, _strtok_s_l, wcstok_s, _wcstok_s_l, _mbstok_s, _mbstok_s_l](../../c-runtime-library/reference/strtok-s-strtok-s-l-wcstok-s-wcstok-s-l-mbstok-s-mbstok-s-l.md), `Tokenize` 대상 문자열을 수정 하지는 않습니다.

### <a name="example"></a>예제

[!code-cpp[NVC_ATLMFC_Utilities#135](../../atl-mfc-shared/codesnippet/cpp/cstringt-class_39.cpp)]

### <a name="remarks"></a>설명

이 예제의 출력은 다음과 같습니다.

```Output
Resulting Token: First
Resulting Token: Second
Resulting Token: Third
```

##  <a name="trim"></a>  CStringT::Trim

선행 및 후행 문자열에서 문자를 삭제 합니다.

```
CStringT& Trim(XCHAR chTarget);
CStringT& Trim(PCXSTR pszTargets);
CStringT& Trim();
```

### <a name="parameters"></a>매개 변수

*chTarget*<br/>
대상 문자 트리밍입니다.

*pszTargets*<br/>
대상 트리밍될 문자를 포함 하는 문자열에 대 한 포인터입니다. 모든 선행 및 후행 문자가 *pszTarget* 에서 잘립니다는 `CStringT` 개체입니다.

### <a name="return-value"></a>반환 값

잘라낸된 문자열을 반환합니다.

### <a name="remarks"></a>설명

다음 중 하나를의 선행 항목과 후행 항목이 모두 제거합니다.

- 지정한 문자 *chTarget*합니다.

- 지정 된 문자열에서 발견 되는 모든 문자 *pszTargets*합니다.

- 공백입니다.

### <a name="example"></a>예제

[!code-cpp[NVC_ATLMFC_Utilities#136](../../atl-mfc-shared/codesnippet/cpp/cstringt-class_40.cpp)]

### <a name="remarks"></a>설명

이 예제의 출력은 다음과 같습니다.

```Output
Before: "******Soccer is best, but liquor is quicker!!!!!"
After : "Soccer is best, but liquor is quicker"
```

##  <a name="trimleft"></a>  CStringT::TrimLeft

문자열에서 선행 문자를 삭제 합니다.

```
CStringT& TrimLeft(XCHAR chTarget);
CStringT& TrimLeft(PCXSTR pszTargets);
CStringT& TrimLeft();
```

### <a name="parameters"></a>매개 변수

*chTarget*<br/>
대상 문자 트리밍입니다.

*pszTargets*<br/>
대상 트리밍될 문자를 포함 하는 문자열에 대 한 포인터입니다. 에 있는 문자의 선행 항목을 모두 *pszTarget* 에서 잘립니다는 `CStringT` 개체입니다.

### <a name="return-value"></a>반환 값

결과 잘라낸된 문자열입니다.

### <a name="remarks"></a>설명

다음 중 하나를의 선행 항목과 후행 항목이 모두 제거합니다.

- 지정한 문자 *chTarget*합니다.

- 지정 된 문자열에서 발견 되는 모든 문자 *pszTargets*합니다.

- 공백입니다.

### <a name="example"></a>예제

[!code-cpp[NVC_ATLMFC_Utilities#137](../../atl-mfc-shared/codesnippet/cpp/cstringt-class_41.cpp)]

##  <a name="trimright"></a>  CStringT::TrimRight

문자열에서 후행 문자를 삭제 합니다.

```
CStringT& TrimRight(XCHAR chTarget);
CStringT& TrimRight(PCXSTR pszTargets);
CStringT& TrimRight();
```

### <a name="parameters"></a>매개 변수

*chTarget*<br/>
대상 문자 트리밍입니다.

*pszTargets*<br/>
대상 트리밍될 문자를 포함 하는 문자열에 대 한 포인터입니다. 모든 후행 문자가 *pszTarget* 에서 잘립니다는 `CStringT` 개체입니다.

### <a name="return-value"></a>반환 값

반환 된 `CStringT` 잘라낸된 문자열을 포함 하는 개체입니다.

### <a name="remarks"></a>설명

후행 개 중 하나를 제거 합니다.

- 지정한 문자 *chTarget*합니다.

- 지정 된 문자열에서 발견 되는 모든 문자 *pszTargets*합니다.

- 공백입니다.

합니다 `CStringT& TrimRight(XCHAR chTarget)` 문자에 대 한 매개 변수를 하나를 적용 하 고 끝에서 해당 문자의 모든 복사본을 제거 하는 버전 `CStringT` 문자열 데이터입니다. 문자열의 끝에서 시작 하 고 앞면 작동 합니다. 때나 다른 문자를 발견할 때 중지 `CSTringT` 문자 데이터 부족 합니다.

`CStringT& TrimRight(PCXSTR pszTargets)` 버전 검색 하려면 다른 모든 문자를 포함 하는 null로 끝나는 문자열을 수락 합니다. 모든 복사본에서 해당 문자가 제거 된 `CStringT` 개체입니다. 문자열의 끝에서 시작 하 고 앞면 작동 합니다. 대상 문자열에 없는 문자를 발견 하면 때나 중지 `CStringT` 문자 데이터 부족 합니다. 전체 대상 문자열의 끝 부분 문자열을 일치 시 키 려 하지 `CStringT`합니다.

`CStringT& TrimRight()` 버전 매개 변수 없이 필요 합니다. 끝에서 후행 공백 문자를 자르는 것은 `CStringT` 문자열입니다. 공백 문자는 줄 바꿈, 공백 또는 탭 수 있습니다.

-

### <a name="example"></a>예제

[!code-cpp[NVC_ATLMFC_Utilities#138](../../atl-mfc-shared/codesnippet/cpp/cstringt-class_42.cpp)]

## <a name="see-also"></a>참고자료

[계층 구조 차트](../../mfc/hierarchy-chart.md)<br/>
[ATL/MFC 공유 클래스](../../atl-mfc-shared/atl-mfc-shared-classes.md)<br/>
[CSimpleStringT 클래스](../../atl-mfc-shared/reference/csimplestringt-class.md)
