---
title: CSemaphore 클래스
ms.date: 11/04/2016
f1_keywords:
- CSemaphore
- AFXMT/CSemaphore
- AFXMT/CSemaphore::CSemaphore
helpviewer_keywords:
- CSemaphore [MFC], CSemaphore
ms.assetid: 385fc7e4-8f86-4be2-85e1-d23b38c12f7f
ms.openlocfilehash: d5a0e4187107aaab7cedf4e7a0e2fc47b9f9f305
ms.sourcegitcommit: fcb48824f9ca24b1f8bd37d647a4d592de1cc925
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/15/2019
ms.locfileid: "69502579"
---
# <a name="csemaphore-class"></a>CSemaphore 클래스

클래스 `CSemaphore` 의 개체는 하나 이상의 프로세스에서 제한 된 수의 스레드가에 액세스 하도록 허용 하는 동기화 개체인 "세마포"를 나타냅니다 .이를 통해 현재 지정 된 리소스에 액세스 하는 스레드 수를 유지할 수 있습니다.

## <a name="syntax"></a>구문

```
class CSemaphore : public CSyncObject
```

## <a name="members"></a>멤버

### <a name="public-constructors"></a>Public 생성자

|이름|Description|
|----------|-----------------|
|[CSemaphore::CSemaphore](#csemaphore)|`CSemaphore` 개체를 생성합니다.|

## <a name="remarks"></a>설명

세마포는 제한 된 수의 사용자만 지원할 수 있는 공유 리소스에 대 한 액세스를 제어 하는 데 유용 합니다. `CSemaphore` 개체의 현재 개수는 허용 되는 추가 사용자 수입니다. 개수가 0에 도달 하면 `CSemaphore` 개체에 의해 제어 되는 리소스를 사용 하려는 모든 시도는 시스템 큐에 삽입 되 고 제한 시간이 초과 되거나 개수가 0 보다 증가 될 때까지 대기 합니다. 한 번에 제어 되는 리소스에 액세스할 수 있는 최대 사용자 수는 `CSemaphore` 개체를 생성 하는 동안 지정 됩니다.

`CSemaphore` 개체를 사용 하려면 필요한 경우 `CSemaphore` 개체를 구성 합니다. 대기 하려는 세마포의 이름을 지정 하 고 응용 프로그램에서 처음에이를 소유 해야 합니다. 그런 다음 생성자가를 반환할 때 세마포에 액세스할 수 있습니다. 제어 되는 리소스에 대 한 액세스가 완료 되 면 [CSyncObject:: Unlock](../../mfc/reference/csyncobject-class.md#unlock) 을 호출 합니다.

개체를 사용 하 `CSemaphore` 는 다른 방법은 제어 하려는 클래스에 형식의 `CSemaphore` 변수를 데이터 멤버로 추가 하는 것입니다. 제어 되는 개체를 생성 하는 동안 초기 액세스 수 `CSemaphore` , 최대 액세스 수, 세마포 이름 (프로세스 경계에서 사용 되는 경우) 및 필요한 보안 특성을 지정 하는 데이터 멤버의 생성자를 호출 합니다.

이러한 방식으로 개체에 `CSemaphore` 의해 제어 되는 리소스에 액세스 하려면 먼저 리소스의 액세스 멤버 함수에 [csinglelock](../../mfc/reference/csinglelock-class.md) 형식의 변수 또는 [CMultiLock](../../mfc/reference/cmultilock-class.md) 형식을 만듭니다. 그런 다음, lock 개체의 `Lock` 멤버 함수 (예 [: csinglelock:: lock](../../mfc/reference/csinglelock-class.md#lock))를 호출 합니다. 이 시점에서 스레드는 리소스에 대 한 액세스 권한을 획득 하 고 리소스를 해제 하 고 액세스할 때까지 기다리거나 리소스가 해제 되 고 시간이 초과 될 때까지 대기 하 여 리소스에 대 한 액세스 권한을 얻을 수 없습니다. 어떤 경우 든 리소스는 스레드로부터 안전한 방식으로 액세스 됩니다. 리소스를 해제 하려면 lock 개체의 멤버 함수 ( `Unlock` 예: [csinglelock:: Unlock](../../mfc/reference/csinglelock-class.md#unlock))를 사용 하거나 lock 개체가 범위를 벗어나는 것을 허용 합니다.

또는 `CSemaphore` 개체를 독립적으로 만들고, 제어 되는 리소스에 액세스 하기 전에 명시적으로 액세스할 수 있습니다. 이 메서드는 소스 코드를 읽는 사람에 게 더 명확 하지만 오류가 발생 하기 쉽습니다.

개체를 `CSemaphore` [사용 하는 방법에 대 한 자세한 내용은 다중 스레딩: 동기화 클래스](../../parallel/multithreading-how-to-use-the-synchronization-classes.md)를 사용 하는 방법

## <a name="inheritance-hierarchy"></a>상속 계층 구조

[CObject](../../mfc/reference/cobject-class.md)

[CSyncObject](../../mfc/reference/csyncobject-class.md)

`CSemaphore`

## <a name="requirements"></a>요구 사항

**헤더:** afxmt

##  <a name="csemaphore"></a>  CSemaphore::CSemaphore

명명 되거나 명명 되지 않은 `CSemaphore` 개체를 생성 합니다.

```
CSemaphore(
    LONG lInitialCount = 1,
    LONG lMaxCount = 1,
    LPCTSTR pstrName = NULL,
    LPSECURITY_ATTRIBUTES lpsaAttributes = NULL);
```

### <a name="parameters"></a>매개 변수

*lInitialCount*<br/>
세마포에 대 한 초기 사용 수입니다. 0 보다 크거나 같고 *lMaxCount*보다 작거나 같아야 합니다.

*lMaxCount*<br/>
세마포에 대 한 최대 사용량 수입니다. 0보다 커야 합니다.

*pstrName*<br/>
세마포의 이름입니다. 프로세스 경계를 넘어 세마포에 액세스할 수 있는 경우를 제공 해야 합니다. 이면 `NULL`개체에 이름이 지정 되지 않습니다. 이름이 기존 세마포에 일치 하면 생성자는 해당 이름의 세마포를 참조 하 `CSemaphore` 는 새 개체를 빌드합니다. 이름이 세마포가 아닌 기존 동기화 개체와 일치 하는 경우 생성이 실패 합니다.

*lpsaAttributes*<br/>
세마포 개체의 보안 특성입니다. 이 구조에 대 한 자세한 설명은 Windows SDK에서 [SECURITY_ATTRIBUTES](/previous-versions/windows/desktop/legacy/aa379560\(v=vs.85\)) 을 참조 하세요.

### <a name="remarks"></a>설명

`CSemaphore` 개체를 액세스 하거나 해제 하려면 [CMultiLock](../../mfc/reference/cmultilock-class.md) 또는 [csinglelock](../../mfc/reference/csinglelock-class.md) 개체를 만들고 해당 [잠금](../../mfc/reference/csinglelock-class.md#lock) 및 잠금 [해제](../../mfc/reference/csinglelock-class.md#unlock) 멤버 함수를 호출 합니다.

> [!IMPORTANT]
>  `CSemaphore` 개체를 만든 후에는 [GetLastError](/windows/win32/api/errhandlingapi/nf-errhandlingapi-getlasterror) 를 사용 하 여 뮤텍스가 아직 존재 하지 않는지 확인 합니다. 뮤텍스가 예기치 않게 존재 하는 경우 rogue 프로세스가 squatting을 나타낼 수 있으며 뮤텍스를 악의적으로 사용 하려고 할 수 있습니다. 이 경우에 권장 되는 보안 인식 절차는 핸들을 닫고 개체를 만드는 동안 오류가 발생 한 것 처럼 계속 진행 하는 것입니다.

## <a name="see-also"></a>참고자료

[CSyncObject 클래스](../../mfc/reference/csyncobject-class.md)<br/>
[계층 구조 차트](../../mfc/hierarchy-chart.md)
