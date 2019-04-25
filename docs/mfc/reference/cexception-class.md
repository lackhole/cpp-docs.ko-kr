---
title: CException 클래스
ms.date: 11/04/2016
f1_keywords:
- CException
- AFX/CException
- AFX/CException::CException
- AFX/CException::Delete
- AFX/CException::ReportError
helpviewer_keywords:
- CException [MFC], CException
- CException [MFC], Delete
- CException [MFC], ReportError
ms.assetid: cfacf14d-bfe4-4666-a5c7-38b800512920
ms.openlocfilehash: 689afa2ffbc27feec6f9e1704a6b295d5eabfaee
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62164002"
---
# <a name="cexception-class"></a>CException 클래스

MFC 라이브러리의 모든 예외에 대한 기본 클래스입니다.

## <a name="syntax"></a>구문

```
class AFX_NOVTABLE CException : public CObject
```

## <a name="members"></a>멤버

### <a name="public-constructors"></a>Public 생성자

|이름|설명|
|----------|-----------------|
|[CException::CException](#cexception)|`CException` 개체를 생성합니다.|

### <a name="public-methods"></a>Public 메서드

|이름|설명|
|----------|-----------------|
|[CException::Delete](#delete)|삭제를 `CException` 개체입니다.|
|[CException::ReportError](#reporterror)|메시지 상자에 오류 메시지가 사용자에 게 보고합니다.|

## <a name="remarks"></a>설명

때문에 `CException` 는 추상 기본 클래스를 만들 수 없습니다 `CException` 개체를 직접 파생된 클래스의 개체를 만들어야 합니다. 나만의 사이트 생성 해야 할 경우 `CException`-스타일 클래스 모델로 위에 나열 된 파생된 클래스 중 하나를 사용 합니다. 파생된 클래스도 사용 하도록 `IMPLEMENT_DYNAMIC`합니다.

파생된 클래스 및 해당 설명이 아래에 나열 됩니다.

|||
|-|-|
|[CSimpleException](../../mfc/reference/csimpleexception-class.md)|한 리소스에 중요 한 MFC 예외의 기본 클래스|
|[CInvalidArgException](../../mfc/reference/cinvalidargexception-class.md)|잘못 된 인수 예외 상태|
|[CMemoryException](../../mfc/reference/cmemoryexception-class.md)|메모리 부족 예외|
|[CNotSupportedException](../../mfc/reference/cnotsupportedexception-class.md)|지원 되지 않는 작업에 대 한 요청|
|[CArchiveException](../../mfc/reference/carchiveexception-class.md)|보관 파일 관련 예외|
|[CFileException](../../mfc/reference/cfileexception-class.md)|파일 관련 예외|
|[CResourceException](../../mfc/reference/cresourceexception-class.md)|Windows 리소스를 찾을 수 없음 또는 불가|
|[COleException](../../mfc/reference/coleexception-class.md)|OLE 예외|
|[CDBException](../../mfc/reference/cdbexception-class.md)|데이터베이스 예외 (즉,: Open Database Connectivity를 기반으로 하는 MFC 데이터베이스 클래스에 대 한 발생 하는 예외 조건)|
|[COleDispatchException](../../mfc/reference/coledispatchexception-class.md)|OLE 디스패치 (자동화) 예외|
|[CUserException](../../mfc/reference/cuserexception-class.md)|리소스를 찾을 수 있는지 여부를 나타내는 예외|
|[CDaoException](../../mfc/reference/cdaoexception-class.md)|데이터 액세스 개체 예외 (즉,: DAO 클래스에 대 한 발생 하는 예외 조건)|
|[CInternetException](../../mfc/reference/cinternetexception-class.md)|인터넷 예외 (즉,: 인터넷 클래스에 대 한 발생 하는 예외 조건)입니다.|

이러한 예외는 사용 하기 위한 것은 [THROW](exception-processing.md#throw), [THROW_LAST](exception-processing.md#throw_last), [시도](exception-processing.md#try), [catch](exception-processing.md#catch), [and_catch](exception-processing.md#and_catch), 및 [end_catch](exception-processing.md#end_catch) 매크로입니다. 예외에 대 한 자세한 내용은 참조 하세요. [예외 처리](exception-processing.md), 또는 문서를 참조 하십시오 [예외 처리 (MFC)](../exception-handling-in-mfc.md)합니다.

특정 예외를 catch 하려면 적절 한 파생된 클래스를 사용 합니다. Catch 모든 형식의 예외를 사용 하 여 `CException`를 사용 하 여 [CObject::IsKindOf](cobject-class.md#iskindof) 간을 구분 `CException`-클래스를 파생 합니다. 유의 `CObject::IsKindOf` 로 선언 된 클래스에 대해서만 작동 합니다 [IMPLEMENT_DYNAMIC](run-time-object-model-services.md#implement_dynamic) 동적 형식 확인을 활용 하기 위해 매크로 합니다. 모든 `CException`-사용자가 만든 파생된 클래스를 사용할지를 `IMPLEMENT_DYNAMIC` 매크로 너무 합니다.

호출 하 여 사용자에 게 예외에 대 한 세부 정보를 보고할 수 있습니다 [GetErrorMessage](cfileexception-class.md#geterrormessage) 또는 [ReportError](#reporterror)두 개의 멤버 함수 중 하나를 사용 하 여 해당 작업 `CException`의 파생 클래스입니다.

매크로, 중 하나에서 예외가 포착 되는 경우는 `CException` 삭제 하지 않을 직접; 개체는 자동으로 삭제 됩니다. 사용 하 여 예외가 포착 되는 경우는 **catch** 키워드를 자동으로 삭제 되지 않습니다. 문서를 참조 하세요 [예외 처리 (MFC)](../exception-handling-in-mfc.md) 예외 개체를 삭제 하는 경우에 대 한 자세한 내용은 합니다.

## <a name="inheritance-hierarchy"></a>상속 계층 구조

[CObject](cobject-class.md)

`CException`

## <a name="requirements"></a>요구 사항

**헤더:** afx.h

##  <a name="cexception"></a>  CException::CException

이 멤버 함수 생성을 `CException` 개체입니다.

```
explicit CException(BOOL bAutoDelete);
```

### <a name="parameters"></a>매개 변수

*b_AutoDelete*<br/>
TRUE를 지정 하는 경우에 대 한 메모리를 `CException` 개체 힙에 할당 된 합니다. 그러면 합니다 `CException` 삭제 될 때 개체는 `Delete` 멤버 함수가 호출 되어 예외를 삭제 합니다. 경우에 FALSE를 지정 합니다 `CException` 개체가 스택에 이거나 전역 개체입니다. 이 경우는 `CException` 개체는 되지 삭제는 `Delete` 멤버 함수를 호출.

### <a name="remarks"></a>설명

이 생성자를 직접 호출 하지 일반적으로 해야 합니다. 인스턴스를 만들도록 예외를 throw 하는 함수를 `CException`-MFC 중 하나를 사용 해야 함수 같은 throw 하거나 해당 생성자를 호출 하 고 파생 클래스 [AfxThrowFileException](exception-processing.md#afxthrowfileexception), 미리 정의 된 형식을 throw 하 합니다. 이 문서는 참조용 으로만 제공 됩니다.

##  <a name="delete"></a>  CException::Delete

이 함수는 있는지 확인 합니다 `CException` 힙에서 개체가 만들어지고 호출한 경우는 **삭제** 개체에 연산자.

```
void Delete();
```

### <a name="remarks"></a>설명

삭제 하는 경우는 `CException` 개체는 `Delete` 멤버 함수는 예외를 삭제 합니다. 사용 하지 마십시오는 **삭제** 연산자를 직접 때문에 `CException` 개체 전역 개체 수 있거나 스택에 생성 합니다.

개체가 생성 될 때 개체를 삭제할지 여부를 지정할 수 있습니다. 자세한 내용은 [CException::CException](#cexception)합니다.

호출 해야 `Delete` 사용 하는 경우는 C++ **시도**- **catch** 메커니즘입니다. MFC 매크로 사용 하는 경우 **시도** 하 고 **CATCH**, 이러한 매크로 자동으로이 함수를 호출 합니다.

### <a name="example"></a>예제

```cpp
CFile* pFile = NULL;
// Constructing a CFile object with this override may throw
// a CFile exception, and won't throw any other exceptions.
// Calling CString::Format() may throw a CMemoryException,
// so we have a catch block for such exceptions, too. Any
// other exception types this function throws will be
// routed to the calling function.
// Note that this example performs the same actions as the
// example for CATCH, but uses C++ try/catch syntax instead
// of using the MFC TRY/CATCH macros. This sample must use
// CException::Delete() to delete the exception objects
// before closing the catch block, while the CATCH example
// implicitly performs the deletion via the macros.
try
{
   pFile = new CFile(_T("C:\\WINDOWS\\SYSTEM.INI"),
      CFile::modeRead | CFile::shareDenyNone);
   ULONGLONG ullLength = pFile->GetLength();
   CString str;
   str.Format(_T("Your SYSTEM.INI file is %u bytes long."), ullLength);
   AfxMessageBox(str);
}
catch(CFileException* pEx)
{
   // Simply show an error message to the user.
   pEx->ReportError();
   pEx->Delete();
}
catch(CMemoryException* pEx)
{
   // We can't recover from this memory exception, so we'll
   // just terminate the app without any cleanup. Normally, an
   // an application should do everything it possibly can to
   // clean up properly and _not_ call AfxAbort().
   pEx->Delete();
   AfxAbort();
}
// If an exception occurrs in the CFile constructor,
// the language will free the memory allocated by new
// and will not complete the assignment to pFile.
// Thus, our clean-up code needs to test for NULL.
if (pFile != NULL)
{
   pFile->Close();
   delete pFile;
}
```

##  <a name="reporterror"></a>  CException::ReportError

사용자에 게 메시지 상자에 보고서 오류 텍스트를이 멤버 함수를 호출 합니다.

```
virtual int ReportError(
    UINT nType = MB_OK,
    UINT nMessageID = 0);
```

### <a name="parameters"></a>매개 변수

*nType*<br/>
메시지 상자의 스타일을 지정합니다. 어떤 조합도 적용할 합니다 [메시지 상자 스타일](styles-used-by-mfc.md#message-box-styles) 상자로 합니다. 이 매개 변수를 지정 하지 않으면 기본값은 MB_OK 합니다.

*nMessageID*<br/>
예외 개체에 오류 메시지가 없는 경우 표시할 메시지를의 리소스 ID (문자열 테이블 항목)을 지정 합니다. 0 인 경우, 메시지 "오류 메시지 없이 사용할 수 있는"가 표시 됩니다.

### <a name="return-value"></a>반환 값

`AfxMessageBox` 값; 메시지 상자를 표시 하려면 충분 한 메모리가 없을 경우 그렇지 않으면 0입니다. 참조 [AfxMessageBox](cstring-formatting-and-message-box-display.md#afxmessagebox) 가능한 반환 값에 대 한 합니다.

### <a name="example"></a>예제

사용의 예로 `CException::ReportError`합니다. 다른 예를 들어에 대 한 예제를 참조 하세요 [CATCH](exception-processing.md#catch)합니다.

```cpp
CFile fileInput;
CFileException ex;

// try to open a file for reading.
// The file will certainly not
// exist because there are too many explicit
// directories in the name.

// if the call to Open() fails, ex will be
// initialized with exception
// information.  the call to ex.ReportError() will
// display an appropriate
// error message to the user, such as
// "\Too\Many\Bad\Dirs.DAT contains an
// invalid path."  The error message text will be
// appropriate for the
// file name and error condition.

if (!fileInput.Open(_T("\\Too\\Many\\Bad\\Dirs.DAT"), CFile::modeRead, &ex))
{
  ex.ReportError();
}
else
{
  // the file was opened, so do whatever work
  // with fileInput we were planning...

  fileInput.Close();
}
```

## <a name="see-also"></a>참고자료

[CObject 클래스](cobject-class.md)<br/>
[계층 구조 차트](../hierarchy-chart.md)<br/>
[예외 처리](exception-processing.md)<br/>
[어떻게 할까요 나만의 사용자 지정 예외 클래스 만들기](http://go.microsoft.com/fwlink/p/?linkid=128045)
