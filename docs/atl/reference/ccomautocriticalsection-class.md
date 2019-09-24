---
title: CComAutoCriticalSection 클래스
ms.date: 11/04/2016
f1_keywords:
- CComAutoCriticalSection
- ATLCORE/ATL::CComAutoCriticalSection
- ATLCORE/ATL::CComAutoCriticalSection::CComAutoCriticalSection
helpviewer_keywords:
- CComAutoCriticalSection class
ms.assetid: 491a9d90-3398-4f90-88f5-fd2172a46b30
ms.openlocfilehash: 116c550f45bf622e7620b3a6f552339b4bcc24a7
ms.sourcegitcommit: fcb48824f9ca24b1f8bd37d647a4d592de1cc925
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/15/2019
ms.locfileid: "69497925"
---
# <a name="ccomautocriticalsection-class"></a>CComAutoCriticalSection 클래스

`CComAutoCriticalSection`임계 영역 개체의 소유권을 가져오고 해제 하는 메서드를 제공 합니다.

## <a name="syntax"></a>구문

```
class CComAutoCriticalSection : public CComCriticalSection
```

## <a name="members"></a>멤버

### <a name="public-constructors"></a>Public 생성자

|이름|Description|
|----------|-----------------|
|[CComAutoCriticalSection::CComAutoCriticalSection](#ccomautocriticalsection)|생성자입니다.|
|[CComAutoCriticalSection::~CComAutoCriticalSection](#dtor)|소멸자입니다.|

## <a name="remarks"></a>설명

`CComAutoCriticalSection`는 생성자에서 임계영역 개체를 자동으로 초기화 하는 것을 `CComAutoCriticalSection`제외하고는 [CComCriticalSection](../../atl/reference/ccomcriticalsection-class.md) 클래스와 유사합니다.

일반적으로 이름 [AutoCriticalSection](ccommultithreadmodel-class.md#autocriticalsection) `typedef`을 통해 `CComAutoCriticalSection`를 사용합니다. [CComMultiThreadModel](../../atl/reference/ccommultithreadmodel-class.md)를 사용하는 경우이 이름은 `CComAutoCriticalSection`를 참조합니다.

이 클래스 `Term` 를 사용 하는 경우 [CComCriticalSection](../../atl/reference/ccomcriticalsection-class.md) 의 및메서드를사용할수없습니다.`Init`

## <a name="inheritance-hierarchy"></a>상속 계층

[CComCriticalSection](../../atl/reference/ccomcriticalsection-class.md)

`CComAutoCriticalSection`

## <a name="requirements"></a>요구 사항

**헤더:**

##  <a name="ccomautocriticalsection"></a>  CComAutoCriticalSection::CComAutoCriticalSection

생성자입니다.

```
CComAutoCriticalSection();
```

### <a name="remarks"></a>설명

는 임계 영역 개체를 초기화 하는 Win32 함수 [InitializeCriticalSection](/windows/win32/api/synchapi/nf-synchapi-initializecriticalsection)를 호출 합니다.

##  <a name="dtor"></a>  CComAutoCriticalSection::~CComAutoCriticalSection

소멸자입니다.

```
~CComAutoCriticalSection() throw();
```

### <a name="remarks"></a>설명

소멸자는 임계 영역 개체에서 사용 하는 모든 시스템 리소스를 해제 하는 [DeleteCriticalSection](/windows/win32/api/synchapi/nf-synchapi-deletecriticalsection)를 호출 합니다.

## <a name="see-also"></a>참고자료

[CComFakeCriticalSection 클래스](../../atl/reference/ccomfakecriticalsection-class.md)<br/>
[클래스 개요](../../atl/atl-class-overview.md)<br/>
[CComCriticalSection 클래스](../../atl/reference/ccomcriticalsection-class.md)
