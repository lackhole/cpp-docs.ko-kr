---
title: progress_reporter 클래스
ms.date: 11/04/2016
f1_keywords:
- progress_reporter
- PPLTASKS/concurrency::progress_reporter
- PPLTASKS/concurrency::progress_reporter::progress_reporter
- PPLTASKS/concurrency::progress_reporter::report
helpviewer_keywords:
- progress_reporter class
ms.assetid: b836efab-2d05-4649-b6fa-d15236f1f813
ms.openlocfilehash: dac74085278418153ddec502f6257ce13885704d
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62394379"
---
# <a name="progressreporter-class"></a>progress_reporter 클래스

진행률 보고자 클래스를 사용하면 특정 형식의 진행률 알림을 보고할 수 있습니다. 각 progress_reporter 개체는 특정 비동기 작업이나 연산에 바인딩됩니다.

## <a name="syntax"></a>구문

```
template<typename _ProgressType>
class progress_reporter;
```

#### <a name="parameters"></a>매개 변수

*_ProgressType*<br/>
진행률 보고자를 통해 보고되는 각 진행률 알림의 페이로드 형식입니다.

## <a name="members"></a>멤버

### <a name="public-constructors"></a>Public 생성자

|이름|설명|
|----------|-----------------|
|[progress_reporter](#ctor)||

### <a name="public-methods"></a>Public 메서드

|이름|설명|
|----------|-----------------|
|[report](#report)|이 진행률 보고자가 바인딩된 비동기 작업이나 연산에 진행률 보고서를 보냅니다.|

## <a name="remarks"></a>설명

이 유형은 Windows 런타임 앱에 사용할 수만 합니다.

## <a name="inheritance-hierarchy"></a>상속 계층 구조

`progress_reporter`

## <a name="requirements"></a>요구 사항

**헤더:** ppltasks.h

**네임스페이스:** 동시성

##  <a name="ctor"></a> progress_reporter

```
progress_reporter();
```

##  <a name="report"></a> 보고서

이 진행률 보고자가 바인딩된 비동기 작업이나 연산에 진행률 보고서를 보냅니다.

```
void report(const _ProgressType& val) const;
```

### <a name="parameters"></a>매개 변수

*val*<br/>
진행률 알림을 통해 보고할 페이로드입니다.

## <a name="see-also"></a>참고자료

[concurrency 네임스페이스](concurrency-namespace.md)
