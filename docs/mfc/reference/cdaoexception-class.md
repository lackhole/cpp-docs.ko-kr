---
title: CDaoException 클래스
ms.date: 11/04/2016
f1_keywords:
- CDaoException
- AFXDAO/CDaoException
- AFXDAO/CDaoException::CDaoException
- AFXDAO/CDaoException::GetErrorCount
- AFXDAO/CDaoException::GetErrorInfo
- AFXDAO/CDaoException::m_nAfxDaoError
- AFXDAO/CDaoException::m_pErrorInfo
- AFXDAO/CDaoException::m_scode
helpviewer_keywords:
- CDaoException [MFC], CDaoException
- CDaoException [MFC], GetErrorCount
- CDaoException [MFC], GetErrorInfo
- CDaoException [MFC], m_nAfxDaoError
- CDaoException [MFC], m_pErrorInfo
- CDaoException [MFC], m_scode
ms.assetid: b2b01fa9-7ce2-42a1-842e-40f13dc50da4
ms.openlocfilehash: 8d49291c51f66ee837f9b31a2ade390cec48c51a
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62399806"
---
# <a name="cdaoexception-class"></a>CDaoException 클래스

DAO(Data Access Objects)를 기반으로 하는 MFC 데이터베이스 클래스에서 발생하는 예외 상태를 나타냅니다.

## <a name="syntax"></a>구문

```
class CDaoException : public CException
```

## <a name="members"></a>멤버

### <a name="public-constructors"></a>Public 생성자

