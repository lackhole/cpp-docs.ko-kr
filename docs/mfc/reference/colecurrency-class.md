---
title: COleCurrency 클래스
ms.date: 11/04/2016
f1_keywords:
- COleCurrency
- AFXDISP/COleCurrency
- AFXDISP/COleCurrency::COleCurrency
- AFXDISP/COleCurrency::Format
- AFXDISP/COleCurrency::GetStatus
- AFXDISP/COleCurrency::ParseCurrency
- AFXDISP/COleCurrency::SetCurrency
- AFXDISP/COleCurrency::SetStatus
- AFXDISP/COleCurrency::m_cur
- AFXDISP/COleCurrency::m_status
helpviewer_keywords:
- COleCurrency [MFC], COleCurrency
- COleCurrency [MFC], Format
- COleCurrency [MFC], GetStatus
- COleCurrency [MFC], ParseCurrency
- COleCurrency [MFC], SetCurrency
- COleCurrency [MFC], SetStatus
- COleCurrency [MFC], m_cur
- COleCurrency [MFC], m_status
ms.assetid: 3a36e345-303f-46fb-a57c-858274378a8d
ms.openlocfilehash: 64f2b00c8a5aefe8a39c24d26af2a97625225059
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62375745"
---
# <a name="colecurrency-class"></a>COleCurrency 클래스

OLE 자동화의 `CURRENCY` 데이터 형식을 캡슐화합니다.

## <a name="syntax"></a>구문

```
class COleCurrency
```

## <a name="members"></a>멤버

### <a name="public-constructors"></a>Public 생성자

