---
title: CObList 클래스
ms.date: 11/04/2016
f1_keywords:
- CObList
- AFXCOLL/CObList
- AFXCOLL/CObList::CObList
- AFXCOLL/CObList::AddHead
- AFXCOLL/CObList::AddTail
- AFXCOLL/CObList::Find
- AFXCOLL/CObList::FindIndex
- AFXCOLL/CObList::GetAt
- AFXCOLL/CObList::GetCount
- AFXCOLL/CObList::GetHead
- AFXCOLL/CObList::GetHeadPosition
- AFXCOLL/CObList::GetNext
- AFXCOLL/CObList::GetPrev
- AFXCOLL/CObList::GetSize
- AFXCOLL/CObList::GetTail
- AFXCOLL/CObList::GetTailPosition
- AFXCOLL/CObList::InsertAfter
- AFXCOLL/CObList::InsertBefore
- AFXCOLL/CObList::IsEmpty
- AFXCOLL/CObList::RemoveAll
- AFXCOLL/CObList::RemoveAt
- AFXCOLL/CObList::RemoveHead
- AFXCOLL/CObList::RemoveTail
- AFXCOLL/CObList::SetAt
helpviewer_keywords:
- CObList [MFC], CObList
- CObList [MFC], AddHead
- CObList [MFC], AddTail
- CObList [MFC], Find
- CObList [MFC], FindIndex
- CObList [MFC], GetAt
- CObList [MFC], GetCount
- CObList [MFC], GetHead
- CObList [MFC], GetHeadPosition
- CObList [MFC], GetNext
- CObList [MFC], GetPrev
- CObList [MFC], GetSize
- CObList [MFC], GetTail
- CObList [MFC], GetTailPosition
- CObList [MFC], InsertAfter
- CObList [MFC], InsertBefore
- CObList [MFC], IsEmpty
- CObList [MFC], RemoveAll
- CObList [MFC], RemoveAt
- CObList [MFC], RemoveHead
- CObList [MFC], RemoveTail
- CObList [MFC], SetAt
ms.assetid: 80699c93-33d8-4f8b-b8cf-7b58aeab64ca
ms.openlocfilehash: 2fc3a3643c675394de555f1411030e278bcee775
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62388243"
---
# <a name="coblist-class"></a>CObList 클래스

순서가 지정 된 고유 하지 않은의 목록을 fSupports `CObject` 포인터에 액세스할 수 있는 순차적으로 또는 포인터 값입니다.

## <a name="syntax"></a>구문

```
class CObList : public CObject
```

## <a name="members"></a>멤버

### <a name="public-constructors"></a>Public 생성자

