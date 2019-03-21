---
title: CStringData 클래스
ms.date: 11/04/2016
f1_keywords:
- CStringData
- ATLSIMPSTR/ATL::CStringData
- ATLSIMPSTR/ATL::AddRef
- ATLSIMPSTR/ATL::data
- ATLSIMPSTR/ATL::IsLocked
- ATLSIMPSTR/ATL::IsShared
- ATLSIMPSTR/ATL::Lock
- ATLSIMPSTR/ATL::Release
- ATLSIMPSTR/ATL::Unlock
- ATLSIMPSTR/ATL::nAllocLength
- ATLSIMPSTR/ATL::nDataLength
- ATLSIMPSTR/ATL::nRefs
- ATLSIMPSTR/ATL::pStringMgr
helpviewer_keywords:
- CStringData class
- shared classes, CStringData
ms.assetid: 4e31b5ca-3dbe-4fd5-b692-8211fbfb2593
ms.openlocfilehash: 5977d26cade89f2e70453d5184323958e99e54c4
ms.sourcegitcommit: dedd4c3cb28adec3793329018b9163ffddf890a4
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/11/2019
ms.locfileid: "57748517"
---
# <a name="cstringdata-class"></a>CStringData 클래스

이 클래스는 문자열 개체의 데이터를 나타냅니다.

## <a name="syntax"></a>구문

```
struct CStringData
```

## <a name="members"></a>멤버

### <a name="methods"></a>메서드

