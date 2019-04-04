---
title: CDataConnection 클래스
ms.date: 03/27/2019
f1_keywords:
- ATL::CDataConnection
- ATL.CDataConnection
- CDataConnection
- CDataConnection.CDataConnection
- ATL.CDataConnection.CDataConnection
- CDataConnection::CDataConnection
- ATL::CDataConnection::CDataConnection
- CDataConnection.Copy
- ATL.CDataConnection.Copy
- ATL::CDataConnection::Copy
- CDataConnection::Copy
- CDataConnection.Open
- ATL.CDataConnection.Open
- CDataConnection::Open
- ATL::CDataConnection::Open
- CDataConnection.OpenNewSession
- ATL.CDataConnection.OpenNewSession
- ATL::CDataConnection::OpenNewSession
- OpenNewSession
- CDataConnection::OpenNewSession
- CDataConnection::operatorBOOL
- ATL::CDataConnection::operatorBOOL
- CDataConnection.operatorBOOL
- ATL.CDataConnection.operatorBOOL
- CDataConnection::operatorBOOL
- ATL::CDataConnection::operatorBOOL
- CDataConnection.operatorBOOL
- ATL.CDataConnection.operatorBOOL
- CDataSource&
- CDataConnection.operatorCDataSource&
- operatorCDataSource&
- CDataConnection::operatorCDataSource&
- CDataSource*
- CDataConnection::operatorCDataSource*
- CDataConnection.operatorCDataSource*
- operatorCDataSource*
- CSession&
- CDataConnection::operatorCSession&
- CDataConnection.operatorCSession&
- operatorCSession&
- CDataConnection.operatorCSession*
- CDataConnection::operatorCSession*
- operatorCSession*
- CSession*
helpviewer_keywords:
- CDataConnection class
- CDataConnection class, constructor
- Copy method
- Open method
- OpenNewSession method
- BOOL operator
- operator bool
- BOOL operator
- operator bool
- CDataSource& operator
- operator & (CDataSource)
- CDataSource* operator
- operator * (CDataSource)
- operator CSession&
- CSession& operator
- operator CSession*
- CSession* operator
ms.assetid: 77432d85-4e20-49ec-a0b0-142137828471
ms.openlocfilehash: 769dfc99f431cb5ba803075e28176713f9bd7092
ms.sourcegitcommit: 309dc532f13242854b47759cef846de59bb807f1
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/28/2019
ms.locfileid: "58565508"
---
# <a name="cdataconnection-class"></a>CDataConnection 클래스

데이터 소스를 사용 하 여 연결을 관리합니다.

## <a name="syntax"></a>구문

```cpp
class CDataConnection
```

## <a name="requirements"></a>요구 사항

**헤더:** atldbcli.h

## <a name="members"></a>멤버

### <a name="methods"></a>메서드

