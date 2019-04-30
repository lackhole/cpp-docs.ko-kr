---
title: CDWordArray 클래스
ms.date: 11/04/2016
f1_keywords:
- CDWordArray
- AFXCOLL/CDWordArray
- AFXCOLL/CObArray::CObArray
- AFXCOLL/CObArray::Add
- AFXCOLL/CObArray::Append
- AFXCOLL/CObArray::Copy
- AFXCOLL/CObArray::ElementAt
- AFXCOLL/CObArray::FreeExtra
- AFXCOLL/CObArray::GetAt
- AFXCOLL/CObArray::GetCount
- AFXCOLL/CObArray::GetData
- AFXCOLL/CObArray::GetSize
- AFXCOLL/CObArray::GetUpperBound
- AFXCOLL/CObArray::InsertAt
- AFXCOLL/CObArray::IsEmpty
- AFXCOLL/CObArray::RemoveAll
- AFXCOLL/CObArray::RemoveAt
- AFXCOLL/CObArray::SetAt
- AFXCOLL/CObArray::SetAtGrow
- AFXCOLL/CObArray::SetSize
helpviewer_keywords:
- CObArray [MFC], CObArray
- CObArray [MFC], Add
- CObArray [MFC], Append
- CObArray [MFC], Copy
- CObArray [MFC], ElementAt
- CObArray [MFC], FreeExtra
- CObArray [MFC], GetAt
- CObArray [MFC], GetCount
- CObArray [MFC], GetData
- CObArray [MFC], GetSize
- CObArray [MFC], GetUpperBound
- CObArray [MFC], InsertAt
- CObArray [MFC], IsEmpty
- CObArray [MFC], RemoveAll
- CObArray [MFC], RemoveAt
- CObArray [MFC], SetAt
- CObArray [MFC], SetAtGrow
- CObArray [MFC], SetSize
ms.assetid: 581be11e-ced6-47d1-8679-e0b8e7d99494
ms.openlocfilehash: 8cc67e62d905710ba5d63bf93c7b8aa1bf50f69c
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62206131"
---
# <a name="cdwordarray-class"></a>CDWordArray 클래스

32비트 2배 워드를 지원합니다.

## <a name="syntax"></a>구문

```
class CDWordArray : public CObject
```

## <a name="members"></a>멤버

멤버 함수 `CDWordArray` 클래스의 멤버 함수와 비슷합니다 [CObArray](../../mfc/reference/cobarray-class.md)합니다. 이처럼 두 함수가 비슷하므로 `CObArray` 참조 설명서에서 멤버 함수 관련 사항을 확인할 수 있습니다. 표시 될 때마다를 `CObject` 포인터를 함수 매개 변수 또는 반환 값으로 대체 한 `DWORD`합니다.

`CObject* CObArray::GetAt( int <nIndex> ) const;`

예를 들어 위의 코드는

`DWORD CDWordArray::GetAt( int <nIndex> ) const;`

### <a name="public-constructors"></a>Public 생성자

