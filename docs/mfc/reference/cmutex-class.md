---
title: CMutex 클래스
ms.date: 11/04/2016
f1_keywords:
- CMutex
- AFXMT/CMutex
- AFXMT/CMutex::CMutex
helpviewer_keywords:
- CMutex [MFC], CMutex
ms.assetid: 6330c050-4f01-4195-a099-2029b92f8cf1
ms.openlocfilehash: f85e562af9d048503be20d1ab5d219fe8d2d039f
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62373650"
---
# <a name="cmutex-class"></a>CMutex 클래스

"뮤텍스"를 나타내는-리소스에 한 스레드가 상호 배타적 액세스를 허용 하는 동기화 개체입니다.

## <a name="syntax"></a>구문

```
class CMutex : public CSyncObject
```

## <a name="members"></a>멤버

### <a name="public-constructors"></a>Public 생성자

|이름|설명|
|----------|-----------------|
|[CMutex::CMutex](#cmutex)|`CMutex` 개체를 생성합니다.|

## <a name="remarks"></a>설명

뮤텍스는 한 번에 하나의 스레드만 데이터 또는 일부 다른 제어 리소스를 수정할 수 있는 경우에 유용 합니다. 예를 들어, 연결 된 목록에 노드를 추가 합니다. 한 번에 하나의 스레드에 의해 에서만 허용 해야 하는 프로세스입니다. 사용 하 여는 `CMutex` 한 번에 하나의 스레드만 목록에 액세스할 수만 연결된 리스트를 제어 하는 개체입니다.

사용 하는 `CMutex` 개체를 생성 합니다 `CMutex` 필요할 때 개체입니다. 뮤텍스를 대기 하려는 이름을 지정 하 고 응용 프로그램에서 소유한 처음에 해야 합니다. 그런 다음 생성자를 반환 하는 경우 뮤텍스를 액세스할 수 있습니다. 호출 [CSyncObject::Unlock](../../mfc/reference/csyncobject-class.md#unlock) 완료 되 면 제어 리소스에 액세스 합니다.

사용 하는 대체 방법을 `CMutex` 개체 형식의 변수를 추가 하는 것 `CMutex` 제어 하려는 클래스를 데이터 멤버로 합니다. 제어 되는 개체의 생성 하는 동안의 생성자를 호출 합니다 `CMutex` 뮤텍스 처음을 소유 하는 뮤텍스의 (프로세스 경계를 넘어 사용) 하는 경우 이름 및 보안 특성을 원하는 경우 지정 된 데이터 멤버입니다.

리소스에 액세스 하 여 제어 `CMutex` 이런 방식으로 개체 유형의 변수를 먼저 만들어야 [CSingleLock](../../mfc/reference/csinglelock-class.md) 또는 형식 [CMultiLock](../../mfc/reference/cmultilock-class.md) 리소스의 액세스 멤버 함수에 있습니다. 다음은 잠금 개체를 호출 `Lock` 멤버 함수 (예를 들어 [CSingleLock::Lock](../../mfc/reference/csinglelock-class.md#lock)). 이 시점에서 스레드 중 하나는 리소스에 액세스할가 리소스를 해제 하 고 액세스를 얻기 또는 출시 될 리소스 및 리소스에 액세스 실패, 시간 초과 대 한 대기 될 때까지 기다립니다. 어떤 경우 든, 스레드로부터 안전한 방식으로 리소스에 액세스 합니다. 리소스를 해제 하려면 잠금 개체를 사용 하 여 `Unlock` 멤버 함수 (예를 들어 [CSingleLock::Unlock](../../mfc/reference/csinglelock-class.md#unlock)), 또는 범위 이탈 잠금 개체를 허용 합니다.

사용 하 여 대 한 자세한 내용은 `CMutex` 문서를 참조 하는 개체를 [다중 스레딩: 동기화 클래스 사용 방법](../../parallel/multithreading-how-to-use-the-synchronization-classes.md)합니다.

## <a name="inheritance-hierarchy"></a>상속 계층 구조

[CObject](../../mfc/reference/cobject-class.md)

[CSyncObject](../../mfc/reference/csyncobject-class.md)

`CMutex`

## <a name="requirements"></a>요구 사항

**헤더:** afxmt.h

##  <a name="cmutex"></a>  CMutex::CMutex

명명 되거나 명명 되지 않은에서는 `CMutex` 개체입니다.

```
CMutex(
    BOOL bInitiallyOwn = FALSE,
    LPCTSTR lpszName = NULL,
    LPSECURITY_ATTRIBUTES lpsaAttribute = NULL);
```

### <a name="parameters"></a>매개 변수

*bInitiallyOwn*<br/>
지정 하는 경우 스레드 만들기는 `CMutex` 개체 처음 뮤텍스에 의해 제어 되는 리소스에 액세스할 수 있습니다.

*lpszName*<br/>
`CMutex` 개체의 이름입니다. 동일한 이름의 다른 뮤텍스 있으면 *lpszName* 프로세스 경계를 넘어 개체를 사용할 경우 제공 해야 합니다. 하는 경우 **NULL**, 뮤텍스 명명 되지 것입니다. 생성자는 새 빌드를 기존 뮤텍스 이름 일치 하는 경우 `CMutex` 해당 이름의 뮤텍스를 참조 하는 개체입니다. 이름이 일치 뮤텍스 없는 기존 동기화 개체를 생성 하지 못합니다.

*lpsaAttribute*<br/>
뮤텍스 개체에 대 한 보안 특성입니다. 에 대 한 전체 설명은이 구조를 참조 하세요 [SECURITY_ATTRIBUTES](https://msdn.microsoft.com/library/windows/desktop/aa379560) Windows SDK에 있습니다.

### <a name="remarks"></a>설명

액세스 하거나 릴리스를 `CMutex` 개체를 만듭니다를 [CMultiLock](../../mfc/reference/cmultilock-class.md) 또는 [CSingleLock](../../mfc/reference/csinglelock-class.md) 개체와 호출 해당 [잠금](../../mfc/reference/csinglelock-class.md#lock) 하 고 [잠금 해제](../../mfc/reference/csinglelock-class.md#unlock) 멤버 함수입니다. 경우는 `CMutex` 개체를 독립 실행형으로 사용 되는, 호출 해당 `Unlock` 멤버 함수를 해제 합니다.

> [!IMPORTANT]
>  만든 후 합니다 `CMutex` 개체를 사용 하 여 [GetLastError](https://msdn.microsoft.com/library/windows/desktop/ms679360) 뮤텍스 이미 존재 하지 않으면 되도록 합니다. 뮤텍스 예기치 않게가 불량 프로세스 무단 점유 이며 뮤텍스를 악의적으로 사용 하려는 수 수를 나타낼 수 있습니다. 이 경우 권장 되는 보안에 민감한 프로시저 핸들을 닫고 개체를 만드는 오류가 발생 하는 경우에 따라 계속입니다.

## <a name="see-also"></a>참고자료

[CSyncObject 클래스](../../mfc/reference/csyncobject-class.md)<br/>
[계층 구조 차트](../../mfc/hierarchy-chart.md)
