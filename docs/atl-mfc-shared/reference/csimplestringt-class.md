---
title: CSimpleStringT 클래스
ms.date: 10/18/2018
f1_keywords:
- CSimpleStringT
- ATLSIMPSTR/ATL::CSimpleStringT
- ATLSIMPSTR/ATL::CSimpleStringT::PCXSTR
- ATLSIMPSTR/ATL::CSimpleStringT::PXSTR
- ATLSIMPSTR/ATL::CSimpleStringT::CSimpleStringT
- ATLSIMPSTR/ATL::CSimpleStringT::Append
- ATLSIMPSTR/ATL::CSimpleStringT::AppendChar
- ATLSIMPSTR/ATL::CSimpleStringT::CopyChars
- ATLSIMPSTR/ATL::CSimpleStringT::CopyCharsOverlapped
- ATLSIMPSTR/ATL::CSimpleStringT::Empty
- ATLSIMPSTR/ATL::CSimpleStringT::FreeExtra
- ATLSIMPSTR/ATL::CSimpleStringT::GetAllocLength
- ATLSIMPSTR/ATL::CSimpleStringT::GetAt
- ATLSIMPSTR/ATL::CSimpleStringT::GetBuffer
- ATLSIMPSTR/ATL::CSimpleStringT::GetBufferSetLength
- ATLSIMPSTR/ATL::CSimpleStringT::GetLength
- ATLSIMPSTR/ATL::CSimpleStringT::GetManager
- ATLSIMPSTR/ATL::CSimpleStringT::GetString
- ATLSIMPSTR/ATL::CSimpleStringT::IsEmpty
- ATLSIMPSTR/ATL::CSimpleStringT::LockBuffer
- ATLSIMPSTR/ATL::CSimpleStringT::Preallocate
- ATLSIMPSTR/ATL::CSimpleStringT::ReleaseBuffer
- ATLSIMPSTR/ATL::CSimpleStringT::ReleaseBufferSetLength
- ATLSIMPSTR/ATL::CSimpleStringT::SetAt
- ATLSIMPSTR/ATL::CSimpleStringT::SetManager
- ATLSIMPSTR/ATL::CSimpleStringT::SetString
- ATLSIMPSTR/ATL::CSimpleStringT::StringLength
- ATLSIMPSTR/ATL::CSimpleStringT::Truncate
- ATLSIMPSTR/ATL::CSimpleStringT::UnlockBuffer
helpviewer_keywords:
- shared classes, CSimpleStringT
- strings [C++], ATL class
- CSimpleStringT class
ms.assetid: 15814fcb-5b8f-4425-a97e-3b61fc9b48d8
ms.openlocfilehash: 1ec28ed5b2f5428cabcf7570c7ac53904e9a64f0
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62252640"
---
# <a name="csimplestringt-class"></a>CSimpleStringT 클래스

이 클래스를 나타냅니다는 `CSimpleStringT` 개체입니다.

## <a name="syntax"></a>구문

```
template <typename BaseType>
class CSimpleStringT
```

### <a name="parameters"></a>매개 변수

*BaseType*<br/>
String 클래스의 문자 형식입니다. 다음 중 하나일 수 있습니다.

- **char** (용 ANSI 문자열)입니다.

- **wchar_t** (용 유니코드 문자열)입니다.

- TCHAR (ANSI 및 유니코드 문자열)에 대 한 합니다.

## <a name="members"></a>멤버

### <a name="public-typedefs"></a>공용 Typedefs