|||
|-|-|
|[AddRef](#addref)|문자열 데이터 개체의 참조 횟수를 증가 시킵니다.|
|[data](#data)|문자열 개체의 문자 데이터를 검색합니다.|
|[IsLocked](#islocked)|연결 된 문자열 개체의 버퍼를 잠겨 있는지 확인 합니다.|
|[IsShared](#isshared)|연결 된 문자열 개체의 버퍼는 현재 공유 하는 경우를 결정 합니다.|
|[잠금](#lock)|연결 된 문자열 개체의 버퍼를 잠급니다.|
|[릴리스](#release)|지정 된 문자열 개체를 해제합니다.|
|[잠금 해제](#unlock)|연결 된 문자열 개체의 버퍼를 잠금 해제합니다.|

### <a name="data-members"></a>데이터 멤버

|||
|-|-|
|[nAllocLength](#nalloclength)|할당 된 데이터의 길이 `XCHAR`(제외한, 종결 null) s|
|[nDataLength](#ndatalength)|현재 사용 되는 데이터의 길이 `XCHAR`(제외한, 종결 null) s|
|[nRefs](#nrefs)|개체의 현재 참조 횟수를 지정 합니다.|
|[pStringMgr](#pstringmgr)|이 문자열 개체의 문자열 관리자에 대 한 포인터입니다.|

## <a name="remarks"></a>설명

이 클래스 사용자 지정 문자열 관리자 구현 하는 개발자가만 사용 해야 합니다. 사용자 지정 문자열 관리자에 대 한 자세한 내용은 참조 하세요. [메모리 관리 및 CStringT](../../atl-mfc-shared/memory-management-with-cstringt.md)

이 클래스는 다양 한 종류의 정보와 같은 더 높은 문자열 개체를 사용 하 여 연결 된 데이터를 캡슐화 [CStringT](../../atl-mfc-shared/reference/cstringt-class.md)하십시오 [CSimpleStringT](../../atl-mfc-shared/reference/csimplestringt-class.md), 또는 [CFixedStringT](../../atl-mfc-shared/reference/cfixedstringt-class.md) 개체입니다. 해당 연결에 대 한 포인터를 포함 하는 모든 높은 문자열 개체 `CStringData` 개체에 같은 문자열 데이터 개체를 가리키도록 하는 여러 문자열 개체를 허용 합니다. 이 관계는 참조 횟수를 나타내는 (`nRefs`)의 `CStringData` 개체입니다.

> [!NOTE]
>  경우에 따라 문자열 형식 (같은 `CFixedString`) 둘 이상의 더 높은 문자열 개체를 사용 하 여 문자열 데이터 개체를 공유 하지 것입니다. 이 대 한 자세한 내용은 참조 하세요. [메모리 관리 및 CStringT](../../atl-mfc-shared/memory-management-with-cstringt.md)합니다.

이 데이터는 구성 됩니다.

- 메모리 관리자 (형식의 [IAtlStringMgr](../../atl-mfc-shared/reference/iatlstringmgr-class.md)) 문자열입니다.

- 현재 길이 ( [nDataLength](#ndatalength)) 문자열입니다.

- 할당 된 길이 ( [nAllocLength](#nalloclength)) 문자열입니다. 성능상의 이유로이 다를 수 있습니다에서 현재 문자열 길이

- 현재 참조 횟수 ( [nRefs](#nrefs))의 `CStringData` 개체입니다. 이 값은 문자열 개체의 수가 동일를 공유 하는 결정 하는 데 사용 됩니다 `CStringData` 개체입니다.

- 실제 문자 버퍼 ( [데이터](#data)) 문자열입니다.

   > [!NOTE]
   > 문자열 개체의 실제 문자 버퍼 문자열 관리자가 할당 되 고에 추가 된 `CStringData` 개체입니다.

## <a name="requirements"></a>요구 사항

**헤더:** atlsimpstr.h

##  <a name="addref"></a>  CStringData::AddRef

문자열 개체의 참조 횟수를 증가 시킵니다.

```
void AddRef() throw();
```

### <a name="remarks"></a>설명

문자열 개체의 참조 횟수를 증가 시킵니다.

> [!NOTE]
>  음수 문자열 버퍼 잠겨 있음을 나타내는 되므로 음수 참조 횟수를 사용 하 여 문자열에서이 메서드를 호출 하지 마십시오.

##  <a name="data"></a>  CStringData::data

String 개체의 문자 버퍼에 대 한 포인터를 반환합니다.

```
void* data() throw();
```

### <a name="return-value"></a>반환 값

문자열 개체의 문자 버퍼에 대 한 포인터입니다.

### <a name="remarks"></a>설명

연결 된 문자열 개체의 현재 문자 버퍼를 반환 하려면이 함수를 호출 합니다.

> [!NOTE]
>  이 버퍼에서 할당 되지 않습니다는 `CStringData` 개체 있지만 필요할 때 문자열 관리자가 있습니다. 할당 된 버퍼 문자열 데이터 개체에 추가 됩니다.

##  <a name="islocked"></a>  CStringData::IsLocked

문자 버퍼 잠겨 있는지 확인 합니다.

```
bool IsLocked() const throw();
```

### <a name="return-value"></a>반환 값

TRUE를 반환 하는 경우 버퍼는 잠겨 있습니다. 그렇지 않으면 FALSE입니다.

### <a name="remarks"></a>설명

현재 string 개체의 문자 버퍼 잠겨 있는지 확인 하려면이 함수를 호출 합니다.

##  <a name="isshared"></a>  CStringData::IsShared

문자 버퍼 공유 되는 경우를 결정 합니다.

```
bool IsShared() const throw();
```

### <a name="return-value"></a>반환 값

TRUE를 반환 하는 경우 버퍼 공유 상태 그렇지 않으면 FALSE입니다.

### <a name="remarks"></a>설명

문자열 데이터 개체의 문자 버퍼 현재 문자열의 여러 개체 간에 공유 되는지 확인 하려면이 함수를 호출 합니다.

##  <a name="lock"></a>  CStringData::Lock

연결 된 문자열 개체의 문자 버퍼를 잠급니다.

```
void Lock() throw();
```

### <a name="remarks"></a>설명

문자열 데이터 개체의 문자 버퍼를 잠그는이 함수를 호출 합니다. 잠금 및 잠금 해제는 개발자가 문자 버퍼에 대 한 직접 액세스 해야 할 경우에 사용 됩니다. 잠금의 좋은 예에 나타난은 [LockBuffer](../../atl-mfc-shared/reference/csimplestringt-class.md#lockbuffer) 및 [UnlockBuffer](../../atl-mfc-shared/reference/csimplestringt-class.md#unlockbuffer) 메서드 `CSimpleStringT`합니다.

> [!NOTE]
>  버퍼는 더 높은 문자열 개체 간에 공유 되지 경우 문자 버퍼를 잠글 수만 있습니다.

##  <a name="nalloclength"></a>  CStringData::nAllocLength

할당 된 문자 버퍼의 길이입니다.

```
int nAllocLength;
```

### <a name="remarks"></a>설명

할당 된 데이터 버퍼의 길이 저장 `XCHAR`s (제외한, 종결 null).

##  <a name="ndatalength"></a>  CStringData::nDataLength

문자열 개체의 현재 길이입니다.

```
int nDataLength;
```

### <a name="remarks"></a>설명

현재 사용 되는 데이터의 길이 저장 `XCHAR`s (제외한, 종결 null).

##  <a name="nrefs"></a>  CStringData::nRefs

문자열 데이터 개체의 참조 횟수입니다.

```
long nRefs;
```

### <a name="remarks"></a>설명

문자열 데이터 개체의 참조 횟수를 저장합니다. 이 수는 문자열 데이터 개체와 연관 된 높은 문자열 개체의 수를 나타냅니다. 음수 값을 문자열 데이터 개체가 현재 잠겨 있는지를 나타냅니다.

##  <a name="pstringmgr"></a>  CStringData::pStringMgr

연결 된 문자열 개체의 메모리 관리자입니다.

```
IAtlStringMgr* pStringMgr;
```

### <a name="remarks"></a>설명

연결 된 문자열 개체에 대 한 메모리 관리자를 저장합니다. 메모리 관리자와 문자열에 대 한 자세한 내용은 참조 하세요. [메모리 관리 및 CStringT](../../atl-mfc-shared/memory-management-with-cstringt.md)합니다.

##  <a name="release"></a>  CStringData::Release

문자열 데이터 개체의 참조 횟수를 감소 시킵니다.

```
void Release() throw();
```

### <a name="remarks"></a>설명

참조 횟수를 감소 시키기 위해이 함수를 호출 해제는 `CStringData` 참조 횟수가 0에 도달 하는 경우 구조체입니다. 이 문자열 개체가 삭제 되 고, 따라서 더 이상 문자열 데이터 개체를 참조할 때 일반적으로 수행 됩니다.

다음 코드를 호출 하는 예를 들어 `CStringData::Release` 와 연결 된 문자열 데이터 개체에 대 한 `str1`:

[!code-cpp[NVC_ATLMFC_Utilities#104](../../atl-mfc-shared/codesnippet/cpp/cstringdata-class_1.cpp)]

##  <a name="unlock"></a>  CStringData::Unlock

연결 된 문자열 개체의 문자 버퍼를 잠금 해제합니다.

```
void Unlock() throw();
```

### <a name="remarks"></a>설명

문자열 데이터 개체의 문자 버퍼를 잠금 해제 하려면이 함수를 호출 합니다. 버퍼를 잠금 해제 된 후을 공유할 수 있습니다 하 고 계산 될 수 참조 합니다.

> [!NOTE]
>  호출할 때마다 `Lock` 해당 호출을 통해 일치 해야 `Unlock`합니다.

개발자는 문자열 데이터를 공유 하지 확인 해야 하는 경우 잠금 및 잠금 해제 사용 됩니다. 잠금의 좋은 예에 나타난은 [LockBuffer](../../atl-mfc-shared/reference/csimplestringt-class.md#lockbuffer) 및 [UnlockBuffer](../../atl-mfc-shared/reference/csimplestringt-class.md#unlockbuffer) 메서드 `CSimpleStringT`합니다.

## <a name="see-also"></a>참고자료

[계층 구조 차트](../../mfc/hierarchy-chart.md)<br/>
[ATL/MFC 공유 클래스](../../atl-mfc-shared/atl-mfc-shared-classes.md)