|이름|설명|
|----------|-----------------|
|[CDaoException::CDaoException](#cdaoexception)|`CDaoException` 개체를 생성합니다.|

### <a name="public-methods"></a>Public 메서드

|이름|설명|
|----------|-----------------|
|[CDaoException::GetErrorCount](#geterrorcount)|데이터베이스 엔진의 오류 컬렉션에 오류 수를 반환합니다.|
|[CDaoException::GetErrorInfo](#geterrorinfo)|Errors 컬렉션에서 특정 오류 개체에 대 한 오류 정보를 반환합니다.|

### <a name="public-data-members"></a>공용 데이터 멤버

|이름|설명|
|----------|-----------------|
|[CDaoException::m_nAfxDaoError](#m_nafxdaoerror)|MFC DAO 클래스의 모든 오류에 대 한 확장 된 오류 코드를 포함합니다.|
|[CDaoException::m_pErrorInfo](#m_perrorinfo)|에 대 한 포인터를 [CDaoErrorInfo](../../mfc/reference/cdaoerrorinfo-structure.md) 하나 DAO 오류 개체에 대 한 정보가 들어 있는 개체입니다.|
|[CDaoException::m_scode](#m_scode)|합니다 [SCODE](#m_scode) 오류와 연결 된 값입니다.|

## <a name="remarks"></a>설명

클래스는 예외의 원인을 확인 하려면 사용할 수 있는 공용 데이터 멤버를 포함 합니다. `CDaoException` 개체 생성 되며 DAO 데이터베이스 클래스의 멤버 함수에 의해 throw 됩니다.

> [!NOTE]
>  DAO 데이터베이스 클래스로 개방형 데이터베이스 연결 (ODBC)에 따라 MFC 데이터베이스 클래스와에서 다릅니다. 모든 DAO 데이터베이스 클래스 이름 "CDao" 접두사가 있습니다. 여전히 DAO 클래스를 사용 하 여 ODBC 데이터 원본 액세스 할 수 있습니다. 일반적으로 기반으로 DAO MFC 클래스는 ODBC를 기반으로 MFC 클래스 보다 더욱 강력한 DAO 기반 클래스를 통해 자신의 데이터베이스 엔진을 통해 ODBC 드라이버를 비롯 하 여 데이터를 액세스할 수 있습니다. DAO 기반 클래스는 또한 직접 DAO 호출 하지 않고도 클래스를 통해 테이블을 추가 하는 등의 데이터 정의 언어 (DDL) 작업을 지원 합니다. ODBC 클래스에서 throw 된 예외에 대 한 자세한 내용은 [CDBException](../../mfc/reference/cdbexception-class.md)합니다.

예외 개체의 범위 내에서 액세스할 수 있습니다는 [CATCH](../../mfc/reference/exception-processing.md#catch) 식입니다. Throw 할 수 있습니다 `CDaoException` 사용 하 여 사용자 고유의 코드에서 개체를 [AfxThrowDaoException](../../mfc/reference/exception-processing.md#afxthrowdaoexception) 전역 함수입니다.

MFC에서 모든 DAO 오류 예외 형식으로 표현 됩니다 `CDaoException`합니다. 이 유형의 예외를 catch 하는 경우 사용할 수 있습니다 `CDaoException` 멤버 함수는 데이터베이스 엔진의 오류 컬렉션에 저장 된 모든 DAO 오류 개체에서 정보를 검색 합니다. 각 오류 발생 오류 컬렉션에 하나 이상의 오류 개체 배치 됩니다. (일반적으로 하나의 오류 개체가 컬렉션에 포함를 ODBC 데이터 소스를 사용 하는 경우 여러 오류 개체를 얻을 가능성이 있습니다.) 다른 DAO 작업이 오류를 생성할 때 오류 컬렉션의 선택을 취소 하 고 새 오류 개체는 오류 컬렉션에 배치 됩니다. 오류를 생성 하지 않는 DAO 작업 오류 컬렉션에는 효과가 없습니다.

DAO 오류 코드에 대 한 DAOERR 파일을 참조 하십시오. 8. 관련된 정보 "트랩 가능한 DAO 도움말에서 Data Access Errors" 항목을 참조 하세요.

일반적으로 되었거나 곧에서 예외 처리에 대 한 자세한 내용은 `CDaoException` 문서를 참조 하는 개체를 [예외 처리 (MFC)](../../mfc/exception-handling-in-mfc.md) 및 [예외: 데이터베이스 예외](../../mfc/exceptions-database-exceptions.md)합니다. 두 번째 기사는 DAO에서 예외 처리를 보여 주는 예제 코드를 포함 합니다.

## <a name="inheritance-hierarchy"></a>상속 계층 구조

[CObject](../../mfc/reference/cobject-class.md)

[CException](../../mfc/reference/cexception-class.md)

`CDaoException`

## <a name="requirements"></a>요구 사항

**헤더:** afxdao.h

##  <a name="cdaoexception"></a>  CDaoException::CDaoException

`CDaoException` 개체를 생성합니다.

```
CDaoException();
```

### <a name="remarks"></a>설명

일반적으로 프레임 워크는 해당 코드는 예외를 throw 하면 예외 개체를 만듭니다. 거의 예외 개체를 명시적으로 생성 해야 합니다. Throw 하려는 경우는 `CDaoException` 고유의 코드에서 전역 함수 호출 [AfxThrowDaoException](../../mfc/reference/exception-processing.md#afxthrowdaoexception)합니다.

그러나 다음 DAO MFC 클래스에 캡슐화 하는 DAO 인터페이스 포인터를 통해 직접 호출 하는 경우는 예외 개체를 만들어야 하는 것이 좋습니다. 이 경우 DAO에서 오류 정보를 검색 해야 합니다. 작업 영역 데이터베이스 컬렉션에 DAODatabases 인터페이스를 통해 DAO 메서드를 호출할 때 DAO에서 오류가 발생 한다고 가정 합니다.

##### <a name="to-retrieve-the-dao-error-information"></a>DAO 오류 정보를 검색 하려면

1. 생성 된 `CDaoException` 개체입니다.

1. 예외 개체의 호출 [GetErrorCount](#geterrorcount) 데이터베이스 엔진의 오류 컬렉션에 있는 오류 개체의 수를 결정 하는 멤버 함수입니다. (일반적으로 하나만 ODBC 데이터 소스를 사용 하는 경우입니다.)

1. 예외 개체의 호출 [GetErrorInfo](#geterrorinfo) 예외 개체를 통해 컬렉션에서 인덱스로 한 번에 하나의 특정 오류 개체를 검색 하는 멤버 함수입니다. 예외 개체 하나 DAO 오류 개체에 대 한 프록시로 생각 됩니다.

1. 현재 검사 [CDaoErrorInfo](../../mfc/reference/cdaoerrorinfo-structure.md) 구조체입니다 `GetErrorInfo` 에서 반환 된 [m_pErrorInfo](#m_perrorinfo) 데이터 멤버입니다. 해당 멤버는 DAO 오류 정보를 제공합니다.

1. ODBC 데이터 원본으로의 경우 3 및 4 자세한 오류 개체에 대 한 필요에 따라 단계를 반복 합니다.

1. 힙의 예외 개체를 생성 하는 경우 사용 하 여 삭제 합니다 **삭제** 완료 될 때 연산자입니다.

MFC DAO 클래스에서 오류를 처리 하는 방법에 대 한 자세한 내용은 문서를 참조 하세요. [예외: 데이터베이스 예외](../../mfc/exceptions-database-exceptions.md)합니다.

##  <a name="geterrorcount"></a>  CDaoException::GetErrorCount

데이터베이스 엔진의 오류 컬렉션의 DAO 오류 개체 수를 검색 하려면이 멤버 함수를 호출 합니다.

```
short GetErrorCount();
```

### <a name="return-value"></a>반환 값

데이터베이스 엔진의 오류 컬렉션의 DAO 오류 개체의 수입니다.

### <a name="remarks"></a>설명

이 정보는 각 컬렉션에 하나 이상의 DAO 오류 개체를 검색 하려면 오류 컬렉션을 반복 하는 데 유용 합니다. Error 개체를 인덱스로 또는 DAO 오류 번호를 검색 하려면 호출을 [GetErrorInfo](#geterrorinfo) 멤버 함수입니다.

> [!NOTE]
>  일반적으로 개체가 하나만 오류에 오류 컬렉션입니다. 그러나 ODBC 데이터 원본을 사용 하 여 작업 하는 경우 있을 수 둘 이상 있습니다.

##  <a name="geterrorinfo"></a>  CDaoException::GetErrorInfo

Errors 컬렉션에서 특정 오류 개체에 대 한 오류 정보를 반환합니다.

```
void GetErrorInfo(int nIndex);
```

### <a name="parameters"></a>매개 변수

*nIndex*<br/>
인덱스 인덱스에서 조회에 대 한 데이터베이스 엔진의 오류 컬렉션에 오류 정보입니다.

### <a name="remarks"></a>설명

다음 종류의 예외에 대 한 정보를 가져오려면이 함수를 호출 합니다.

- 오류 코드

- Source

- 설명

- 도움말 파일

- 도움말 컨텍스트

`GetErrorInfo` 예외 개체의 정보를 저장 `m_pErrorInfo` 데이터 멤버입니다. 반환 된 정보는 간략 한 설명을 참조 하세요 [m_pErrorInfo](#m_perrorinfo)합니다. 형식의 예외를 catch 하는 경우 `CDaoException` MFC throw를 `m_pErrorInfo` 멤버 이미 입력 되어 있습니다. 직접 DAO 호출 하려는 경우 예외 개체의 호출 해야 합니다 `GetErrorInfo` 멤버 함수에 맞게 직접 `m_pErrorInfo`입니다. 자세한 내용은 참조 하세요. 합니다 [CDaoErrorInfo](../../mfc/reference/cdaoerrorinfo-structure.md) 구조입니다.

DAO 예외 및 예제 코드에 대 한 자세한 문서를 참고 [예외: 데이터베이스 예외](../../mfc/exceptions-database-exceptions.md)합니다.

##  <a name="m_nafxdaoerror"></a>  CDaoException::m_nAfxDaoError

오류 코드를 확장 하는 MFC를 포함 합니다.

### <a name="remarks"></a>설명

이 코드는 MFC DAO 클래스의 특정 구성 요소에 몇몇 있는 경우에 제공 됩니다.

가능한 값은 다음과 같습니다.

- MFC에서 최근 작업 발생 하지 않았음 NO_AFX_DAO_ERROR 확장 오류입니다. 그러나 작업 수 생성 DAO 또는 OLE에서 다른 오류를 확인 해야 하므로 [m_pErrorInfo](#m_perrorinfo) 부분과 [m_scode](#m_scode)합니다.

- AFX_DAO_ERROR_ENGINE_INITIALIZATION MFC Microsoft Jet 데이터베이스 엔진을 초기화 하지 못했습니다. OLE를 초기화 하지 못했을 수 있습니다 또는 취소 되었을 DAO 데이터베이스 엔진 개체의 인스턴스를 만들 수 있습니다. 이러한 문제는 일반적으로 DAO 나 OLE의 잘못 된 설치를 제안 합니다.

- AFX_DAO_ERROR_DFX_BIND DAO 레코드 필드 교환 (DFX) 함수 호출에 사용 되는 주소 없거나 올바르지 않습니다 (주소 데이터를 바인딩하는 사용 되지 않음 된). DFX 호출에서 잘못 된 주소를 전달 했습니다 수 또는 주소 DFX 작업 간에 잘못 될 수 있습니다.

- AFX_DAO_ERROR_OBJECT_NOT_OPEN 하려는 쿼리 정의 또는 열린 상태에서 포함 되지 않은 테이블 정의 기반으로 레코드 집합을 엽니다.

##  <a name="m_perrorinfo"></a>  CDaoException::m_pErrorInfo

에 대 한 포인터를 포함 한 `CDaoErrorInfo` DAO 오류 개체를 호출 하 여 마지막으로 검색에 대 한 정보를 제공 하는 구조 [GetErrorInfo](#geterrorinfo)합니다.

### <a name="remarks"></a>설명

이 개체에는 다음 정보를 포함합니다.

|CDaoErrorInfo 멤버|정보|의미|
|--------------------------|-----------------|-------------|
|`m_lErrorCode`|오류 코드|DAO 오류 코드|
|`m_strSource`|Source|개체 또는 원래 오류를 생성 하는 응용 프로그램의 이름|
|`m_strDescription`|설명|오류와 관련 된 설명 문자열|
|`m_strHelpFile`|도움말 파일|사용자는 문제에 대 한 정보를 얻을 수는 Windows 도움말 파일에 대 한 경로|
|`m_lHelpContext`|도움말 컨텍스트|DAO 도움말 파일의 항목에 대 한 컨텍스트 ID|

에 포함 된 정보에 대 한 자세한 내용은 합니다 `CDaoErrorInfo` 개체를 참조 하십시오 합니다 [CDaoErrorInfo](../../mfc/reference/cdaoerrorinfo-structure.md) 구조입니다.

##  <a name="m_scode"></a>  CDaoException::m_scode

형식의 값을 포함 `SCODE` 는 오류를 설명 합니다.

### <a name="remarks"></a>설명

OLE 코드입니다. 거의 모든 경우에 보다 구체적인 MFC 또는 DAO 오류 정보는 다른 사용할 수 있으므로이 값을 사용 해야 거의 `CDaoException` 데이터 멤버입니다.

SCODE에 대 한 자세한 내용은 [OLE 오류 코드 구조](/windows/desktop/com/structure-of-com-error-codes) Windows SDK에 있습니다. SCODE 데이터 형식은 HRESULT 데이터 형식에 매핑됩니다.

## <a name="see-also"></a>참고자료

[CException 클래스](../../mfc/reference/cexception-class.md)<br/>
[계층 구조 차트](../../mfc/hierarchy-chart.md)<br/>
[CException 클래스](../../mfc/reference/cexception-class.md)