|이름|설명|
|----------|-----------------|
|[CSimpleStringT::PCXSTR](#pcxstr)|상수 문자열 포인터입니다.|
|[CSimpleStringT::PXSTR](#pxstr)|문자열 포인터입니다.|

### <a name="public-constructors"></a>Public 생성자

|이름|설명|
|----------|-----------------|
|[CSimpleStringT::CSimpleStringT](#ctor)|생성 `CSimpleStringT` 다양 한 방법으로 개체입니다.|
|[CSimpleStringT::~CSimpleStringT](#dtor)|소멸자|

### <a name="public-methods"></a>Public 메서드

|이름|설명|
|----------|-----------------|
|[CSimpleStringT::Append](#append)|추가 된 `CSimpleStringT` 개체를 기존 `CSimpleStringT` 개체입니다.|
|[CSimpleStringT::AppendChar](#appendchar)|기존 문자를 추가 `CSimpleStringT` 개체입니다.|
|[CSimpleStringT::CopyChars](#copychars)|다른 문자열에 문자 또는 문자를 복사합니다.|
|[CSimpleStringT::CopyCharsOverlapped](#copycharsoverlapped)|버퍼는 겹치는 다른 문자열에 문자 또는 문자를 복사 합니다.|
|[CSimpleStringT::Empty](#empty)|길이가 0 인 문자열을 강제로 수행 합니다.|
|[CSimpleStringT::FreeExtra](#freeextra)|이전에 문자열 개체에서 할당 하는 추가 메모리를 해제 합니다.|
|[CSimpleStringT::GetAllocLength](#getalloclength)|할당 된 길이 검색 한 `CSimpleStringT` 개체입니다.|
|[CSimpleStringT::GetAt](#getat)|지정된 된 위치에 문자를 반환합니다.|
|[CSimpleStringT::GetBuffer](#getbuffer)|문자에 대 한 포인터를 반환 합니다.는 `CSimpleStringT`합니다.|
|[CSimpleStringT::GetBufferSetLength](#getbuffersetlength)|문자에 대 한 포인터를 반환 합니다.는 `CSimpleStringT`, 지정 된 길이입니다.|
|[CSimpleStringT::GetLength](#getlength)|문자 수가 반환을 `CSimpleStringT` 개체입니다.|
|[CSimpleStringT::GetManager](#getmanager)|메모리 관리자를 검색 합니다 `CSimpleStringT` 개체입니다.|
|[CSimpleStringT::GetString](#getstring)|문자열 검색|
|[CSimpleStringT::IsEmpty](#isempty)|테스트 여부는 `CSimpleStringT` 문자를 포함 하는 개체입니다.|
|[CSimpleStringT::LockBuffer](#lockbuffer)|참조 횟수를 사용 하지 않도록 설정 하 고 버퍼에 문자열을 보호 합니다.|
|[CSimpleStringT::Preallocate](#preallocate)|문자 버퍼에 대 한 특정 크기의 메모리를 할당합니다.|
|[CSimpleStringT::ReleaseBuffer](#releasebuffer)|반환 되는 버퍼의 제어권을 해제 `GetBuffer`합니다.|
|[CSimpleStringT::ReleaseBufferSetLength](#releasebuffersetlength)|반환 되는 버퍼의 제어권을 해제 `GetBuffer`합니다.|
|[CSimpleStringT::SetAt](#setat)|지정된 된 위치에 문자를 설정합니다.|
|[CSimpleStringT::SetManager](#setmanager)|설정의 메모리 관리자는 `CSimpleStringT` 개체입니다.|
|[CSimpleStringT::SetString](#setstring)|문자열을 설정 하는 `CSimpleStringT` 개체입니다.|
|[CSimpleStringT::StringLength](#stringlength)|지정된 된 문자열의 문자 수를 반환합니다.|
|[CSimpleStringT::Truncate](#truncate)|지정한 길이 문자열을 자릅니다.|
|[CSimpleStringT::UnlockBuffer](#unlockbuffer)|참조 횟수를 사용 하도록 설정 하 고 버퍼에 문자열을 해제 합니다.|

### <a name="public-operators"></a>Public 연산자

|이름|설명|
|----------|-----------------|
|[CSimpleStringT::operator PCXSTR](#operator_pcxstr)|에 저장 된 문자에 직접 액세스를 `CSimpleStringT` C 스타일 문자열로 개체입니다.|
|[CSimpleStringT::operator\[\]](#operator_at)|지정된 된 위치에 문자를 반환 합니다-에 대 한 연산자 대체 `GetAt`합니다.|
|[CSimpleStringT::operator +=](#operator_add_eq)|기존 문자열의 끝에 새 문자열을 연결합니다.|
|[CSimpleStringT::operator =](#operator_eq)|새 값을 할당 한 `CSimpleStringT` 개체입니다.|

### <a name="remarks"></a>설명

`CSimpleStringT` 시각적 개체에서 지 원하는 다양 한 문자열 클래스에 대 한 기본 클래스인 C++입니다. 기본 버퍼 조작 문자열 개체의 메모리 관리에 대 한 최소한의 지원을 제공합니다. 고급 문자열 개체를 참조 하세요 [CStringT 클래스](../../atl-mfc-shared/reference/cstringt-class.md)합니다.

### <a name="requirements"></a>요구 사항

**헤더:** atlsimpstr.h

## <a name="append"></a> CSimpleStringT::Append

추가 된 `CSimpleStringT` 개체를 기존 `CSimpleStringT` 개체입니다.

### <a name="syntax"></a>구문

```
void Append(const CSimpleStringT& strSrc);
void Append(PCXSTR pszSrc, int nLength);
void Append(PCXSTR pszSrc);
```

#### <a name="parameters"></a>매개 변수

*strSrc*<br/>
`CSimpleStringT` 추가할 개체입니다.

*pszSrc*<br/>
추가할 문자를 포함 하는 문자열에 대 한 포인터입니다.

*nLength*<br/>
추가할 문자 수입니다.

### <a name="remarks"></a>설명

기존 추가 하려면이 메서드를 호출 `CSimpleStringT` 개체를 다른 `CSimpleStringT` 개체입니다.

### <a name="example"></a>예제

다음 예에서는 `CSimpleStringT::Append`의 사용법을 보여줍니다.

```cpp
CSimpleString str1(pMgr), str2(pMgr);
str1.SetString(_T("Soccer is"));
str2.SetString(_T(" an elegant game"));
str1.Append(str2);
ASSERT(_tcscmp(str1, _T("Soccer is an elegant game")) == 0);
```

##  <a name="appendchar"></a> CSimpleStringT::AppendChar

기존 문자를 추가 `CSimpleStringT` 개체입니다.

### <a name="syntax"></a>구문

```
void AppendChar(XCHAR ch);
```

#### <a name="parameters"></a>매개 변수

*ch*<br/>
추가할 문자

### <a name="remarks"></a>설명

기존의 끝에 지정된 된 문자를 추가 하려면이 함수를 호출 `CSimpleStringT` 개체입니다.

##  <a name="copychars"></a> CSimpleStringT::CopyChars

문자 또는 문자 복사를 `CSimpleStringT` 개체입니다.

### <a name="syntax"></a>구문

```
static void CopyChars(
    XCHAR* pchDest,
    const XCHAR* pchSrc,
    int nChars) throw();
```

#### <a name="parameters"></a>매개 변수

*pchDest*<br/>
문자열 포인터입니다.

*pchSrc*<br/>
복사할 문자를 포함 하는 문자열에 대 한 포인터입니다.

*nChars*<br/>
수가 *pchSrc* 복사 될 문자입니다.

### <a name="remarks"></a>설명

문자를 복사 하려면이 메서드를 호출 *pchSrc* 에 *pchDest* 문자열입니다.

### <a name="example"></a>예제

다음 예에서는 `CSimpleStringT::CopyChars`의 사용법을 보여줍니다.

```cpp
CSimpleString str(_T("xxxxxxxxxxxxxxxxxxx"), 20, pMgr);
TCHAR* pszSrc = _T("Hello world!");
_tprintf_s(_T("%s\n"), str);
str.CopyChars(str.GetBuffer(), pszSrc, 12);
_tprintf_s(_T("%s\n"), str);
```

##  <a name="copycharsoverlapped"></a>  CSimpleStringT::CopyCharsOverlapped

문자 또는 문자 복사를 `CSimpleStringT` 개체입니다.

### <a name="syntax"></a>구문

```
static void CopyCharsOverlapped(
    XCHAR* pchDest,
    const XCHAR* pchSrc,
    int nChars) throw();
```

#### <a name="parameters"></a>매개 변수

*pchDest*<br/>
문자열 포인터입니다.

*pchSrc*<br/>
복사할 문자를 포함 하는 문자열에 대 한 포인터입니다.

*nChars*<br/>
수가 *pchSrc* 복사 될 문자입니다.

### <a name="remarks"></a>설명

문자를 복사 하려면이 메서드를 호출 *pchSrc* 에 *pchDest* 문자열입니다. 와 달리 `CopyChars`, `CopyCharsOverlapped` 겹칠 수 있습니다 하는 문자 버퍼에서 복사 하기 위한 안전한 방법을 제공 합니다.

### <a name="example"></a>예제

예를 참조 하세요 [CSimpleStringT::CopyChars](#copychars), 또는 소스 코드에 대 한 `CSimpleStringT::SetString` (atlsimpstr.h에 있음).

##  <a name="ctor"></a>  CSimpleStringT::CSimpleStringT

`CSimpleStringT` 개체를 생성합니다.

### <a name="syntax"></a>구문

```
CSimpleStringT(const XCHAR* pchSrc, int nLength, IAtlStringMgr* pStringMgr);
CSimpleStringT(PCXSTR pszSrc, IAtlStringMgr* pStringMgr);
CSimpleStringT(const CSimpleStringT& strSrc);
explicit CSimpleStringT(IAtlStringMgr* pStringMgr) throw();
```

#### <a name="parameters"></a>매개 변수

*strSrc*<br/>
기존 `CSimpleStringT` 에이 복사 될 개체 `CSimpleStringT` 개체입니다.

*pchSrc*<br/>
길이 문자 배열에 대 한 포인터 *nLength*, null 종료 되지 않습니다.

*pszSrc*<br/>
복사할이 null로 끝나는 문자열을 `CSimpleStringT` 개체입니다.

*nLength*<br/>
문자 수가 `pch`합니다.

*pStringMgr*<br/>
메모리 관리자에 대 한 포인터를 `CSimpleStringT` 개체입니다. 에 대 한 자세한 내용은 `IAtlStringMgr` 및 메모리 관리에 대 한 `CSimpleStringT`를 참조 하십시오 [메모리 관리 및 CStringT](../memory-management-with-cstringt.md)합니다.

### <a name="remarks"></a>설명

새 `CSimpleStringT` 개체를 생성합니다. 생성자에 할당 된 새 저장소를 입력된 데이터를 복사 하기 때문에 메모리 예외가 발생할 수 있습니다.

### <a name="example"></a>예제

다음 예제에서는의 사용을 보여 줍니다 `CSimpleStringT::CSimpleStringT` ATL을 사용 하 여 **typedef** `CSimpleString`합니다. `CSimpleString` 자주 사용 되는 클래스 템플릿의 특수화 인 `CSimpleStringT`합니다.

```cpp
CSimpleString s1(pMgr);
// Empty string
CSimpleString s2(_T("cat"), pMgr);
// From a C string literal

CSimpleString s3(s2);
// Copy constructor
CSimpleString s4(s2 + _T(" ") + s3);

// From a string expression
CSimpleString s5(_T("xxxxxx"), 6, pMgr);
// s5 = "xxxxxx"
```

##  <a name="empty"></a>  CSimpleStringT::Empty

이 사용 하면 `CSimpleStringT` 빈 문자열 개체를 적절 하 게 메모리를 해제 합니다.

### <a name="syntax"></a>구문

```
void Empty() throw();
```

### <a name="remarks"></a>설명

자세한 내용은 참조 하세요. [문자열: CString 예외 정리](../cstring-exception-cleanup.md)합니다.

### <a name="example"></a>예제

다음 예에서는 `CSimpleStringT::Empty`의 사용법을 보여줍니다.

```cpp
CSimpleString s(pMgr);
ASSERT(s.IsEmpty());
```

##  <a name="freeextra"></a>  CSimpleStringT::FreeExtra

문자열에서 이전에 할당 되었지만 더 이상 필요 하지는 추가 메모리를 해제 합니다.

### <a name="syntax"></a>구문

```
void FreeExtra();
```

### <a name="remarks"></a>설명

이 문자열 개체가 사용한 메모리 오버 헤드를 줄여야 합니다. 메서드를 다시 반환 하는 정확한 길이 버퍼를 할당 [GetLength](#getlength)합니다.

### <a name="example"></a>예제

```cpp
CAtlString basestr;
IAtlStringMgr* pMgr;

pMgr= basestr.GetManager();
ASSERT(pMgr != NULL);

// Create a CSimpleString with 28 characters
CSimpleString str(_T("Many sports are fun to play."), 28, pMgr);
_tprintf_s(_T("Alloc length is %d, String length is %d\n"),
   str.GetAllocLength(), str.GetLength());

// Assigning a smaller string won't cause CSimpleString to free its
// memory, because it assumes the string will grow again anyway.
str = _T("Soccer is best!");
_tprintf_s(_T("Alloc length is %d, String length is %d\n"),
   str.GetAllocLength(), str.GetLength());

// This call forces CSimpleString to release the extra
// memory it doesn't need.
str.FreeExtra();
_tprintf_s(_T("Alloc length is %d, String length is %d\n"),
   str.GetAllocLength(), str.GetLength());
```

### <a name="remarks"></a>설명

이 예제의 출력은 다음과 같습니다.

```Output
Alloc length is 1031, String length is 1024
Alloc length is 1031, String length is 15
Alloc length is 15, String length is 15
```

##  <a name="getalloclength"></a>  CSimpleStringT::GetAllocLength

할당 된 길이 검색 한 `CSimpleStringT` 개체입니다.

### <a name="syntax"></a>구문

```
int GetAllocLength() const throw();
```

### <a name="return-value"></a>반환 값

이 개체에 할당 된 문자의 수입니다.

### <a name="remarks"></a>설명

이 할당 된 문자의 수를 확인 하려면이 메서드를 호출 `CSimpleStringT` 개체입니다. 참조 [FreeExtra](#freeextra) 이 함수를 호출 하는 예입니다.

##  <a name="getat"></a>  CSimpleStringT::GetAt

하나의 문자를 반환 합니다.는 `CSimpleStringT` 개체입니다.

### <a name="syntax"></a>구문

```
XCHAR GetAt(int iChar) const;
```

#### <a name="parameters"></a>매개 변수

*iChar*<br/>
문자의 0부터 시작 인덱스는 `CSimpleStringT` 개체입니다. 합니다 *iChar* 매개 변수 보다 큰 또는 0 및 반환 하는 값 미만 이어야 합니다. [GetLength](#getlength)합니다. 그렇지 않으면 `GetAt` 하면 예외가 발생 합니다.

### <a name="return-value"></a>반환 값

`XCHAR` 문자열에 지정된 된 위치에 문자를 포함 하는 합니다.

### <a name="remarks"></a>설명

지정 된 하나의 문자를 반환 하려면이 메서드를 호출 *iChar*합니다. 오버 로드 된 첨자 (**[]**) 연산자에 대 한 편리한 별칭입니다 `GetAt`합니다. 사용 하 여 예외를 생성 하지 않고 null 종결자가 주소 지정 가능 `GetAt`합니다. 그러나 하 여 계산 되지 않습니다 `GetLength`, 반환 값은 0입니다.

### <a name="example"></a>예제

다음 예제에 사용 하는 방법을 보여 줍니다. `CSimpleStringT::GetAt`합니다.

```cpp
CSimpleString s(_T("abcdef"), pMgr);
ASSERT(s.GetAt(2) == _T('c'));
```

##  <a name="getbuffer"></a>  CSimpleStringT::GetBuffer

에 대 한 내부 문자 버퍼에 대 한 포인터를 반환 합니다 `CSimpleStringT` 개체입니다.

### <a name="syntax"></a>구문

```
PXSTR GetBuffer(int nMinBufferLength);
PXSTR GetBuffer();
```

#### <a name="parameters"></a>매개 변수

*nMinBufferLength*<br/>
문자 버퍼에서 보유할 수 있는 문자의 최소 수입니다. 이 값에 null 종결자를 위한 공간이 포함 되지 않습니다.

하는 경우 *nMinBufferLength* 현재 버퍼의 길이 보다 크면 `GetBuffer` 현재 버퍼 제거, 요청된 된 크기의 버퍼를 사용 하 여 대체 및 개체 참조 횟수를 0으로 다시 설정 합니다. 이전에 호출한 경우 [LockBuffer](#lockbuffer) 이 버퍼에서 버퍼 잠금이 손실 합니다.

### <a name="return-value"></a>반환 값

`PXSTR` 개체의 문자 (null로 종료 됨) 버퍼에 대 한 포인터입니다.

### <a name="remarks"></a>설명

버퍼 콘텐츠를 반환 하려면이 메서드는 `CSimpleStringT` 개체입니다. 반환 된 `PXSTR` 상수가 아닙니다. 따라서 직접 수정할 수 있습니다 및 `CSimpleStringT` 내용입니다.

반환 된 포인터를 사용 하는 경우 `GetBuffer` 호출 문자열 내용을 변경 해야 합니다 [ReleaseBuffer](#releasebuffer) 다른 사용 하기 전에 `CSimpleStringT` 멤버 메서드.

반환 된 주소 `GetBuffer` 유효 하지 않을를 호출한 후 `ReleaseBuffer` 때문에 추가 `CSimpleStringT` 작업이 발생할 수 있습니다는 `CSimpleStringT` 버퍼가 다시 할당 합니다. 버퍼의 길이 변경 하지 않는 경우 다시 할당 되지 않습니다는 `CSimpleStringT`합니다.

버퍼 메모리는 자동으로 해제 될 때를 `CSimpleStringT` 개체는 소멸 됩니다.

유지 추적 경우 문자열 길이 직접, 종결 null 문자를 추가 해서는 안 됩니다. 하지만 사용 하 여 버퍼를 해제 하는 경우 최종 문자열 길이 지정 해야 `ReleaseBuffer`합니다. Null 종결 문자를 추가한 경우 길이 대 한-1 (기본값)를 전달 해야 합니다. `ReleaseBuffer` 버퍼 길이 결정합니다.

충족 하기 위해 메모리가 부족 한 경우는 `GetBuffer` 이 메서드에서 throw CMemoryException *를 요청 합니다.

### <a name="example"></a>예제

```cpp
CSimpleString s(_T("abcd"), pMgr);
LPTSTR pBuffer = s.GetBuffer(10);
int sizeOfBuffer = s.GetAllocLength();

// Directly access CSimpleString buffer
_tcscpy_s(pBuffer, sizeOfBuffer, _T("Hello"));
ASSERT(_tcscmp(s, _T("Hello")) == 0);
s.ReleaseBuffer();
```

##  <a name="getbuffersetlength"></a>  CSimpleStringT::GetBufferSetLength

에 대 한 내부 문자 버퍼에 대 한 포인터를 반환 합니다 `CSimpleStringT` 개체에서 잘림 또는에서 지정한 길이 정확 하 게 일치 하는 데 필요한 경우 해당 길이 증가 *nLength*합니다.

### <a name="syntax"></a>구문

```
PXSTR GetBufferSetLength(int nLength);
```

#### <a name="parameters"></a>매개 변수

*nLength*<br/>
정확한 크기를 `CSimpleStringT` 문자의 문자 버퍼입니다.

### <a name="return-value"></a>반환 값

`PXSTR` 개체의 문자 (null로 종료 됨) 버퍼에 대 한 포인터입니다.

### <a name="remarks"></a>설명

내부 버퍼의 지정 된 길이 검색 하려면이 메서드는 `CSimpleStringT` 개체입니다. 반환 된 `PXSTR` 포인터가 아닙니다 **const** 를 직접 수정 되므로 하며 `CSimpleStringT` 내용입니다.

반환 된 포인터를 사용 하는 경우 [GetBufferSetLength](#getbuffersetlength) 문자열 콘텐츠를 변경 하려면 호출 `ReleaseBuffer` 의 내부 상태를 업데이트할 `CsimpleStringT` 다른 사용 하기 전에 `CSimpleStringT` 메서드.

반환 된 주소 `GetBufferSetLength` 유효 하지 않을를 호출한 후 `ReleaseBuffer` 때문에 추가 `CSimpleStringT` 작업이 발생할 수 있습니다는 `CSimpleStringT` 버퍼가 다시 할당 합니다. 버퍼의 길이 변경 하지 않는 경우 다시 할당 되지 않습니다는 `CSimpleStringT`합니다.

버퍼 메모리는 자동으로 해제 될 때를 `CSimpleStringT` 개체는 소멸 됩니다.

추적 있습니다 문자열 길이 직접, 종결 null 문자를 추가 하지 마십시오. 사용 하 여 버퍼를 해제 하는 경우에 최종 문자열 길이 지정 해야 `ReleaseBuffer`합니다. 호출할 때 null 종결 문자를 추가 수행 하는 경우 `ReleaseBuffer`,-1 (기본값) 길이 전달 `ReleaseBuffer`, 및 `ReleaseBuffer` 수행할지를 `strlen` 해당 길이 확인 하는 버퍼에서 합니다.

참조 횟수에 대 한 자세한 내용은 다음 문서를 참조 합니다.

- [참조 횟수를 통해 개체 수명 관리](/windows/desktop/com/managing-object-lifetimes-through-reference-counting) Windows SDK에에서 있습니다.

- [참조 카운팅 구현](/windows/desktop/com/implementing-reference-counting) Windows SDK에에서 있습니다.

- [참조 횟수를 관리 하는 것에 대 한 규칙](/windows/desktop/com/rules-for-managing-reference-counts) Windows SDK에에서 있습니다.

### <a name="example"></a>예제

다음 예에서는 `CSimpleStringT::GetBufferSetLength`의 사용법을 보여줍니다.

```cpp
CSimpleString str(pMgr);
LPTSTR pstr = str.GetBufferSetLength(3);
pstr[0] = _T('C');
pstr[1] = _T('u');
pstr[2] = _T('p');

// No need for trailing zero or call to ReleaseBuffer()
// because GetBufferSetLength() set it for us.

str += _T(" soccer is best!");
ASSERT(_tcscmp(str, _T("Cup soccer is best!")) == 0);
```

##  <a name="getlength"></a>  CSimpleStringT::GetLength

에 있는 문자의 수를 반환 합니다 `CSimpleStringT` 개체입니다.

### <a name="syntax"></a>구문

```
int GetLength() const throw();
```

### <a name="return-value"></a>반환 값

문자열의 문자 수입니다.

### <a name="remarks"></a>설명

개체의 문자 수를 반환 하려면이 메서드를 호출 합니다. 수는 null 종결자를 포함 하지 않습니다.

멀티 바이트 문자 집합 (MBCS)에 대 한 `GetLength` 개수 한 멀티 바이트 문자의 각 8 비트 문자, 즉, 한 선행 및 후행 바이트 2 바이트도 간주 됩니다. 참조 [FreeExtra](#freeextra) 이 함수를 호출 하는 예입니다.

##  <a name="getmanager"></a>  CSimpleStringT::GetManager

메모리 관리자를 검색 합니다 `CSimpleStringT` 개체입니다.

### <a name="syntax"></a>구문

```
IAtlStringMgr* GetManager() const throw();
```

### <a name="return-value"></a>반환 값

Memory manager에 대 한 포인터를 `CSimpleStringT` 개체입니다.

### <a name="remarks"></a>설명

사용 하는 관리자는 메모리를 검색 하려면이 메서드를 호출 합니다 `CSimpleStringT` 개체입니다. 메모리 관리자 및 문자열 개체에 대 한 자세한 내용은 참조 하세요. [메모리 관리 및 CStringT](../memory-management-with-cstringt.md)합니다.

##  <a name="getstring"></a>  CSimpleStringT::GetString

문자열을 검색합니다.

### <a name="syntax"></a>구문

```
PCXSTR GetString() const throw();
```

### <a name="return-value"></a>반환 값

Null로 끝나는 문자열에 대 한 포인터입니다.

### <a name="remarks"></a>설명

연결 된 문자열을 검색 하려면이 메서드는 `CSimpleStringT` 개체입니다.

> [!NOTE]
>  반환 된 `PCXSTR` 포인터가 **const** 직접 수정할 수 없도록 하 고 `CSimpleStringT` 내용입니다.

### <a name="example"></a>예제

다음 예에서는 `CSimpleStringT::GetString`의 사용법을 보여줍니다.

```cpp
CSimpleString str(pMgr);
str += _T("Cup soccer is best!");
_tprintf_s(_T("%s"), str.GetString());
```

##  <a name="isempty"></a>  CSimpleStringT::IsEmpty

테스트는 `CSimpleStringT` 빈 조건에 대 한 개체입니다.

### <a name="syntax"></a>구문

```
bool IsEmpty() const throw();
```

### <a name="return-value"></a>반환 값

경우 TRUE를 반환 합니다 `CSimpleStringT` 개체의 0 길이; 그렇지 않으면 FALSE입니다.

### <a name="remarks"></a>설명

개체가 비어 있는지 확인 하려면이 메서드를 호출 합니다.

### <a name="example"></a>예제

다음 예에서는 `CSimpleStringT::IsEmpty`의 사용법을 보여줍니다.

```cpp
CSimpleString s(pMgr);
ASSERT(s.IsEmpty());
```

##  <a name="lockbuffer"></a>  CSimpleStringT::LockBuffer

참조 횟수를 사용 하지 않도록 설정 하 고 버퍼에 문자열을 보호 합니다.

### <a name="syntax"></a>구문

```
PXSTR LockBuffer();
```

### <a name="return-value"></a>반환 값

에 대 한 포인터를 `CSimpleStringT` 개체 또는 null로 끝나는 문자열입니다.

### <a name="remarks"></a>설명

버퍼를 잠그는이 메서드를 호출 합니다 `CSimpleStringT` 개체입니다. 호출 하 여 `LockBuffer`, 참조 횟수에 대 한-1을 사용 하 여 문자열의 복사본을 만듭니다. 참조 횟수 값-1 이면 문자열 버퍼에 "잠금" 상태인 것으로 간주 됩니다. 잠긴 상태에서는 문자열은 두 가지 방법으로 보호 됩니다.

- 해당 문자열은 잠긴된 문자열에 할당 된 경우에 다른 문자열이 없으면 잠긴된 문자열에서 데이터에 대 한 참조를 가져올 수 있습니다.

- 되지 잠긴된 문자열은 잠긴된 문자열에는 다른 문자열을 복사 하는 경우에 다른 문자열을를 참조 해야 합니다.

문자열 버퍼에 잠금 시키면 버퍼에 대 한 문자열의 단독 보유를 그대로 유지 됩니다.

사용 하 여 완료 한 후 `LockBuffer`, 호출 [UnlockBuffer](#unlockbuffer) 참조 횟수를 1로 재설정 합니다.

> [!NOTE]
>  호출 하는 경우 [GetBuffer](#getbuffer) 잠긴된 버퍼에 설정 된 `GetBuffer` 매개 변수 `nMinBufferLength` 현재 버퍼의 길이 보다 큰, 버퍼 잠금이 손실 됩니다. 이러한 호출을 `GetBuffer` 현재 버퍼를 제거 하 고 요청된 된 크기의 버퍼를 사용 하 여 대체 참조 횟수를 0으로 다시 설정 합니다.

참조 횟수에 대 한 자세한 내용은 다음 문서를 참조 합니다.

- [참조 횟수를 통해 개체 수명 관리](/windows/desktop/com/managing-object-lifetimes-through-reference-counting) Windows SDK에서

- [참조 카운팅 구현](/windows/desktop/com/implementing-reference-counting) Windows SDK에서

- [참조 횟수를 관리 하는 것에 대 한 규칙](/windows/desktop/com/rules-for-managing-reference-counts) Windows SDK에서

### <a name="example"></a>예제

다음 예에서는 `CSimpleStringT::LockBuffer`의 사용법을 보여줍니다.

```cpp
CSimpleString str(_T("Hello"), pMgr);
TCHAR ch;

str.LockBuffer();
ch = str.GetAt(2);
_tprintf_s(_T("%c"), ch);
str.UnlockBuffer();
```

##  <a name="operator_at"></a>  CSimpleStringT::operator\[\]

문자 배열의 단일 문자에 액세스 하려면이 함수를 호출 합니다.

### <a name="syntax"></a>구문

```
XCHAR operator[](int iChar) const;
```

#### <a name="parameters"></a>매개 변수

*iChar*<br/>
문자열에서 문자의 0부터 시작 인덱스입니다.

### <a name="remarks"></a>설명

오버 로드 된 첨자 (**[]**) 연산자의 0부터 시작 하는 인덱스로 지정 된 단일 문자를 반환 합니다. *iChar*합니다. 이 연산자는 편리한 대체 합니다 [GetAt](#getat) 멤버 함수입니다.

> [!NOTE]
>  첨자를 사용할 수 있습니다 (**[]**)에 있는 문자의 값을 검색할 연산자를 `CSimpleStringT`, 하지만 있는 문자의 값을 변경 하려면 사용할 수 없습니다를 `CSimpleStringT`입니다.

### <a name="example"></a>예제

다음 예에서는 `CSimpleStringT::operator []`의 사용법을 보여줍니다.

```cpp
CSimpleString s(_T("abc"), pMgr);
ASSERT(s[1] == _T('b'));
```

## <a name="operator_at"></a>  CSimpleStringT::operator \[\]

문자 배열의 단일 문자에 액세스 하려면이 함수를 호출 합니다.

### <a name="syntax"></a>구문

```
XCHAR operator[](int iChar) const;
```

### <a name="parameters"></a>매개 변수

*iChar*<br/>
문자열에서 문자의 0부터 시작 인덱스입니다.

### <a name="remarks"></a>설명

오버 로드 된 첨자 (**[]**) 연산자의 0부터 시작 하는 인덱스로 지정 된 단일 문자를 반환 합니다. *iChar*합니다. 이 연산자는 편리한 대체 합니다 [GetAt](#getat) 멤버 함수입니다.

> [!NOTE]
>  첨자를 사용할 수 있습니다 (**[]**)에 있는 문자의 값을 검색할 연산자를 `CSimpleStringT`, 하지만 있는 문자의 값을 변경 하려면 사용할 수 없습니다를 `CSimpleStringT`입니다.

##  <a name="operator_add_eq"></a>  CSimpleStringT::operator +=

기존 문자열의 끝에 새 문자열 또는 문자를 조인합니다.

### <a name="syntax"></a>구문

```
CSimpleStringT& operator +=(PCXSTR pszSrc);
CSimpleStringT& operator +=(const CSimpleStringT& strSrc);
template<int t_nSize>
CSimpleStringT& operator+=(const CStaticString< XCHAR, t_nSize >& strSrc);
CSimpleStringT& operator +=(char ch);
CSimpleStringT& operator +=(unsigned char ch);
CSimpleStringT& operator +=(wchar_t ch);
```

#### <a name="parameters"></a>매개 변수

*pszSrc*<br/>
Null로 끝나는 문자열에 대 한 포인터입니다.

*strSrc*<br/>
기존에 대 한 포인터 `CSimpleStringT` 개체입니다.

*ch*<br/>
추가할 문자입니다.

### <a name="remarks"></a>설명

다른 연산자를 허용 `CSimpleStringT` 개체 또는 문자입니다. 메모리를 확인 합니다.이 추가 문자에 대 한 새 저장소를 할당할 수 있습니다 때문에이 연결 연산자를 사용할 때마다 예외가 발생할 수 있습니다 `CSimpleStringT` 개체입니다.

### <a name="example"></a>예제

다음 예에서는 `CSimpleStringT::operator +=`의 사용법을 보여줍니다.

```cpp
CSimpleString str(_T("abc"), pMgr);
ASSERT(_tcscmp((str += _T("def")), _T("abcdef")) == 0);
```

##  <a name="operator_eq"></a>  CSimpleStringT::operator =

새 값을 할당 한 `CSimpleStringT` 개체입니다.

### <a name="syntax"></a>구문

```
CSimpleStringT& operator =(PCXSTR pszSrc);
CSimpleStringT& operator =(const CSimpleStringT& strSrc);
```

#### <a name="parameters"></a>매개 변수

*pszSrc*<br/>
Null로 끝나는 문자열에 대 한 포인터입니다.

*strSrc*<br/>
기존에 대 한 포인터 `CSimpleStringT` 개체입니다.

### <a name="remarks"></a>설명

대상 문자열 (왼쪽)에 새 데이터를 저장 하기에 충분 이미 있으면 새 메모리 할당이 없습니다 수행 됩니다. 참고 해당 메모리 할당 연산자를 사용 하 여 결과 보유할 새 저장소 할당 종종 되므로 때마다 예외가 발생할 수 있습니다 `CSimpleStringT` 개체입니다.

### <a name="example"></a>예제

다음 예에서는 `CSimpleStringT::operator =`의 사용법을 보여줍니다.

```cpp
CSimpleString s1(pMgr), s2(pMgr);
// Empty CSimpleStringT objects

s1 = _T("cat");
// s1 = "cat"
ASSERT(_tcscmp(s1, _T("cat")) == 0);

s2 = s1;               // s1 and s2 each = "cat"
ASSERT(_tcscmp(s2, _T("cat")) == 0);

s1 = _T("the ") + s1;
// Or expressions
ASSERT(_tcscmp(s1, _T("the cat")) == 0);

s1 = _T("x");
// Or just individual characters
ASSERT(_tcscmp(s1, _T("x")) == 0);
```

##  <a name="operator_pcxstr"></a>  CSimpleStringT::operator PCXSTR

에 저장 된 문자에 직접 액세스를 `CSimpleStringT` C 스타일 문자열로 개체입니다.

### <a name="syntax"></a>구문

```
operator PCXSTR() const throw();
```

### <a name="return-value"></a>반환 값

문자열의 데이터를 문자 포인터입니다.

### <a name="remarks"></a>설명

문자가 복사 됩니다. 포인터에만 반환 됩니다. 이 연산자를 사용 하 여 주의 해야 합니다. 변경 하는 경우는 `CString` 개체 포인터를 무효화 하는 메모리를 재할당 하는 문자 포인터를 가져온 후 발생할 수 있습니다.

### <a name="example"></a>예제

다음 예에서는 `CSimpleStringT::operator PCXSTR`의 사용법을 보여줍니다.

```cpp
// If the prototype of a function is known to the compiler,
// the PCXSTR cast operator may be invoked implicitly.

CSimpleString strSports(L"Soccer is Best!", pMgr);
WCHAR sz[1024];

wcscpy_s(sz, strSports);

// If the prototype isn't known or is a va_arg prototype,
// you must invoke the cast operator explicitly. For example,
// the va_arg part of a call to swprintf_s() needs the cast:

swprintf_s(sz, 1024, L"I think that %s!\n", (PCWSTR)strSports);

// While the format parameter is known to be an PCXSTR and
// therefore doesn't need the cast:

swprintf_s(sz, 1024, strSports);

// Note that some situations are ambiguous. This line will
// put the address of the strSports object to stdout:

wcout << strSports;

// while this line will put the content of the string out:

wcout << (PCWSTR)strSports;
```

##  <a name="pcxstr"></a>  CSimpleStringT::PCXSTR

상수 문자열 포인터입니다.

### <a name="syntax"></a>구문

```
typedef ChTraitsBase< BaseType >::PCXSTR PCXSTR;
```

##  <a name="preallocate"></a>  CSimpleStringT::Preallocate

특정 기간에 대 한 바이트를 할당 합니다 `CSimpleStringT` 개체입니다.

### <a name="syntax"></a>구문

```
void Preallocate( int nLength);
```

#### <a name="parameters"></a>매개 변수

*nLength*<br/>
정확한 크기를 `CSimpleStringT` 문자의 문자 버퍼입니다.

### <a name="remarks"></a>설명

에 대 한 특정 버퍼 크기를 할당 하려면이 메서드를 호출 합니다 `CSimpleStringT` 개체입니다.

`CSimpleStringT` 문자 버퍼에 대 한 공간을 할당할 수 없는 경우 STATUS_NO_MEMORY 예외를 생성 합니다. 기본적으로 메모리 할당은 WIN32 API 함수에 의해 수행 `HeapAlloc` 또는 `HeapReAlloc`합니다.

### <a name="example"></a>예제

다음 예에서는 `CSimpleStringT::Preallocate`의 사용법을 보여줍니다.

```cpp
CSimpleString str(pMgr);
_tprintf_s(_T("Allocated length: %d\n"), str.GetAllocLength());
str.Preallocate(100);
_tprintf_s(_T("Allocated length: %d\n"), str.GetAllocLength());
```

##  <a name="pxstr"></a>  CSimpleStringT::PXSTR

문자열 포인터입니다.

### <a name="syntax"></a>구문

```
typedef ChTraitsBase< BaseType >::PXSTR PXSTR;
```

##  <a name="releasebuffer"></a>  CSimpleStringT::ReleaseBuffer

에 할당 된 버퍼의 제어권을 해제 [GetBuffer](#getbuffer)합니다.

### <a name="syntax"></a>구문

```
void ReleaseBuffer(int nNewLength = -1);
```

#### <a name="parameters"></a>매개 변수

*nNewLength*<br/>
문자를 제외 하 고 null 종결자에 있는 문자열의 새 길이입니다. 기본값-1로 설정 하는 문자열이 null 인 경우 종료를 `CSimpleStringT` 크기 문자열의 현재 길이입니다.

### <a name="remarks"></a>설명

다시 할당 하거나 문자열 개체의 버퍼를 확보 하려면이 메서드를 호출 합니다. 버퍼에서 문자열은 종료 null을 생략할 수를 알고 있는 경우는 *nNewLength* 인수입니다. 문자열에 null이 아닌 경우 종료를 사용 하 여 *nNewLength* 해당 길이를 지정 합니다. 반환 된 주소로 [GetBuffer](#getbuffer) 에 대 한 호출 후 유효 하지 `ReleaseBuffer` 또는 기타 `CSimpleStringT` 작업 합니다.

### <a name="example"></a>예제

다음 예에서는 `CSimpleStringT::ReleaseBuffer`의 사용법을 보여줍니다.

```cpp
const int bufferSize = 1024;
CSimpleString s(_T("abc"), pMgr);
LPTSTR p = s.GetBuffer(bufferSize);
_tcscpy_s(p, bufferSize, _T("abc"));

// use the buffer directly
ASSERT(s.GetLength() == 3);

// String length = 3
s.ReleaseBuffer();

// Surplus memory released, p is now invalid.
ASSERT(s.GetLength() == 3);

// Length still 3
```

##  <a name="releasebuffersetlength"></a>  CSimpleStringT::ReleaseBufferSetLength

에 할당 된 버퍼의 제어권을 해제 [GetBuffer](#getbuffer)합니다.

### <a name="syntax"></a>구문

```
void ReleaseBufferSetLength(int nNewLength);
```

#### <a name="parameters"></a>매개 변수

*nNewLength*<br/>
해제 하 고 문자열의 길이

### <a name="remarks"></a>설명

이 함수는 기능적으로 비슷합니다 [ReleaseBuffer](#releasebuffer) 제외 하 고 문자열 개체에 대 한 올바른 길이 전달 해야 합니다.

##  <a name="setat"></a>  CSimpleStringT::SetAt

설정에서 단일 문자를 `CSimpleStringT` 개체입니다.

### <a name="syntax"></a>구문

```
void SetAt(int iChar, XCHAR ch);
```

#### <a name="parameters"></a>매개 변수

*iChar*<br/>
문자의 0부터 시작 인덱스는 `CSimpleStringT` 개체입니다. 합니다 *iChar* 매개 변수 보다 큰 또는 0 및 반환 하는 값 미만 이어야 합니다. [GetLength](#getlength)합니다.

*ch*<br/>
새 문자입니다.

### <a name="remarks"></a>설명

에 있는 문자를 덮어쓰려면이 메서드를 호출 *iChar*합니다. 이 메서드는 경우 문자열을 확대 하지 *iChar* 기존 문자열의 한계를 초과 합니다.

### <a name="example"></a>예제

다음 예에서는 `CSimpleStringT::SetAt`의 사용법을 보여줍니다.

```cpp
CSimpleString s(_T("abcdef"), pMgr);
s.SetAt(1, _T('a'));
ASSERT(_tcscmp(s, _T("aacdef")) == 0);
```

##  <a name="setmanager"></a>  CSimpleStringT::SetManager

메모리 관리자를 지정 합니다 `CSimpleStringT` 개체입니다.

### <a name="syntax"></a>구문

```
void SetManager(IAtlStringMgr* pStringMgr);
```

#### <a name="parameters"></a>매개 변수

*pStringMgr*<br/>
새 메모리 관리자에 대 한 포인터입니다.

### <a name="remarks"></a>설명

새 메모리를 지정 하려면이 방법을 사용 하는 관리자를 호출 합니다 `CSimpleStringT` 개체입니다. 메모리 관리자 및 문자열 개체에 대 한 자세한 내용은 참조 하세요. [메모리 관리 및 CStringT](../memory-management-with-cstringt.md)합니다.

### <a name="example"></a>예제

다음 예에서는 `CSimpleStringT::SetManager`의 사용법을 보여줍니다.

```cpp
CSimpleString s(pMgr);
s.SetManager(pCustomMgr);
```

##  <a name="setstring"></a>  CSimpleStringT::SetString

문자열을 설정 하는 `CSimpleStringT` 개체입니다.

### <a name="syntax"></a>구문

```
void SetString(PCXSTR pszSrc, int nLength);
void SetString(PCXSTR pszSrc);
```

#### <a name="parameters"></a>매개 변수

*pszSrc*<br/>
Null로 끝나는 문자열에 대 한 포인터입니다.

*nLength*<br/>
문자 수가 *pszSrc*합니다.

### <a name="remarks"></a>설명

문자열을 복사 합니다 `CSimpleStringT` 개체입니다. `SetString` 버퍼에서 오래 된 문자열 데이터를 덮어씁니다.

두 버전의 `SetString` 확인 여부 *pszSrc* null 포인터 이며 이면 E_INVALIDARG 오류를 throw 합니다.

매개 변수 1 버전이 `SetString` 예상 *pszSrc* null로 끝나는 문자열을 가리키도록 합니다.

두 매개 변수 버전 `SetString` 또한 *pszSrc* null로 끝나는 문자열 이어야 합니다. 사용 하 여 *nLength* 문자열 길이로 null 종결자를 먼저 발견할 하지 않는 한 합니다.

두 매개 변수 버전 `SetString` 도 확인 여부를 *pszSrc* 에서 현재 버퍼의 위치를 가리키는 `CSimpleStringT`합니다. 이 특별 한 경우 `SetString` 문자열 데이터를 버퍼에 다시 복사 하는 대로 문자열 데이터를 덮어쓰지 않습니다 메모리 복사 함수를 사용 합니다.

### <a name="example"></a>예제

다음 예에서는 `CSimpleStringT::SetString`의 사용법을 보여줍니다.

```cpp
CSimpleString s(_T("abcdef"), pMgr);
ASSERT(_tcscmp(s, _T("abcdef")) == 0);
s.SetString(_T("Soccer"), 6);
ASSERT(_tcscmp(s, _T("Soccer")) == 0);
```

##  <a name="stringlength"></a>  CSimpleStringT::StringLength

지정된 된 문자열의 문자 수를 반환합니다.

### <a name="syntax"></a>구문

```
ATL_NOINLINE static int StringLength(PCXSTR psz) throw();
```

#### <a name="parameters"></a>매개 변수

*psz*<br/>
Null로 끝나는 문자열에 대 한 포인터입니다.

### <a name="return-value"></a>반환 값

문자 수가 *psz*; null 종결자를 제외 합니다.

### <a name="remarks"></a>설명

가리키는 문자열의 문자 수를 검색 하려면이 메서드를 호출 *psz*합니다.

### <a name="example"></a>예제

다음 예에서는 `CSimpleStringT::StringLength`의 사용법을 보여줍니다.

```cpp
ASSERT(CSimpleString::StringLength(_T("soccer")) == 6);
```

##  <a name="truncate"></a>  CSimpleStringT::Truncate

새 길이 문자열을 자릅니다.

### <a name="syntax"></a>구문

```
void Truncate(int nNewLength);
```

#### <a name="parameters"></a>매개 변수

*nNewLength*<br/>
문자열의 새 길이입니다.

### <a name="remarks"></a>설명

새 길이 문자열의 내용을 자를이 메서드를 호출 합니다.

> [!NOTE]
>  버퍼의 할당 된 길이는 영향을 주지 않습니다. 현재 버퍼를 늘리거나 줄일를 참조 하세요 [FreeExtra](#freeextra) 하 고 [Preallocate](#preallocate)합니다.

### <a name="example"></a>예제

다음 예에서는 `CSimpleStringT::Truncate`의 사용법을 보여줍니다.

```cpp
CSimpleString str(_T("abcdefghi"), pMgr);
_tprintf_s(_T("Allocated length: %d\n"), str.GetLength());
_tprintf_s(_T("Contents: %s\n"), str);
str.Truncate(4);
_tprintf_s(_T("Allocated length: %d\n"), str.GetLength());
_tprintf_s(_T("Contents: %s\n"), str);
```

##  <a name="unlockbuffer"></a>  CSimpleStringT::UnlockBuffer

버퍼를 잠금 해제는 `CSimpleStringT` 개체입니다.

### <a name="syntax"></a>구문

```
void UnlockBuffer() throw();
```

### <a name="remarks"></a>설명

문자열의 참조 횟수가 1로 다시 설정 하려면이 메서드를 호출 합니다.

합니다 `CSimpleStringT` 소멸자를 자동으로 호출 `UnlockBuffer` 소멸자가 호출 될 때 버퍼 잠겨 있지는 되도록 합니다. 이 방법의 예제를 참조 하세요 [LockBuffer](#lockbuffer)합니다.

##  <a name="dtor"></a>  CSimpleStringT::~CSimpleStringT

`CSimpleStringT` 개체를 제거합니다.

### <a name="syntax"></a>구문

```
~CSimpleStringT() throw();
```

### <a name="remarks"></a>설명

삭제 하려면이 메서드를 호출 합니다 `CSimpleStringT` 개체입니다.

## <a name="see-also"></a>참고자료

[계층 구조 차트](../../mfc/hierarchy-chart.md)<br/>
[ATL/MFC 공유 클래스](../../atl-mfc-shared/atl-mfc-shared-classes.md)
