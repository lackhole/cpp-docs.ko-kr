---
title: CArchive 클래스
ms.date: 11/04/2016
f1_keywords:
- CArchive
- AFX/CArchive
- AFX/CArchive::CArchive
- AFX/CArchive::Abort
- AFX/CArchive::Close
- AFX/CArchive::Flush
- AFX/CArchive::GetFile
- AFX/CArchive::GetObjectSchema
- AFX/CArchive::IsBufferEmpty
- AFX/CArchive::IsLoading
- AFX/CArchive::IsStoring
- AFX/CArchive::MapObject
- AFX/CArchive::Read
- AFX/CArchive::ReadClass
- AFX/CArchive::ReadObject
- AFX/CArchive::ReadString
- AFX/CArchive::SerializeClass
- AFX/CArchive::SetLoadParams
- AFX/CArchive::SetObjectSchema
- AFX/CArchive::SetStoreParams
- AFX/CArchive::Write
- AFX/CArchive::WriteClass
- AFX/CArchive::WriteObject
- AFX/CArchive::WriteString
- AFX/CArchive::m_pDocument
helpviewer_keywords:
- CArchive [MFC], CArchive
- CArchive [MFC], Abort
- CArchive [MFC], Close
- CArchive [MFC], Flush
- CArchive [MFC], GetFile
- CArchive [MFC], GetObjectSchema
- CArchive [MFC], IsBufferEmpty
- CArchive [MFC], IsLoading
- CArchive [MFC], IsStoring
- CArchive [MFC], MapObject
- CArchive [MFC], Read
- CArchive [MFC], ReadClass
- CArchive [MFC], ReadObject
- CArchive [MFC], ReadString
- CArchive [MFC], SerializeClass
- CArchive [MFC], SetLoadParams
- CArchive [MFC], SetObjectSchema
- CArchive [MFC], SetStoreParams
- CArchive [MFC], Write
- CArchive [MFC], WriteClass
- CArchive [MFC], WriteObject
- CArchive [MFC], WriteString
- CArchive [MFC], m_pDocument
ms.assetid: 9e950d23-b874-456e-ae4b-fe00781a7699
ms.openlocfilehash: 8f169964c6a313f37b5ea50a5105af29af7b59b1
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62391324"
---
# <a name="carchive-class"></a>CArchive 클래스

개체의 복잡 한 네트워크를 해당 개체를 삭제 한 후 유지 되는 영구 이진 형식 (일반적으로 디스크 저장소)에 저장할 수 있습니다.

## <a name="syntax"></a>구문

```
class CArchive
```

## <a name="members"></a>멤버

### <a name="public-constructors"></a>Public 생성자

