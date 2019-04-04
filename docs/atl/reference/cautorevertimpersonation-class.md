---
title: CAutoRevertImpersonation 클래스
ms.date: 11/04/2016
f1_keywords:
- CAutoRevertImpersonation
- ATLSECURITY/ATL::CAutoRevertImpersonation
- ATLSECURITY/ATL::CAutoRevertImpersonation::CAutoRevertImpersonation
- ATLSECURITY/ATL::CAutoRevertImpersonation::Attach
- ATLSECURITY/ATL::CAutoRevertImpersonation::Detach
- ATLSECURITY/ATL::CAutoRevertImpersonation::GetAccessToken
helpviewer_keywords:
- CAutoRevertImpersonation class
ms.assetid: 43732849-1940-4bd4-9d52-7a5698bb8838
ms.openlocfilehash: 78488fba080e397b06eb67ebe8039fb3e8d5e035
ms.sourcegitcommit: 5cecccba0a96c1b4ccea1f7a1cfd91f259cc5bde
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/01/2019
ms.locfileid: "58779380"
---
# <a name="cautorevertimpersonation-class"></a>CAutoRevertImpersonation 클래스

이 클래스 되돌립니다 [CAccessToken](../../atl/reference/caccesstoken-class.md) 범위를 벗어나면 nonimpersonating 상태 개체입니다.

## <a name="syntax"></a>구문

```
class CAutoRevertImpersonation
```

## <a name="members"></a>멤버

### <a name="public-constructors"></a>Public 생성자

|이름|설명|
|----------|-----------------|
|[CAutoRevertImpersonation::CAutoRevertImpersonation](#cautorevertimpersonation)|생성 된 `CAutoRevertImpersonation` 개체|
|[CAutoRevertImpersonation::~CAutoRevertImpersonation](#dtor)|개체를 제거 하 고 액세스 토큰 가장을 되돌립니다.|

### <a name="public-methods"></a>Public 메서드

|이름|설명|
|----------|-----------------|
|[CAutoRevertImpersonation::Attach](#attach)|액세스 토큰의 가장 되돌리기가 자동화합니다.|
|[CAutoRevertImpersonation::Detach](#detach)|자동 가장 되돌리기가 취소합니다.|
|[CAutoRevertImpersonation::GetAccessToken](#getaccesstoken)|이 개체와 연결 된 액세스 토큰 현재를 검색 합니다.|

## <a name="remarks"></a>설명

[액세스 토큰](/windows/desktop/SecAuthZ/access-tokens) 개체인 프로세스 또는 스레드의 보안 컨텍스트를 설명 하는 Windows NT 또는 Windows 2000 시스템에 로그온 한 각 사용자에 게 할당 됩니다. 이러한 액세스 토큰을 사용 하 여 나타낼 수는 `CAccessToken` 클래스입니다.

액세스 토큰을 가장 하는 데 필요한 경우가 있습니다. 이 클래스는 편의상 제공 되지만 액세스 토큰의 가장을 수행 하지 않습니다. nonimpersonated 상태로 자동 되돌리기가 수행합니다. 즉, 여러 가지 방법으로 액세스 토큰 가장을 수행할 수 있습니다.

Windows의 액세스 제어 모델에 대 한 소개를 참조 하세요 [Access Control](/windows/desktop/SecAuthZ/access-control) Windows SDK에 있습니다.

## <a name="requirements"></a>요구 사항

**헤더:** atlsecurity.h

##  <a name="attach"></a>  CAutoRevertImpersonation::Attach

액세스 토큰의 가장 되돌리기가 자동화합니다.

```
void Attach(const CAccessToken* pAT) throw();
```

### <a name="parameters"></a>매개 변수

*pAT*<br/>
주소를 [CAccessToken](../../atl/reference/caccesstoken-class.md) 개체를 자동으로 되돌릴 수

### <a name="remarks"></a>설명

경우에이 메서드를 사용 해야 합니다 [CAutoRevertImpersonation](../../atl/reference/cautorevertimpersonation-class.md) 개체는 NULL을 사용 하 여 만든 `CAccessToken` 포인터 이거나 [분리](#detach) 이전에 호출 되었습니다. 간단한 경우이 방법을 사용 하려면 필요 없는 합니다.

##  <a name="cautorevertimpersonation"></a>  CAutoRevertImpersonation::CAutoRevertImpersonation

`CAutoRevertImpersonation` 개체를 생성합니다.

```
CAutoRevertImpersonation(const CAccessToken* pAT) throw();
```

### <a name="parameters"></a>매개 변수

*pAT*<br/>
주소를 [CAccessToken](../../atl/reference/caccesstoken-class.md) 개체를 자동으로 되돌려집니다.

### <a name="remarks"></a>설명

액세스 토큰의 실제 가장에서 가급적를 만들기 전에 별도로 수행할 수 해야는 `CAutoRevertImpersonation` 개체입니다. 이 가장 시기에 자동으로 되돌릴 수는 `CAutoRevertImpersonation` 범위를 벗어나면 합니다.

##  <a name="dtor"></a>  CAutoRevertImpersonation::~CAutoRevertImpersonation

개체를 제거 하 고 액세스 토큰 가장을 되돌립니다.

```
~CAutoRevertImpersonation() throw();
```

### <a name="remarks"></a>설명

모든 현재 적용에 대 한 가장을 되돌립니다 합니다 [CAccessToken](../../atl/reference/caccesstoken-class.md) 생성 시 또는 제공 된 개체를 [연결](#attach) 메서드. 없으면 `CAccessToken` 는 연결 된 소멸자에 영향을 주지 않습니다.

##  <a name="detach"></a>  CAutoRevertImpersonation::Detach

자동 가장 되돌리기가 취소합니다.

```
const CAccessToken* Detach() throw();
```

### <a name="return-value"></a>반환 값

이전에 연결된 된 주소의 [CAccessToken](../../atl/reference/caccesstoken-class.md), 연결이 없습니다. 존재 하는 경우에 null입니다.

### <a name="remarks"></a>설명

호출 **분리** 방지 합니다 `CAutoRevertImpersonation` 개체에 적용 된 모든 가장 현재 되돌릴 합니다 [CAccessToken](../../atl/reference/caccesstoken-class.md) 이 개체와 연결 된 개체입니다. `CAutoRevertImpersonation` 영향을 주지 않습니다를 사용 하 여 제거 하거나 동일한 또는 다른 클라우드에 다시 연결할 수 `CAccessToken` 를 사용 하 여 개체 [연결](#attach)합니다.

##  <a name="getaccesstoken"></a>  CAutoRevertImpersonation::GetAccessToken

이 개체와 연결 된 액세스 토큰 현재를 검색 합니다.

```
const CAccessToken* GetAccessToken() throw();
```

### <a name="return-value"></a>반환 값

이전에 연결된 된 주소의 [CAccessToken](../../atl/reference/caccesstoken-class.md), 연결이 없습니다. 존재 하는 경우에 null입니다.

### <a name="remarks"></a>설명

가장의 되돌리기가 포함 하는 용도로이 메서드를 호출 하면 합니다 `CAccessToken` 개체를 [분리](#detach) 메서드를 대신 사용 해야 합니다.

## <a name="see-also"></a>참고자료

[ATLSecurity 샘플](../../overview/visual-cpp-samples.md)<br/>
[액세스 토큰](/windows/desktop/SecAuthZ/access-tokens)<br/>
[클래스 개요](../../atl/atl-class-overview.md)
