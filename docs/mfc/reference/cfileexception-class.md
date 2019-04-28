---
title: CFileException 클래스
ms.date: 11/04/2016
f1_keywords:
- CFileException
- AFX/CFileException
- AFX/CFileException::CFileException
- AFX/CFileException::ErrnoToException
- AFX/CFileException::GetErrorMessage
- AFX/CFileException::OsErrorToException
- AFX/CFileException::ThrowErrno
- AFX/CFileException::ThrowOsError
- AFX/CFileException::m_cause
- AFX/CFileException::m_lOsError
- AFX/CFileException::m_strFileName
helpviewer_keywords:
- CFileException [MFC], CFileException
- CFileException [MFC], ErrnoToException
- CFileException [MFC], GetErrorMessage
- CFileException [MFC], OsErrorToException
- CFileException [MFC], ThrowErrno
- CFileException [MFC], ThrowOsError
- CFileException [MFC], m_cause
- CFileException [MFC], m_lOsError
- CFileException [MFC], m_strFileName
ms.assetid: f6491bb9-bfbc-42fd-a952-b33f9b62323f
ms.openlocfilehash: a3514c76d4136fe2bc0b096cc382e6f7f4dd3392
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62205938"
---
# <a name="cfileexception-class"></a>CFileException 클래스

파일 관련 예외 상태를 나타냅니다.

## <a name="syntax"></a>구문

```
class CFileException : public CException
```

## <a name="members"></a>멤버

### <a name="public-constructors"></a>Public 생성자