|이름|설명|
|----------|-----------------|
|[CArchive::CArchive](#carchive)|`CArchive` 개체를 만듭니다.|

### <a name="public-methods"></a>Public 메서드

|이름|설명|
|----------|-----------------|
|[CArchive::Abort](#abort)|예외를 throw 하지 않고 보관 파일을 닫습니다.|
|[CArchive::Close](#close)|기록 되지 않은 데이터를 플러시하고에서 연결을 끊습니다는 `CFile`합니다.|
|[CArchive::Flush](#flush)|보관 버퍼에서 기록 되지 않은 데이터를 플러시합니다.|
|[CArchive::GetFile](#getfile)|가져옵니다는 `CFile` 이 보관 파일에 대 한 개체 포인터입니다.|
|[CArchive::GetObjectSchema](#getobjectschema)|호출 된 `Serialize` deserialize 되는 개체의 버전을 확인 하는 함수입니다.|
|[CArchive::IsBufferEmpty](#isbufferempty)|Windows 소켓 중 버퍼가 비어 있는지 여부를 결정 프로세스를 수신 합니다.|
|[CArchive::IsLoading](#isloading)|보관 파일을 로드 하는 여부를 결정 합니다.|
|[CArchive::IsStoring](#isstoring)|보관 파일에 저장 되어 있는지 여부를 결정 합니다.|
|[CArchive::MapObject](#mapobject)|맵의 파일에 serialize 되지 않습니다 하지만 하위 개체 참조에 사용할 수 있는 개체를 배치 합니다.|
|[CArchive::Read](#read)|원시 바이트를 읽습니다.|
|[CArchive::ReadClass](#readclass)|클래스 참조를 사용 하 여 이전에 저장 하는 읽기 `WriteClass`합니다.|
|[CArchive::ReadObject](#readobject)|개체의 호출 `Serialize` 로드를 위한 함수입니다.|
|[CArchive::ReadString](#readstring)|단일 텍스트 줄을 읽습니다.|
|[CArchive::SerializeClass](#serializeclass)|에 대 한 클래스 참조를 씁니다 합니다 `CArchive` 방향에 따라 개체를 `CArchive`입니다.|
|[CArchive::SetLoadParams](#setloadparams)|부하 배열 증가 함에 따라 크기를 설정 합니다. 모든 개체를 로드 하기 전에 또는 하기 전에 호출 해야 합니다 `MapObject` 또는 `ReadObject` 라고 합니다.|
|[CArchive::SetObjectSchema](#setobjectschema)|보관 개체에 저장 된 개체 스키마를 설정 합니다.|
|[CArchive::SetStoreParams](#setstoreparams)|Serialization 프로세스 중에 고유한 개체를 식별 하는 데 map의 블록 크기 및 해시 테이블 크기를 설정 합니다.|
|[CArchive::Write](#write)|원시 바이트를 씁니다.|
|[CArchive::WriteClass](#writeclass)|에 대 한 참조를 기록 합니다 `CRuntimeClass` 에 `CArchive`.|
|[CArchive::WriteObject](#writeobject)|개체의 호출 `Serialize` 저장 하기 위한 함수입니다.|
|[CArchive::WriteString](#writestring)|단일 텍스트 줄을 씁니다.|

### <a name="public-operators"></a>Public 연산자

|이름|설명|
|----------|-----------------|
|[CArchive::operator &lt;&lt;](#operator_lt_lt)|개체 및 보관 파일에 기본 형식 저장합니다.|
|[CArchive::operator &gt;&gt;](#operator_gt_gt)|보관 파일에서 기본 형식과 개체를 로드합니다.|

### <a name="public-data-members"></a>공용 데이터 멤버

|이름|설명|
|----------|-----------------|
|[CArchive::m_pDocument](#m_pdocument)||

## <a name="remarks"></a>설명

`CArchive` 기본 클래스는 없습니다.

나중에 로드할 수 있습니다 개체 영구 저장소에서 메모리에 재구성을 합니다. 이 프로세스 데이터를 영구 "serialization" 라고 합니다.

일종의 이진 스트림으로 보관 개체를 생각할 수 있습니다. 입력/출력 스트림에 같은 저장소에서 데이터를 읽기 및 버퍼링 된 쓰기를 허용 및 보관 파일을 사용 하 여 연결 됩니다. 입/출력 스트림 ASCII 문자의 시퀀스를 처리 하지만 보관 효율적이 고 중복 되지 않은 형식으로 이진 개체 데이터를 처리 합니다.

만들어야 합니다는 [CFile](../../mfc/reference/cfile-class.md) 개체를 만들기 전에 `CArchive` 개체입니다. 또한 보관 파일의 로드/저장 상태 파일의 열기 모드와 호환 되는지 확인 해야 합니다. 파일당 하나의 활성 archive로 제한 됩니다.

생성 하는 경우는 `CArchive` 개체 클래스의 개체에 연결할 `CFile` (또는 파생된 클래스)는 열려 있는 파일을 나타내는입니다. 또한 로드 하거나 저장 하기 위해 보관을 사용할지 여부를 지정 합니다. A `CArchive` 기본 형식 뿐만 아니라 개체의 개체를 처리할 수 있습니다 [CObject](../../mfc/reference/cobject-class.md)-serialization을 위한 클래스를 파생 합니다. Serializable 클래스는 일반적으로를 `Serialize` 멤버 함수의 경우 일반적으로 사용 합니다 [DECLARE_SERIAL](../../mfc/reference/run-time-object-model-services.md#declare_serial) 및 [IMPLEMENT_SERIAL](../../mfc/reference/run-time-object-model-services.md#implement_serial) 매크로 클래스 아래에 설명 된 대로 `CObject`.

오버 로드 된 추출 ( **>>**) 및 삽입 ( **<<**) 연산자는 모두 기본 형식을 지 원하는 프로그래밍 인터페이스를 편리 하 게 보관 하 고 `CObject` -클래스를 파생 합니다.

`CArchive` 또한 MFC Windows 소켓 클래스를 사용 하 여 프로그래밍을 지원 [CSocket](../../mfc/reference/csocket-class.md) 하 고 [CSocketFile](../../mfc/reference/csocketfile-class.md)합니다. 합니다 [IsBufferEmpty](#isbufferempty) 멤버 함수는 해당 사용을 지원 합니다.

에 대 한 자세한 `CArchive`, 문서를 참조 하세요 [Serialization](../../mfc/serialization-in-mfc.md) 고 [Windows 소켓: 보관 파일을 사용 하 여 소켓을 사용 하 여](../../mfc/windows-sockets-using-sockets-with-archives.md)입니다.

## <a name="inheritance-hierarchy"></a>상속 계층 구조

`CArchive`

## <a name="requirements"></a>요구 사항

**헤더:** afx.h

##  <a name="abort"></a>  CArchive::Abort

예외를 throw 하지 않고 보관 파일을 닫으려면이 함수를 호출 합니다.

```
void Abort ();
```

### <a name="remarks"></a>설명

`CArchive` 소멸자를 호출할 일은 좀처럼 `Close`에 저장 되지 않은 모든 데이터를 플러시하는 연결 된 `CFile` 개체. 이 예외가 발생할 수 있습니다.

이러한 예외를 catch 할 때 사용 하는 것이 좋습니다 `Abort`destructing 되도록는 `CArchive` 개체 추가 예외가 발생 하지 않습니다. 예외를 처리 하는 경우 `CArchive::Abort` 때문에 오류에 예외를 throw 하지는 달리 [CArchive::Close](#close), `Abort` 오류를 무시 합니다.

사용 하는 경우 **새** 할당할는 `CArchive` 힙에 개체 파일을 닫은 후 삭제 해야 합니다.

### <a name="example"></a>예제

  예를 참조 하세요 [CArchive::WriteClass](#writeclass)합니다.

##  <a name="carchive"></a>  CArchive::CArchive

생성 된 `CArchive` 개체 및 로드 하거나 개체를 저장 하기 위해 사용할가 있는지 여부를 지정 합니다.

```
CArchive(
    CFile* pFile,
    UINT nMode,
    int nBufSize = 4096,
    void* lpBuf = NULL);
```

### <a name="parameters"></a>매개 변수

*pFile*<br/>
에 대 한 포인터를 `CFile` 개체 ultimate 소스 또는 영구 데이터의 대상입니다.

*nMode*<br/>
개체에서 로드 되거나 보관 파일에 저장 될 지 여부를 지정 하는 플래그입니다. 합니다 *nMode* 매개 변수는 다음 값 중 하나가 있어야 합니다.

- `CArchive::load` 보관 파일에서 데이터를 로드합니다. 하기만 `CFile` 읽기 권한.

- `CArchive::store` 보관 파일에 데이터를 저장합니다. 필요한 `CFile` 쓰기 권한.

- `CArchive::bNoFlushOnDelete` 보관 파일을 자동으로 호출 하는 것을 금지 `Flush` 보관 소멸자가 호출 하는 경우. 이 플래그를 설정한 경우 사용자는 명시적으로 호출 하는 일을 담당 `Close` 소멸자를 호출 하기 전에 합니다. 그렇지 않으면 데이터가 손상 됩니다.

*nBufSize*<br/>
내부 파일 버퍼의 크기를 바이트 단위로 지정 하는 정수입니다. 참고는 기본 버퍼 크기는 4,096 바이트입니다. 큰 개체를 정기적으로 보관 하는 경우 파일 버퍼 크기의 배수인 더 큰 버퍼 크기를 사용 하는 경우 성능이 향상 됩니다.

*lpBuf*<br/>
사용자가 제공한 버퍼 크기에 대 한 선택적 포인터 *nBufSize*합니다. 이 매개 변수를 지정 하지 않으면 하는 경우 보관 로컬 힙에서 버퍼를 할당 및 개체 소멸 될 때 해제 합니다. 보관 파일에서 사용자가 제공한 버퍼를 해제 하지 않습니다.

### <a name="remarks"></a>설명

보관 파일을 만든 후에이 사양은 변경할 수 없습니다.

사용할 수 없습니다 `CFile` 작업 상태를 변경할 파일의 보관 파일을 닫아야만 합니다. 이러한 작업은 보관 파일의 무결성을 손상 됩니다. 보관 파일의 파일 개체를 확보 하 여 파일 포인터의 위치를 직렬화 하는 동안 언제 든 액세스할 수 있습니다 합니다 [GetFile](#getfile) 멤버 함수 및 사용 하는 [CFile::GetPosition](../../mfc/reference/cfile-class.md#getposition) 함수 . 호출 해야 [CArchive::Flush](#flush) 파일 포인터의 위치를 가져오기 전에 합니다.

### <a name="example"></a>예제

[!code-cpp[NVC_MFCSerialization#12](../../mfc/codesnippet/cpp/carchive-class_1.cpp)]

##  <a name="close"></a>  CArchive::Close

버퍼에 남아 있는 데이터를 플러시하고 닫습니다, 보관 저장소 보관 파일에서 연결을 끊습니다.

```
void Close();
```

### <a name="remarks"></a>설명

보관 파일에 추가 작업이 없습니다 허용 됩니다. 아카이브를 닫은 후에 동일한 파일에 대 한 다른 보관을 만들 수 있습니다 또는 파일을 닫을 수 있습니다.

멤버 함수 `Close` 하면 모든 데이터가 보관 파일에서 파일을 전송 하는 보관 파일을 사용할 수 없습니다. 저장소 미디어에 파일을 전송할지를 완료 하려면 먼저 사용 해야 [CFile::Close](../../mfc/reference/cfile-class.md#close) 및 다음 제거를 `CFile` 개체입니다.

### <a name="example"></a>예제

  예를 참조 하세요 [CArchive::WriteString](#writestring)합니다.

##  <a name="flush"></a>  CArchive::Flush

파일을 쓸 수 있도록 보관 버퍼에 남아 있는 데이터를 강제로 수행 합니다.

```
void Flush();
```

### <a name="remarks"></a>설명

멤버 함수 `Flush` 파일로 보관 파일에서 모든 데이터를 전송 하면 됩니다. 호출 해야 합니다 [CFile::Close](../../mfc/reference/cfile-class.md#close) 저장소 매체에서 파일 전송이 완료 합니다.

### <a name="example"></a>예제

[!code-cpp[NVC_MFCSerialization#13](../../mfc/codesnippet/cpp/carchive-class_2.cpp)]

##  <a name="getfile"></a>  CArchive::GetFile

가져옵니다는 `CFile` 이 보관 파일에 대 한 개체 포인터입니다.

```
CFile* GetFile() const;
```

### <a name="return-value"></a>반환 값

에 대 한 상수 포인터는 `CFile` 사용 중인 개체입니다.

### <a name="remarks"></a>설명

보관 파일을 사용 하기 전에 플러시해야 `GetFile`합니다.

### <a name="example"></a>예제

[!code-cpp[NVC_MFCSerialization#14](../../mfc/codesnippet/cpp/carchive-class_3.cpp)]

##  <a name="getobjectschema"></a>  CArchive::GetObjectSchema

이 함수를 호출 합니다 `Serialize` 현재 deserialize 되는 개체의 버전을 확인 하는 함수입니다.

```
UINT GetObjectSchema();
```

### <a name="return-value"></a>반환 값

Deserialization을 읽고 개체의 버전 중

### <a name="remarks"></a>설명

이 함수를 호출할 때만 유효한 합니다 `CArchive` 개체를 로드 하는 ( [CArchive::IsLoading](#isloading) 0이 아닌 값을 반환 합니다). 첫 번째 호출 해야 합니다 `Serialize` 함수 및 한 번만 호출된 합니다. 반환 값-1 (단위)의 버전 번호를 알려진 아님을 나타냅니다.

A `CObject`-파생된 클래스 VERSIONABLE_SCHEMA 결합을 사용할 수 있습니다 (비트를 사용 하 여 **또는**) (IMPLEMENT_SERIAL 매크로)의 스키마 버전이 자체를 사용 하 여 개체를 만들려면 "버전 관리가 가능한," 개체 즉, 해당 `Serialize` 멤버 함수는 여러 버전을 읽을 수 있습니다. VERSIONABLE_SCHEMA) (없이 기본 프레임 워크 기능 버전이 일치 하지 않는 경우 예외를 throw 하는 것입니다.

### <a name="example"></a>예제

[!code-cpp[NVC_MFCSerialization#15](../../mfc/codesnippet/cpp/carchive-class_4.cpp)]

##  <a name="isbufferempty"></a>  CArchive::IsBufferEmpty

보관 개체의 내부 버퍼가 비어 있는지 여부를 결정 하는이 멤버 함수를 호출 합니다.

```
BOOL IsBufferEmpty() const;
```

### <a name="return-value"></a>반환 값

보관 파일의 버퍼가 비어 있으면 0이 아닌 값 그렇지 않으면 0입니다.

### <a name="remarks"></a>설명

이 함수는 MFC Windows 소켓 클래스를 사용 하 여 프로그래밍 지원 제공 `CSocketFile`합니다. 연결 된 보관 파일에 사용할 필요가 없습니다를 `CFile` 개체입니다.

사용 하는 이유 `IsBufferEmpty` 와 연결 된 보관 파일을 사용 하 여를 `CSocketFile` 개체는 둘 이상의 메시지 또는 레코드 보관 파일의 버퍼 포함 될 수 있습니다. 하나의 메시지를 받은 후 사용할지 `IsBufferEmpty` 버퍼가 비어 될 때까지 데이터 수신을 계속 하는 루프를 제어 합니다. 자세한 내용은 참조 하세요. 합니다 [수신](../../mfc/reference/casyncsocket-class.md#receive) 클래스의 멤버 함수 `CAsyncSocket`를 사용 하는 방법을 보여 주는 `IsBufferEmpty`합니다.

자세한 내용은 참조 하세요. [Windows 소켓: 보관 파일을 사용 하 여 소켓을 사용 하 여](../../mfc/windows-sockets-using-sockets-with-archives.md)입니다.

##  <a name="isloading"></a>  CArchive::IsLoading

보관 된 데이터를 로드 하 고 있는지 여부를 결정 합니다.

```
BOOL IsLoading() const;
```

### <a name="return-value"></a>반환 값

보관 파일을 로드;에 대 한 현재 사용 중인 경우 0이 아닌 값 그렇지 않으면 0입니다.

### <a name="remarks"></a>설명

이 구성원 함수가 호출 되는 `Serialize` 보관 된 클래스의 함수입니다.

### <a name="example"></a>예제

[!code-cpp[NVC_MFCSerialization#16](../../mfc/codesnippet/cpp/carchive-class_5.cpp)]

##  <a name="isstoring"></a>  CArchive::IsStoring

보관 파일에서 데이터를 저장 하는지 여부를 결정 합니다.

```
BOOL IsStoring() const;
```

### <a name="return-value"></a>반환 값

보관 파일을 저장 합니다; 현재 사용 중인 경우 0이 아닌 값 그렇지 않으면 0입니다.

### <a name="remarks"></a>설명

이 구성원 함수가 호출 되는 `Serialize` 보관 된 클래스의 함수입니다.

경우는 `IsStoring` 보관 파일의 상태는 0이 아닌 경우 다음 해당 `IsLoading` status = 0, 또는 그 반대로 합니다.

### <a name="example"></a>예제

[!code-cpp[NVC_MFCSerialization#17](../../mfc/codesnippet/cpp/carchive-class_6.cpp)]

##  <a name="mapobject"></a>  CArchive::MapObject

맵의 파일을 실제로 serialize 되지 않습니다 하지만 하위 개체 참조에 사용할 수 있는 개체를 배치 하려면이 멤버 함수를 호출 합니다.

```
void MapObject(const CObject* pOb);
```

### <a name="parameters"></a>매개 변수

*pOb*<br/>
저장 되는 개체에 대 한 상수 포인터입니다.

### <a name="remarks"></a>설명

예를 들어 문서를 serialize 하지 않을 수 있습니다 하지만 문서의 일부 포함 된 항목을 serialize 하는 것입니다. 호출 하 여 `MapObject`, 해당 항목 또는 하위 개체, 문서를 참조할 수 있습니다. Serialize 된 하위 항목을 serialize 할 수 또한 자신의 *m_pDocument* 후방 포인터입니다.

호출할 수 있습니다 `MapObject` 에 저장 하 고 로드를 `CArchive` 개체입니다. `MapObject` 지정한 개체에서 유지 관리 하는 내부 데이터 구조를 추가 합니다 `CArchive` 개체 serialization 및 deserialization 중에 있지만 달리 [ReadObject](#readobject) 및 [WriteObject](#writeobject)를 호출 하지 않습니다 개체에 serialize 합니다.

### <a name="example"></a>예제

[!code-cpp[NVC_MFCSerialization#18](../../mfc/codesnippet/cpp/carchive-class_7.h)]

[!code-cpp[NVC_MFCSerialization#19](../../mfc/codesnippet/cpp/carchive-class_8.cpp)]

[!code-cpp[NVC_MFCSerialization#20](../../mfc/codesnippet/cpp/carchive-class_9.h)]

[!code-cpp[NVC_MFCSerialization#21](../../mfc/codesnippet/cpp/carchive-class_10.cpp)]

##  <a name="m_pdocument"></a>  CArchive::m_pDocument

기본적으로이 포인터를 NULL로 설정를 `CDocument` 의 사용자 값으로 설정 된 `CArchive` 가 인스턴스.

```
CDocument* m_pDocument;
```

### <a name="remarks"></a>설명

이 포인터를 사용 하는 일반적인 serialize 되는 모든 개체에는 serialization 프로세스에 대 한 추가 정보를 전달 하는 것입니다. 문서를 사용 하 여 포인터를 초기화 하 여 수행 됩니다 (한 `CDocument`-파생 클래스)는 serialize 되 고, 필요한 경우 문서 내에서 개체를 문서에 액세스할 수 있도록 하는 방식에서. 이 포인터는 에서도 `COleClientItem` serialization 동안에 개체입니다.

프레임 워크 집합 *m_pDocument* 사용자 파일을 실행 하면 serialize 되 고 문서를 열거나 저장 명령입니다. 파일 열기 또는 저장 아닌 다른 이유로 개체 연결 및 OLE 컨테이너 문서를 serialize 하는 경우 명시적으로 설정 해야 *m_pDocument*합니다. 예를 들어, 이렇게 하려면 컨테이너 문서를 클립보드에 직렬화 할 때입니다.

### <a name="example"></a>예제

[!code-cpp[NVC_MFCSerialization#35](../../mfc/codesnippet/cpp/carchive-class_11.cpp)]

##  <a name="operator_lt_lt"></a>  CArchive::operator &lt;&lt;

지정 된 개체 또는 형식 보관 파일에 저장합니다.

```
friend CArchive& operator<<(
    CArchive& ar,
    const CObject* pOb);

throw(
    CArchiveException*,
    CFileException*);

CArchive& AFXAPI operator<<(
    CArchive& ar,
    const RECT& rect);

CArchive& AFXAPI operator<<(
    CArchive& ar,
    POINT point);

CArchive& AFXAPI operator<<(
    CArchive& ar,
    SIZE size);

template<typename BaseType,
    class StringTraits> CArchive& operator<<(
    const ATL::CStringT<BaseType,
    StringTraits>& str);

CArchive& operator<<(BYTE by);
CArchive& operator<<(WORD w);
CArchive& operator<<(LONG l);
CArchive& operator<<(DWORD dw);
CArchive& operator<<(float f);
CArchive& operator<<(double d);
CArchive& operator<<(int i);
CArchive& operator<<(short w);
CArchive& operator<<(char ch);
CArchive& operator<<(wchar_t ch);
CArchive& operator<<(unsigned u);
CArchive& operator<<(bool b);
CArchive& operator<<(ULONGLONG dwdw);
CArchive& operator<<(LONGLONG dwdw);
```

### <a name="return-value"></a>반환 값

`CArchive` 한 줄에 여러 삽입 연산자를 사용 하도록 설정 하는 참조 합니다.

### <a name="remarks"></a>설명

위의 마지막 두 버전은 64 비트 정수를 저장 하기 위해.

IMPLEMENT_SERIAL 매크로 클래스 구현에서 사용한 경우에 대 한 삽입 연산자를 오버 로드할 `CObject` 보호 된 호출 `WriteObject`합니다. 이 함수를 호출 하 여 `Serialize` 클래스의 함수입니다.

합니다 [CStringT](../../atl-mfc-shared/reference/cstringt-class.md) 삽입 연산자 (<<) 진단 덤프 및 보관에 저장을 지원 합니다.

### <a name="example"></a>예제

이 예제에서는 사용 합니다 `CArchive` 삽입 연산자 << 사용 하 여는 **int** 및 **긴** 형식.

[!code-cpp[NVC_MFCSerialization#31](../../mfc/codesnippet/cpp/carchive-class_12.cpp)]

### <a name="example"></a>예제

이 예제에서는 2의 사용을 보여 줍니다.는 `CArchive` 삽입 연산자 <<와 `CStringT` 형식입니다.

[!code-cpp[NVC_MFCSerialization#32](../../mfc/codesnippet/cpp/carchive-class_13.cpp)]

##  <a name="operator_gt_gt"></a>  CArchive::operator &gt;&gt;

보관 파일에서 지정 된 개체 또는 기본 형식을 로드합니다.

```
friend CArchive& operator>>(
    CArchive& ar,
    CObject *& pOb);

throw(
    CArchiveException*,
    CFileException*,
    CMemoryException*);

friend CArchive& operator>>(
    CArchive& ar,
    const CObject *& pOb);

throw(
    CArchiveException*,
    CFileException*,
    CMemoryException*);

CArchive& AFXAPI operator>>(
    CArchive& ar,
    const RECT& rect);

CArchive& AFXAPI operator>>(
    CArchive& ar,
    POINT point);

CArchive& AFXAPI operator>>(
    CArchive& ar,
    SIZE size);

template<typename BaseType,
    class StringTraits> CArchive& operator>>(
    ATL::CStringT<BaseType,
    StringTraits>& str);

CArchive& operator>>(BYTE& by);
CArchive& operator>>(WORD& w);
CArchive& operator>>(int& i);
CArchive& operator>>(LONG& l);
CArchive& operator>>(DWORD& dw);
CArchive& operator>>(float& f);
CArchive& operator>>(double& d);
CArchive& operator>>(short& w);
CArchive& operator>>(char& ch);
CArchive& operator>>(wchar_t& ch);
CArchive& operator>>(unsigned& u);
CArchive& operator>>(bool& b);
CArchive& operator>>(ULONGLONG& dwdw);
CArchive& operator>>(LONGLONG& dwdw);
```

### <a name="return-value"></a>반환 값

`CArchive` 한 줄에 여러 추출 연산자를 사용 하도록 설정 하는 참조 합니다.

### <a name="remarks"></a>설명

위의 마지막 두 버전을 64 비트 정수의 로드에 해당 됩니다.

IMPLEMENT_SERIAL 매크로 클래스 구현에서 사용한 경우에 대 한 추출 연산자를 오버 로드 `CObject` 보호 된 호출 `ReadObject` 함수 (0이 아닌 런타임 클래스 포인터로). 이 함수를 호출 하 여 `Serialize` 클래스의 함수입니다.

합니다 [CStringT](../../atl-mfc-shared/reference/cstringt-class.md) 추출 연산자 (>>) 보관 파일에서 로드 하도록 지원 합니다.

### <a name="example"></a>예제

이 예제에서는 사용 합니다 `CArchive` 추출 연산자 >> 사용 하 여는 **int** 형식.

[!code-cpp[NVC_MFCSerialization#33](../../mfc/codesnippet/cpp/carchive-class_14.cpp)]

### <a name="example"></a>예제

이 예제에서는 사용 합니다 `CArchive` 삽입 및 추출 연산자 <\< 및 >> 사용 하 여는 `CStringT` 형식.

[!code-cpp[NVC_MFCSerialization#34](../../mfc/codesnippet/cpp/carchive-class_15.cpp)]

##  <a name="read"></a>  CArchive::Read

보관 파일에서 지정 된 바이트 수를 읽습니다.

```
UINT Read(void* lpBuf, UINT nMax);
```

### <a name="parameters"></a>매개 변수

*lpBuf*<br/>
보관 파일에서 읽은 데이터를 수신 하는 사용자가 제공한 버퍼에 대 한 포인터입니다.

*nMax*<br/>
부호 없는 정수로 바이트 수가 지정 보관 파일에서 읽을 수 있습니다.

### <a name="return-value"></a>반환 값

실제로 읽은 바이트 수를 포함 하는 부호 없는 정수입니다. 반환 값은 요청 된 수보다 적은 경우 파일의 끝에 도달 했습니다. 파일 끝 조건에서 예외가 throw 됩니다.

### <a name="remarks"></a>설명

보관 파일에 바이트를 해석 하지는 않습니다.

사용할 수는 `Read` 내에서 멤버 함수에 `Serialize` 개체에 포함 된 일반 구조를 읽기 위한 함수입니다.

### <a name="example"></a>예제

[!code-cpp[NVC_MFCSerialization#24](../../mfc/codesnippet/cpp/carchive-class_16.cpp)]

##  <a name="readclass"></a>  CArchive::ReadClass

이 멤버 함수를 사용 하 여 이전에 저장 된 클래스에 대 한 참조를 읽을 호출 [WriteClass](#writeclass)합니다.

```
CRuntimeClass* ReadClass(
    const CRuntimeClass* pClassRefRequested = NULL,
    UINT* pSchema = NULL,
    DWORD* pObTag = NULL);
```

### <a name="parameters"></a>매개 변수

*pClassRefRequested*<br/>
에 대 한 포인터를 [CRuntimeClass](../../mfc/reference/cruntimeclass-structure.md) 요청 클래스 참조에 해당 합니다. NULL 일 수 있습니다.

*pSchema*<br/>
이전에 저장 되는 런타임 클래스의 스키마에 대 한 포인터입니다.

*pObTag*<br/>
개체의 고유 태그를 나타내는 숫자입니다. 구현에 의해 내부적으로 사용 [ReadObject](#readobject)합니다. 고급 프로그래밍만;에 대 한 노출 *pObTag* 일반적으로 NULL 이어야 합니다.

### <a name="return-value"></a>반환 값

에 대 한 포인터를 [CRuntimeClass](../../mfc/reference/cruntimeclass-structure.md) 구조입니다.

### <a name="remarks"></a>설명

하는 경우 *pClassRefRequested* NULL이 아니면 `ReadClass` 보관된 클래스 정보를 런타임 클래스와 호환 되는지 확인 합니다. 호환 되지 않았으면 `ReadClass` 시킵니다를 [CArchiveException](../../mfc/reference/carchiveexception-class.md)합니다.

런타임 클래스를 사용 해야 합니다 [DECLARE_SERIAL](../../mfc/reference/run-time-object-model-services.md#declare_serial) 하 고 [IMPLEMENT_SERIAL](../../mfc/reference/run-time-object-model-services.md#implement_serial)고, 그렇지 않으면 `ReadClass` 시킵니다를 [CNotSupportedException](../../mfc/reference/cnotsupportedexception-class.md)합니다.

하는 경우 *pSchema* 가 null 인 경우 저장된 클래스의 스키마를 호출 하 여 검색할 수 있습니다 [CArchive::GetObjectSchema](#getobjectschema)이 고, 그렇지 않으면 <strong>\*</strong>  *pSchema* 이전에 저장 된 런타임 클래스의 스키마에 포함 됩니다.

사용할 수 있습니다 [SerializeClass](#serializeclass) 대신 `ReadClass`, 읽기 및 쓰기 클래스 참조를 모두 처리 합니다.

### <a name="example"></a>예제

  예를 참조 하세요 [CArchive::WriteClass](#writeclass)합니다.

##  <a name="readobject"></a>  CArchive::ReadObject

보관 파일에서 개체 데이터를 읽고 적절 한 형식의 개체를 생성 합니다.

```
CObject* ReadObject(const CRuntimeClass* pClass);
```

### <a name="parameters"></a>매개 변수

*pClass*<br/>
에 대 한 상수 포인터를 [CRuntimeClass](../../mfc/reference/cruntimeclass-structure.md) 읽기 하려는 개체에 해당 합니다.

### <a name="return-value"></a>반환 값

A [CObject](../../mfc/reference/cobject-class.md) 올바른 안전 하 게 캐스팅 해야 하는 포인터를 사용 하 여 클래스를 파생 [CObject::IsKindOf](../../mfc/reference/cobject-class.md#iskindof)합니다.

### <a name="remarks"></a>설명

이 함수는 일반적으로 호출한 합니다 `CArchive` 추출 ( **>>**) 연산자에 대해 오버 로드를 [CObject](../../mfc/reference/cobject-class.md) 포인터입니다. `ReadObject`를 호출 하는 `Serialize` 보관 된 클래스의 함수입니다.

0이 아닌 제공 하는 경우 *pClass* 으로 얻을 수 있는 매개 변수를 [RUNTIME_CLASS](../../mfc/reference/run-time-object-model-services.md#runtime_class) 매크로 이면 함수는 보관 된 개체의 런타임 클래스를 확인 합니다. 이 클래스의 구현에서 IMPLEMENT_SERIAL 매크로 사용한 가정 합니다.

### <a name="example"></a>예제

  예를 참조 하세요 [CArchive::WriteObject](#writeobject)합니다.

##  <a name="readstring"></a>  CArchive::ReadString

텍스트 데이터와 연결 된 파일에서 버퍼로 읽어들여를이 멤버 함수를 호출 합니다 `CArchive` 개체입니다.

```
BOOL ReadString(CString& rString);
LPTSTR ReadString(LPTSTR lpsz, UINT nMax);
```

### <a name="parameters"></a>매개 변수

*rString*<br/>
에 대 한 참조를 [CString](../../atl-mfc-shared/reference/cstringt-class.md) 는 CArchive 개체에 연결 된 파일에서 읽은 후 결과 문자열을 포함 하는 합니다.

*lpsz*<br/>
Null로 끝나는 문자열을 받는 사용자가 제공한 버퍼에 대 한 포인터를 지정 합니다.

*nMax*<br/>
읽을 문자의 최대 수를 지정 합니다. 하나 여야 합니다의 크기 보다 작아야 합니다 *lpsz* 버퍼입니다.

### <a name="return-value"></a>반환 값

BOOL, 성공 하면 TRUE를 반환 하는 버전 FALSE이 고, 그렇지 합니다.

반환 하는 버전에는 `LPTSTR`, 텍스트 데이터를 포함 하는 버퍼에 대 한 포인터 파일의 끝에 도달한 경우 NULL입니다.

### <a name="remarks"></a>설명

멤버 함수의 버전은 *최대* 매개 변수 버퍼 보유할의 제한 *최대* -1 문자입니다. 읽기는 캐리지 리턴-줄 바꿈 쌍으로 중지 됩니다. 후행 줄 바꿈 문자가 항상 제거 됩니다. Null 문자 ('\0')는 두 경우 모두 추가 됩니다.

[CArchive::Read](#read) 캐리지 리턴-줄 바꿈 쌍에 텍스트 모드 입력 하지만 종료 하지 않는 한 사용할 수도 있습니다.

### <a name="example"></a>예제

  예를 참조 하세요 [CArchive::WriteString](#writestring)합니다.

##  <a name="serializeclass"></a>  CArchive::SerializeClass

저장 하 고 기본 클래스의 버전 정보를 로드 하려는 경우이 멤버 함수를 호출 합니다.

```
void SerializeClass(const CRuntimeClass* pClassRef);
```

### <a name="parameters"></a>매개 변수

*pClassRef*<br/>
기본 클래스에 대 한 런타임 클래스 개체에 대 한 포인터입니다.

### <a name="remarks"></a>설명

`SerializeClass` 읽거나 기록 하는 클래스에 대 한 참조를 `CArchive` 방향에 따라 개체를 `CArchive`입니다. 사용 하 여 `SerializeClass` 대신 [ReadClass](#readclass) 하 고 [WriteClass](#writeclass) 기본 클래스 개체를 serialize 하는 편리한 방법으로 `SerializeClass` 더 적은 코드 및 더 적은 매개 변수가 필요 합니다.

와 같은 `ReadClass`, `SerializeClass` 보관된 클래스 정보를 런타임 클래스와 호환 되는지 확인 합니다. 호환 되지 않았으면 `SerializeClass` 시킵니다를 [CArchiveException](../../mfc/reference/carchiveexception-class.md)합니다.

런타임 클래스를 사용 해야 합니다 [DECLARE_SERIAL](../../mfc/reference/run-time-object-model-services.md#declare_serial) 하 고 [IMPLEMENT_SERIAL](../../mfc/reference/run-time-object-model-services.md#implement_serial)고, 그렇지 않으면 `SerializeClass` 시킵니다를 [CNotSupportedException](../../mfc/reference/cnotsupportedexception-class.md)합니다.

사용 된 [RUNTIME_CLASS](../../mfc/reference/run-time-object-model-services.md#runtime_class) 매크로 대 한 값을 검색 하는 *pRuntimeClass* 매개 변수. 기본 클래스를 사용 해야 합니다 [IMPLEMENT_SERIAL](../../mfc/reference/run-time-object-model-services.md#implement_serial) 매크로입니다.

### <a name="example"></a>예제

[!code-cpp[NVC_MFCSerialization#25](../../mfc/codesnippet/cpp/carchive-class_17.h)]

##  <a name="setloadparams"></a>  CArchive::SetLoadParams

호출 `SetLoadParams` 다 수의 읽을 시기가 되 면 `CObject`-보관에서 파생 되는 개체입니다.

```
void SetLoadParams(UINT nGrowBy = 1024);
```

### <a name="parameters"></a>매개 변수

*nGrowBy*<br/>
크기 증가 필요한 경우 할당할 요소 슬롯의 최소 수입니다.

### <a name="remarks"></a>설명

`CArchive` 보관 파일에 저장 된 개체에 대 한 참조를 확인 하는 부하 배열을 사용 합니다. `SetLoadParams` 이 기능을 사용 하면 부하 배열 증가 하는 크기를 설정할 수 있습니다.

호출 해야 하면 `SetLoadParams` 개체 로드 되 면 이나 뒤 [MapObject](#mapobject) 하거나 [ReadObject](#readobject) 라고 합니다.

### <a name="example"></a>예제

[!code-cpp[NVC_MFCSerialization#26](../../mfc/codesnippet/cpp/carchive-class_18.h)]

##  <a name="setobjectschema"></a>  CArchive::SetObjectSchema

보관 개체에 저장 된 개체 스키마를 설정 하려면이 멤버 함수 호출 *nSchema*합니다.

```
void SetObjectSchema(UINT nSchema);
```

### <a name="parameters"></a>매개 변수

*nSchema*<br/>
개체의 스키마를 지정합니다.

### <a name="remarks"></a>설명

다음에 호출할 [GetObjectSchema](#getobjectschema) 에 저장 된 값을 반환 합니다 *nSchema*합니다.

사용 하 여 `SetObjectSchema` 고급 버전 관리;에 대 한 예를 들어, 하려는 경우 강제로 특정 버전을 읽을 수는 `Serialize` 파생된 클래스의 함수입니다.

### <a name="example"></a>예제

[!code-cpp[NVC_MFCSerialization#27](../../mfc/codesnippet/cpp/carchive-class_19.cpp)]

##  <a name="setstoreparams"></a>  CArchive::SetStoreParams

사용 하 여 `SetStoreParams` 다 수의 저장할 때 `CObject`-파생 개체를 보관에서 합니다.

```
void SetStoreParams(UINT nHashSize = 2053, UINT nBlockSize = 128);
```

### <a name="parameters"></a>매개 변수

*nHashSize*<br/>
인터페이스 포인터에 대 한 해시 테이블의 크기를 매핑합니다. 소수 있어야 합니다.

*nBlockSize*<br/>
매개 변수를 확장 하는 것에 대 한 메모리 할당 세분성을 지정 합니다. 최상의 성능을 위해 2의 거듭제곱 이어야 합니다.

### <a name="remarks"></a>설명

`SetStoreParams` serialization 프로세스 중에 고유한 개체를 식별 하는 데 map의 블록 크기 및 해시 테이블 크기를 설정할 수 있습니다.

호출 해야 하면 `SetStoreParams` 개체를 저장 된 후 또는 한 후 [MapObject](#mapobject) 또는 [WriteObject](#writeobject) 라고 합니다.

### <a name="example"></a>예제

[!code-cpp[NVC_MFCSerialization#26](../../mfc/codesnippet/cpp/carchive-class_18.h)]

##  <a name="write"></a>  CArchive::Write

보관 파일에 지정 된 바이트 수를 씁니다.

```
void Write(const void* lpBuf, INT nMax);
```

### <a name="parameters"></a>매개 변수

*lpBuf*<br/>
보관 파일에 쓸 데이터가 포함 된 사용자가 제공한 버퍼에 대 한 포인터입니다.

*nMax*<br/>
보관 파일에 쓸 바이트 수를 지정 하는 정수입니다.

### <a name="remarks"></a>설명

보관 파일에서 바이트를 포맷 하지 않습니다.

사용할 수는 `Write` 내에서 멤버 함수에 `Serialize` 일반적인 구조를 작성 하는 함수 개체에 포함 된 합니다.

### <a name="example"></a>예제

[!code-cpp[NVC_MFCSerialization#23](../../mfc/codesnippet/cpp/carchive-class_20.cpp)]

##  <a name="writeclass"></a>  CArchive::WriteClass

사용 하 여 `WriteClass` 파생된 클래스의 serialization 동안 기본 클래스의 버전 및 클래스 정보를 저장 합니다.

```
void WriteClass(const CRuntimeClass* pClassRef);
```

### <a name="parameters"></a>매개 변수

*pClassRef*<br/>
에 대 한 포인터를 [CRuntimeClass](../../mfc/reference/cruntimeclass-structure.md) 요청 클래스 참조에 해당 합니다.

### <a name="remarks"></a>설명

`WriteClass` 에 대 한 참조를 기록 합니다 [CRuntimeClass](../../mfc/reference/cruntimeclass-structure.md) 기본 클래스에 대 한는 `CArchive`합니다. 사용 하 여 [CArchive::ReadClass](#readclass) 대 참조를 검색 합니다.

`WriteClass` 보관 된 클래스 정보를 런타임 클래스와 호환 되는지 확인 합니다. 호환 되지 않았으면 `WriteClass` 시킵니다를 [CArchiveException](../../mfc/reference/carchiveexception-class.md)합니다.

런타임 클래스를 사용 해야 합니다 [DECLARE_SERIAL](../../mfc/reference/run-time-object-model-services.md#declare_serial) 하 고 [IMPLEMENT_SERIAL](../../mfc/reference/run-time-object-model-services.md#implement_serial)고, 그렇지 않으면 `WriteClass` 시킵니다를 [CNotSupportedException](../../mfc/reference/cnotsupportedexception-class.md)합니다.

사용할 수 있습니다 [SerializeClass](#serializeclass) 대신 `WriteClass`, 읽기 및 쓰기 클래스 참조를 모두 처리 합니다.

### <a name="example"></a>예제

[!code-cpp[NVC_MFCSerialization#28](../../mfc/codesnippet/cpp/carchive-class_21.cpp)]

##  <a name="writeobject"></a>  CArchive::WriteObject

지정 된 저장 `CObject` 보관 파일에 있습니다.

```
void WriteObject(const CObject* pOb);
```

### <a name="parameters"></a>매개 변수

*pOb*<br/>
저장 되는 개체에 대 한 상수 포인터입니다.

### <a name="remarks"></a>설명

이 함수는 일반적으로 호출한 합니다 `CArchive` 삽입 ( **<<**) 연산자에 대해 오버 로드 `CObject`합니다. `WriteObject`를 호출 하는 `Serialize` 보관 된 클래스의 함수입니다.

IMPLEMENT_SERIAL 매크로 사용 하 여 보관을 사용 하도록 설정 해야 합니다. `WriteObject` 보관 파일을 ASCII 클래스 이름을 씁니다. 이 클래스 이름은 로드 프로세스 동안 나중에 유효성이 검사 됩니다. 특별 한 인코딩 체계를 클래스의 여러 개체에 대 한 클래스 이름의 불필요 한 중복을 방지합니다. 이 체계는 또한 둘 이상의 포인터의 대상인 개체의 중복 저장소를 방지 합니다.

인코딩 (ASCII 클래스 이름의 존재 여부 포함) 하는 방법을 정확 하 게 개체는 구현 세부 정보 및 변경할 수 이후 버전의 라이브러리입니다.

> [!NOTE]
>  만들기, 삭제 및 보관 하기 전에 개체를 모두 업데이트를 완료 합니다. 개체 수정 하 여 보관을 혼합 하면 보관 손상 됩니다.

### <a name="example"></a>예제

클래스의 정의 대 한 `CAge`, 예를 참조 하세요 [CObList::CObList](../../mfc/reference/coblist-class.md#coblist)합니다.

[!code-cpp[NVC_MFCSerialization#29](../../mfc/codesnippet/cpp/carchive-class_22.cpp)]

##  <a name="writestring"></a>  CArchive::WriteString

이 멤버 함수를 사용 하 여 버퍼에서 데이터와 연결 된 파일에 쓸는 `CArchive` 개체입니다.

```
void WriteString(LPCTSTR lpsz);
```

### <a name="parameters"></a>매개 변수

*lpsz*<br/>
Null로 끝나는 문자열을 포함 하는 버퍼에 대 한 포인터를 지정 합니다.

### <a name="remarks"></a>설명

Null 종결 문자 ('\0') 파일에 기록 되지 않습니다. 또는 줄 바꿈 문자를 자동으로 기록 됩니다.

`WriteString` 디스크 꽉 참 조건을 포함 하 여 여러 조건에 대 한 응답에서 예외를 throw 합니다.

`Write` 사용할 수도 있습니다 하지만 null 문자에서 종료 하는 대신 파일에 요청된 된 바이트 수가 기록 합니다.

### <a name="example"></a>예제

[!code-cpp[NVC_MFCSerialization#30](../../mfc/codesnippet/cpp/carchive-class_23.cpp)]

## <a name="see-also"></a>참고자료

[계층 구조 차트](../../mfc/hierarchy-chart.md)<br/>
[CFile 클래스](../../mfc/reference/cfile-class.md)<br/>
[CObject 클래스](../../mfc/reference/cobject-class.md)<br/>
[CSocket 클래스](../../mfc/reference/csocket-class.md)<br/>
[CSocketFile 클래스](../../mfc/reference/csocketfile-class.md)