|||
|-|-|
|[CDataConnection](#cdataconnection)|생성자입니다. 인스턴스화하고 초기화는 `CDataConnection` 개체입니다.|
|[복사](#copy)|기존 데이터 연결의 복사본을 만듭니다.|
|[열기](#open)|초기화 문자열을 사용 하 여 데이터 원본에 연결을 엽니다.|
|[OpenNewSession](#opennewsession)|현재 연결에서 새 세션을 엽니다.|

### <a name="operators"></a>연산자

|||
|-|-|
|[연산자 BOOL](#op_bool)|현재 세션이 열려 있는지 여부를 결정 합니다.|
|[operator bool](#op_bool_ole)|현재 세션이 열려 있는지 여부를 결정 합니다.|
|[operator CDataSource&](#op_cdata_amp)|포함된 된 참조를 반환 합니다 `CDataSource` 개체입니다.|
|[operator CDataSource*](#op_cdata_star)|포함된 `CDataSource` 개체에 대한 포인터를 반환합니다.|
|[연산자 CSession &](#op_csession_amp)|포함된 된 참조를 반환 합니다 `CSession` 개체입니다.|
|[연산자 CSession *](#op_csession_star)|포함된 `CSession` 개체에 대한 포인터를 반환합니다.|

## <a name="remarks"></a>설명

`CDataConnection` 필요한 개체 (데이터 소스 및 세션) 및 데이터 원본에 연결할 때 수행 해야 하는 작업을 캡슐화 하기 때문에 클라이언트를 만들기 위한 유용한 클래스

없이 `CDataConnection`를 만들 필요가 `CDataSource` 개체를 호출 해당 [OpenFromInitializationString](../../data/oledb/cdatasource-openfrominitializationstring.md) 메서드를의 인스턴스를 만들 수는 [CSession](../../data/oledb/csession-class.md) 개체를 호출 해당 [ 오픈](../../data/oledb/csession-open.md) 메서드를 만든 다음을 [CCommand](../../data/oledb/ccommand-class.md) 개체와 호출 해당 `Open`* 메서드.

사용 하 여 `CDataConnection`, 연결 개체를 만들 초기화 문자열을 전달 하 고 명령을 열려면 해당 연결을 사용 해야 합니다. 데이터베이스에 대 한 연결을 반복적으로 사용 하려는 경우 연결을 열어는 것이 좋습니다 및 `CDataConnection` 작업을 수행 하는 편리한 방법을 제공 합니다.

> [!NOTE]
>  여러 세션을 처리 해야 하는 데이터베이스 응용 프로그램을 만드는 경우 사용 해야 합니다 [OpenNewSession](../../data/oledb/cdataconnection-opennewsession.md)합니다.

## <a name="cdataconnection"></a> CDataConnection::CDataConnection

인스턴스화하고 초기화는 `CDataConnection` 개체입니다.

### <a name="syntax"></a>구문

```cpp
CDataConnection();
CDataConnection(const CDataConnection &ds);
```

#### <a name="parameters"></a>매개 변수

*ds*<br/>
[in] 기존 데이터 연결에 대 한 참조입니다.

### <a name="remarks"></a>설명

첫 번째 재정의에서는 새 `CDataConnection` 기본 설정 사용 하 여 개체입니다.

두 번째 재정의에서는 새 `CDataConnection` 설정 지정할 데이터 연결 개체에 해당 하는 개체입니다.

## <a name="copy"></a> CDataConnection::Copy

기존 데이터 연결의 복사본을 만듭니다.

### <a name="syntax"></a>구문

```cpp
CDataConnection& Copy(const CDataConnection & ds) throw();
```

#### <a name="parameters"></a>매개 변수

*ds*<br/>
[in] 복사할 기존 데이터 연결에 대 한 참조입니다.

## <a name="open"></a> CDataConnection::Open

초기화 문자열을 사용 하 여 데이터 원본에 연결을 엽니다.

### <a name="syntax"></a>구문

```cpp
HRESULT Open(LPCOLESTR szInitString) throw();
```

#### <a name="parameters"></a>매개 변수

*szInitString*<br/>
[in] 데이터 원본 초기화 문자열입니다.

### <a name="return-value"></a>반환 값

표준 HRESULT입니다.

## <a name="opennewsession"></a> CDataConnection::OpenNewSession

현재 연결 개체의 데이터 원본을 사용 하 여 새 세션을 엽니다.

### <a name="syntax"></a>구문

```cpp
HRESULT OpenNewSession(CSession & session) throw();
```

#### <a name="parameters"></a>매개 변수

*session*<br/>
[에서/out] 새 세션 개체에 대 한 참조입니다.

### <a name="remarks"></a>설명

새 세션 현재 연결 개체의 포함 된 데이터 원본 개체를 사용 하 여 해당 부모 및 모든 데이터 원본으로 동일한 정보를 액세스할 수 있습니다.

### <a name="return-value"></a>반환 값

표준 HRESULT입니다.

## <a name="op_bool"></a> CDataConnection::operator BOOL

현재 세션이 열려 있는지 여부를 결정 합니다.

### <a name="syntax"></a>구문

```cpp
operator BOOL() throw();
```

### <a name="remarks"></a>설명

반환 **BOOL** (MFC typedef) 값입니다. **TRUE** 열려 있습니다; 현재 세션은 **FALSE** 현재 세션이 닫힌 것을 의미 합니다.

## <a name="op_bool_ole"></a> Cdataconnection:: Operator bool (OLE DB)

현재 세션이 열려 있는지 여부를 결정 합니다.

### <a name="syntax"></a>구문

```cpp
operator bool() throw();
```

### <a name="remarks"></a>설명

반환 된 **bool** (c + + 데이터 형식) 값입니다. **true** 열려 있습니다; 현재 세션은 **false** 현재 세션이 닫힌 것을 의미 합니다.

## <a name="op_cdata_amp"></a> CDataConnection::operator CDataSource&amp;

포함된 된 참조를 반환 합니다 `CDataSource` 개체입니다.

### <a name="syntax"></a>구문

```cpp
operator const CDataSource&() throw();
```

### <a name="remarks"></a>설명

이 연산자에 포함된 된 참조를 반환 합니다 `CDataSource` 개체를 전달할 수 있도록를 `CDataConnection` 개체 위치를 `CDataSource` 참조가 필요한 데 있습니다.

### <a name="example"></a>예제

함수가 있는 경우 (같은 `func` 아래)를 사용 하는 `CDataSource` 참조를 사용할 수 `CDataSource&` 전달할를 `CDataConnection` 개체를 대신 합니다.

[!code-cpp[NVC_OLEDB_Consumer#3](../../data/oledb/codesnippet/cpp/cdataconnection-operator-cdatasource-amp_1.cpp)]

[!code-cpp[NVC_OLEDB_Consumer#4](../../data/oledb/codesnippet/cpp/cdataconnection-operator-cdatasource-amp_2.cpp)]

## <a name="op_cdata_star"></a> CDataConnection::operator CDataSource*

포함된 `CDataSource` 개체에 대한 포인터를 반환합니다.

### <a name="syntax"></a>구문

```cpp
operator const CDataSource*() throw();
```

### <a name="remarks"></a>설명

이 연산자는 `CDataSource` 포인터가 예상되는 위치에 `CDataConnection` 개체를 전달할 수 있게 해주는, 포함된 `CDataSource` 개체에 대한 포인터를 반환합니다.

참조 [operator CDataSource &](../../data/oledb/cdataconnection-operator-cdatasource-amp.md) 사용 예입니다.

## <a name="op_csession_amp"></a> CDataConnection::operator CSession&amp;

포함된 된 참조를 반환 합니다 `CSession` 개체입니다.

### <a name="syntax"></a>구문

```cpp
operator const CSession&();
```

### <a name="remarks"></a>설명

이 연산자에 포함된 된 참조를 반환 합니다 `CSession` 개체를 전달할 수 있도록를 `CDataConnection` 개체 위치를 `CSession` 참조가 필요한 데 있습니다.

### <a name="example"></a>예제

함수가 있는 경우 (같은 `func` 아래)를 사용 하는 `CSession` 참조를 사용할 수 `CSession&` 전달할를 `CDataConnection` 개체를 대신 합니다.

[!code-cpp[NVC_OLEDB_Consumer#5](../../data/oledb/codesnippet/cpp/cdataconnection-operator-csession-amp_1.cpp)]

[!code-cpp[NVC_OLEDB_Consumer#6](../../data/oledb/codesnippet/cpp/cdataconnection-operator-csession-amp_2.cpp)]

## <a name="op_csession_star"></a> CDataConnection::operator CSession*

포함된 `CSession` 개체에 대한 포인터를 반환합니다.

### <a name="syntax"></a>구문

```cpp
operator const CSession*() throw();
```

### <a name="remarks"></a>설명

이 연산자는 `CSession` 포인터가 예상되는 위치에 `CDataConnection` 개체를 전달할 수 있게 해주는, 포함된 `CSession` 개체에 대한 포인터를 반환합니다.

### <a name="example"></a>예제

참조 [연산자 CSession &](../../data/oledb/cdataconnection-operator-csession-amp.md) 사용 예입니다.

## <a name="see-also"></a>참고 항목

[OLE DB 소비자 템플릿(C++)](../../data/oledb/ole-db-consumer-templates-cpp.md)<br/>
[OLE DB 소비자 템플릿 참조](../../data/oledb/ole-db-consumer-templates-reference.md)