|이름|설명|
|----------|-----------------|
|[CObList::CObList](#coblist)|에 대 한 빈 목록을 생성 `CObject` 포인터입니다.|

### <a name="public-methods"></a>Public 메서드

|이름|설명|
|----------|-----------------|
|[CObList::AddHead](#addhead)|(새 헤드는) 목록 헤드에 요소 (또는 다른 목록의 모든 요소)를 추가 합니다.|
|[CObList::AddTail](#addtail)|(새 비상은) 목록의 끝에 요소 (또는 다른 목록의 모든 요소)를 추가 합니다.|
|[CObList::Find](#find)|포인터 값으로 지정 된 요소의 위치를 가져옵니다.|
|[CObList::FindIndex](#findindex)|인덱스는 0부터 시작 하 여 지정 된 요소의 위치를 가져옵니다.|
|[CObList::GetAt](#getat)|지정된 된 위치에 요소를 가져옵니다.|
|[CObList::GetCount](#getcount)|이 목록의 요소 수를 반환합니다.|
|[CObList::GetHead](#gethead)|(비워 둘 수 없습니다) 목록의 head 요소를 반환 합니다.|
|[CObList::GetHeadPosition](#getheadposition)|목록의 헤드 요소의 위치를 반환합니다.|
|[CObList::GetNext](#getnext)|반복에 대 한 다음 요소를 가져옵니다.|
|[CObList::GetPrev](#getprev)|반복에 대 한 이전 요소를 가져옵니다.|
|[CObList::GetSize](#getsize)|이 목록의 요소 수를 반환합니다.|
|[CObList::GetTail](#gettail)|(비워 둘 수 없습니다) 목록의 꼬리 요소를 반환 합니다.|
|[CObList::GetTailPosition](#gettailposition)|목록의 꼬리 요소의 위치를 반환합니다.|
|[CObList::InsertAfter](#insertafter)|지정된 된 위치 뒤에 새 요소를 삽입 합니다.|
|[CObList::InsertBefore](#insertbefore)|지정된 된 위치 앞에 새 요소를 삽입합니다.|
|[CObList::IsEmpty](#isempty)|빈 목록 조건 (요소 없음)에 대해 테스트 합니다.|
|[CObList::RemoveAll](#removeall)|이 목록의 모든 요소를 제거합니다.|
|[CObList::RemoveAt](#removeat)|위치 지정이 목록에서 요소를 제거 합니다.|
|[CObList::RemoveHead](#removehead)|목록 헤드에서 요소를 제거합니다.|
|[CObList::RemoveTail](#removetail)|목록의 꼬리에서 요소를 제거합니다.|
|[CObList::SetAt](#setat)|지정된 된 위치에 요소를 설정합니다.|

## <a name="remarks"></a>설명

`CObList` 이중 연결 목록 처럼 동작합니다.

위치 형식의 변수는 목록에 대 한 키입니다. 순차적 목록을 순회 하는 반복기와 책갈피를 저장할 위치를 위치 변수를 사용할 수 있습니다. 그러나 위치는 인덱스를 동일 않습니다.

요소를 삽입 목록 헤드에 있는, 테일에서 알려진 위치에 매우 빠릅니다. 순차 검색이 값 또는 인덱스 별로 요소 조회 하는 데 필요한 경우 이 검색 목록이 긴 경우에 느려질 수 있습니다.

`CObList` serialization 및 요소 덤프를 지원 하기 위해 IMPLEMENT_SERIAL 매크로 통합 합니다. 목록을 `CObject` 포인터 오버 로드 된 삽입 연산자를 사용 하 여 또는 사용 하 여 보관 파일에 저장 됩니다 합니다 `Serialize` 멤버 함수를 각각 `CObject` 요소가 차례로 serialize 됩니다.

개별 덤프가 필요한 경우 `CObject` 목록의 요소를 1 이상으로 덤프 컨텍스트 깊이 설정 해야 합니다.

경우는 `CObList` 개체를 삭제 하면 해당 요소를 제거 하면만 또는 `CObject` 제거 되 고 포인터, 참조 하는 개체입니다.

고유한 클래스를 파생할 수 `CObList`입니다. 새 목록 클래스에서 파생 된 개체에 대 한 포인터를 포함 하도록 디자인 된 `CObject`, 새 데이터 멤버 및 새 멤버 함수를 추가 합니다. 결과 목록 않음을 유의 엄격 하 게 형식이 안전한의 삽입을 허용 하므로 `CObject` 포인터입니다.

> [!NOTE]
>  사용 해야 합니다는 [IMPLEMENT_SERIAL](run-time-object-model-services.md#implement_serial) 목록을 serialize 하려는 경우 파생된 클래스의 구현에는 매크로입니다.

사용 하 여 대 한 자세한 내용은 `CObList`, 문서를 참조 하세요 [컬렉션](../../mfc/collections.md)합니다.

## <a name="inheritance-hierarchy"></a>상속 계층 구조

[CObject](../../mfc/reference/cobject-class.md)

`CObList`

## <a name="requirements"></a>요구 사항

**헤더:** afxcoll.h

##  <a name="addhead"></a>  CObList::AddHead

이 목록 헤드에 새 요소 또는 요소의 목록을 추가합니다.

```
POSITION AddHead(CObject* newElement);
void AddHead(CObList* pNewList);
```

### <a name="parameters"></a>매개 변수

*newElement*<br/>
`CObject` 이 목록에 추가에 대 한 포인터입니다.

*pNewList*<br/>
다른 포인터 `CObList` 목록입니다. 에 있는 요소 *pNewList* 이 목록에 추가 됩니다.

### <a name="return-value"></a>반환 값

첫 번째 버전에는 새로 삽입 된 요소의 위치 값을 반환합니다.

다음 표에서 다른 멤버와 유사한 함수 `CObList::AddHead`합니다.

|클래스|멤버 함수|
|-----------|---------------------|
|[CPtrList](../../mfc/reference/cptrlist-class.md)|**위치 AddHead (void** <strong>\*</strong> `newElement` **);**<br /><br /> **void AddHead( CPtrList** <strong>\*</strong> `pNewList` **);**|
|[CStringList](../../mfc/reference/cstringlist-class.md)|**POSITION AddHead(const CString&** `newElement` **);**<br /><br /> **POSITION AddHead(LPCTSTR** `newElement` **);**<br /><br /> **void AddHead(CStringList** <strong>\*</strong> `pNewList` **);**|

### <a name="remarks"></a>설명

목록 작업 전에 비어 있을 수 있습니다.

### <a name="example"></a>예제

  참조 [CObList::CObList](#coblist) 목록은 `CAge` 클래스입니다.

[!code-cpp[NVC_MFCCollections#89](../../mfc/codesnippet/cpp/coblist-class_1.cpp)]

이 프로그램의 결과 아래와 같습니다.

```Output
AddHead example: A CObList with 2 elements
a CAge at $44A8 40
a CAge at $442A 21
```

##  <a name="addtail"></a>  CObList::AddTail

이 목록의 꼬리에 새 요소 또는 요소의 목록을 추가합니다.

```
POSITION AddTail(CObject* newElement);
void AddTail(CObList* pNewList);
```

### <a name="parameters"></a>매개 변수

*newElement*<br/>
`CObject` 이 목록에 추가에 대 한 포인터입니다.

*pNewList*<br/>
다른 포인터 `CObList` 목록입니다. 에 있는 요소 *pNewList* 이 목록에 추가 됩니다.

### <a name="return-value"></a>반환 값

첫 번째 버전에는 새로 삽입 된 요소의 위치 값을 반환합니다.

### <a name="remarks"></a>설명

목록 작업 전에 비어 있을 수 있습니다.

다음 표에서 다른 멤버와 유사한 함수 `CObList::AddTail`합니다.

|클래스|멤버 함수|
|-----------|---------------------|
|[CPtrList](../../mfc/reference/cptrlist-class.md)|**위치 AddTail (void** <strong>\*</strong> `newElement` **);**<br /><br /> **void AddTail( CPtrList** <strong>\*</strong> `pNewList` **);**|
|[CStringList](../../mfc/reference/cstringlist-class.md)|**위치 AddTail (const CString &** `newElement` **);**<br /><br /> **위치 AddTail (LPCTSTR** `newElement` **);**<br /><br /> **void AddTail( CStringList** <strong>\*</strong> `pNewList` **);**|

### <a name="example"></a>예제

  참조 [CObList::CObList](#coblist) 목록은 `CAge` 클래스입니다.

[!code-cpp[NVC_MFCCollections#90](../../mfc/codesnippet/cpp/coblist-class_2.cpp)]

이 프로그램의 결과 아래와 같습니다.

```Output
AddTail example: A CObList with 2 elements
a CAge at $444A 21
a CAge at $4526 40
```

##  <a name="coblist"></a>  CObList::CObList

빈 생성 `CObject` 포인터 목록입니다.

```
CObList(INT_PTR nBlockSize = 10);
```

### <a name="parameters"></a>매개 변수

*nBlockSize*<br/>
확장 목록에 대 한 메모리 할당 세분성입니다.

### <a name="remarks"></a>설명

단위로 메모리를 할당 목록 늘어나면 *nBlockSize* 항목입니다. 메모리 할당이 실패 하면는 `CMemoryException` throw 됩니다.

다음 표에서 다른 멤버와 유사한 함수 `CObList::CObList`합니다.

|클래스|멤버 함수|
|-----------|---------------------|
|[CPtrList](../../mfc/reference/cptrlist-class.md)|**CPtrList( INT_PTR** `nBlockSize` **= 10 );**|
|[CStringList](../../mfc/reference/cstringlist-class.md)|**CStringList( INT_PTR** `nBlockSize` **= 10 );**|

### <a name="example"></a>예제

  목록은 다음과 같습니다 합니다 `CObject`-클래스를 파생 `CAge` 모든 컬렉션 예제에 사용 합니다.

[!code-cpp[NVC_MFCCollections#91](../../mfc/codesnippet/cpp/coblist-class_3.h)]

예로 `CObList` 생성자 사용:

[!code-cpp[NVC_MFCCollections#92](../../mfc/codesnippet/cpp/coblist-class_4.cpp)]

##  <a name="find"></a>  CObList::Find

검색을 첫 번째를 찾도록 순차적 목록을 `CObject` 일치 하는 지정 된 포인터 `CObject` 포인터입니다.

```
POSITION Find(
    CObject* searchValue,
    POSITION startAfter = NULL) const;
```

### <a name="parameters"></a>매개 변수

*searchValue*<br/>
이 목록에서 찾을 개체 포인터입니다.

*startAfter*<br/>
검색 시작 위치입니다.

### <a name="return-value"></a>반환 값

반복 또는 개체 포인터 검색;에 사용할 수 있는 위치 값 개체가 없을 경우 NULL입니다.

### <a name="remarks"></a>설명

개체의 내용이 아닌, 포인터 값이 비교 되는 참고 합니다.

다음 표에서 다른 멤버와 유사한 함수 `CObList::Find`합니다.

|클래스|멤버 함수|
|-----------|---------------------|
|[CPtrList](../../mfc/reference/cptrlist-class.md)|**위치 찾기 (void** <strong>\*</strong> `searchValue` **, 위치** `startAfter` **= NULL) const;**|
|[CStringList](../../mfc/reference/cstringlist-class.md)|**위치 찾기 (LPCTSTR** `searchValue` **, 위치** `startAfter` **= NULL) const;**|

### <a name="example"></a>예제

참조 [CObList::CObList](#coblist) 목록은 `CAge` 클래스입니다.

[!code-cpp[NVC_MFCCollections#93](../../mfc/codesnippet/cpp/coblist-class_5.cpp)]

##  <a name="findindex"></a>  CObList::FindIndex

값을 사용 하 여 *nIndex* 목록 인덱스로.

```
POSITION FindIndex(INT_PTR nIndex) const;
```

### <a name="parameters"></a>매개 변수

*nIndex*<br/>
찾을 목록 요소의 0부터 시작 하는 인덱스입니다.

### <a name="return-value"></a>반환 값

반복 또는 개체 포인터 검색;에 사용할 수 있는 위치 값 경우에는 NULL *nIndex* 너무 큽니다. (경우 어설션을 생성 하는 프레임 워크 *nIndex* 음수입니다.)

### <a name="remarks"></a>설명

중지 목록 헤드에서 순차적 검색을 시작 하기를 *n*번째 요소입니다.

다음 표에서 다른 멤버와 유사한 함수 `CObList::FindIndex`합니다.

|클래스|멤버 함수|
|-----------|---------------------|
|[CPtrList](../../mfc/reference/cptrlist-class.md)|**위치 FindIndex (INT_PTR** `nIndex` **) const;**|
|[CStringList](../../mfc/reference/cstringlist-class.md)|**위치 FindIndex (INT_PTR** `nIndex` **) const;**|

### <a name="example"></a>예제

참조 [CObList::CObList](#coblist) 목록은 `CAge` 클래스입니다.

[!code-cpp[NVC_MFCCollections#94](../../mfc/codesnippet/cpp/coblist-class_6.cpp)]

##  <a name="getat"></a>  CObList::GetAt

위치 형식의 변수는 목록에 대 한 키입니다.

```
CObject*& GetAt(POSITION position);
const CObject*& GetAt(POSITION position) const;
```

### <a name="parameters"></a>매개 변수

*position*<br/>
이전 반환한 위치 값 `GetHeadPosition` 또는 `Find` 멤버 함수 호출 합니다.

### <a name="return-value"></a>반환 값

에 대 한 반환 값 설명을 참조 하세요 [GetHead](#gethead)합니다.

### <a name="remarks"></a>설명

인덱스를 동일 하지 않습니다 하 고 작업할 수 없습니다. 위치 값을 직접. `GetAt` 검색 된 `CObject` 지정된 된 위치와 연결 된 포인터입니다.

위치 값 목록에서 올바른 위치를 나타내도록 해야 합니다. 올바르지 않으면 Microsoft Foundation Class 라이브러리의 디버그 버전 어설션 합니다.

다음 표에서 다른 멤버와 유사한 함수 `CObList::GetAt`합니다.

|클래스|멤버 함수|
|-----------|---------------------|
|[CPtrList](../../mfc/reference/cptrlist-class.md)|**const void\*& GetAt( POSITION** *position* **) const;**<br /><br /> **void\*& GetAt( POSITION** *position* **);**|
|[CStringList](../../mfc/reference/cstringlist-class.md)|**const CString & GetAt (위치** *위치* **) const;**<br /><br /> **CString& GetAt( POSITION** *position* **);**|

### <a name="example"></a>예제

  예를 참조 하세요 [FindIndex](#findindex)합니다.

##  <a name="getcount"></a>  CObList::GetCount

이 목록의 요소 수를 가져옵니다.

```
INT_PTR GetCount() const;
```

### <a name="return-value"></a>반환 값

요소 수를 포함 하는 정수 값입니다.

다음 표에서 다른 멤버와 유사한 함수 `CObList::GetCount`합니다.

|클래스|멤버 함수|
|-----------|---------------------|
|[CPtrList](../../mfc/reference/cptrlist-class.md)|**INT_PTR GetCount( ) const;**|
|[CStringList](../../mfc/reference/cstringlist-class.md)|**INT_PTR GetCount( ) const;**|

### <a name="example"></a>예제

참조 [CObList::CObList](#coblist) 목록은 `CAge` 클래스입니다.

[!code-cpp[NVC_MFCCollections#95](../../mfc/codesnippet/cpp/coblist-class_7.cpp)]

##  <a name="gethead"></a>  CObList::GetHead

가져옵니다는 `CObject` 이 목록의 head 요소를 나타내는 포인터입니다.

```
CObject*& GetHead();
const CObject*& GetHead() const;
```

### <a name="return-value"></a>반환 값

목록에 대 한 포인터를 통해 액세스 하는 경우는 `const CObList`, 한 다음 `GetHead` 반환을 `CObject` 포인터. 함수 대입문의 오른쪽에만 사용할 수 있으며 따라서 목록 수정 되지 않도록에서 보호 합니다.

목록에 직접 또는 포인터를 통해 액세스 하는 경우는 `CObList`, 한 다음 `GetHead` 에 대 한 참조를 반환 합니다를 `CObject` 포인터입니다. 이 대입문의 어느 쪽에 사용할 함수를 허용 하며 따라서 목록 항목을 수정할 수 있습니다.

### <a name="remarks"></a>설명

호출 하기 전에 비어 있지 않은지 확인 해야 `GetHead`합니다. 목록이 비어 있으면 Microsoft Foundation Class 라이브러리의 디버그 버전 어설션 합니다. 사용 하 여 [IsEmpty](#isempty) 목록 요소에 있는지 확인 합니다.

다음 표에서 다른 멤버와 유사한 함수 `CObList::GetHead`합니다.

|클래스|멤버 함수|
|-----------|---------------------|
|[CPtrList](../../mfc/reference/cptrlist-class.md)|**const void\*& GetHead( ) const; void\*& GetHead( );**|
|[CStringList](../../mfc/reference/cstringlist-class.md)|**const CString& GetHead( ) const; CString& GetHead( );**|

### <a name="example"></a>예제

참조 [CObList::CObList](#coblist) 목록은 `CAge` 클래스입니다.

다음 예제에서는 `GetHead` 대입문의 왼쪽에 있습니다.

[!code-cpp[NVC_MFCCollections#96](../../mfc/codesnippet/cpp/coblist-class_8.cpp)]

##  <a name="getheadposition"></a>  CObList::GetHeadPosition

이 목록의 헤드 요소의 위치를 가져옵니다.

```
POSITION GetHeadPosition() const;
```

### <a name="return-value"></a>반환 값

반복 또는 개체 포인터 검색;에 사용할 수 있는 위치 값 목록이 비어 있는 경우 NULL입니다.

다음 표에서 다른 멤버와 유사한 함수 `CObList::GetHeadPosition`합니다.

|클래스|멤버 함수|
|-----------|---------------------|
|[CPtrList](../../mfc/reference/cptrlist-class.md)|**Const; GetHeadPosition ()를 배치 합니다.**|
|[CStringList](../../mfc/reference/cstringlist-class.md)|**Const; GetHeadPosition ()를 배치 합니다.**|

### <a name="example"></a>예제

참조 [CObList::CObList](#coblist) 목록은 `CAge` 클래스입니다.

[!code-cpp[NVC_MFCCollections#97](../../mfc/codesnippet/cpp/coblist-class_9.cpp)]

##  <a name="getnext"></a>  CObList::GetNext

로 식별 되는 목록 요소를 가져옵니다 *rPosition*를 설정한 *rPosition* 에 `POSITION` 목록에서 다음 항목의 값입니다.

```
CObject*& GetNext(POSITION& rPosition);
const CObject* GetNext(POSITION& rPosition) const;
```

### <a name="parameters"></a>매개 변수

*rPosition*<br/>
이전 반환한 위치 값에 대 한 참조가 `GetNext`, `GetHeadPosition`, 또는 다른 멤버 함수 호출 합니다.

### <a name="return-value"></a>반환 값

에 대 한 반환 값 설명을 참조 하세요 [GetHead](#gethead)합니다.

### <a name="remarks"></a>설명

사용할 수 있습니다 `GetNext` 에 대 한 호출의 초기 위치를 설정한 경우 정방향 반복 루프에서 `GetHeadPosition` 또는 `Find`합니다.

위치 값 목록에서 올바른 위치를 나타내도록 해야 합니다. 올바르지 않으면 Microsoft Foundation Class 라이브러리의 디버그 버전 어설션 합니다.

검색 된 요소가 있으면 목록에서 마지막으로 다음의 새 값 *rPosition* NULL로 설정 됩니다.

반복 하는 동안 요소를 제거 하는 것이 가능 합니다. 예를 참조 하세요 [RemoveAt](#removeat)합니다.

> [!NOTE]
>  반환할 MFC 8.0부터이 메서드의 const 버전이 변경 되었습니다 `const CObject*` 대신 `const CObject*&`합니다.  이 변경은 컴파일러를 사용 하 여 준수 상태로 전환 하는 C++ 표준입니다.

다음 표에서 다른 멤버와 유사한 함수 `CObList::GetNext`합니다.

|클래스|멤버 함수|
|-----------|---------------------|
|[CPtrList](../../mfc/reference/cptrlist-class.md)|`void*& GetNext( POSITION&` `rPosition` `);`<br /><br /> `const void* GetNext( POSITION&` `rPosition` `) const;`|
|[CStringList](../../mfc/reference/cstringlist-class.md)|`CString& GetNext( POSITION&` `rPosition` `);`<br /><br /> `const CString& GetNext( POSITION&` `rPosition` `) const;`|

### <a name="example"></a>예제

  참조 [CObList::CObList](#coblist) 목록은 `CAge` 클래스입니다.

[!code-cpp[NVC_MFCCollections#98](../../mfc/codesnippet/cpp/coblist-class_10.cpp)]

이 프로그램의 결과 아래와 같습니다.

```Output
a CAge at $479C 40
a CAge at $46C0 21
```

##  <a name="getprev"></a>  CObList::GetPrev

로 식별 되는 목록 요소를 가져옵니다 *rPosition*를 설정한 *rPosition* 목록의 이전 항목의 위치 값입니다.

```
CObject*& GetPrev(POSITION& rPosition);
const CObject* GetPrev(POSITION& rPosition) const;
```

### <a name="parameters"></a>매개 변수

*rPosition*<br/>
이전 반환한 위치 값에 대 한 참조 `GetPrev` 또는 다른 멤버 함수 호출 합니다.

### <a name="return-value"></a>반환 값

에 대 한 반환 값 설명을 참조 하세요 [GetHead](#gethead)합니다.

### <a name="remarks"></a>설명

사용할 수 있습니다 `GetPrev` 에 대 한 호출의 초기 위치를 설정 하는 경우 역방향 반복 루프에서 `GetTailPosition` 또는 `Find`합니다.

위치 값 목록에서 올바른 위치를 나타내도록 해야 합니다. 올바르지 않으면 Microsoft Foundation Class 라이브러리의 디버그 버전 어설션 합니다.

검색 된 요소가 있으면 목록에서 첫 번째 다음의 새 값 *rPosition* NULL로 설정 됩니다.

> [!NOTE]
>  반환할 MFC 8.0부터이 메서드의 const 버전이 변경 되었습니다 `const CObject*` 대신 `const CObject*&`합니다.  이 변경은 컴파일러를 사용 하 여 준수 상태로 전환 하는 C++ 표준입니다.

다음 표에서 다른 멤버와 유사한 함수 `CObList::GetPrev`합니다.

|클래스|멤버 함수|
|-----------|---------------------|
|[CPtrList](../../mfc/reference/cptrlist-class.md)|`void*& GetPrev( POSITION&` `rPosition` `);`<br /><br /> `const void* GetPrev( POSITION&` `rPosition` `) const;`|
|[CStringList](../../mfc/reference/cstringlist-class.md)|`CString& GetPrev( POSITION&` `rPosition` `);`<br /><br /> `const CString& GetPrev( POSITION&` `rPosition` `) const;`|

### <a name="example"></a>예제

  참조 [CObList::CObList](#coblist) 목록은 `CAge` 클래스입니다.

[!code-cpp[NVC_MFCCollections#99](../../mfc/codesnippet/cpp/coblist-class_11.cpp)]

이 프로그램의 결과 아래와 같습니다.

```Output
a CAge at $421C 21
a CAge at $421C 40
```

##  <a name="getsize"></a>  CObList::GetSize

목록 요소의 수를 반환합니다.

```
INT_PTR GetSize() const;
```

### <a name="return-value"></a>반환 값

목록의 항목 수입니다.

### <a name="remarks"></a>설명

목록의 요소 수를 검색 하려면이 메서드를 호출 합니다.

다음 표에서 다른 멤버와 유사한 함수 `CObList::GetSize`합니다.

|클래스|멤버 함수|
|-----------|---------------------|
|[CPtrList](../../mfc/reference/cptrlist-class.md)|**INT_PTR GetSize( ) const;**|
|[CStringList](../../mfc/reference/cstringlist-class.md)|**INT_PTR GetSize( ) const;**|

### <a name="example"></a>예제

참조 [CObList::CObList](#coblist) 목록은 `CAge` 클래스입니다.

[!code-cpp[NVC_MFCCollections#100](../../mfc/codesnippet/cpp/coblist-class_12.cpp)]

##  <a name="gettail"></a>  CObList::GetTail

가져옵니다는 `CObject` 이 목록의 꼬리 요소를 나타내는 포인터입니다.

```
CObject*& GetTail();
const CObject*& GetTail() const;
```

### <a name="return-value"></a>반환 값

에 대 한 반환 값 설명을 참조 하세요 [GetHead](#gethead)합니다.

### <a name="remarks"></a>설명

호출 하기 전에 비어 있지 않은지 확인 해야 `GetTail`합니다. 목록이 비어 있으면 Microsoft Foundation Class 라이브러리의 디버그 버전 어설션 합니다. 사용 하 여 [IsEmpty](#isempty) 목록 요소에 있는지 확인 합니다.

다음 표에서 다른 멤버와 유사한 함수 `CObList::GetTail`합니다.

|클래스|멤버 함수|
|-----------|---------------------|
|[CPtrList](../../mfc/reference/cptrlist-class.md)|**const void\*& GetTail( ) const; void\*& GetTail( );**|
|[CStringList](../../mfc/reference/cstringlist-class.md)|**const CString& GetTail( ) const; CString& GetTail( );**|

### <a name="example"></a>예제

참조 [CObList::CObList](#coblist) 목록은 `CAge` 클래스입니다.

[!code-cpp[NVC_MFCCollections#101](../../mfc/codesnippet/cpp/coblist-class_13.cpp)]

##  <a name="gettailposition"></a>  CObList::GetTailPosition

이 목록의 꼬리 요소의 위치를 가져옵니다. **NULL** 목록이 비어 있는 경우.

```
POSITION GetTailPosition() const;
```

### <a name="return-value"></a>반환 값

반복 또는 개체 포인터 검색;에 사용할 수 있는 위치 값 목록이 비어 있는 경우 NULL입니다.

다음 표에서 다른 멤버와 유사한 함수 `CObList::GetTailPosition`합니다.

|클래스|멤버 함수|
|-----------|---------------------|
|[CPtrList](../../mfc/reference/cptrlist-class.md)|**Const; GetTailPosition ()를 배치 합니다.**|
|[CStringList](../../mfc/reference/cstringlist-class.md)|**Const; GetTailPosition ()를 배치 합니다.**|

### <a name="example"></a>예제

참조 [CObList::CObList](#coblist) 목록은 `CAge` 클래스입니다.

[!code-cpp[NVC_MFCCollections#102](../../mfc/codesnippet/cpp/coblist-class_14.cpp)]

##  <a name="insertafter"></a>  CObList::InsertAfter

이 목록에 지정 된 위치의 요소 뒤 요소를 추가합니다.

```
POSITION InsertAfter(
    POSITION position,
    CObject* newElement);
```

### <a name="parameters"></a>매개 변수

*position*<br/>
이전 반환한 위치 값 `GetNext`, `GetPrev`, 또는 `Find` 멤버 함수 호출 합니다.

*newElement*<br/>
이 목록에 추가할 개체 포인터입니다.

다음 표에서 다른 멤버와 유사한 함수 `CObList::InsertAfter`합니다.

|클래스|멤버 함수|
|-----------|---------------------|
|[CPtrList](../../mfc/reference/cptrlist-class.md)|**POSITION InsertAfter( POSITION** *position* **, void** <strong>\*</strong> `newElement` **);**|
|[CStringList](../../mfc/reference/cstringlist-class.md)|**POSITION InsertAfter( POSITION** *position* **, const CString&** `newElement` **);**<br /><br /> **POSITION InsertAfter( POSITION** *position* **, LPCTSTR** `newElement` **);**|

### <a name="return-value"></a>반환 값

동일한 위치 값으로는 *위치* 매개 변수입니다.

### <a name="example"></a>예제

  참조 [CObList::CObList](#coblist) 목록은 `CAge` 클래스입니다.

[!code-cpp[NVC_MFCCollections#103](../../mfc/codesnippet/cpp/coblist-class_15.cpp)]

이 프로그램의 결과 아래와 같습니다.

```Output
InsertAfter example: A CObList with 3 elements
a CAge at $4A44 40
a CAge at $4A64 65
a CAge at $4968 21
```

##  <a name="insertbefore"></a>  CObList::InsertBefore

이 목록에서 지정된 위치의 요소 앞에 요소를 추가합니다.

```
POSITION InsertBefore(
    POSITION position,
    CObject* newElement);
```

### <a name="parameters"></a>매개 변수

*position*<br/>
이전 반환한 위치 값 `GetNext`, `GetPrev`, 또는 `Find` 멤버 함수 호출 합니다.

*newElement*<br/>
이 목록에 추가할 개체 포인터입니다.

### <a name="return-value"></a>반환 값

반복 또는 개체 포인터 검색;에 사용할 수 있는 위치 값 목록이 비어 있는 경우 NULL입니다.

다음 표에서 다른 멤버와 유사한 함수 `CObList::InsertBefore`합니다.

|클래스|멤버 함수|
|-----------|---------------------|
|[CPtrList](../../mfc/reference/cptrlist-class.md)|**POSITION InsertBefore( POSITION** *position* **, void** <strong>\*</strong> `newElement` **);**|
|[CStringList](../../mfc/reference/cstringlist-class.md)|**위치 InsertBefore (위치** *위치* **, const CString &** `newElement` **);**<br /><br /> **POSITION InsertBefore( POSITION** *position* **, LPCTSTR** `newElement` **);**|

### <a name="example"></a>예제

  참조 [CObList::CObList](#coblist) 목록은 `CAge` 클래스입니다.

[!code-cpp[NVC_MFCCollections#104](../../mfc/codesnippet/cpp/coblist-class_16.cpp)]

이 프로그램의 결과 아래와 같습니다.

```Output
InsertBefore example: A CObList with 3 elements
a CAge at $4AE2 40
a CAge at $4B02 65
a CAge at $49E6 21
```

##  <a name="isempty"></a>  CObList::IsEmpty

이 목록에 요소가 있는지 여부를 나타냅니다.

```
BOOL IsEmpty() const;
```

### <a name="return-value"></a>반환 값

이 목록은 비어 있으면 0이 아닌 값 그렇지 않으면 0입니다.

다음 표에서 다른 멤버와 유사한 함수 `CObList::IsEmpty`합니다.

|클래스|멤버 함수|
|-----------|---------------------|
|[CPtrList](../../mfc/reference/cptrlist-class.md)|**BOOL IsEmpty( ) const;**|
|[CStringList](../../mfc/reference/cstringlist-class.md)|**BOOL IsEmpty( ) const;**|

### <a name="example"></a>예제

  예를 참조 하세요 [RemoveAll](#removeall)합니다.

##  <a name="removeall"></a>  CObList::RemoveAll

이 목록의 모든 요소를 제거 하 고 연결 된 해제 `CObList` 메모리입니다.

```
void RemoveAll();
```

### <a name="remarks"></a>설명

목록에 수식이 이미 있으면 오류가 생성 됩니다.

요소를 제거 하는 경우는 `CObList`, 목록에서 개체 포인터를 제거 합니다. 개체 자체를 삭제 하려면 사용자의 책임입니다.

다음 표에서 다른 멤버와 유사한 함수 `CObList::RemoveAll`합니다.

|클래스|멤버 함수|
|-----------|---------------------|
|[CPtrList](../../mfc/reference/cptrlist-class.md)|**void RemoveAll( );**|
|[CStringList](../../mfc/reference/cstringlist-class.md)|**void RemoveAll( );**|

### <a name="example"></a>예제

참조 [CObList::CObList](#coblist) 목록은 `CAge` 클래스입니다.

[!code-cpp[NVC_MFCCollections#105](../../mfc/codesnippet/cpp/coblist-class_17.cpp)]

##  <a name="removeat"></a>  CObList::RemoveAt

이 목록에서 지정된 된 요소를 제거합니다.

```
void RemoveAt(POSITION position);
```

### <a name="parameters"></a>매개 변수

*position*<br/>
목록에서 제거할 요소의 위치입니다.

### <a name="remarks"></a>설명

요소를 제거 하는 경우는 `CObList`, 목록에서 개체 포인터를 제거 합니다. 개체 자체를 삭제 하려면 사용자의 책임입니다.

위치 값 목록에서 올바른 위치를 나타내도록 해야 합니다. 올바르지 않으면 Microsoft Foundation Class 라이브러리의 디버그 버전 어설션 합니다.

다음 표에서 다른 멤버와 유사한 함수 `CObList::RemoveAt`합니다.

|클래스|멤버 함수|
|-----------|---------------------|
|[CPtrList](../../mfc/reference/cptrlist-class.md)|**void RemoveAt( POSITION** *position* **);**|
|[CStringList](../../mfc/reference/cstringlist-class.md)|**void RemoveAt( POSITION** *position* **);**|

### <a name="example"></a>예제

  목록 반복 하는 동안 요소를 제거 하는 동안 주의 해야 합니다. 다음 예제에서는 유효한 보장 하는 제거 기법 **위치** 에 대 한 값 [GetNext](#getnext)합니다.

참조 [CObList::CObList](#coblist) 목록은 `CAge` 클래스입니다.

[!code-cpp[NVC_MFCCollections#106](../../mfc/codesnippet/cpp/coblist-class_18.cpp)]

이 프로그램의 결과 아래와 같습니다.

`RemoveAt example: A CObList with 2 elements`

`a CAge at $4C1E 65`

`a CAge at $4B22 21`

##  <a name="removehead"></a>  CObList::RemoveHead

목록 헤드에서 요소를 제거 하 고에 대 한 포인터를 반환 합니다.

```
CObject* RemoveHead();
```

### <a name="return-value"></a>반환 값

`CObject` 목록 헤드에 이전에 대 한 포인터입니다.

### <a name="remarks"></a>설명

호출 하기 전에 비어 있지 않은지 확인 해야 `RemoveHead`합니다. 목록이 비어 있으면 Microsoft Foundation Class 라이브러리의 디버그 버전 어설션 합니다. 사용 하 여 [IsEmpty](#isempty) 목록 요소에 있는지 확인 합니다.

다음 표에서 다른 멤버와 유사한 함수 `CObList::RemoveHead`합니다.

|클래스|멤버 함수|
|-----------|---------------------|
|[CPtrList](../../mfc/reference/cptrlist-class.md)|**void\* RemoveHead( );**|
|[CStringList](../../mfc/reference/cstringlist-class.md)|**CString RemoveHead( );**|

### <a name="example"></a>예제

참조 [CObList::CObList](#coblist) 목록은 `CAge` 클래스입니다.

[!code-cpp[NVC_MFCCollections#107](../../mfc/codesnippet/cpp/coblist-class_19.cpp)]

##  <a name="removetail"></a>  CObList::RemoveTail

목록의 꼬리에서 요소를 제거 하 고에 대 한 포인터를 반환 합니다.

```
CObject* RemoveTail();
```

### <a name="return-value"></a>반환 값

목록의 끝에 있는 개체에 대 한 포인터입니다.

### <a name="remarks"></a>설명

호출 하기 전에 비어 있지 않은지 확인 해야 `RemoveTail`합니다. 목록이 비어 있으면 Microsoft Foundation Class 라이브러리의 디버그 버전 어설션 합니다. 사용 하 여 [IsEmpty](#isempty) 목록 요소에 있는지 확인 합니다.

다음 표에서 다른 멤버와 유사한 함수 `CObList::RemoveTail`합니다.

|클래스|멤버 함수|
|-----------|---------------------|
|[CPtrList](../../mfc/reference/cptrlist-class.md)|**void\* RemoveTail( );**|
|[CStringList](../../mfc/reference/cstringlist-class.md)|**CString RemoveTail( );**|

### <a name="example"></a>예제

참조 [CObList::CObList](#coblist) 목록은 `CAge` 클래스입니다.

[!code-cpp[NVC_MFCCollections#108](../../mfc/codesnippet/cpp/coblist-class_20.cpp)]

##  <a name="setat"></a>  CObList::SetAt

지정된 된 위치에 요소를 설정합니다.

```
void SetAt(
    POSITION pos,
    CObject* newElement);
```

### <a name="parameters"></a>매개 변수

*pos*<br/>
설정할 요소의 위치입니다.

*newElement*<br/>
`CObject` 목록에 쓸 수에 대 한 포인터입니다.

### <a name="remarks"></a>설명

위치 형식의 변수는 목록에 대 한 키입니다. 인덱스를 동일 하지 않습니다 하 고 작업할 수 없습니다. 위치 값을 직접. `SetAt` 기록 된 `CObject` 목록의 지정된 된 위치에 대 한 포인터입니다.

위치 값 목록에서 올바른 위치를 나타내도록 해야 합니다. 올바르지 않으면 Microsoft Foundation Class 라이브러리의 디버그 버전 어설션 합니다.

다음 표에서 다른 멤버와 유사한 함수 `CObList::SetAt`합니다.

|클래스|멤버 함수|
|-----------|---------------------|
|[CPtrList](../../mfc/reference/cptrlist-class.md)|**void SetAt( POSITION** `pos` **, const CString&** `newElement` **);**|
|[CStringList](../../mfc/reference/cstringlist-class.md)|**void SetAt( POSITION** `pos` **, LPCTSTR** `newElement` **);**|

### <a name="example"></a>예제

  참조 [CObList::CObList](#coblist) 목록은 `CAge` 클래스입니다.

[!code-cpp[NVC_MFCCollections#109](../../mfc/codesnippet/cpp/coblist-class_21.cpp)]

이 프로그램의 결과 아래와 같습니다.

```Output
SetAt example: A CObList with 2 elements
a CAge at $4D98 40
a CAge at $4DB8 65
```

## <a name="see-also"></a>참고자료

[CObject 클래스](../../mfc/reference/cobject-class.md)<br/>
[계층 구조 차트](../../mfc/hierarchy-chart.md)<br/>
[CStringList 클래스](../../mfc/reference/cstringlist-class.md)<br/>
[CPtrList 클래스](../../mfc/reference/cptrlist-class.md)
