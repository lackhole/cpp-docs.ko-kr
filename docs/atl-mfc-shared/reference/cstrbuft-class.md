---
title: CStrBufT 클래스
ms.date: 10/18/2018
f1_keywords:
- CStrBufT
- ATLSIMPSTR/ATL::CStrBufT
- ATLSIMPSTR/ATL::CStrBufT::CStrBufT
- ATLSIMPSTR/ATL::CStrBufT::SetLength
- ATLSIMPSTR/ATL::CStrBufT::AUTO_LENGTH
- ATLSIMPSTR/ATL::CStrBufT::SET_LENGTH
helpviewer_keywords:
- strings [C++], custom memory management
- CStrBufT class
- shared classes, CStrBufT
ms.assetid: 6b50fa8f-87e8-4ed4-a229-157ce128710f
ms.openlocfilehash: 81c3b429089eab3ba95c178e3fc7cf2bf55783a2
ms.sourcegitcommit: dedd4c3cb28adec3793329018b9163ffddf890a4
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/11/2019
ms.locfileid: "57747452"
---
# <a name="cstrbuft-class"></a>CStrBufT 클래스

이 클래스는 자동 리소스 정리에 대 한 제공 `GetBuffer` 하 고 `ReleaseBuffer` 기존 호출 `CStringT` 개체입니다.

## <a name="syntax"></a>구문

```
template<typename TCharType>
class CStrBufT
```

#### <a name="parameters"></a>매개 변수

*TCharType*<br/>
문자 형식을 `CStrBufT` 클래스입니다. 다음 중 하나일 수 있습니다.

- **char** (용 ANSI 문자열)

- **wchar_t** (용 유니코드 문자열)

- (ANSI 및 유니코드 문자열)에 대 한 TCHAR

## <a name="members"></a>멤버

### <a name="public-typedefs"></a>공용 Typedefs

|이름|설명|
|----------|-----------------|
|PCXSTR|상수 문자열 포인터입니다.|
|PXSTR|문자열 포인터입니다.|
|`StringType`|이 클래스 템플릿의 특수화에 의해 조작 될 버퍼가 문자열 형식입니다.|

### <a name="public-constructors"></a>Public 생성자

