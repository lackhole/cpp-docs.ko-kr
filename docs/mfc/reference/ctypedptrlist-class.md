---
title: CTypedPtrList 클래스
ms.date: 11/04/2016
f1_keywords:
- CTypedPtrList
- AFXTEMPL/CTypedPtrList
- AFXTEMPL/CTypedPtrList::AddHead
- AFXTEMPL/CTypedPtrList::AddTail
- AFXTEMPL/CTypedPtrList::GetAt
- AFXTEMPL/CTypedPtrList::GetHead
- AFXTEMPL/CTypedPtrList::GetNext
- AFXTEMPL/CTypedPtrList::GetPrev
- AFXTEMPL/CTypedPtrList::GetTail
- AFXTEMPL/CTypedPtrList::RemoveHead
- AFXTEMPL/CTypedPtrList::RemoveTail
- AFXTEMPL/CTypedPtrList::SetAt
helpviewer_keywords:
- CTypedPtrList [MFC], AddHead
- CTypedPtrList [MFC], AddTail
- CTypedPtrList [MFC], GetAt
- CTypedPtrList [MFC], GetHead
- CTypedPtrList [MFC], GetNext
- CTypedPtrList [MFC], GetPrev
- CTypedPtrList [MFC], GetTail
- CTypedPtrList [MFC], RemoveHead
- CTypedPtrList [MFC], RemoveTail
- CTypedPtrList [MFC], SetAt
ms.assetid: c273096e-1756-4340-864b-4a08b674a65e
ms.openlocfilehash: 9233e83a08fde87c15be5cc1c42a2f1dd3b56511
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62324508"
---
# <a name="ctypedptrlist-class"></a>CTypedPtrList 클래스

클래스 `CPtrList`의 개체에 대한 형식 안전 "래퍼"를 제공합니다.

## <a name="syntax"></a>구문

```
template<class BASE_CLASS, class TYPE>
class CTypedPtrList : public BASE_CLASS
```

#### <a name="parameters"></a>매개 변수

*BASE_CLASS*<br/>
형식화 된 포인터 목록 클래스의 기본 클래스 에 대 한 포인터 목록 클래스 여야 합니다 ( `CObList` 또는 `CPtrList`).

*TYPE*<br/>
기본 클래스 목록에 저장 된 요소의 형식입니다.

## <a name="members"></a>멤버

### <a name="public-methods"></a>Public 메서드

