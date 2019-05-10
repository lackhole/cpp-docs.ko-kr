---
title: CCriticalSection 클래스
ms.date: 11/04/2016
f1_keywords:
- CCriticalSection
- AFXMT/CCriticalSection
- AFXMT/CCriticalSection::CCriticalSection
- AFXMT/CCriticalSection::Lock
- AFXMT/CCriticalSection::Unlock
- AFXMT/CCriticalSection::m_sect
helpviewer_keywords:
- CCriticalSection [MFC], CCriticalSection
- CCriticalSection [MFC], Lock
- CCriticalSection [MFC], Unlock
- CCriticalSection [MFC], m_sect
ms.assetid: f776f74b-5b0b-4f32-9c13-2b8e4a0d7b2b
ms.openlocfilehash: 2c89647afc8a9a8c6564d25afe20d48818a643f2
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62385380"
---
# <a name="ccriticalsection-class"></a>CCriticalSection 클래스

"임계 섹션" 나타냅니다-리소스 또는 코드 섹션에 액세스 하는 한 번에 하나의 스레드를 허용 하는 동기화 개체입니다.

## <a name="syntax"></a>구문

```
class CCriticalSection : public CSyncObject
```

## <a name="members"></a>멤버

### <a name="public-constructors"></a>Public 생성자