|이름|설명|
|----------|-----------------|
|[CStrBufT::CStrBufT](#cstrbuft)|문자열 버퍼 개체에 대 한 생성자입니다.|

### <a name="public-methods"></a>Public 메서드

|이름|설명|
|----------|-----------------|
|[CStrBufT::SetLength](#setlength)|연결 된 문자열 개체의 문자 버퍼 길이 설정합니다.|

### <a name="public-operators"></a>Public 연산자

|이름|설명|
|----------|-----------------|
|[CStrBufT::operator PCXSTR](#operator_pcxstr)|검색을 **const** 연결 된 문자열 개체의 문자 버퍼에 대 한 포인터입니다.|
|[CStrBufT::operator PXSTR](#operator_pxstr)|연결 된 문자열 개체의 문자 버퍼에 대 한 포인터를 검색합니다.|

### <a name="public-constants"></a>공용 상수

|이름|설명|
|----------|-----------------|
|[CStrBufT::AUTO_LENGTH](#auto_length)|릴리스마다 문자열의 새 길이 자동으로 결정 합니다.|
|[CStrBufT::SET_LENGTH](#set_length)|GetBuffer 시 문자열 개체의 길이 설정 합니다.|

## <a name="remarks"></a>설명

이 클래스에 대 한 호출을 대체 하는 것에 대 한 래퍼 클래스로 사용 됩니다 [GetBuffer](../../atl-mfc-shared/reference/csimplestringt-class.md#getbuffer) 하 고 [ReleaseBuffer](../../atl-mfc-shared/reference/csimplestringt-class.md#releasebuffer), 또는 [GetBufferSetLength](../../atl-mfc-shared/reference/csimplestringt-class.md#getbuffersetlength) 고 `ReleaseBuffer`입니다.

도우미 클래스로 서 주로 `CStrBufT` 방법에 대 한 걱정 없이 문자열 개체의 문자 버퍼를 사용 하려면 개발자는 편리한 방법을 제공 하거나 호출 하는 경우 `ReleaseBuffer`합니다. 가능한 예외 또는 여러 기존 코드 경로가;의 경우 자연스럽 게 범위를 벗어나면으로 래퍼 개체 이므로 문자열 리소스를 해제 하려면 해당 소멸자를 유발 합니다.

## <a name="requirements"></a>요구 사항

**헤더:** atlsimpstr.h

##  <a name="auto_length"></a>  CStrBufT::AUTO_LENGTH

릴리스마다 문자열의 새 길이 자동으로 결정 합니다.

```
static const DWORD AUTO_LENGTH = 0x01;
```

### <a name="remarks"></a>설명

릴리스마다 문자열의 새 길이 자동으로 결정 합니다. 문자열에는 null 종료를 사용 해야 합니다.

##  <a name="cstrbuft"></a>  CStrBufT::CStrBufT

버퍼 개체를 생성합니다.

```
CStrBufT(StringType& str, int nMinLength, DWORD dwFlags = AUTO_LENGTH) throw(...);
explicit CStrBufT(StringType& str) throw(...);
```

### <a name="parameters"></a>매개 변수

*str*<br/>
버퍼와 연결 된 문자열 개체입니다. 일반적으로 개발자가 사용 하 여의 미리 정의 된 typedef `CStrBuf` (TCHAR variant 형식) `CStrBufA` (**char** 변형) 및 `CStrBufW` (**wchar_t** 변형).

*nMinLength*<br/>
문자 버퍼의 최소 길이입니다.

*dwFlags*<br/>
문자열 길이 자동으로 결정할지를 결정 합니다. 다음 중 하나일 수 있습니다.

- AUTO_LENGTH 문자열 길이가 자동으로 결정 될 때 [CSimpleStringT::Release](../../atl-mfc-shared/reference/csimplestringt-class.md#releasebuffer) 라고 합니다. 문자열에는 null 종료를 사용 해야 합니다. 기본 값입니다.

- SET_LENGTH 문자열 길이 경우 설정 됩니다 [CSimpleStringT::GetBuffer](../../atl-mfc-shared/reference/csimplestringt-class.md#getbuffer) 라고 합니다.

### <a name="remarks"></a>설명

연결 된 문자열 개체에 대 한 문자열 버퍼를 만듭니다. 생성 되는 동안 [CSimpleStringT::GetBuffer](../../atl-mfc-shared/reference/csimplestringt-class.md#getbuffer) 하거나 [CSimpleStringT::GetBufferSetLength](../../atl-mfc-shared/reference/csimplestringt-class.md#getbuffersetlength) 라고 합니다.

복사 생성자가 보면 **개인**합니다.

##  <a name="operator_pcxstr"></a>  CStrBufT::operator PCXSTR

C 스타일 문자열로 연결 된 문자열 개체에 저장 된 문자에 직접 액세스 합니다.

```
operator PCXSTR() const throw();
```

### <a name="return-value"></a>반환 값

문자열의 데이터를 문자 포인터입니다.

### <a name="remarks"></a>설명

문자열 개체의 문자 버퍼에 대 한 포인터를 반환 하려면이 함수를 호출 합니다. 이 포인터를 사용 하 여 문자열 개체의 내용은 변경할 수 없습니다.

##  <a name="operator_pxstr"></a>  CStrBufT::operator PXSTR

C 스타일 문자열로 연결 된 문자열 개체에 저장 된 문자에 직접 액세스 합니다.

```
operator PXSTR() throw();
```

### <a name="return-value"></a>반환 값

문자열의 데이터를 문자 포인터입니다.

### <a name="remarks"></a>설명

문자열 개체의 문자 버퍼에 대 한 포인터를 반환 하려면이 함수를 호출 합니다. 개발자는이 포인터를 사용 하 여 문자열 개체의 내용을 변경할 수 있습니다.

##  <a name="pcxstr"></a>  CStrBufT::PCXSTR

상수 문자열 포인터입니다.

```
typedef CSimpleStringT<TCharType>::PCXSTR PCXSTR;
```

##  <a name="pxstr"></a>  CStrBufT::PXSTR

문자열 포인터입니다.

```
typedef CSimpleStringT<TCharType>::PXSTR PXSTR;
```

##  <a name="set_length"></a>  CStrBufT::SET_LENGTH

에 있는 문자열 개체의 길이 설정할 `GetBuffer` 시간입니다.

```
static const DWORD SET_LENGTH = 0x02;
```

### <a name="remarks"></a>설명

GetBuffer 시 문자열 개체의 길이 설정 합니다.

하는 경우 결정 [CSimpleStringT::GetBuffer](../../atl-mfc-shared/reference/csimplestringt-class.md#getbuffer) 하 고 [CSimpleStringT::GetBufferSetLength](../../atl-mfc-shared/reference/csimplestringt-class.md#getbuffersetlength) 문자열 버퍼 개체가 생성 될 때 호출 됩니다.

##  <a name="setlength"></a>  CStrBufT::SetLength

문자 버퍼의 길이 설정 합니다.

```
void SetLength(int nLength);
```

### <a name="parameters"></a>매개 변수

*nLength*<br/>
문자열 개체의 문자 버퍼의 새 길이입니다.

> [!NOTE]
>  생성자에 지정 된 최소 버퍼 길이 보다 작거나 같아야 `CStrBufT`합니다.

### <a name="remarks"></a>설명

버퍼 개체를 나타내는 문자열의 길이 설정 하려면이 함수를 호출 합니다.

##  <a name="stringtype"></a>  CStrBufT::StringType

이 클래스 템플릿의 특수화에 의해 조작 될 버퍼가 문자열 형식입니다.

```
typedef CSimpleStringT<TCharType> StringType;
```

### <a name="remarks"></a>설명

`TCharType` 클래스 템플릿의 특수화를 사용 하는 문자 유형입니다.

## <a name="see-also"></a>참고자료

[계층 구조 차트](../../mfc/hierarchy-chart.md)<br/>
[ATL/MFC 공유 클래스](../../atl-mfc-shared/atl-mfc-shared-classes.md)
