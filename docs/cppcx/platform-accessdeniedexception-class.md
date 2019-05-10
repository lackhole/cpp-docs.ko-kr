---
title: Platform::AccessDeniedException 클래스
ms.date: 12/30/2016
ms.topic: reference
f1_keywords:
- VCCORLIB/Platform::AccessDeniedException
- VCCORLIB/Platform::AccessDeniedException::AccessDeniedException
helpviewer_keywords:
- Platform::AccessDeniedException
ms.assetid: 6ae2155b-7b16-4587-8d2d-da05eab4c7e9
ms.openlocfilehash: 4abbac977a256ff27f99caaf77393450d3ccf858
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62161773"
---
# <a name="platformaccessdeniedexception-class"></a>Platform::AccessDeniedException 클래스

리소스 또는 기능에 대한 액세스가 거부된 경우 throw됩니다.

## <a name="syntax"></a>구문

```cpp
public ref class AccessDeniedException : COMException,    IException,    IPrintable,   IEquatable
```

### <a name="remarks"></a>설명

이 예외가 발생하면 응용 프로그램의 패키지 매니페스트에 적절한 기능을 요청했고 필요한 선언을 만들었는지 확인하세요. 자세한 내용은 [COMException](../cppcx/platform-comexception-class.md) 클래스를 참조하세요.

### <a name="requirements"></a>요구 사항

**지원 되는 최소 클라이언트:** Windows 8

**지원 되는 최소 서버:** Windows Server 2012

**네임스페이스:** 플랫폼

**메타데이터:** platform.winmd

## <a name="see-also"></a>참고자료

[Platform::COMException 클래스](../cppcx/platform-comexception-class.md)