|이름|설명|
|----------|-----------------|
|[CFileException::CFileException](#cfileexception)|`CFileException` 개체를 생성합니다.|

### <a name="public-methods"></a>Public 메서드

|이름|설명|
|----------|-----------------|
|[CFileException::ErrnoToException](#errnotoexception)|반환 하면 런타임 오류 번호에 해당 하는 코드입니다.|
|[CFileException::GetErrorMessage](#geterrormessage)|예외를 설명 하는 메시지를 검색 합니다.|
|[CFileException::OsErrorToException](#oserrortoexception)|운영 체제 오류 코드에 해당 하는 이유 코드를 반환 합니다.|
|[CFileException::ThrowErrno](#throwerrno)|런타임 오류 수에 따라 파일 예외를 throw 합니다.|
|[CFileException::ThrowOsError](#throwoserror)|운영 체제 오류 수를 기반으로 파일 예외를 throw 합니다.|

### <a name="public-data-members"></a>공용 데이터 멤버

|이름|설명|
|----------|-----------------|
|[CFileException::m_cause](#m_cause)|예외 원인에 해당 하는 이식 가능한 코드를 포함 합니다.|
|[CFileException::m_lOsError](#m_loserror)|관련된 운영 체제 오류 번호를 포함합니다.|
|[CFileException::m_strFileName](#m_strfilename)|이 예외에 대 한 파일의 이름을 포함합니다.|

## <a name="remarks"></a>설명

`CFileException` 클래스 코드를 이식 가능한 원인 및 운영 체제 시스템-관련 오류 번호를 포함 하는 공용 데이터 멤버를 포함 합니다. 클래스는 또한 파일 예외를 throw 한 운영 체제 오류 및 C 런타임 오류에 대 한 원인은 코드를 반환 하는 것에 대 한 정적 멤버 함수를 제공 합니다.

`CFileException` 개체를 생성 하 고 throw `CFile` 멤버 함수에 파생된 클래스의 멤버 함수입니다. 범위 내에서 이러한 개체에 액세스할 수 있습니다는 **CATCH** 식입니다. 이식성에 대 한 예외에 대 한 이유를 가져오려는 원인 코드만 사용 합니다. 예외에 대 한 자세한 내용은 문서 참조 [예외 처리 (MFC)](../../mfc/exception-handling-in-mfc.md)합니다.

## <a name="inheritance-hierarchy"></a>상속 계층 구조

[CObject](../../mfc/reference/cobject-class.md)

[CException](../../mfc/reference/cexception-class.md)

`CFileException`

## <a name="requirements"></a>요구 사항

**헤더:** afx.h

##  <a name="cfileexception"></a>  CFileException::CFileException

생성 된 `CFileException` 원인 코드와 운영 체제 코드 개체에 저장 하는 개체입니다.

```
CFileException(
    int cause = CFileException::none,
    LONG lOsError = -1,
    LPCTSTR lpszArchiveName = NULL);
```

### <a name="parameters"></a>매개 변수

*cause*<br/>
예외에 대 한 이유를 나타내는 열거 형식 변수입니다. 참조 [CFileException::m_cause](#m_cause) 가능한 값 목록은 합니다.

*lOsError*<br/>
사용 가능한 경우 예외는 운영 체제별 이유입니다. 합니다 *lOsError* 보다 자세한 정보를 제공 하는 매개 변수 *일으킬* 않습니다.

*lpszArchiveName*<br/>
이름을 포함 하는 문자열을 가리키는 `CFile` 예외를 발생 시키는 개체입니다.

### <a name="remarks"></a>설명

이 생성자를 직접 사용 하지 않고 대신 전역 함수를 호출 [AfxThrowFileException](exception-processing.md#afxthrowfileexception)합니다.

> [!NOTE]
>  변수의 *lOsError* 에 적용 됩니다 `CFile` 고 `CStdioFile` 개체입니다. `CMemFile` 클래스는이 오류 코드를 처리 하지 않습니다.

##  <a name="errnotoexception"></a>  CFileException::ErrnoToException

지정 된 런타임 라이브러리 오류 값을 변환 된 `CFileException` 오류 값을 열거 합니다.

```
static int PASCAL ErrnoToException(int nErrno);
```

### <a name="parameters"></a>매개 변수

*nErrno*<br/>
ERRNO 런타임 포함 파일에 정의 된 정수 오류 코드입니다. 8.

### <a name="return-value"></a>반환 값

지정 된 런타임 라이브러리 오류 값에 해당 하는 열거형된 값입니다.

### <a name="remarks"></a>설명

참조 [CFileException::m_cause](#m_cause) 가능한 목록에 대 한 값을 열거 합니다.

### <a name="example"></a>예제

[!code-cpp[NVC_MFCFiles#26](../../atl-mfc-shared/reference/codesnippet/cpp/cfileexception-class_1.cpp)]

##  <a name="geterrormessage"></a>  CFileException::GetErrorMessage

예외를 설명 하는 텍스트를 검색 합니다.

```
virtual BOOL GetErrorMessage(
    LPTSTR lpszError,
    UINT nMaxError,
    PUINT pnHelpContext = NULL) const;
```

### <a name="parameters"></a>매개 변수

*lpszError*<br/>
[out에서] 오류 메시지를 받는 버퍼에 대 한 포인터입니다.

*nMaxError*<br/>
[in] 지정 된 버퍼에 저장할 수 문자의 최대 수입니다. Null 종결 문자 포함 됩니다.

*pnHelpContext*<br/>
[out에서] 도움말 컨텍스트 ID를 수신 하는 부호 없는 정수에 대 한 포인터 경우 `NULL`, ID가 없습니다. 반환 됩니다.

### <a name="return-value"></a>반환 값

메서드가 성공 하면 TRUE입니다. 그렇지 않으면 FALSE입니다.

### <a name="remarks"></a>설명

지정 된 버퍼가 너무 작은 경우 오류 메시지는 잘립니다.

### <a name="example"></a>예제

다음 예제에서는 `CFileException::GetErrorMessage`합니다.

[!code-cpp[NVC_MFCExceptions#22](../../mfc/codesnippet/cpp/cfileexception-class_2.cpp)]

##  <a name="m_cause"></a>  CFileException::m_cause

`CFileException` 열거형 형식으로 정의되는 값을 포함합니다.

```
int m_cause;
```

### <a name="remarks"></a>설명

이 데이터 멤버는 형식의 공용 변수 **int**합니다. 아래에 열거자와 해당 의미가 나와 있습니다.

- `CFileException::none` 0: 오류가 발생 했습니다.

- `CFileException::genericException` 1: 지정되지 않은 오류가 발생했습니다.

- `CFileException::fileNotFound` 2: 파일을 찾을 수 없습니다.

- `CFileException::badPath` 3: 전체 또는 일부 경로를 잘못 되었습니다.

- `CFileException::tooManyOpenFiles` 4: 열려 있는 파일의 허용 된 수를 초과 했습니다.

- `CFileException::accessDenied` 5: 파일에 액세스할 수 없습니다.

- `CFileException::invalidFile` 6: 잘못 된 파일 핸들을 사용 하려고가 했습니다.

- `CFileException::removeCurrentDir` 7: 현재 작업 디렉터리를 제거할 수 없습니다.

- `CFileException::directoryFull` 8: 자세한 디렉터리 항목이 없습니다.

- `CFileException::badSeek` 9: 파일 포인터를 설정 하는 동안 오류가 발생 했습니다.

- `CFileException::hardIO` 10: 하드웨어 오류가 발생이 했습니다.

- `CFileException::sharingViolation` 11: 공유. EXE가 로드 되지 또는 공유 영역이 잠겼습니다.

- `CFileException::lockViolation` 12: 이미 잠겨 있는 영역을 잠그려는 시도가 있었습니다.

- `CFileException::diskFull` 14: 디스크가 꽉 찼습니다.

- `CFileException::endOfFile` 15: 파일의 끝에 도달 했습니다.

    > [!NOTE]
    >  이러한 `CFileException` 원인 열거자는 `CArchiveException` 원인 열거자와는 다릅니다.

    > [!NOTE]
    > `CArchiveException::generic`은 사용되지 않습니다. 대신 `genericException`를 사용하세요. 하는 경우 **제네릭** 응용 프로그램에서 사용 되 고 /clr을 쉽게 이해할 수 없는 오류가 발생 하는 구문을 사용 하 여 작성 합니다.

### <a name="example"></a>예제

[!code-cpp[NVC_MFCFiles#30](../../atl-mfc-shared/reference/codesnippet/cpp/cfileexception-class_3.cpp)]

##  <a name="m_loserror"></a>  CFileException::m_lOsError

이 예외에 대 한 운영 체제 오류 코드를 포함합니다.

```
LONG m_lOsError;
```

### <a name="remarks"></a>설명

오류 코드 목록은 운영 체제 기술 설명서를 참조 하십시오. 이 데이터 멤버 형식의 공용 변수를 LONG입니다.

##  <a name="m_strfilename"></a>  CFileException::m_strFileName

이 예외 상태에 대 한 파일의 이름을 포함합니다.

```
CString m_strFileName;
```

##  <a name="oserrortoexception"></a>  CFileException::OsErrorToException

에 해당 하는 열거자를 반환 합니다는 주어진 *lOsError* 값입니다. 오류 코드를 알 수 없는 경우 반환 `CFileException::generic`합니다.

```
static int PASCAL OsErrorToException(LONG lOsError);
```

### <a name="parameters"></a>매개 변수

*lOsError*<br/>
운영 체제 시스템-관련 오류 코드입니다.

### <a name="return-value"></a>반환 값

지정 된 운영 체제 오류 값에 해당 하는 열거형된 값입니다.

### <a name="example"></a>예제

[!code-cpp[NVC_MFCFiles#27](../../atl-mfc-shared/reference/codesnippet/cpp/cfileexception-class_4.cpp)]

##  <a name="throwerrno"></a>  CFileException::ThrowErrno

생성을 `CFileException` 개체에 해당 하는 주어진 *nErrno* 값을 다음 예외를 throw 합니다.

```
static void PASCAL ThrowErrno(int nErrno, LPCTSTR lpszFileName = NULL);
```

### <a name="parameters"></a>매개 변수

*nErrno*<br/>
ERRNO 런타임 포함 파일에 정의 된 정수 오류 코드입니다. 8.

*lpszFileName*<br/>
파일의 이름을 포함 하는 문자열에 대 한 포인터를 발생 시킨 예외를 사용 가능한 경우.

### <a name="example"></a>예제

[!code-cpp[NVC_MFCFiles#28](../../atl-mfc-shared/reference/codesnippet/cpp/cfileexception-class_5.cpp)]

##  <a name="throwoserror"></a>  CFileException::ThrowOsError

Throw를 `CFileException` 에 해당 하는 주어진 *lOsError* 값입니다. 오류 코드를 알 수 없는 경우 함수를 코딩 된 예외를 throw `CFileException::generic`합니다.

```
static void PASCAL ThrowOsError(LONG lOsError, LPCTSTR lpszFileName = NULL);
```

### <a name="parameters"></a>매개 변수

*lOsError*<br/>
운영 체제 시스템-관련 오류 코드입니다.

*lpszFileName*<br/>
파일의 이름을 포함 하는 문자열에 대 한 포인터를 발생 시킨 예외를 사용 가능한 경우.

### <a name="example"></a>예제

[!code-cpp[NVC_MFCFiles#29](../../atl-mfc-shared/reference/codesnippet/cpp/cfileexception-class_6.cpp)]

## <a name="see-also"></a>참고자료

[CException 클래스](../../mfc/reference/cexception-class.md)<br/>
[계층 구조 차트](../../mfc/hierarchy-chart.md)<br/>
[예외 처리](../../mfc/reference/exception-processing.md)