|이름|설명|
|----------|-----------------|
|[CObArray::CObArray](../../mfc/reference/cobarray-class.md#cobarray)|빈 배열을 생성합니다.|

### <a name="public-methods"></a>Public 메서드

|이름|설명|
|----------|-----------------|
|[CObArray::Add](../../mfc/reference/cobarray-class.md#add)|배열 끝에 요소를 추가하고 필요하면 배열을 확장합니다.|
|[CObArray::Append](../../mfc/reference/cobarray-class.md#append)|배열에 다른 배열을 추가하고 필요하면 배열을 확장합니다.|
|[CObArray::Copy](../../mfc/reference/cobarray-class.md#copy)|배열에 다른 배열을 복사하고 필요하면 배열을 확장합니다.|
|[CObArray::ElementAt](../../mfc/reference/cobarray-class.md#elementat)|배열 내의 바이트에 대 한 임시 참조를 반환합니다.|
|[CObArray::FreeExtra](../../mfc/reference/cobarray-class.md#freeextra)|현재 상한을 초과하며 사용되지 않는 모든 메모리를 해제합니다.|
|[CObArray::GetAt](../../mfc/reference/cobarray-class.md#getat)|지정된 인덱스의 값을 반환합니다.|
|[CObArray::GetCount](../../mfc/reference/cobarray-class.md#getcount)|이 배열에 있는 요소의 수를 가져옵니다.|
|[CObArray::GetData](../../mfc/reference/cobarray-class.md#getdata)|배열의 요소에 대한 액세스를 허용합니다. NULL 일 수 있습니다.|
|[CObArray::GetSize](../../mfc/reference/cobarray-class.md#getsize)|이 배열에 있는 요소의 수를 가져옵니다.|
|[CObArray::GetUpperBound](../../mfc/reference/cobarray-class.md#getupperbound)|유효한 최대 인덱스를 반환합니다.|
|[CObArray::InsertAt](../../mfc/reference/cobarray-class.md#insertat)|지정한 인덱스에 요소 하나 또는 다른 배열의 모든 요소를 삽입합니다.|
|[CObArray::IsEmpty](../../mfc/reference/cobarray-class.md#isempty)|배열이 비어 있는지를 확인합니다.|
|[CObArray::RemoveAll](../../mfc/reference/cobarray-class.md#removeall)|이 배열의 모든 요소를 반환합니다.|
|[CObArray::RemoveAt](../../mfc/reference/cobarray-class.md#removeat)|특정 인덱스의 요소를 제거합니다.|
|[CObArray::SetAt](../../mfc/reference/cobarray-class.md#setat)|지정된 인덱스의 값을 설정합니다. 배열은 확장할 수 없습니다.|
|[CObArray::SetAtGrow](../../mfc/reference/cobarray-class.md#setatgrow)|지정된 인덱스의 값을 설정합니다. 필요한 경우 배열을 확장합니다.|
|[CObArray::SetSize](../../mfc/reference/cobarray-class.md#setsize)|이 배열에 포함된 요소의 수를 설정합니다.|

### <a name="public-operators"></a>Public 연산자

|이름|설명|
|----------|-----------------|
|[CObArray::operator \[ \]](../../mfc/reference/cobarray-class.md#operator_at)|지정한 인덱스에 있는 요소를 설정하거나 가져옵니다.|

## <a name="remarks"></a>설명

`CDWordArray`는 serialization 및 요소 덤프를 지원하기 위해 `IMPLEMENT_SERIAL` 매크로를 통합합니다. 2 배 워드 배열을 오버 로드 된 삽입을 사용 하 여 보관 파일에 저장 되는 경우 ( **<<**) 연산자 또는 `Serialize` 멤버 함수를 각 요소는 다시 직렬화 합니다.

> [!NOTE]
>  배열을 사용하기 전에 `SetSize`를 사용하여 배열 크기를 설정하고 배열에 대해 메모리를 할당합니다. `SetSize`를 사용하지 않는 경우 배열에 요소를 추가하면 배열이 자주 다시 할당되고 복사됩니다. 이처럼 다시 할당 및 복사가 자주 수행되면 효율성이 떨어지며 메모리가 조각화될 수 있습니다.

배열의 개별 요소에서 출력을 디버깅 해야 하는 수준의 설정 해야 합니다는 `CDumpContext` 개체 1 이상입니다.

사용 하 여 대 한 자세한 내용은 `CDWordArray`, 문서를 참조 하세요 [컬렉션](../../mfc/collections.md)합니다.

## <a name="requirements"></a>요구 사항

**헤더:** afxcoll.h

## <a name="see-also"></a>참고자료

[CObject 클래스](../../mfc/reference/cobject-class.md)<br/>
[계층 구조 차트](../../mfc/hierarchy-chart.md)<br/>
[CObArray 클래스](../../mfc/reference/cobarray-class.md)