|이름|설명|
|----------|-----------------|
|[COleCurrency::COleCurrency](#colecurrency)|`COleCurrency` 개체를 생성합니다.|

### <a name="public-methods"></a>Public 메서드

|이름|설명|
|----------|-----------------|
|[COleCurrency::Format](#format)|형식이 지정 된 문자열 표현을 생성 한 `COleCurrency` 개체입니다.|
|[COleCurrency::GetStatus](#getstatus)|이 상태 (유효성)를 가져옵니다 `COleCurrency` 개체입니다.|
|[COleCurrency::ParseCurrency](#parsecurrency)|통화 값을 문자열로 읽고의 값을 설정 `COleCurrency`합니다.|
|[COleCurrency::SetCurrency](#setcurrency)|이 값을 설정 `COleCurrency` 개체입니다.|
|[COleCurrency::SetStatus](#setstatus)|상태를 설정 합니다 (유효성)이 `COleCurrency` 개체입니다.|

### <a name="public-operators"></a>Public 연산자

|이름|설명|
|----------|-----------------|
|[operator =](#operator_eq)|복사본을 `COleCurrency` 값입니다.|
|[operator +, -](#operator_plus_minus)|추가 빼고의 부호를 변경 `COleCurrency` 값입니다.|
|[operator +=, -=](#operator_plus_minus_eq)|더하고 빼는 `COleCurrency` 값이 `COleCurrency` 개체입니다.|
|[operator */](#operator_star)|눈금을 `COleCurrency` 정수 값입니다.|
|[operator *=, /=](#operator_star_div_eq)|이 확장 `COleCurrency` 정수 값입니다.|
|[연산자 <<](#operator_stream)|출력을 `COleCurrency` 값을 `CArchive` 또는 `CDumpContext`합니다.|
|[operator >>](#operator_stream)|입력 한 `COleCurrency` 에서 개체 `CArchive`합니다.|
|[통화 연산자](#operator_currency)|변환 된 `COleCurrency` 을 통화 값입니다.|
|[operator ==, <, <=, etc.](#colecurrency_relational_operators)|두 `COleCurrency` 값입니다.|

### <a name="public-data-members"></a>공용 데이터 멤버

|이름|설명|
|----------|-----------------|
|[COleCurrency::m_cur](#m_cur)|이 대 한 기본 통화 포함 `COleCurrency` 개체입니다.|
|[COleCurrency::m_status](#m_status)|이 상태를 포함 `COleCurrency` 개체입니다.|

## <a name="remarks"></a>설명

`COleCurrency` 기본 클래스는 없습니다.

통화는 8 바이트 2의 보수 정수 값이 10,000 단위 배율의로 구현 됩니다. 소수점 기호 왼쪽에는 15자리 고정 소수점 번호가 있고 오른쪽에는 4자리 고정 소수점 번호가 있습니다. 통화 데이터 형식이 고정 소수점 계산에 대 한 비용을 포함 하는 계산에 대 한 매우 유용한 정확도 중요 합니다. 가능한 형식 중 하나인는 `VARIANT` OLE 자동화의 데이터 형식입니다.

`COleCurrency` 또한이 고정 소수점 형식에 대 한 일부 기본 산술 연산을 구현합니다. 고정 소수점 계산 시 발생 하는 반올림 오류를 제어 하도록 선택 했습니다. 지원 되는 작업입니다.

## <a name="inheritance-hierarchy"></a>상속 계층 구조

`COleCurrency`

## <a name="requirements"></a>요구 사항

**헤더:** afxdisp.h

##  <a name="colecurrency"></a>  COleCurrency::COleCurrency

`COleCurrency` 개체를 생성합니다.

```
COleCurrency();
COleCurrency(CURRENCY cySrc);
  COleCurrency(const COleCurrency& curSrc);
COleCurrency(const VARIANT& varSrc);

COleCurrency(
    long nUnits,
    long nFractionalUnits);
```

### <a name="parameters"></a>매개 변수

*cySrc*<br/>
복사할 새 통화 값 `COleCurrency` 개체입니다.

*curSrc*<br/>
기존 `COleCurrency` 복사할 새 개체 `COleCurrency` 개체입니다.

*varSrc*<br/>
기존 `VARIANT` 데이터 구조 (가능한 경우는 `COleVariant` 개체) (VT_CY) 통화 값으로 변환 되어 새 복사할 `COleCurrency` 개체입니다.

*nUnits*하십시오 *nFractionalUnits* 복사할 새 단위 및 값의 (1/10에서 000's) 소수 부분을 나타내는 `COleCurrency` 개체입니다.

### <a name="remarks"></a>설명

이 생성자의 모든 새로 만들기 `COleCurrency` 개체를 지정된 된 값으로 초기화 합니다. 이 생성자의 각 간략 한 설명은 다음과 같습니다. 다른 언급이 없는 경우 새 상태 `COleCurrency` 항목에 잘못 설정 됩니다.

- COleCurrency() 구문을 `COleCurrency` 0 (영)으로 초기화 하는 개체입니다.

- COleCurrency (`cySrc`)를 생성 한 `COleCurrency` 에서 개체를 [통화](/windows/desktop/api/wtypes/ns-wtypes-tagcy) 값입니다.

- COleCurrency (`curSrc`)를 생성 한 `COleCurrency` 기존 개체 `COleCurrency` 개체입니다. 새 개체는 소스 개체와 동일한 상태입니다.

- COleCurrency (`varSrc`)를 생성 한 `COleCurrency` 개체입니다. 변환 하려고 시도 [VARIANT](/windows/desktop/api/oaidl/ns-oaidl-tagvariant) 구조 또는 `COleVariant` 개체 (VT_CY) 통화 값입니다. 이 변환에 성공한 경우 변환 된 값은 복사할 새 `COleCurrency` 개체입니다. 없으면의 값을 `COleCurrency` 개체 영 (0) 및 해당 상태를 잘못 됨로 설정 됩니다.

- `COleCurrency(`nUnits`, `nFractionalUnits`) Constructs a `COleCurrency' 개체에서 지정된 된 숫자 구성 요소입니다. 소수 부분의 절대값이 10,000 보다 크면 단위에 적절 한 조정이 이루어집니다. 참고 단위 및 소수 부분이 서명 된 long 값으로 지정 됩니다.

자세한 내용은 참조는 [통화](/windows/desktop/api/wtypes/ns-wtypes-tagcy) 및 [VARIANT](/windows/desktop/api/oaidl/ns-oaidl-tagvariant) Windows SDK에는 항목입니다.

### <a name="example"></a>예제

다음 예에서는 0이 매개 변수 및 매개 변수 2 생성자의 효과 보여 줍니다.

[!code-cpp[NVC_MFCOleContainer#10](../../mfc/codesnippet/cpp/colecurrency-class_1.cpp)]

##  <a name="format"></a>  COleCurrency::Format

통화 값의 서식이 지정 된 표현을 만들려면이 멤버 함수를 호출 합니다.

```
CString Format(DWORD  dwFlags = 0, LCID  lcid = LANG_USER_DEFAULT) const;
```

### <a name="parameters"></a>매개 변수

*dwFlags*<br/>
로캘 설정에 대 한 플래그를 나타냅니다. 통화 관련 플래그를 같습니다.

- LOCALE_NOUSEROVERRIDE는 사용자 지정 사용자 설정 대신 시스템 기본 로캘 설정을 사용 합니다.

*lcid*<br/>
변환에 사용할 로캘 ID를 나타냅니다.

### <a name="return-value"></a>반환 값

`CString` 서식이 지정 된 통화 값이 들어 있는입니다.

### <a name="remarks"></a>설명

로컬 언어 사양 (로캘 Id)를 사용 하 여 값 형식을 지정 합니다. 통화 기호는 반환 된 값에 포함 되지 않습니다. 하는 경우이 상태의 `COleCurrency` 개체가 null 이면 반환 값은 빈 문자열입니다. 상태가 올바르지 않은 경우 반환 문자열 IDS_INVALID_CURRENCY 문자열 리소스에 의해 지정 됩니다.

### <a name="example"></a>예제

[!code-cpp[NVC_MFCOleContainer#11](../../mfc/codesnippet/cpp/colecurrency-class_2.cpp)]

##  <a name="getstatus"></a>  COleCurrency::GetStatus

상태 (유효성)를 가져오려면이 멤버 함수 호출을 지정 `COleCurrency` 개체입니다.

```
CurrencyStatus GetStatus() const;
```

### <a name="return-value"></a>반환 값

이 상태를 반환 합니다 `COleCurrency` 값입니다.

### <a name="remarks"></a>설명

반환 값으로 정의 됩니다는 `CurrencyStatus` 내에 정의 된 형식 열거는 `COleCurrency` 클래스입니다.

```
enum CurrencyStatus {
    valid = 0,
    invalid = 1,
    null = 2
    };
```

이러한 상태 값의 간략 한 설명을 다음 목록을 참조 합니다.

  - `COleCurrency::valid` 나타냅니다이 `COleCurrency` 개체는 유효 합니다.

  - `COleCurrency::invalid` 나타냅니다이 `COleCurrency` 개체가 잘못 되었습니다. 즉, 해당 값 잘못 되었을 수 있습니다.

  - `COleCurrency::null` 나타냅니다이 `COleCurrency` 개체가 null 인 경우 즉,이 개체에 대해 제공 된 값입니다. (이 값이 "null" 의"값 없음."와 반대로 데이터베이스 점에서 C++ NULL입니다.)

상태를 `COleCurrency` 개체가 같은 경우에 유효 하지 않습니다.

- 변형에서 해당 값이 설정 된 경우 또는 `COleVariant` 통화 값으로 변환할 수 없는 값입니다.

- 발생 한 경우이 개체에는 오버플로 또는 언더플로 산술 할당 작업 중 예를 들어 `+=` 나 **\* =** 합니다.

- 잘못 된 값이이 개체에 할당 되었습니다 하는 경우.

- 이 개체의 상태를 사용 하 여 잘못 된 명시적으로 설정 되었는지 여부 [SetStatus](#setstatus)합니다.

작업에 대 한 자세한 내용은 다음 구성원 함수를 참조 하세요 잘못 된 상태를 설정할 수 있습니다는.

- [COleCurrency](#colecurrency)

- [operator =](#operator_eq)

- [operator + -](#operator_plus_minus)

- [operator + = 및 =](#operator_plus_minus_eq)

- [operator * /](#operator_star)

- [operator *= and /=](#operator_star_div_eq)

### <a name="example"></a>예제

[!code-cpp[NVC_MFCOleContainer#12](../../mfc/codesnippet/cpp/colecurrency-class_3.cpp)]

##  <a name="m_cur"></a>  COleCurrency::m_cur

내부 [통화](/windows/desktop/api/wtypes/ns-wtypes-tagcy) 이 대 한 구조 `COleCurrency` 개체입니다.

### <a name="remarks"></a>설명

> [!CAUTION]
>  값을 변경 합니다 `CURRENCY` 이 함수에서 반환 된 포인터에 의해 액세스 되는 구조는이 값을 변경 `COleCurrency` 개체입니다. 이 상태는 변경 되지 않습니다 `COleCurrency` 개체입니다.

자세한 내용은 참조는 [통화](/windows/desktop/api/wtypes/ns-wtypes-tagcy) Windows SDK에는 항목입니다.

##  <a name="m_status"></a>  COleCurrency::m_status

이 데이터 멤버의 형식을 열거 형식인 `CurrencyStatus`, 내에서 정의 되는 `COleCurrency` 클래스.

```
enum CurrencyStatus{
    valid = 0,
    invalid = 1,
    null = 2,
};
```

### <a name="remarks"></a>설명

이러한 상태 값의 간략 한 설명을 다음 목록을 참조 합니다.

- `COleCurrency::valid` 나타냅니다이 `COleCurrency` 개체는 유효 합니다.

- `COleCurrency::invalid` 나타냅니다이 `COleCurrency` 개체가 잘못 되었습니다. 즉, 해당 값 잘못 되었을 수 있습니다.

- `COleCurrency::null` 나타냅니다이 `COleCurrency` 개체가 null 인 경우 즉,이 개체에 대해 제공 된 값입니다. (이 값이 "null" 의"값 없음."와 반대로 데이터베이스 점에서 C++ NULL입니다.)

상태를 `COleCurrency` 개체가 같은 경우에 유효 하지 않습니다.

- 변형에서 해당 값이 설정 된 경우 또는 `COleVariant` 통화 값으로 변환할 수 없는 값입니다.

- 발생 한 경우이 개체에는 오버플로 또는 언더플로 산술 할당 작업 중 예를 들어 `+=` 나 **\* =** 합니다.

- 잘못 된 값이이 개체에 할당 되었습니다 하는 경우.

- 이 개체의 상태를 사용 하 여 잘못 된 명시적으로 설정 되었는지 여부 [SetStatus](#setstatus)합니다.

작업에 대 한 자세한 내용은 다음 구성원 함수를 참조 하세요 잘못 된 상태를 설정할 수 있습니다는.

- [COleCurrency](#colecurrency)

- [operator =](#operator_eq)

- [operator +, -](#operator_plus_minus)

- [operator +=, -=](#operator_plus_minus_eq)

- [operator */](#operator_star)

- [operator *=, /=](#operator_star_div_eq)

> [!CAUTION]
>  이 데이터 멤버는 고급 프로그래밍 시나리오입니다. 인라인 멤버 함수를 사용 해야 [GetStatus](#getstatus) 하 고 [SetStatus](#setstatus)합니다. 참조 `SetStatus` 이 데이터 멤버를 명시적으로 설정 하는 것에 대 한 추가 주의 사항에 대 한 합니다.

##  <a name="operator_eq"></a>  COleCurrency::operator =

이러한 오버 로드 된 할당 연산자 복사 원본 통화 값이 `COleCurrency` 개체입니다.

```
const COleCurrency& operator=(CURRENCY cySrc);
const COleCurrency& operator=(const COleCurrency& curSrc);
  const COleCurrency& operator=(const VARIANT& varSrc);
```

### <a name="remarks"></a>설명

각 연산자에 대 한 간단한 설명은 다음과 같습니다.

- **연산자 = (** `cySrc` **)** 는 `CURRENCY` 값에 복사 됩니다는 `COleCurrency` 개체 및 해당 상태에 잘못 설정 됩니다.

- **operator = (** `curSrc` **)** 값 및 기존 피연산자의 상태를 `COleCurrency` 개체를이 복사할 `COleCurrency` 개체.

- **연산자 = (** *varSrc* **)** 하는 경우 변환 된 `VARIANT` 값 (또는 [COleVariant](../../mfc/reference/colevariant-class.md) 개체) 통화로 ( `VT_CY`)는 성공 하면 변환 된 값이 복사 됩니다 `COleCurrency` 개체 및 해당 상태에 잘못 설정 됩니다. 변환이 성공적 이면 값은 `COleCurrency` 개체 0과를 잘못 됨 상태가로 설정 됩니다.

자세한 내용은 참조는 [통화](/windows/desktop/api/wtypes/ns-wtypes-tagcy) 및 [VARIANT](/windows/desktop/api/oaidl/ns-oaidl-tagvariant) Windows SDK에는 항목입니다.

### <a name="example"></a>예제

[!code-cpp[NVC_MFCOleContainer#15](../../mfc/codesnippet/cpp/colecurrency-class_4.cpp)]

##  <a name="operator_plus_minus"></a>  COleCurrency::operator +, -

이러한 연산자를 사용 하면 추가 하 고 두 빼는 `COleCurrency` 값을 서로 부호를 변경 하는 `COleCurrency` 값입니다.

```
COleCurrency operator+(const COleCurrency& cur) const;
COleCurrency operator-(const COleCurrency& cur) const;
COleCurrency operator-() const;
```

### <a name="remarks"></a>설명

Null이 고, 결과의 상태를 피연산자 중 하나 이면 `COleCurrency` 값은 null입니다.

경우는 산술 연산 오버플로 결과 `COleCurrency` 값이 잘못 되었습니다.

유효 하지 않으며 다른 피연산자가 null이 아닌 결과 상태 `COleCurrency` 값이 잘못 되었습니다.

유효 하 고, 잘못 된 경우 null 상태 값에 대 한 자세한 내용은 참조는 [m_status](#m_status) 멤버 변수입니다.

### <a name="example"></a>예제

[!code-cpp[NVC_MFCOleContainer#16](../../mfc/codesnippet/cpp/colecurrency-class_5.cpp)]

##  <a name="operator_plus_minus_eq"></a>  COleCurrency::operator +=, -=

더하기 및 빼기를 사용 하면 한 `COleCurrency` 값을이 `COleCurrency` 개체입니다.

```
const COleCurrency& operator+=(const COleCurrency& cur);
const COleCurrency& operator-=(const COleCurrency& cur);
```

### <a name="remarks"></a>설명

이 피연산자 중 하나가 null 이면이 상태의 경우 `COleCurrency` 개체가 설정 된 null로 합니다.

경우는 산술 연산 오버플로이 상태의 `COleCurrency` 개체가 설정 된를 잘못 됨.

피연산자 중 하나가 올바르지 않습니다. null이 아니면 다른 경우이 상태의 `COleCurrency` 개체가 설정 된를 잘못 됨.

유효 하 고, 잘못 된 경우 null 상태 값에 대 한 자세한 내용은 참조는 [m_status](#m_status) 멤버 변수입니다.

### <a name="example"></a>예제

[!code-cpp[NVC_MFCOleContainer#17](../../mfc/codesnippet/cpp/colecurrency-class_6.cpp)]

##  <a name="operator_star"></a>  COleCurrency::operator \* 및 /

확장 하도록 허용 된 `COleCurrency` 정수 값입니다.

```
COleCurrency operator*(long nOperand) const;
COleCurrency operator/(long nOperand) const;
```

### <a name="remarks"></a>설명

경우는 `COleCurrency` 피연산자가 null 이면 결과의 상태 `COleCurrency` 값이 null입니다.

산술 연산 오버플로 하는 경우 또는 언더플로로 이어질, 결과의 상태 `COleCurrency` 값이 잘못 되었습니다.

경우는 `COleCurrency` 피연산자 유효 하지 않은 결과 상태 `COleCurrency` 값이 잘못 되었습니다.

유효 하 고, 잘못 된 경우 null 상태 값에 대 한 자세한 내용은 참조는 [m_status](#m_status) 멤버 변수입니다.

### <a name="example"></a>예제

[!code-cpp[NVC_MFCOleContainer#18](../../mfc/codesnippet/cpp/colecurrency-class_7.cpp)]

##  <a name="operator_star_div_eq"></a>  COleCurrency::operator \*=, /=

이 확장 하도록 허용 `COleCurrency` 정수 값입니다.

```
const COleCurrency& operator*=(long nOperand);
const COleCurrency& operator/=(long nOperand);
```

### <a name="remarks"></a>설명

경우는 `COleCurrency` 피연산자가 null이 상태의 `COleCurrency` 개체가 설정 된 null로 합니다.

경우는 산술 연산 오버플로이 상태의 `COleCurrency` 개체가 설정 된를 잘못 됨.

경우는 `COleCurrency` 피연산자 올바르지 않습니다.이 상태의 `COleCurrency` 개체가 설정 된를 잘못 됨.

유효 하 고, 잘못 된 경우 null 상태 값에 대 한 자세한 내용은 참조는 [m_status](#m_status) 멤버 변수입니다.

### <a name="example"></a>예제

[!code-cpp[NVC_MFCOleContainer#19](../../mfc/codesnippet/cpp/colecurrency-class_8.cpp)]

##  <a name="operator_stream"></a>  COleCurrency::operator &lt;&lt;, &gt;&gt;

진단 덤프 및 보관에 저장을 지원 합니다.

```
friend CDumpContext& operator<<(
    CDumpContext& dc,
    COleCurrency curSrc);

friend CArchive& operator<<(
    CArchive& ar,
    COleCurrency curSrc);

friend CArchive& operator>>(
    CArchive& ar,
    COleCurrency& curSrc);
```

### <a name="remarks"></a>설명

추출 ( **>>**) 연산자는 보관 파일에서 로드를 지원 합니다.

##  <a name="operator_currency"></a>  COleCurrency::operator 통화

반환 된 `CURRENCY` 구조 값이 복사 됩니다 `COleCurrency` 개체입니다.

```
operator CURRENCY() const;
```

### <a name="remarks"></a>설명

##  <a name="parsecurrency"></a>  COleCurrency::ParseCurrency

통화 값을 읽을 문자열의 구문을 분석 하려면이 멤버 함수를 호출 합니다.

```
BOOL ParseCurrency(
    LPCTSTR lpszCurrency,
    DWORD dwFlags = 0,
    LCID lcid = LANG_USER_DEFAULT);

throw(CMemoryException*);
throw(COleException*);
```

### <a name="parameters"></a>매개 변수

*lpszCurrency*<br/>
구문 분석 하는 null로 끝나는 문자열에 대 한 포인터입니다.

*dwFlags*<br/>
로캘 설정에는 다음 플래그를 가능한 경우에 대 한 플래그를 나타냅니다.

- LOCALE_NOUSEROVERRIDE는 사용자 지정 사용자 설정 대신 시스템 기본 로캘 설정을 사용 합니다.

*lcid*<br/>
변환에 사용할 로캘 ID를 나타냅니다.

### <a name="return-value"></a>반환 값

문자열을 통화 값으로, 0 그렇지 않은 경우 변환 된 경우에 0이 아닙니다.

### <a name="remarks"></a>설명

소스 문자열에서 숫자가 아닌 문자의 의미에 대 한 로컬 언어 사양 (로캘 Id)를 사용합니다.

로캘 ID 값, 참조 [여러 언어를 지 원하는](/previous-versions/windows/desktop/automat/supporting-multiple-national-languages)합니다.

문자열에 통화 변환 된 경우 값을이 값 `COleCurrency` 개체 유효한 값 및 해당 상태를로 설정 됩니다.

이 상태의 숫자 오버플로 발생 한 경우 또는 통화 값으로 문자열을 변환할 수 있으면 `COleCurrency` 개체가 잘못 되었습니다.

메모리 할당 오류로 인해 문자열 변환이 실패 한 경우이 함수가 throw 된 [CMemoryException](../../mfc/reference/cmemoryexception-class.md)합니다. 이 함수의 다른 오류 상태에 있는 throw 된 [COleException](../../mfc/reference/coleexception-class.md)합니다.

### <a name="example"></a>예제

[!code-cpp[NVC_MFCOleContainer#13](../../mfc/codesnippet/cpp/colecurrency-class_9.cpp)]

##  <a name="colecurrency_relational_operators"></a>  COleCurrency 관계형 연산자

두 통화 값을 비교 하 고 조건이 true 이면 0이 아닌 반환 그렇지 않으면 0입니다.

```
BOOL operator==(const COleCurrency& cur) const;
BOOL operator!=(const COleCurrency& cur) const;
BOOL operator<(const COleCurrency& cur) const;
BOOL operator>(const COleCurrency& cur) const;
BOOL operator<=(const COleCurrency& cur) const;
BOOL operator>=(const COleCurrency& cur) const;
```

### <a name="remarks"></a>설명

> [!NOTE]
>  정렬 작업의 반환 값 ( **<** 를 **\< =** 하십시오 **>**, **>=**) null 이거나 잘못 된 피연산자 중 하나가 상태가 정의 되지 않습니다. 같음 연산자 ( `==`, `!=`)는 피연산자의 상태는 것이 좋습니다.

### <a name="example"></a>예제

[!code-cpp[NVC_MFCOleContainer#20](../../mfc/codesnippet/cpp/colecurrency-class_10.cpp)]

##  <a name="setcurrency"></a>  COleCurrency::SetCurrency

단위 및 소수 자릿수 부분을 설정 하려면이 멤버 함수를 호출 `COleCurrency` 개체입니다.

```
void SetCurrency(
    long nUnits,
    long nFractionalUnits);
```

### <a name="parameters"></a>매개 변수

*nUnits*하십시오 *nFractionalUnits* 복사할이 단위 및 값의 (1/10에서 000's) 소수 부분을 나타내는 `COleCurrency` 개체입니다.

### <a name="remarks"></a>설명

소수 부분의 절대값이 10,000 보다 크면 다음 예에서는 세 번째 에서처럼 단위에 적절 한 조정이 이루어집니다.

참고 단위 및 소수 부분이 서명 된 long 값으로 지정 됩니다. 다음 예제에서는 네 번째 매개 변수를 부호가 다른 경우 어떻게 되는지 보여 줍니다.

### <a name="example"></a>예제

[!code-cpp[NVC_MFCOleContainer#14](../../mfc/codesnippet/cpp/colecurrency-class_11.cpp)]

##  <a name="setstatus"></a>  COleCurrency::SetStatus

이 상태 (유효성)를 설정 하려면이 멤버 함수 호출 `COleCurrency` 개체입니다.

```
void SetStatus(CurrencyStatus  status  );
```

### <a name="parameters"></a>매개 변수

*status*<br/>
이 대 한 새 상태 `COleCurrency` 개체입니다.

### <a name="remarks"></a>설명

합니다 *상태* 매개 변수 값으로 정의 됩니다 합니다 `CurrencyStatus` 열거 형식 내에 정의 된를 `COleCurrency` 클래스입니다.

```
enum CurrencyStatus {
    valid = 0,
    invalid = 1,
    null = 2
    };
```

이러한 상태 값의 간략 한 설명을 다음 목록을 참조 합니다.

- `COleCurrency::valid` 나타냅니다이 `COleCurrency` 개체는 유효 합니다.

- `COleCurrency::invalid` 나타냅니다이 `COleCurrency` 개체가 잘못 되었습니다. 즉, 해당 값 잘못 되었을 수 있습니다.

- `COleCurrency::null` 나타냅니다이 `COleCurrency` 개체가 null 인 경우 즉,이 개체에 대해 제공 된 값입니다. (이 값이 "null" 의"값 없음."와 반대로 데이터베이스 점에서 C++ NULL입니다.)

> [!CAUTION]
>  이 기능은 고급 프로그래밍 시나리오에 대 한 합니다. 이 함수는이 개체의 데이터를 변경 하지 않습니다. null 또는 잘못 된 상태를 설정 하려면 가장 자주 사용 됩니다. 대입 연산자 ( [연산자 =](#operator_eq)) 및 [SetCurrency](#setcurrency) 원본 값에 따라 개체의 상태를 설정 하려면.

## <a name="see-also"></a>참고자료

[계층 구조 차트](../../mfc/hierarchy-chart.md)<br/>
[COleVariant 클래스](../../mfc/reference/colevariant-class.md)