|이름|설명|
|----------|-----------------|
|[CCriticalSection::CCriticalSection](#ccriticalsection)|`CCriticalSection` 개체를 생성합니다.|

### <a name="public-methods"></a>Public 메서드

|이름|설명|
|----------|-----------------|
|[CCriticalSection::Lock](#lock)|에 대 한 액세스를 사용 하 여 `CCriticalSection` 개체입니다.|
|[CCriticalSection::Unlock](#unlock)|`CCriticalSection` 개체를 해제합니다.|

### <a name="public-operators"></a>Public 연산자

|이름|설명|
|----------|-----------------|
|[CCriticalSection::operator CRITICAL_SECTION *](#operator_critical_section_star)|내부 CRITICAL_SECTION 개체에 대 한 포인터를 검색합니다.|

### <a name="public-data-members"></a>공용 데이터 멤버

|이름|설명|
|----------|-----------------|
|[CCriticalSection::m_sect](#m_sect)|CRITICAL_SECTION 개체입니다.|

## <a name="remarks"></a>설명

임계 영역 데이터 또는 일부 다른 제어 리소스를 수정 하려면 한 번에 하나의 스레드만 수 하는 경우에 유용 합니다. 예를 들어, 연결 된 목록에 노드를 추가 합니다. 한 번에 하나의 스레드에 의해 에서만 허용 해야 하는 프로세스입니다. 사용 하 여는 `CCriticalSection` 한 번에 하나의 스레드만 목록에 액세스할 수만 연결된 리스트를 제어 하는 개체입니다.

> [!NOTE]
>  기능을 `CCriticalSection` 클래스는 실제 Win32 CRITICAL_SECTION 개체에 의해 제공 됩니다.

임계 영역 뮤텍스 대신 사용 됩니다 (참조 [CMutex](../../mfc/reference/cmutex-class.md)) 속도가 중요 한 시간과 리소스 프로세스 경계를 넘어 사용 되지 것입니다.

사용 하는 방법은 두 가지가 있습니다를 `CCriticalSection` 개체: 독립 실행형 및 클래스에 포함 합니다.

- 독립 실행형을 사용 하는 독립 실행형 방법 `CCriticalSection` 개체를 생성 합니다 `CCriticalSection` 필요할 때 개체입니다. 생성자에서 성공적으로 반환 된 후 명시적으로 호출 하 여 개체 잠금 [잠금](#lock)합니다. 호출 [잠금 해제](#unlock) 완료 되 면 중요 섹션에 액세스 합니다. 소스 코드를 읽는 사람에 게 명확 하 게 파악할 하는 동안이 메서드는 액세스 전후 중요 섹션을 잠금을 해제 해야 하는 대로 오류 발생 가능성이.

   사용 하는 것이 더 좋습니다 메서드는 [CSingleLock](../../mfc/reference/csinglelock-class.md) 클래스입니다. 또한를 `Lock` 및 `Unlock` 방법 이지만 비용이 있습니다 예외가 발생 하는 경우에 리소스를 잠금 해제에 대해 걱정할 필요가 없습니다.

- 메서드를 추가 하 여 여러 스레드를 사용 하 여 클래스를 공유할 수도 있습니다를 포함 한 `CCriticalSection`-클래스와 잠금이 필요한 경우 데이터 멤버 형식 데이터 멤버입니다.

사용 하 여 대 한 자세한 내용은 `CCriticalSection` 문서를 참조 하는 개체를 [다중 스레딩: 동기화 클래스 사용 방법](../../parallel/multithreading-how-to-use-the-synchronization-classes.md)합니다.

## <a name="inheritance-hierarchy"></a>상속 계층 구조

[CObject](../../mfc/reference/cobject-class.md)

[CSyncObject](../../mfc/reference/csyncobject-class.md)

`CCriticalSection`

## <a name="requirements"></a>요구 사항

**헤더:** afxmt.h

##  <a name="ccriticalsection"></a>  CCriticalSection::CCriticalSection

`CCriticalSection` 개체를 생성합니다.

```
CCriticalSection();
```

### <a name="remarks"></a>설명

에 액세스 하거나 릴리스를 `CCriticalSection` 개체를 만듭니다를 [CSingleLock](../../mfc/reference/csinglelock-class.md) 개체와 호출 해당 [잠금](../../mfc/reference/csinglelock-class.md#lock) 및 [잠금 해제](../../mfc/reference/csinglelock-class.md#unlock) 멤버 함수입니다. 경우는 `CCriticalSection` 호출, 개체를 독립 실행형으로 사용 되는 해당 [잠금 해제](#unlock) 멤버 함수를 해제 합니다.

메모리 예외를 필요한 시스템 메모리를 할당할 생성자가 실패 하는 경우 (형식이 [CMemoryException](../../mfc/reference/cmemoryexception-class.md)) 자동으로 throw 됩니다.

### <a name="example"></a>예제

  예를 참조 하세요 [CCriticalSection::Lock](#lock)합니다.

##  <a name="lock"></a>  CCriticalSection::Lock

임계 영역 개체에 액세스 하려면이 멤버 함수를 호출 합니다.

```
BOOL Lock();
BOOL Lock(DWORD dwTimeout);
```

### <a name="parameters"></a>매개 변수

*dwTimeout*<br/>
`Lock` 이 매개 변수 값을 무시합니다.

### <a name="return-value"></a>반환 값

함수가 성공 하면 0이 아닌 값 그렇지 않으면 0입니다.

### <a name="remarks"></a>설명

`Lock` 임계 영역 개체의 신호를 받을 때까지 반환 하지 것입니다는 차단 호출 (사용 가능).

일정 시간된 대기 필요한 경우 사용할 수는 [CMutex](../../mfc/reference/cmutex-class.md) 대신 개체를 `CCriticalSection` 개체입니다.

하는 경우 `Lock` 메모리 예외를 필요한 시스템 메모리를 할당 하지 못했습니다 (형식의 [CMemoryException](../../mfc/reference/cmemoryexception-class.md)) 자동으로 throw 됩니다.

### <a name="example"></a>예제

이 예제에서는 공유 리소스에 대 한 액세스를 제어 하 여 중첩 된 임계 방법을 보여 줍니다 (정적 `_strShared` 개체) 공유를 사용 하 여 `CCriticalSection` 개체입니다. `SomeMethod` 함수를 안전한 방식으로 공유 리소스를 업데이트 하는 방법을 보여 줍니다.

[!code-cpp[NVC_MFC_Utilities#11](../../mfc/codesnippet/cpp/ccriticalsection-class_1.h)]

##  <a name="m_sect"></a>  CCriticalSection::m_sect

모든 사용 되는 임계 영역 개체를 포함 `CCriticalSection` 메서드.

```
CRITICAL_SECTION m_sect;
```

##  <a name="operator_critical_section_star"></a>  CCriticalSection::operator CRITICAL_SECTION *

CRITICAL_SECTION 개체를 검색 합니다.

```
operator CRITICAL_SECTION*();
```

### <a name="remarks"></a>설명

내부 CRITICAL_SECTION 개체에 대 한 포인터를 검색 하려면이 함수를 호출 합니다.

##  <a name="unlock"></a>  CCriticalSection::Unlock

릴리스는 `CCriticalSection` 다른 스레드에서 사용에 대 한 개체입니다.

```
BOOL Unlock();
```

### <a name="return-value"></a>반환 값

0이 아닌 값을 `CCriticalSection` 스레드에서 개체를 소유 하 고 및 0이 고, 그렇지 않으면 릴리스 되었습니다.

### <a name="remarks"></a>설명

경우는 `CCriticalSection` 독립 실행형 되 `Unlock` 중요 섹션에 의해 제어 리소스 사용을 완료 한 후 바로 호출 해야 합니다. 경우는 [CSingleLock](../../mfc/reference/csinglelock-class.md) 개체를 사용 중인 `CCriticalSection::Unlock` 잠금 개체에서 호출 되며 `Unlock` 멤버 함수입니다.

### <a name="example"></a>예제

  예를 참조 하세요 [CCriticalSection::Lock](#lock)합니다.

## <a name="see-also"></a>참고자료

[CSyncObject 클래스](../../mfc/reference/csyncobject-class.md)<br/>
[계층 구조 차트](../../mfc/hierarchy-chart.md)<br/>
[CMutex 클래스](../../mfc/reference/cmutex-class.md)
