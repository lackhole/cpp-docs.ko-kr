---
title: CArchiveException 클래스
ms.date: 11/04/2016
f1_keywords:
- CArchiveException
- AFX/CArchiveException
- AFX/CArchiveException::CArchiveException
- AFX/CArchiveException::m_cause
- AFX/CArchiveException::m_strFileName
helpviewer_keywords:
- CArchiveException [MFC], CArchiveException
- CArchiveException [MFC], m_cause
- CArchiveException [MFC], m_strFileName
ms.assetid: da31a127-e86c-41d1-b0b6-bed0865b1b49
ms.openlocfilehash: 731735bccf9225e67d82b1fe90336c92a630b368
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62391311"
---
# <a name="carchiveexception-class"></a>CArchiveException 클래스

Serialization 예외 상태를 나타냅니다.

## <a name="syntax"></a>구문

```
class CArchiveException : public CException
```

## <a name="members"></a>멤버

### <a name="public-constructors"></a>Public 생성자

|이름|설명|
|----------|-----------------|
|[CArchiveException::CArchiveException](#carchiveexception)|`CArchiveException` 개체를 생성합니다.|

### <a name="public-data-members"></a>공용 데이터 멤버

|이름|설명|
|----------|-----------------|
|[CArchiveException::m_cause](#m_cause)|예외 원인을 나타냅니다.|
|[CArchiveException::m_strFileName](#m_strfilename)|이 예외 상태에 대 한 파일의 이름을 지정합니다.|

## <a name="remarks"></a>설명

`CArchiveException` 클래스는 예외의 원인을 나타내는 공용 데이터 멤버를 포함 합니다.

`CArchiveException` 개체를 생성 하 고 내부에서 throw [CArchive](../../mfc/reference/carchive-class.md) 멤버 함수입니다. 범위 내에서 이러한 개체에 액세스할 수 있습니다는 **CATCH** 식입니다. 이유 코드 운영 체제와 무관 합니다. 예외 처리에 대 한 자세한 내용은 참조 하세요. [예외 처리 (MFC)](../../mfc/exception-handling-in-mfc.md)합니다.

## <a name="inheritance-hierarchy"></a>상속 계층 구조

[CObject](../../mfc/reference/cobject-class.md)

[CException](../../mfc/reference/cexception-class.md)

`CArchiveException`

## <a name="requirements"></a>요구 사항

**헤더:** afx.h

##  <a name="carchiveexception"></a>  CArchiveException::CArchiveException

생성을 `CArchiveException` 개체의 값을 저장 *발생할* 개체에서입니다.

```
CArchiveException(
    int cause = CArchiveException::none,
    LPCTSTR lpszArchiveName = NULL);
```

### <a name="parameters"></a>매개 변수

*cause*<br/>
예외에 대 한 이유를 나타내는 열거 형식 변수입니다. 열거자 목록은 참조 하세요. 합니다 [m_cause](#m_cause) 데이터 멤버입니다.

*lpszArchiveName*<br/>
이름을 포함 하는 문자열을 가리키는 `CArchive` 예외를 발생 시키는 개체입니다.

### <a name="remarks"></a>설명

만들 수 있습니다는 `CArchiveException` 힙에 개체 및 직접 throw 또는 전역 함수가 [AfxThrowArchiveException](../../mfc/reference/exception-processing.md#afxthrowarchiveexception) 를 처리 합니다.

이 생성자를 직접 사용 하지 마십시오 전역 함수를 호출 하는 대신 `AfxThrowArchiveException`합니다.

##  <a name="m_cause"></a>  CArchiveException::m_cause

예외의 원인을 지정합니다.

```
int m_cause;
```

### <a name="remarks"></a>설명

이 데이터 멤버는 형식의 공용 변수 **int**합니다. 으로 정의 된 해당 값을 `CArchiveException` 열거 형식입니다. 아래에 열거자와 해당 의미가 나와 있습니다.

- `CArchiveException::none` 오류가 발생 했습니다.

- `CArchiveException::genericException` 지정 되지 않은 오류가 발생 했습니다.

- `CArchiveException::readOnly` 로드에 대 한 열린 보관 파일에 쓰려고 했습니다.

- `CArchiveException::endOfFile` 개체를 읽는 중에 도달 하면된 않은 파일의 끝이 나타났습니다.

- `CArchiveException::writeOnly` 저장 하기 위한 열린 보관 파일에서 읽기를 시도 합니다.

- `CArchiveException::badIndex` 잘못 된 파일 형식입니다.

- `CArchiveException::badClass` 잘못 된 형식의 개체로 개체를 읽을 하려고 했습니다.

- `CArchiveException::badSchema` 클래스의 다른 버전을 사용 하 여 개체를 읽을 하려고 했습니다.

    > [!NOTE]
    >  이러한 `CArchiveException` 원인 열거자는 `CFileException` 원인 열거자와는 다릅니다.

    > [!NOTE]
    > `CArchiveException::generic`은 사용되지 않습니다. 대신 `genericException`를 사용하세요. 하는 경우 **제네릭** 응용 프로그램에서 사용 되 고 빌드된 /clr을 사용 하 여 있습니다 쉽게 이해할 수 없는 구문 오류가 있습니다.

##  <a name="m_strfilename"></a>  CArchiveException::m_strFileName

이 예외 상태에 대 한 파일의 이름을 지정합니다.

```
CString m_strFileName;
```

## <a name="see-also"></a>참고자료

[CException 클래스](../../mfc/reference/cexception-class.md)<br/>
[계층 구조 차트](../../mfc/hierarchy-chart.md)<br/>
[CArchive 클래스](../../mfc/reference/carchive-class.md)<br/>
[AfxThrowArchiveException](../../mfc/reference/exception-processing.md#afxthrowarchiveexception)<br/>
[예외 처리](../../mfc/reference/exception-processing.md)
