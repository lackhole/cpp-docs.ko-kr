---
title: accelerator_view_removed 클래스
ms.date: 03/27/2019
f1_keywords:
- accelerator_view_removed
- AMPRT/accelerator_view_removed
- AMPRT/Concurrency::accelerator_view_removed::accelerator_view_removed
- AMPRT/Concurrency::accelerator_view_removed::get_view_removed_reason
helpviewer_keywords:
- AMPRT/Concurrency::accelerator_view_removed::accelerator_view_removed Class
ms.assetid: 262446de-311c-454e-a5ed-e2aaced0d88a
ms.openlocfilehash: eddcf44966d197068113c5e7817dad37841261a3
ms.sourcegitcommit: 00e26915924869cd7eb3c971a7d0604388abd316
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/10/2019
ms.locfileid: "65524838"
---
# <a name="acceleratorviewremoved-class"></a>accelerator_view_removed 클래스

Windows 시간 초과 검색 및 복구 메커니즘으로 인해 내부 DirectX 호출이 실패할 때 throw되는 예외입니다.

## <a name="syntax"></a>구문

```
class accelerator_view_removed : public runtime_exception;
```

## <a name="members"></a>멤버

### <a name="public-constructors"></a>Public 생성자

|이름|설명|
|----------|-----------------|
|[accelerator_view_removed 생성자](#ctor)|`accelerator_view_removed` 클래스의 새 인스턴스를 초기화합니다.|

### <a name="public-methods"></a>Public 메서드

|이름|설명|
|----------|-----------------|
|[get_view_removed_reason](#get_view_removed_reason)|`accelerator_view` 개체 제거의 원인을 나타내는 HRESULT 오류 코드를 반환합니다.|

## <a name="inheritance-hierarchy"></a>상속 계층 구조

`exception`

`runtime_exception`

`out_of_memory`

## <a name="requirements"></a>요구 사항

**헤더:** amprt.h

**네임스페이스:** 동시성

## <a name="ctor"></a> accelerator_view_removed

새 인스턴스를 초기화 합니다 [accelerator_view_removed](accelerator-view-removed-class.md) 클래스입니다.

### <a name="syntax"></a>구문

```
explicit accelerator_view_removed(
    const char * message,
    HRESULT view_removed_reason ) throw();

explicit accelerator_view_removed(
    HRESULT view_removed_reason ) throw();
```

### <a name="parameters"></a>매개 변수

*message*<br/>
오류에 대한 설명입니다.

*view_removed_reason*<br/>
`accelerator_view` 개체 제거의 원인을 나타내는 HRESULT 오류 코드입니다.

### <a name="return-value"></a>반환 값

`accelerator_view_removed` 클래스의 새 인스턴스입니다.

## <a name="get_view_removed_reason"></a> get_view_removed_reason

`accelerator_view` 개체 제거의 원인을 나타내는 HRESULT 오류 코드를 반환합니다.

### <a name="syntax"></a>구문

```
HRESULT get_view_removed_reason() const throw();
```

## <a name="see-also"></a>참고자료

[Concurrency 네임스페이스(C++ AMP)](concurrency-namespace-cpp-amp.md)
