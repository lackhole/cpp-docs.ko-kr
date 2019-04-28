---
title: CEnumerator 클래스
ms.date: 11/04/2016
f1_keywords:
- CEnumerator
- CEnumerator::Find
- ATL::CEnumerator::Find
- ATL.CEnumerator.Find
- CEnumerator.Find
- GetMoniker
- CEnumerator.GetMoniker
- CEnumerator::GetMoniker
- ATL.CEnumerator.GetMoniker
- ATL::CEnumerator::GetMoniker
- ATL.CEnumerator.Open
- CEnumerator::Open
- ATL::CEnumerator::Open
- CEnumerator.Open
helpviewer_keywords:
- CEnumerator class
- Find method
- GetMoniker method
- Open method
ms.assetid: 25805f1b-26e3-402f-af83-1b5fe5ddebf7
ms.openlocfilehash: 23467caf46d38175a74dab061f60e11009f1f481
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62230842"
---
# <a name="cenumerator-class"></a>CEnumerator 클래스

노출 하는 OLE DB 열거자 개체를 사용 하는 [ISourcesRowset](/previous-versions/windows/desktop/ms715969(v=vs.85)) 모든 데이터 원본 및 열거자를 설명 하는 행 집합을 반환 하는 인터페이스입니다.

## <a name="syntax"></a>구문

```cpp
class CEnumerator :
   public CAccessorRowset< CAccessor <CEnumeratorAccessor >>
```

## <a name="requirements"></a>요구 사항

**헤더:** atldbcli.h

## <a name="members"></a>멤버

### <a name="methods"></a>메서드

|||
|-|-|
|[Find](#find)|지정한 이름을 가진 하나를 찾고 사용할 수 있는 공급자 (데이터 원본)를 통해 검색 합니다.|
|[GetMoniker](#getmoniker)|검색 된 `IMoniker` 현재 레코드에 대 한 인터페이스입니다.|
|[열기](#open)|열거자를 엽니다.|

## <a name="remarks"></a>설명

검색할 수 있습니다는 `ISourcesRowset` 이 클래스에서 간접적으로 데이터입니다.

## <a name="find"></a> CEnumerator::Find

사용 가능한 공급자 중에서 지정된 된 이름을 찾습니다.

### <a name="syntax"></a>구문

```cpp
bool Find(TCHAR* szSearchName) throw();
```

#### <a name="parameters"></a>매개 변수

*szSearchName*<br/>
[in] 이름에 대 한 검색입니다.

### <a name="return-value"></a>반환 값

**true** 경우 이름을 찾을 수 있습니다. 그렇지 않으면 **false**합니다.

### <a name="remarks"></a>설명

이 이름에 매핑되는 `SOURCES_NAME` 의 멤버는 [ISourcesRowset](/previous-versions/windows/desktop/ms715969(v=vs.85)) 인터페이스입니다.

## <a name="getmoniker"></a> CEnumerator::GetMoniker

모니커를 변환할 수는 문자열의 구성 요소를 추출 하려면 표시 이름을 구문 분석 합니다.

### <a name="syntax"></a>구문

```cpp
HRESULT GetMoniker(LPMONIKER* ppMoniker) const throw();

HRESULT GetMoniker(LPMONIKER* ppMoniker,
   LPCTSTR lpszDisplayName) const throw();
```

#### <a name="parameters"></a>매개 변수

*ppMoniker*<br/>
[out] 표시 이름에서 모니커가 구문 분석 ([cenumeratoraccessor:: M_szparsename](../../data/oledb/cenumeratoraccessor-m-szparsename.md))의 현재 행입니다.

*lpszDisplayName*<br/>
[in] 구문 분석에 대 한 표시 이름입니다.

### <a name="return-value"></a>반환 값

표준 HRESULT입니다.

## <a name="open"></a> Cenumerator:: Open

지정 된 경우 하나를 호출 하 여 행 집합 열거자에 대 한 검색 하는 경우 열거자에 대 한 모니커를 바인딩합니다 [ISourcesRowset::GetSourcesRowset](/previous-versions/windows/desktop/ms711200(v=vs.85))합니다.

### <a name="syntax"></a>구문

```cpp
HRESULT Open(LPMONIKER pMoniker) throw();

HRESULT Open(const CLSID* pClsid = & CLSID_OLEDB_ENUMERATOR) throw();

HRESULT Open(const CEnumerator& enumerator) throw();
```

#### <a name="parameters"></a>매개 변수

*pMoniker*<br/>
[in] 모니커는 열거자에 대 한 포인터입니다.

*pClsid*<br/>
[in] 에 대 한 포인터를 `CLSID` 열거자입니다.

*enumerator*<br/>
[in] 열거자에 대 한 참조입니다.

### <a name="return-value"></a>반환 값

표준 HRESULT입니다.

## <a name="see-also"></a>참고자료

[DBViewer](../../overview/visual-cpp-samples.md)<br/>
[OLE DB 소비자 템플릿(C++)](../../data/oledb/ole-db-consumer-templates-cpp.md)<br/>
[OLE DB 소비자 템플릿 참조](../../data/oledb/ole-db-consumer-templates-reference.md)