|이름|설명|
|----------|-----------------|
|[CTypedPtrList::AddHead](#addhead)|(새 헤드는) 목록 헤드에 요소 (또는 다른 목록의 모든 요소)를 추가 합니다.|
|[CTypedPtrList::AddTail](#addtail)|(새 비상은) 목록의 끝에 요소 (또는 다른 목록의 모든 요소)를 추가 합니다.|
|[CTypedPtrList::GetAt](#getat)|지정된 된 위치에 요소를 가져옵니다.|
|[CTypedPtrList::GetHead](#gethead)|(비워 둘 수 없습니다) 목록의 head 요소를 반환 합니다.|
|[CTypedPtrList::GetNext](#getnext)|반복에 대 한 다음 요소를 가져옵니다.|
|[CTypedPtrList::GetPrev](#getprev)|반복에 대 한 이전 요소를 가져옵니다.|
|[CTypedPtrList::GetTail](#gettail)|(비워 둘 수 없습니다) 목록의 꼬리 요소를 반환 합니다.|
|[CTypedPtrList::RemoveHead](#removehead)|목록 헤드에서 요소를 제거합니다.|
|[CTypedPtrList::RemoveTail](#removetail)|목록의 꼬리에서 요소를 제거합니다.|
|[CTypedPtrList::SetAt](#setat)|지정된 된 위치에 요소를 설정합니다.|

## <a name="remarks"></a>설명

사용 하는 경우 `CTypedPtrList` 대신 `CObList` 하거나 `CPtrList`, C++ 형식 검사 기능에 일치 하지 않는 포인터 형식으로 인 한 오류를 제거 하는 데 도움이 됩니다.

또한 합니다 `CTypedPtrList` 를 사용 하는 경우 캐스팅을 상당 부분을 수행 하는 래퍼 `CObList` 또는 `CPtrList`합니다.

때문에 모든 `CTypedPtrList` 함수는 인라인,이 템플릿을 사용 하 여 크게 영향을 주지 않습니다 크기 또는 코드의 속도.

목록에서 파생 `CObList` 를 serialize 할 수 있지만 파생 된 `CPtrList` 수 없습니다.

`CTypedPtrList` 개체를 삭제하거나 해당 요소를 제거할 경우 참조하는 엔터티가 아니라 포인터만 제거됩니다.

사용 하 여 대 한 자세한 내용은 `CTypedPtrList`, 문서를 참조 하세요 [컬렉션](../../mfc/collections.md) 하 고 [템플릿 기반 클래스](../../mfc/template-based-classes.md)합니다.

## <a name="example"></a>예제

이 예의 인스턴스를 만듭니다 `CTypedPtrList`, 하나의 개체를 추가, 디스크 목록을 serialize 및 다음 개체를 삭제 합니다.

[!code-cpp[NVC_MFCCollections#110](../../mfc/codesnippet/cpp/ctypedptrlist-class_1.cpp)]

[!code-cpp[NVC_MFCCollections#111](../../mfc/codesnippet/cpp/ctypedptrlist-class_2.cpp)]

## <a name="inheritance-hierarchy"></a>상속 계층 구조

`BASE_CLASS`

`_CTypedPtrList`

`CTypedPtrList`

## <a name="requirements"></a>요구 사항

**헤더:** afxtempl.h

##  <a name="addhead"></a>  CTypedPtrList::AddHead

이 멤버 함수 호출 `BASE_CLASS` **:: AddHead**합니다.

```
POSITION AddHead(TYPE newElement);
void AddHead(CTypedPtrList<BASE_CLASS, TYPE>* pNewList);
```

### <a name="parameters"></a>매개 변수

*TYPE*<br/>
기본 클래스 목록에 저장 된 요소의 형식입니다.

*newElement*<br/>
이 목록에 추가할 개체 포인터입니다. NULL 값이 허용 됩니다.

*BASE_CLASS*<br/>
형식화 된 포인터 목록 클래스의 기본 클래스 에 대 한 포인터 목록 클래스 여야 합니다 ( [CObList](../../mfc/reference/coblist-class.md) 하거나 [CPtrList](../../mfc/reference/cptrlist-class.md)).

*pNewList*<br/>
다른 포인터 [CTypedPtrList](../../mfc/reference/ctypedptrlist-class.md) 개체입니다. 에 있는 요소 *pNewList* 이 목록에 추가 됩니다.

### <a name="return-value"></a>반환 값

첫 번째 버전에는 새로 삽입 된 요소의 위치 값을 반환합니다.

### <a name="remarks"></a>설명

목록의 시작 하기 전에 새 요소를 추가 하는 첫 번째 버전입니다. 두 번째 버전은 다른 목록을 헤드 앞에 요소를 추가합니다.

##  <a name="addtail"></a>  CTypedPtrList::AddTail

이 멤버 함수 호출 `BASE_CLASS` **:: AddTail**합니다.

```
POSITION AddTail(TYPE newElement);
void AddTail(CTypedPtrList<BASE_CLASS, TYPE>* pNewList);
```

### <a name="parameters"></a>매개 변수

*TYPE*<br/>
기본 클래스 목록에 저장 된 요소의 형식입니다.

*newElement*<br/>
이 목록에 추가할 개체 포인터입니다. NULL 값이 허용 됩니다.

*BASE_CLASS*<br/>
형식화 된 포인터 목록 클래스의 기본 클래스 에 대 한 포인터 목록 클래스 여야 합니다 ( [CObList](../../mfc/reference/coblist-class.md) 하거나 [CPtrList](../../mfc/reference/cptrlist-class.md)).

*pNewList*<br/>
다른 포인터 [CTypedPtrList](../../mfc/reference/ctypedptrlist-class.md) 개체입니다. 에 있는 요소 *pNewList* 이 목록에 추가 됩니다.

### <a name="return-value"></a>반환 값

첫 번째 버전에는 새로 삽입 된 요소의 위치 값을 반환합니다.

### <a name="remarks"></a>설명

목록의 꼬리 후 새 요소를 추가 하는 첫 번째 버전입니다. 두 번째 버전 목록의 꼬리 다음 다른 목록과 요소를 추가합니다.

##  <a name="getat"></a>  CTypedPtrList::GetAt

위치 형식의 변수는 목록에 대 한 키입니다.

```
TYPE& GetAt(POSITION position);
TYPE GetAt(POSITION position) const;
```

### <a name="parameters"></a>매개 변수

*TYPE*<br/>
템플릿 매개 변수 목록에 저장 된 요소의 형식을 지정 합니다.

*position*<br/>
이전 반환한 위치 값 `GetHeadPosition` 또는 `Find` 멤버 함수 호출 합니다.

### <a name="return-value"></a>반환 값

목록에 대 한 포인터를 통해 액세스 하는 경우는 `const CTypedPtrList`, 한 다음 `GetAt` 템플릿 매개 변수로 지정 된 형식의 포인터를 반환 합니다 *형식*합니다. 함수 대입문의 오른쪽에만 사용할 수 있으며 따라서 목록 수정 되지 않도록에서 보호 합니다.

목록에 직접 또는 포인터를 통해 액세스 하는 경우는 `CTypedPtrList`, 한 다음 `GetAt` 템플릿 매개 변수로 지정 된 형식의 포인터에 대 한 참조를 반환 *형식*합니다. 이 대입문의 어느 쪽에 사용할 함수를 허용 하며 따라서 목록 항목을 수정할 수 있습니다.

### <a name="remarks"></a>설명

인덱스를 동일 하지 않습니다 하 고 작업할 수 없습니다. 위치 값을 직접. `GetAt` 검색 된 `CObject` 지정된 된 위치와 연결 된 포인터입니다.

위치 값 목록에서 올바른 위치를 나타내도록 해야 합니다. 올바르지 않으면 Microsoft Foundation Class 라이브러리의 디버그 버전 어설션 합니다.

이 인라인 함수 호출 `BASE_CLASS` **:: GetAt**합니다.

##  <a name="gethead"></a>  CTypedPtrList::GetHead

이 목록의 head 요소를 나타내는 포인터를 가져옵니다.

```
TYPE& GetHead();
TYPE GetHead() const;
```

### <a name="parameters"></a>매개 변수

*TYPE*<br/>
템플릿 매개 변수 목록에 저장 된 요소의 형식을 지정 합니다.

### <a name="return-value"></a>반환 값

목록에 대 한 포인터를 통해 액세스 하는 경우는 `const CTypedPtrList`, 한 다음 `GetHead` 템플릿 매개 변수로 지정 된 형식의 포인터를 반환 합니다 *형식*합니다. 함수 대입문의 오른쪽에만 사용할 수 있으며 따라서 목록 수정 되지 않도록에서 보호 합니다.

목록에 직접 또는 포인터를 통해 액세스 하는 경우는 `CTypedPtrList`, 한 다음 `GetHead` 템플릿 매개 변수로 지정 된 형식의 포인터에 대 한 참조를 반환 *형식*합니다. 이 대입문의 어느 쪽에 사용할 함수를 허용 하며 따라서 목록 항목을 수정할 수 있습니다.

### <a name="remarks"></a>설명

호출 하기 전에 비어 있지 않은지 확인 해야 `GetHead`합니다. 목록이 비어 있으면 Microsoft Foundation Class 라이브러리의 디버그 버전 어설션 합니다. 사용 하 여 [IsEmpty](../../mfc/reference/coblist-class.md#isempty) 목록 요소에 있는지 확인 합니다.

##  <a name="getnext"></a>  CTypedPtrList::GetNext

로 식별 되는 목록 요소를 가져옵니다 *rPosition*를 설정한 *rPosition* 목록에서 다음 항목의 위치 값입니다.

```
TYPE& GetNext(POSITION& rPosition);
TYPE GetNext(POSITION& rPosition) const;
```

### <a name="parameters"></a>매개 변수

*TYPE*<br/>
템플릿 매개 변수를이 목록에 포함 된 요소의 형식을 지정 합니다.

*rPosition*<br/>
이전 반환한 위치 값에 대 한 참조가 `GetNext`, `GetHeadPosition`, 또는 다른 멤버 함수 호출 합니다.

### <a name="return-value"></a>반환 값

목록에 대 한 포인터를 통해 액세스 하는 경우는 `const CTypedPtrList`, 한 다음 `GetNext` 템플릿 매개 변수로 지정 된 형식의 포인터를 반환 합니다 *형식*합니다. 함수 대입문의 오른쪽에만 사용할 수 있으며 따라서 목록 수정 되지 않도록에서 보호 합니다.

목록에 직접 또는 포인터를 통해 액세스 하는 경우는 `CTypedPtrList`, 한 다음 `GetNext` 템플릿 매개 변수로 지정 된 형식의 포인터에 대 한 참조를 반환 *형식*합니다. 이 대입문의 어느 쪽에 사용할 함수를 허용 하며 따라서 목록 항목을 수정할 수 있습니다.

### <a name="remarks"></a>설명

사용할 수 있습니다 `GetNext` 에 대 한 호출의 초기 위치를 설정한 경우 정방향 반복 루프에서 `GetHeadPosition` 또는 [CPtrList::Find](../../mfc/reference/coblist-class.md#find)합니다.

위치 값 목록에서 올바른 위치를 나타내도록 해야 합니다. 올바르지 않으면 Microsoft Foundation Class 라이브러리의 디버그 버전 어설션 합니다.

검색 된 요소가 있으면 목록에서 마지막으로 다음의 새 값 *rPosition* NULL로 설정 됩니다.

반복 하는 동안 요소를 제거 하는 것이 가능 합니다. 예를 참조 하세요 [CObList::RemoveAt](../../mfc/reference/coblist-class.md#removeat)합니다.

##  <a name="getprev"></a>  CTypedPtrList::GetPrev

로 식별 되는 목록 요소를 가져옵니다 *rPosition*를 설정한 *rPosition* 목록의 이전 항목의 위치 값입니다.

```
TYPE& GetPrev(POSITION& rPosition);
TYPE GetPrev(POSITION& rPosition) const;
```

### <a name="parameters"></a>매개 변수

*TYPE*<br/>
템플릿 매개 변수를이 목록에 포함 된 요소의 형식을 지정 합니다.

*rPosition*<br/>
이전 반환한 위치 값에 대 한 참조 `GetPrev` 또는 다른 멤버 함수 호출 합니다.

### <a name="return-value"></a>반환 값

목록에 대 한 포인터를 통해 액세스 하는 경우는 `const CTypedPtrList`, 한 다음 `GetPrev` 템플릿 매개 변수로 지정 된 형식의 포인터를 반환 합니다 *형식*합니다. 함수 대입문의 오른쪽에만 사용할 수 있으며 따라서 목록 수정 되지 않도록에서 보호 합니다.

목록에 직접 또는 포인터를 통해 액세스 하는 경우는 `CTypedPtrList`, 한 다음 `GetPrev` 템플릿 매개 변수로 지정 된 형식의 포인터에 대 한 참조를 반환 *형식*합니다. 이 대입문의 어느 쪽에 사용할 함수를 허용 하며 따라서 목록 항목을 수정할 수 있습니다.

### <a name="remarks"></a>설명

사용할 수 있습니다 `GetPrev` 에 대 한 호출의 초기 위치를 설정 하는 경우 역방향 반복 루프에서 `GetTailPosition` 또는 `Find`합니다.

위치 값 목록에서 올바른 위치를 나타내도록 해야 합니다. 올바르지 않으면 Microsoft Foundation Class 라이브러리의 디버그 버전 어설션 합니다.

검색 된 요소가 있으면 목록에서 첫 번째 다음의 새 값 *rPosition* NULL로 설정 됩니다.

##  <a name="gettail"></a>  CTypedPtrList::GetTail

이 목록의 head 요소를 나타내는 포인터를 가져옵니다.

```
TYPE& GetTail();
TYPE GetTail() const;
```

### <a name="parameters"></a>매개 변수

*TYPE*<br/>
템플릿 매개 변수 목록에 저장 된 요소의 형식을 지정 합니다.

### <a name="return-value"></a>반환 값

목록에 대 한 포인터를 통해 액세스 하는 경우는 `const CTypedPtrList`, 한 다음 `GetTail` 템플릿 매개 변수로 지정 된 형식의 포인터를 반환 합니다 *형식*합니다. 함수 대입문의 오른쪽에만 사용할 수 있으며 따라서 목록 수정 되지 않도록에서 보호 합니다.

목록에 직접 또는 포인터를 통해 액세스 하는 경우는 `CTypedPtrList`, 한 다음 `GetTail` 템플릿 매개 변수로 지정 된 형식의 포인터에 대 한 참조를 반환 *형식*합니다. 이 대입문의 어느 쪽에 사용할 함수를 허용 하며 따라서 목록 항목을 수정할 수 있습니다.

### <a name="remarks"></a>설명

호출 하기 전에 비어 있지 않은지 확인 해야 `GetTail`합니다. 목록이 비어 있으면 Microsoft Foundation Class 라이브러리의 디버그 버전 어설션 합니다. 사용 하 여 [IsEmpty](../../mfc/reference/coblist-class.md#isempty) 목록 요소에 있는지 확인 합니다.

##  <a name="removehead"></a>  CTypedPtrList::RemoveHead

목록 헤드에서 요소를 제거 하 고 반환 합니다.

```
TYPE RemoveHead();
```

### <a name="parameters"></a>매개 변수

*TYPE*<br/>
템플릿 매개 변수 목록에 저장 된 요소의 형식을 지정 합니다.

### <a name="return-value"></a>반환 값

목록 헤드에 이전에 대 한 포인터입니다. 템플릿 매개 변수로 지정 된 형식의 포인터가 *형식*합니다.

### <a name="remarks"></a>설명

호출 하기 전에 비어 있지 않은지 확인 해야 `RemoveHead`합니다. 목록이 비어 있으면 Microsoft Foundation Class 라이브러리의 디버그 버전 어설션 합니다. 사용 하 여 [IsEmpty](../../mfc/reference/coblist-class.md#isempty) 목록 요소에 있는지 확인 합니다.

##  <a name="removetail"></a>  CTypedPtrList::RemoveTail

목록의 꼬리에서 요소를 제거 하 고 반환 합니다.

```
TYPE RemoveTail();
```

### <a name="parameters"></a>매개 변수

*TYPE*<br/>
템플릿 매개 변수 목록에 저장 된 요소의 형식을 지정 합니다.

### <a name="return-value"></a>반환 값

목록 끝부분에 있는 이전에 대 한 포인터입니다. 템플릿 매개 변수로 지정 된 형식의 포인터가 *형식*합니다.

### <a name="remarks"></a>설명

호출 하기 전에 비어 있지 않은지 확인 해야 `RemoveTail`합니다. 목록이 비어 있으면 Microsoft Foundation Class 라이브러리의 디버그 버전 어설션 합니다. 사용 하 여 [IsEmpty](../../mfc/reference/coblist-class.md#isempty) 목록 요소에 있는지 확인 합니다.

##  <a name="setat"></a>  CTypedPtrList::SetAt

이 멤버 함수 호출 `BASE_CLASS` **:: SetAt**합니다.

```
void SetAt(POSITION pos, TYPE newElement);
```

### <a name="parameters"></a>매개 변수

*pos*<br/>
설정할 요소의 위치입니다.

*TYPE*<br/>
기본 클래스 목록에 저장 된 요소의 형식입니다.

*newElement*<br/>
목록에 쓸 개체 포인터입니다.

### <a name="remarks"></a>설명

위치 형식의 변수는 목록에 대 한 키입니다. 인덱스를 동일 하지 않습니다 하 고 작업할 수 없습니다. 위치 값을 직접. `SetAt` 개체 포인터를 목록의 지정된 된 위치에 씁니다.

위치 값 목록에서 올바른 위치를 나타내도록 해야 합니다. 올바르지 않으면 Microsoft Foundation Class 라이브러리의 디버그 버전 어설션 합니다.

설명, 자세한 [CObList::SetAt](../../mfc/reference/coblist-class.md#setat)합니다.

## <a name="see-also"></a>참고자료

[MFC 샘플 수집](../../overview/visual-cpp-samples.md)<br/>
[계층 구조 차트](../../mfc/hierarchy-chart.md)<br/>
[CPtrList 클래스](../../mfc/reference/cptrlist-class.md)<br/>
[CObList 클래스](../../mfc/reference/coblist-class.md)
