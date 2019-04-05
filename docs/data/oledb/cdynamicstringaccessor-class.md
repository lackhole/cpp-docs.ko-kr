---
title: CDynamicStringAccessor 클래스
ms.date: 11/04/2016
f1_keywords:
- CDynamicStringAccessor
- CDynamicStringAccessor.GetString
- CDynamicStringAccessor::GetString
- CDynamicStringAccessor::SetString
- CDynamicStringAccessor.SetString
helpviewer_keywords:
- CDynamicStringAccessor class
- GetString method
- SetString method
ms.assetid: 138dc4de-c7c3-478c-863e-431e48249027
ms.openlocfilehash: 6ba56143beb3411734899839a46ab42992dfa4d8
ms.sourcegitcommit: c7f90df497e6261764893f9cc04b5d1f1bf0b64b
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/05/2019
ms.locfileid: "59035665"
---
# <a name="cdynamicstringaccessor-class"></a>CDynamicStringAccessor 클래스

데이터베이스 스키마(데이터베이스의 내부 구조)에 대해 모를 때 데이터 소스에 액세스할 수 있습니다.

## <a name="syntax"></a>구문

```cpp
template< typename BaseType, DBTYPEENUM OleDbType >
class CDynamicStringAccessorT : public CDynamicAccessor
```

## <a name="requirements"></a>요구 사항

**헤더**: atldbcli.h

## <a name="members"></a>멤버

### <a name="methods"></a>메서드

|||
|-|-|
|[GetString](#getstring)|지정된 열 데이터를 문자열로 검색합니다.|
|[SetString](#setstring)|지정된 열 데이터를 문자열로 설정합니다.|

## <a name="remarks"></a>설명

하는 동안 [CDynamicAccessor](../../data/oledb/cdynamicaccessor-class.md) 공급자가 보고 한 원시 형식으로 데이터를 요청 `CDynamicStringAccessor` 는 공급자 문자열 데이터로 데이터 저장소에서 액세스 하는 모든 데이터를 인출 하는 요청입니다. 표시 하거나 데이터 저장소의 내용을 인쇄와 같은 데이터 저장소에 대 한 값을 계산할 필요가 없는 간단한 작업에 특히 유용 합니다.

데이터 저장소에 있는 열 데이터의 네이티브 형식은 중요하지 않습니다. 공급자가 데이터 변환을 지원할 수 있는 한 데이터를 문자열 형식으로 제공합니다. 공급자 문자열 (은)는 네이티브 데이터 형식에서 변환할을 지원 하지 않으면, 요청 호출 DB_S_ERRORSOCCURED, 성공 값을 반환 하 고 해당 열에 대 한 상태는 변환 문제가 표시 됩니다. DBSTATUS_E_CANTCONVERTVALUE 합니다.

사용 하 여 `CDynamicStringAccessor` 열 정보를 가져오는 방법입니다. 이 열 정보를 사용 하 여 접근자를 런타임에 동적으로 만듭니다.

열 정보를 만들고이 클래스에 의해 관리 되는 버퍼에 저장 됩니다. 사용 하 여 버퍼에서 데이터를 가져올 [GetString](../../data/oledb/cdynamicstringaccessor-getstring.md)를 사용 하 여 버퍼에 저장 하거나 [SetString](../../data/oledb/cdynamicstringaccessor-setstring.md)합니다.

토론 및 동적 접근자 클래스를 사용 하 여 예제를 참조 하세요 [동적 접근자를 사용 하 여](../../data/oledb/using-dynamic-accessors.md)입니다.

## <a name="getstring"></a> CDynamicStringAccessor::GetString

지정된 열 데이터를 문자열로 검색합니다.

### <a name="syntax"></a>구문

```cpp
BaseType* GetString(DBORDINAL nColumn) const throw();

BaseType* GetString(const CHAR* pColumnName) const throw();

BaseType* GetString(const WCHAR* pColumnName) const throw();
```

#### <a name="parameters"></a>매개 변수

*nColumn*<br/>
[in] 열 번호입니다. 열 번호는 1부터 시작 합니다. 값이 0 있으면 책갈피 열을 참조 합니다.

*pColumnName*<br/>
[in] 열 이름이 포함 된 문자열에 대 한 포인터입니다.

### <a name="return-value"></a>반환 값

지정 된 열에서 검색 된 문자열 값에 대 한 포인터입니다. 형식의 값이 `BaseType`를 수 있습니다 **CHAR** 또는 **WCHAR** _UNICODE가 정의 되었는지에 따라 합니다. 지정된 된 열이 없는 경우 NULL을 반환 합니다.

### <a name="remarks"></a>설명

두 번째 폼은 열 이름을 ANSI 문자열로 재정의 합니다. 세 번째 폼은 열 이름을 유니코드 문자열로 재정의 합니다.

## <a name="setstring"></a> CDynamicStringAccessor::SetString

지정된 열 데이터를 문자열로 설정합니다.

### <a name="syntax"></a>구문

```cpp
HRESULT SetString(DBORDINAL nColumn,
   BaseType* data) throw();

HRESULT SetString(const CHAR* pColumnName,
   BaseType* data) throw();

HRESULT SetString(const WCHAR* pColumnName,
   BaseType* data) throw();
```

#### <a name="parameters"></a>매개 변수

*nColumn*<br/>
[in] 열 번호입니다. 열 번호는 1부터 시작 합니다. 특수 값이 0 있으면 책갈피 열을 참조 합니다.

*pColumnName*<br/>
[in] 열 이름이 포함 된 문자열에 대 한 포인터입니다.

*데이터*<br/>
[in] 지정된 된 열에 쓸 문자열 데이터에 대 한 포인터입니다.

### <a name="return-value"></a>반환 값

지정 된 열을 설정 하는 문자열 값에 대 한 포인터입니다. 형식의 값이 `BaseType`를 수 있습니다 **CHAR** 또는 **WCHAR** _UNICODE가 정의 되었는지에 따라 합니다.

### <a name="remarks"></a>설명

세 번째 재정의 폼은 열 이름을 유니코드 문자열로 및 두 번째 폼은 열 이름은 ANSI 문자열을 재정의 합니다.

런타임 어설션 실패가 발생할 경우 생성 됨 _SECURE_ATL 0이 아닌 값에 정의 된 경우 입력 *데이터* 문자열 열 참조 데이터의 최대 허용 길이 보다 깁니다. 그렇지 않은 경우 입력된 문자열을 최대 허용 길이 보다 긴 경우 잘립니다.

## <a name="see-also"></a>참고자료

[OLE DB 소비자 템플릿](../../data/oledb/ole-db-consumer-templates-cpp.md)<br/>
[OLE DB 소비자 템플릿 참조](../../data/oledb/ole-db-consumer-templates-reference.md)<br/>
[CAccessor 클래스](../../data/oledb/caccessor-class.md)<br/>
[CDynamicParameterAccessor 클래스](../../data/oledb/cdynamicparameteraccessor-class.md)<br/>
[CManualAccessor 클래스](../../data/oledb/cmanualaccessor-class.md)<br/>
[CDynamicAccessor 클래스](../../data/oledb/cdynamicaccessor-class.md)<br/>
[CDynamicStringAccessorA 클래스](../../data/oledb/cdynamicstringaccessora-class.md)<br/>
[CDynamicStringAccessorW 클래스](../../data/oledb/cdynamicstringaccessorw-class.md)<br/>
[CXMLAccessor 클래스](../../data/oledb/cxmlaccessor-class.md)