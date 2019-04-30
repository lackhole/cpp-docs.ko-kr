---
title: CSecurityAttributes 클래스
ms.date: 11/04/2016
f1_keywords:
- CSecurityAttributes
- ATLSECURITY/ATL::CSecurityAttributes
- ATLSECURITY/ATL::CSecurityAttributes::CSecurityAttributes
- ATLSECURITY/ATL::CSecurityAttributes::Set
helpviewer_keywords:
- CSecurityAttributes class
ms.assetid: a094880c-52e1-4a28-97ff-752d5869908e
ms.openlocfilehash: 66188a2c944379cfae813220937ac1e7e98fb41d
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62278035"
---
# <a name="csecurityattributes-class"></a>CSecurityAttributes 클래스

이 클래스는 보안 특성 구조에 대 한 씬 래퍼입니다.

> [!IMPORTANT]
>  이 클래스 및 해당 멤버는 Windows 런타임에서 실행 되는 응용 프로그램에서 사용할 수 없습니다.

## <a name="syntax"></a>구문

```
class CSecurityAttributes : public SECURITY_ATTRIBUTES
```

## <a name="members"></a>멤버

### <a name="public-constructors"></a>Public 생성자

|이름|설명|
|----------|-----------------|
|[CSecurityAttributes::CSecurityAttributes](#csecurityattributes)|생성자입니다.|

### <a name="public-methods"></a>Public 메서드

|이름|설명|
|----------|-----------------|
|[CSecurityAttributes::Set](#set)|특성을 설정 하려면이 메서드는 `CSecurityAttributes` 개체입니다.|

## <a name="remarks"></a>설명

합니다 `SECURITY_ATTRIBUTES` 구조에 포함 된를 [보안 설명자](/windows/desktop/api/winnt/ns-winnt-_security_descriptor) 개체의 생성에 사용 되며이 구조를 지정 하 여 검색 핸들을 상속할 수 인지 여부를 지정 합니다.

Windows의 액세스 제어 모델에 대 한 소개를 참조 하세요 [Access Control](/windows/desktop/SecAuthZ/access-control) Windows SDK에 있습니다.

## <a name="inheritance-hierarchy"></a>상속 계층 구조

`SECURITY_ATTRIBUTES`

`CSecurityAttributes`

## <a name="requirements"></a>요구 사항

**헤더:** atlsecurity.h

##  <a name="csecurityattributes"></a>  CSecurityAttributes::CSecurityAttributes

생성자입니다.

```
CSecurityAttributes() throw();
explicit CSecurityAttributes(const CSecurityDesc& rSecurityDescriptor, bool bInheritsHandle = false) throw(...);
```

### <a name="parameters"></a>매개 변수

*rSecurityDescriptor*<br/>
보안 설명자에 대한 참조입니다.

*bInheritsHandle*<br/>
새 프로세스가 만들어질 때 반환된 핸들의 상속 여부를 지정합니다. 이 멤버가 true이면 새 프로세스가 핸들을 상속합니다.

##  <a name="set"></a>  CSecurityAttributes::Set

특성을 설정 하려면이 메서드는 `CSecurityAttributes` 개체입니다.

```
void Set(const CSecurityDesc& rSecurityDescriptor, bool bInheritHandle = false) throw(...);
```

### <a name="parameters"></a>매개 변수

*rSecurityDescriptor*<br/>
보안 설명자에 대한 참조입니다.

*bInheritHandle*<br/>
새 프로세스가 만들어질 때 반환된 핸들의 상속 여부를 지정합니다. 이 멤버가 true이면 새 프로세스가 핸들을 상속합니다.

### <a name="remarks"></a>설명

이 메서드는 생성자가 초기화 된 `CSecurityAttributes` 개체입니다.

## <a name="see-also"></a>참고자료

[보안 샘플](../../overview/visual-cpp-samples.md)<br/>
[SECURITY_ATTRIBUTES](https://msdn.microsoft.com/library/windows/desktop/aa379560)<br/>
[보안 설명자](/windows/desktop/api/winnt/ns-winnt-_security_descriptor)<br/>
[클래스 개요](../../atl/atl-class-overview.md)<br/>
[보안 전역 함수](../../atl/reference/security-global-functions.md)
