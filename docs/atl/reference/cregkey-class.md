---
title: CRegKey 클래스
ms.date: 11/04/2016
f1_keywords:
- CRegKey
- ATLBASE/ATL::CRegKey
- ATLBASE/ATL::CRegKey::CRegKey
- ATLBASE/ATL::CRegKey::Attach
- ATLBASE/ATL::CRegKey::Close
- ATLBASE/ATL::CRegKey::Create
- ATLBASE/ATL::CRegKey::DeleteSubKey
- ATLBASE/ATL::CRegKey::DeleteValue
- ATLBASE/ATL::CRegKey::Detach
- ATLBASE/ATL::CRegKey::EnumKey
- ATLBASE/ATL::CRegKey::Flush
- ATLBASE/ATL::CRegKey::GetKeySecurity
- ATLBASE/ATL::CRegKey::NotifyChangeKeyValue
- ATLBASE/ATL::CRegKey::Open
- ATLBASE/ATL::CRegKey::QueryBinaryValue
- ATLBASE/ATL::CRegKey::QueryDWORDValue
- ATLBASE/ATL::CRegKey::QueryGUIDValue
- ATLBASE/ATL::CRegKey::QueryMultiStringValue
- ATLBASE/ATL::CRegKey::QueryQWORDValue
- ATLBASE/ATL::CRegKey::QueryStringValue
- ATLBASE/ATL::CRegKey::QueryValue
- ATLBASE/ATL::CRegKey::RecurseDeleteKey
- ATLBASE/ATL::CRegKey::SetBinaryValue
- ATLBASE/ATL::CRegKey::SetDWORDValue
- ATLBASE/ATL::CRegKey::SetGUIDValue
- ATLBASE/ATL::CRegKey::SetKeySecurity
- ATLBASE/ATL::CRegKey::SetKeyValue
- ATLBASE/ATL::CRegKey::SetMultiStringValue
- ATLBASE/ATL::CRegKey::SetQWORDValue
- ATLBASE/ATL::CRegKey::SetStringValue
- ATLBASE/ATL::CRegKey::SetValue
- ATLBASE/ATL::CRegKey::m_hKey
- ATLBASE/ATL::CRegKey::m_pTM
helpviewer_keywords:
- CRegKey class
- ATL, registry
- registry, deleting values
- registry, writing to
- registry, deleting keys
ms.assetid: 3afce82b-ba2c-4c1a-8404-dc969e1af74b
ms.openlocfilehash: 1215c66f1f40cfbc96b813d4eb5084f07698bc01
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62278087"
---
# <a name="cregkey-class"></a>CRegKey 클래스

이 클래스는 시스템 레지스트리에서 항목을 조작 하기 위한 메서드를 제공 합니다.

> [!IMPORTANT]
>  이 클래스 및 해당 멤버는 Windows 런타임에서 실행 되는 응용 프로그램에서 사용할 수 없습니다.

## <a name="syntax"></a>구문

```
class CRegKey
```

## <a name="members"></a>멤버

### <a name="public-constructors"></a>Public 생성자

|이름|설명|
|----------|-----------------|
|[CRegKey::CRegKey](#cregkey)|생성자입니다.|
|[CRegKey::~CRegKey](#dtor)|소멸자입니다.|

### <a name="public-methods"></a>Public 메서드

|이름|설명|
|----------|-----------------|
|[CRegKey::Attach](#attach)|HKEY입니다를 연결 하려면이 메서드를 호출 합니다 `CRegKey` 설정 하 여 개체를 [m_hKey](#m_hkey) 멤버에 대 한 핸들 `hKey`합니다.|
|[CRegKey::Close](#close)|해제 하려면이 메서드를 호출 합니다 [m_hKey](#m_hkey) 멤버 처리 하 고 NULL로 설정 합니다.|
|[CRegKey::Create](#create)|하위 키로 존재 하지 않는 경우 지정된 된 키를 만들려면이 메서드를 호출할 `hKeyParent`합니다.|
|[CRegKey::DeleteSubKey](#deletesubkey)|레지스트리에서 지정된 된 키를 제거 하려면이 메서드를 호출 합니다.|
|[CRegKey::DeleteValue](#deletevalue)|값 필드를 제거 하려면이 메서드를 호출 [m_hKey](#m_hkey)합니다.|
|[CRegKey::Detach](#detach)|분리 하려면이 메서드를 호출 합니다 [m_hKey](#m_hkey) 멤버 핸들 합니다 `CRegKey` 개체 및 설정 `m_hKey` NULL로.|
|[CRegKey::EnumKey](#enumkey)|열린 레지스트리 키의 하위 키를 열거 하는이 메서드를 호출 합니다.|
|[CRegKey::Flush](#flush)|레지스트리에 모든 열린 레지스트리 키의 특성을 작성 하려면이 메서드를 호출 합니다.|
|[CRegKey::GetKeySecurity](#getkeysecurity)|열린 레지스트리 키를 보호 하는 보안 설명자의 복사본을 검색 하려면이 메서드를 호출 합니다.|
|[CRegKey::NotifyChangeKeyValue](#notifychangekeyvalue)|이 메서드는 특성 또는 열린 레지스트리 키의 내용을 변경 하는 방법에 대 한 호출자에 게를 알립니다.|
|[CRegKey::Open](#open)|지정된 된 키를 열고 설정 하려면이 메서드를 호출 [m_hKey](#m_hkey) 이 키의 핸들입니다.|
|[CRegKey::QueryBinaryValue](#querybinaryvalue)|지정 된 값 이름에 대 한 이진 데이터를 검색 하려면이 메서드를 호출 합니다.|
|[CRegKey::QueryDWORDValue](#querydwordvalue)|지정 된 값 이름을 DWORD 데이터를 검색 하려면이 메서드를 호출 합니다.|
|[CRegKey::QueryGUIDValue](#queryguidvalue)|지정 된 값 이름에 대 한 GUID 데이터를 검색 하려면이 메서드를 호출 합니다.|
|[CRegKey::QueryMultiStringValue](#querymultistringvalue)|지정 된 값 이름에 대 한 다중 데이터를 검색 하려면이 메서드를 호출 합니다.|
|[CRegKey::QueryQWORDValue](#queryqwordvalue)|지정 된 값 이름을 QWORD 데이터를 검색 하려면이 메서드를 호출 합니다.|
|[CRegKey::QueryStringValue](#querystringvalue)|지정 된 값 이름에 대 한 문자열 데이터를 검색 하려면이 메서드를 호출 합니다.|
|[CRegKey::QueryValue](#queryvalue)|지정 된 값 필드에 대 한 데이터를 검색 하려면이 메서드를 호출 [m_hKey](#m_hkey)합니다. 이 메서드의 이전 버전이 더 이상 지원 되지 않으며 ATL_DEPRECATED로 표시 됩니다.|
|[CRegKey::RecurseDeleteKey](#recursedeletekey)|레지스트리에서 지정된 된 키를 제거 하 고 모든 하위 키를 명시적으로 제거 하려면이 메서드를 호출 합니다.|
|[CRegKey::SetBinaryValue](#setbinaryvalue)|레지스트리 키의 이진 값을 설정 하려면이 메서드를 호출 합니다.|
|[CRegKey::SetDWORDValue](#setdwordvalue)|레지스트리 키 DWORD 값을 설정 하려면이 메서드를 호출 합니다.|
|[CRegKey::SetGUIDValue](#setguidvalue)|레지스트리 키의 GUID 값을 설정 하려면이 메서드를 호출 합니다.|
|[CRegKey::SetKeySecurity](#setkeysecurity)|레지스트리 키의 보안을 설정 하려면이 메서드를 호출 합니다.|
|[CRegKey::SetKeyValue](#setkeyvalue)|지정된 된 키의 지정 된 값 필드에 데이터를 저장 하려면이 메서드를 호출 합니다.|
|[CRegKey::SetMultiStringValue](#setmultistringvalue)|레지스트리 키의 다중 문자열 값을 설정 하려면이 메서드를 호출 합니다.|
|[CRegKey::SetQWORDValue](#setqwordvalue)|레지스트리 키의 QWORD 값을 설정 하려면이 메서드를 호출 합니다.|
|[CRegKey::SetStringValue](#setstringvalue)|레지스트리 키의 문자열 값을 설정 하려면이 메서드를 호출 합니다.|
|[CRegKey::SetValue](#setvalue)|지정 된 값 필드에 데이터를 저장 하려면이 메서드를 호출 [m_hKey](#m_hkey)합니다. 이 메서드의 이전 버전이 더 이상 지원 되지 않으며 ATL_DEPRECATED로 표시 됩니다.|

### <a name="public-operators"></a>Public 연산자

|이름|설명|
|----------|-----------------|
|[CRegKey::operator HKEY](#operator_hkey)|변환 된 `CRegKey` 개체는 HKEY입니다.|
|[CRegKey::operator =](#operator_eq)|대입 연산자입니다.|

### <a name="public-data-members"></a>공용 데이터 멤버

|이름|설명|
|----------|-----------------|
|[CRegKey::m_hKey](#m_hkey)|연결 된 레지스트리 키의 핸들을 포함 합니다 `CRegKey` 개체입니다.|
|[CRegKey::m_pTM](#m_ptm)|에 대 한 포인터 `CAtlTransactionManager` 개체|

## <a name="remarks"></a>설명

`CRegKey` 만들기 및 삭제에 시스템 레지스트리 키와 값에 대 한 메서드를 제공 합니다. 레지스트리는 소프트웨어 버전 번호, 설치 된 하드웨어 및 COM 개체의 논리적-물리적 매핑 등 시스템 구성 요소에 대 한 정의 설치 관련 집합을 포함합니다.

`CRegKey` 지정된 된 컴퓨터에 대 한 시스템 레지스트리에 프로그래밍 인터페이스를 제공합니다. 예를 들어, 특정 레지스트리 키를 열려면 호출 `CRegKey::Open`합니다. 를 검색 하거나 데이터 값을 수정 하려면 호출 `CRegKey::QueryValue` 또는 `CRegKey::SetValue`, 각각. 키를 닫으려면 호출 `CRegKey::Close`합니다.

키를 닫으면 해당 레지스트리 데이터를 쓸 (플러시) 하드 디스크입니다. 이 프로세스는 몇 초 정도 걸릴 수 있습니다. 응용 프로그램 해야 명시적으로 레지스트리 데이터 하드 디스크에 쓸 경우 호출할 수 있습니다 합니다 [RegFlushKey](/windows/desktop/api/winreg/nf-winreg-regflushkey) Win32 함수입니다. 그러나 `RegFlushKey` 많은 시스템 리소스를 사용 하 고 반드시 필요한 경우에 호출 해야 합니다.

> [!IMPORTANT]
>  레지스트리 위치를 지정 하려면 호출자를 허용 하는 메서드는 신뢰할 수 없는 데이터를 읽을 수도 있습니다. 사용 하는 방법 [regqueryvalueex가](/windows/desktop/api/winreg/nf-winreg-regqueryvalueexa) 이 함수는 NULL 종료 문자열을 명시적으로 처리 하지 않는 고려해 야 합니다. 두 조건은 모두 호출 코드에서 확인 해야 합니다.

## <a name="requirements"></a>요구 사항

**헤더:** atlbase.h

##  <a name="attach"></a>  CRegKey::Attach

HKEY입니다를 연결 하려면이 메서드를 호출 합니다 `CRegKey` 설정 하 여 개체를 [m_hKey](#m_hkey) 멤버에 대 한 핸들 *hKey*합니다.

```
void Attach(HKEY hKey) throw();
```

### <a name="parameters"></a>매개 변수

*hKey*<br/>
레지스트리 키의 핸들입니다.

### <a name="remarks"></a>설명

`Attach` 경우에 어설션 `m_hKey` NULL이 아닌 합니다.

##  <a name="close"></a>  CRegKey::Close

해제 하려면이 메서드를 호출 합니다 [m_hKey](#m_hkey) 멤버 처리 하 고 NULL로 설정 합니다.

```
LONG Close() throw();
```

### <a name="return-value"></a>반환 값

성공 하면 반환 ERROR_SUCCESS입니다. 그렇지 않으면 오류 값을 반환합니다.

##  <a name="create"></a>  CRegKey::Create

하위 키로 존재 하지 않는 경우 지정된 된 키를 만들려면이 메서드를 호출할 *hKeyParent*합니다.

```
LONG Create(
    HKEY hKeyParent,
    LPCTSTR lpszKeyName,
    LPTSTR lpszClass = REG_NONE,
    DWORD dwOptions = REG_OPTION_NON_VOLATILE,
    REGSAM samDesired = KEY_READ | KEY_WRITE,
    LPSECURITY_ATTRIBUTES lpSecAttr = NULL,
    LPDWORD lpdwDisposition = NULL) throw();
```

### <a name="parameters"></a>매개 변수

*hKeyParent*<br/>
열린 키는의 핸들입니다.

*lpszKeyName*<br/>
만들거나 열 수는 키의 이름을 지정 합니다. 이 이름은는 하위 키를 사용 해야 합니다. *hKeyParent*합니다.

*lpszClass*<br/>
키를 만들거나 열 수의 클래스를 지정 합니다. 기본값은 REG_NONE 합니다.

*dwOptions*<br/>
키에 대 한 옵션입니다. 기본값은 REG_OPTION_NON_VOLATILE 합니다. 가능한 값 및 설명의 목록을 참조 하세요 [RegCreateKeyEx](/windows/desktop/api/winreg/nf-winreg-regcreatekeyexa) Windows SDK에 있습니다.

*samDesired*<br/>
키에 대 한 보안 액세스 합니다. 기본값은 KEY_READ &#124; KEY_WRITE 합니다. 가능한 값 및 설명의 목록을 참조 하세요. `RegCreateKeyEx`합니다.

*lpSecAttr*<br/>
에 대 한 포인터를 [SECURITY_ATTRIBUTES](https://msdn.microsoft.com/library/windows/desktop/aa379560) 키의 핸들을 자식 프로세스가 상속할 수 있는지 여부를 나타내는 구조입니다. 기본적으로이 매개 변수는 NULL (즉 핸들을 상속할 수 없습니다)입니다.

*lpdwDisposition*<br/>
[out] NULL이 아닌 경우 (키 있으며 생성 된) 경우 REG_CREATED_NEW_KEY 또는 REG_OPENED_EXISTING_KEY (경우 검색 키가 있고 열린).

### <a name="return-value"></a>반환 값

성공 하면 ERROR_SUCCESS를 반환 하 고 키를 엽니다. 메서드가 실패 하는 경우 반환 값은 WINERROR에 정의 된 0이 아닌 오류 코드입니다. 8.

### <a name="remarks"></a>설명

`Create` 설정 된 [m_hKey](#m_hkey) 이 키의 핸들에 대 한 멤버입니다.

##  <a name="cregkey"></a>  CRegKey::CRegKey

생성자입니다.

```
CRegKey() throw();
CRegKey(CRegKey& key) throw();
explicit CRegKey(HKEY hKey) throw();
CRegKey(CAtlTransactionManager* pTM) throw();
```

### <a name="parameters"></a>매개 변수

*key*<br/>
`CRegKey` 개체에 대한 참조입니다.

*hKey*<br/>
레지스트리 키에 대 한 핸들입니다.

*pTM*<br/>
CAtlTransactionManager 개체에 대한 포인터

### <a name="remarks"></a>설명

새 `CRegKey` 개체를 만듭니다. 기존 개체를 만들 수 있습니다 `CRegKey` 개체 또는 레지스트리 키에 대 한 핸들입니다.

##  <a name="dtor"></a>  CRegKey::~CRegKey

소멸자입니다.

```
~CRegKey() throw();
```

### <a name="remarks"></a>설명

소멸자 릴리스 `m_hKey`합니다.

##  <a name="deletesubkey"></a>  CRegKey::DeleteSubKey

레지스트리에서 지정된 된 키를 제거 하려면이 메서드를 호출 합니다.

```
LONG DeleteSubKey(LPCTSTR lpszSubKey) throw();
```

### <a name="parameters"></a>매개 변수

*lpszSubKey*<br/>
삭제할 키의 이름을 지정 합니다. 이 이름은는 하위 키를 사용 해야 합니다. [m_hKey](#m_hkey)합니다.

### <a name="return-value"></a>반환 값

성공 하면 ERROR_SUCCESS를 반환 합니다. 메서드가 실패 하는 경우 반환 값은 WINERROR에 정의 된 0이 아닌 오류 코드입니다. 8.

### <a name="remarks"></a>설명

`DeleteSubKey` 하위 키가 없는 하는 키만 삭제할 수 있습니다. 키에 하위 키가 있으면 호출 [RecurseDeleteKey](#recursedeletekey) 대신 합니다.

##  <a name="deletevalue"></a>  CRegKey::DeleteValue

값 필드를 제거 하려면이 메서드를 호출 [m_hKey](#m_hkey)합니다.

```
LONG DeleteValue(LPCTSTR lpszValue) throw();
```

### <a name="parameters"></a>매개 변수

*lpszValue*<br/>
제거할 값 필드를 지정 합니다.

### <a name="return-value"></a>반환 값

성공 하면 ERROR_SUCCESS를 반환 합니다. 메서드가 실패 하는 경우 반환 값은 WINERROR에 정의 된 0이 아닌 오류 코드입니다. 8.

##  <a name="detach"></a>  CRegKey::Detach

분리 하려면이 메서드를 호출 합니다 [m_hKey](#m_hkey) 멤버 핸들 합니다 `CRegKey` 개체 및 설정 `m_hKey` NULL로.

```
HKEY Detach() throw();
```

### <a name="return-value"></a>반환 값

HKEY 연관 된 `CRegKey` 개체입니다.

##  <a name="enumkey"></a>  CRegKey::EnumKey

열린 레지스트리 키의 하위 키를 열거 하는이 메서드를 호출 합니다.

```
LONG EnumKey(
    DWORD iIndex,
    LPTSTR pszName,
    LPDWORD pnNameLength,
    FILETIME* pftLastWriteTime = NULL) throw();
```

### <a name="parameters"></a>매개 변수

*iIndex*<br/>
하위 키 인덱스입니다. 이 매개 변수는 첫 번째 호출에 대 한 0 이어야 합니다 하 고 후속 호출에 대 한 증가

*pszName*<br/>
Null 종결 문자를 포함 하 여 하위 키의 이름을 받는 버퍼에 대 한 포인터입니다. 하위 키의 이름만 전체 키 계층이 아닌 버퍼에 복사 됩니다.

*pnNameLength*<br/>
지정 된 버퍼의 TCHARs에서 크기를 지정 하는 변수에 대 한 포인터를 *pszName* 매개 변수입니다. 이 크기는 null 종결 문자를 포함 해야 합니다. 반환 되 면 메서드를 가리키는 변수의 *pnNameLength* 버퍼에 저장 된 문자 수를 포함 합니다. 반환 된 수는 null 종결 문자를 포함 하지 않습니다.

*pftLastWriteTime*<br/>
시간을 수신 하는 변수에 대 한 포인터 열거 된 하위 키를 마지막으로 쓴 됩니다.

### <a name="return-value"></a>반환 값

메서드가 성공 하면 반환 값은 ERROR_SUCCESS입니다. 메서드가 실패 하는 경우 반환 값은 WINERROR에 정의 된 0이 아닌 오류 코드입니다. 8.

### <a name="remarks"></a>설명

하위 키를 열거 하려면 호출 `CRegKey::EnumKey` 0의 인덱스를 포함 합니다. 인덱스 값을 증분 시키고 메서드 ERROR_NO_MORE_ITEMS 반환 될 때까지 반복 합니다. 자세한 내용은 [RegEnumKeyEx](/windows/desktop/api/winreg/nf-winreg-regenumkeyexa) Windows SDK에 있습니다.

##  <a name="flush"></a>  CRegKey::Flush

레지스트리에 모든 열린 레지스트리 키의 특성을 작성 하려면이 메서드를 호출 합니다.

```
LONG Flush() throw();
```

### <a name="return-value"></a>반환 값

메서드가 성공 하면 반환 값은 ERROR_SUCCESS입니다. 메서드가 실패 하는 경우 반환 값은 WINERROR에 정의 된 0이 아닌 오류 코드입니다. 8.

### <a name="remarks"></a>설명

자세한 내용은 [RegEnumFlush](/windows/desktop/api/winreg/nf-winreg-regflushkey) Windows SDK에 있습니다.

##  <a name="getkeysecurity"></a>  CRegKey::GetKeySecurity

열린 레지스트리 키를 보호 하는 보안 설명자의 복사본을 검색 하려면이 메서드를 호출 합니다.

```
LONG GetKeySecurity(
    SECURITY_INFORMATION si,
    PSECURITY_DESCRIPTOR psd,
    LPDWORD pnBytes) throw();
```

### <a name="parameters"></a>매개 변수

*si*<br/>
합니다 [SECURITY_INFORMATION](/windows/desktop/SecAuthZ/security-information) 요청한 보안 정보를 나타내는 값입니다.

*psd*<br/>
요청 된 보안 설명자의 복사본을 받는 버퍼에 대 한 포인터입니다.

*pnBytes*<br/>
가리키는 버퍼의 바이트 크기 *psd*합니다.

### <a name="return-value"></a>반환 값

메서드가 성공 하면 반환 값은 ERROR_SUCCESS입니다. 메서드가 실패 하면 0이 아닌 오류 코드를 WINERROR에 정의 되어 반환이 됩니다. 8.

### <a name="remarks"></a>설명

자세한 내용은 [RegGetKeySecurity](/windows/desktop/api/winreg/nf-winreg-reggetkeysecurity)합니다.

##  <a name="m_hkey"></a>  CRegKey::m_hKey

연결 된 레지스트리 키의 핸들을 포함 합니다 `CRegKey` 개체입니다.

```
HKEY m_hKey;
```

##  <a name="m_ptm"></a>  CRegKey::m_pTM

`CAtlTransactionManager` 개체에 대한 포인터입니다.

```
CAtlTransactionManager* m_pTM;
```

### <a name="remarks"></a>설명

##  <a name="notifychangekeyvalue"></a>  CRegKey::NotifyChangeKeyValue

이 메서드는 특성 또는 열린 레지스트리 키의 내용을 변경 하는 방법에 대 한 호출자에 게를 알립니다.

```
LONG NotifyChangeKeyValue(
    BOOL bWatchSubtree,
    DWORD dwNotifyFilter,
    HANDLE hEvent,
    BOOL bAsync = TRUE) throw();
```

### <a name="parameters"></a>매개 변수

*bWatchSubtree*<br/>
지정된 된 키와 모든 하위 키 또는 지정된 된 키에만 변경 내용을 보고할 것인지 여부를 나타내는 플래그를 지정 합니다. 이 매개 변수가 TRUE 인 경우 메서드는 키 및 해당 하위 키의 변경 내용을 보고 합니다. 매개 변수가 FALSE 인 경우 메서드는 키만 변경을 보고 합니다.

*dwNotifyFilter*<br/>
보고 해야 하는 변경 내용을 제어 하는 플래그 집합을 지정 합니다. 이 매개 변수 값의 조합일 수 있습니다.

|값|의미|
|-----------|-------------|
|REG_NOTIFY_CHANGE_NAME|하위 키를 추가 하거나 삭제 하는 경우 호출자를 게 알립니다.|
|REG_NOTIFY_CHANGE_ATTRIBUTES|키 보안 설명자 정보 등의 특성 변경의 호출자를 게 알립니다.|
|REG_NOTIFY_CHANGE_LAST_SET|키의 값 변경의 호출자를 게 알립니다. 이 추가 또는 값을 삭제 하거나 기존 값을 변경 합니다.|
|REG_NOTIFY_CHANGE_SECURITY|키의 보안 설명자에 대 한 변경 내용이 호출자를 게 알립니다.|

*hEvent*<br/>
이벤트에 대한 핸들. 경우는 *bAsync* 매개 변수가 TRUE 인 메서드가 즉시 반환 하 고이 이벤트 신호를 보내 변경 내용을 보고 됩니다. 하는 경우 *bAsync* 은 FALSE *hEvent* 무시 됩니다.

*bAsync*<br/>
메서드가 변경 내용을 보고 하는 방법을 나타내는 플래그를 지정 합니다. 이 매개 변수가 TRUE 인 경우 메서드를 즉시 반환 하 고 지정된 된 이벤트 신호를 보내 변경 내용을 보고 합니다. 이 매개 변수가 FALSE 인 경우 변경 내용이 발생 될 때까지 메서드를 반환 하지 않습니다. 하는 경우 *hEvent* 유효한 이벤트를 지정 하지 않는 합니다 *bAsync* 매개 변수가 TRUE 인 경우.

### <a name="return-value"></a>반환 값

메서드가 성공 하면 반환 값은 ERROR_SUCCESS입니다. 메서드가 실패 하는 경우 반환 값은 WINERROR에 정의 된 0이 아닌 오류 코드입니다. 8.

### <a name="remarks"></a>설명

> [!NOTE]
>  이 메서드는 지정된 된 키가 삭제 되 면 호출자에 게를 알리지 않습니다.

자세한 내용과 샘플 프로그램에 대 한 참조 [RegNotifyChangeKeyValue](/windows/desktop/api/winreg/nf-winreg-regnotifychangekeyvalue)합니다.

##  <a name="open"></a>  CRegKey::Open

지정된 된 키를 열고 설정 하려면이 메서드를 호출 [m_hKey](#m_hkey) 이 키의 핸들입니다.

```
LONG Open(
    HKEY hKeyParent,
    LPCTSTR lpszKeyName,
    REGSAM samDesired = KEY_READ | KEY_WRITE) throw();
```

### <a name="parameters"></a>매개 변수

*hKeyParent*<br/>
열린 키는의 핸들입니다.

*lpszKeyName*<br/>
만들거나 열 수는 키의 이름을 지정 합니다. 이 이름은는 하위 키를 사용 해야 합니다. *hKeyParent*합니다.

*samDesired*<br/>
키에 대 한 보안 액세스 합니다. 기본값은 KEY_ALL_ACCESS 합니다. 가능한 값 및 설명의 목록을 참조 하세요 [RegCreateKeyEx](/windows/desktop/api/winreg/nf-winreg-regcreatekeyexa) Windows SDK에 있습니다.

### <a name="return-value"></a>반환 값

성공 하면 반환 ERROR_SUCCESS입니다. 그렇지 않으면 0이 아닌 오류 값 WINERROR에 정의 합니다. 8.

### <a name="remarks"></a>설명

경우는 *lpszkeyname 만들기* 매개 변수가 NULL 인지 지점 빈 문자열로 `Open` 로 식별 되는 키의 새 핸들을 열 *hKeyParent*, 이전에 열린된 핸들을 닫지 않고 합니다.

와 달리 [CRegKey::Create](#create), `Open` 존재 하지 않는 경우 지정된 된 키를 만들지 것입니다.

##  <a name="operator_hkey"></a>  CRegKey::operator HKEY

변환 된 `CRegKey` 개체는 HKEY입니다.

```
operator HKEY() const throw();
```

##  <a name="operator_eq"></a>  CRegKey::operator =

대입 연산자입니다.

```
CRegKey& operator= (CRegKey& key) throw();
```

### <a name="parameters"></a>매개 변수

*key*<br/>
복사할 키입니다.

### <a name="return-value"></a>반환 값

새 키에 대 한 참조를 반환합니다.

### <a name="remarks"></a>설명

이 연산자를 분리 *키* 현재 개체에서에 할당 된 `CRegKey` 개체를 대신 합니다.

##  <a name="querybinaryvalue"></a>  CRegKey::QueryBinaryValue

지정 된 값 이름에 대 한 이진 데이터를 검색 하려면이 메서드를 호출 합니다.

```
LONG QueryBinaryValue(
    LPCTSTR pszValueName,
    void* pValue,
    ULONG* pnBytes) throw();
```

### <a name="parameters"></a>매개 변수

*pszValueName*<br/>
쿼리 값의 이름을 포함 하는 null로 끝나는 문자열에 대 한 포인터입니다.

*pValue*<br/>
값의 데이터를 받는 버퍼에 대 한 포인터입니다.

*pnBytes*<br/>
버퍼를 바이트 단위로 크기를 지정 하는 변수에 대 한 포인터에서 가리키는 합니다 *pValue* 매개 변수입니다. 메서드가 반환 하는 경우이 변수는 버퍼에 복사 된 데이터의 크기를 포함 합니다.

### <a name="return-value"></a>반환 값

메서드가 성공 하는 경우에 ERROR_SUCCESS 반환 됩니다. 값을 읽는 메서드가 실패 하면, WINERROR에 정의 된 0이 아닌 오류 코드를 반환 합니다. 8. 참조 하는 데이터 형식 REG_BINARY 없으면 ERROR_INVALID_DATA 반환 됩니다.

### <a name="remarks"></a>설명

이 메서드를 활용 `RegQueryValueEx` 확인 올바른 형식의 데이터 반환 됩니다. 참조 [regqueryvalueex가](/windows/desktop/api/winreg/nf-winreg-regqueryvalueexa) 대 한 자세한 내용은 합니다.

> [!IMPORTANT]
>  이 메서드는 호출자가 잠재적으로 신뢰할 수 없는 데이터를 읽는 모든 레지스트리 위치를 지정할 수 있습니다. 또한 합니다 [regqueryvalueex가](/windows/desktop/api/winreg/nf-winreg-regqueryvalueexa) 이 메서드에서 사용 되는 함수는 NULL 종료 문자열을 명시적으로 처리 하지 않습니다. 두 조건은 모두 호출 코드에서 확인 해야 합니다.

##  <a name="querydwordvalue"></a>  CRegKey::QueryDWORDValue

지정 된 값 이름을 DWORD 데이터를 검색 하려면이 메서드를 호출 합니다.

```
LONG QueryDWORDValue(
    LPCTSTR pszValueName,
    DWORD& dwValue) throw();
```

### <a name="parameters"></a>매개 변수

*pszValueName*<br/>
쿼리 값의 이름을 포함 하는 null로 끝나는 문자열에 대 한 포인터입니다.

*dwValue*<br/>
DWORD를 받는 버퍼에 대 한 포인터입니다.

### <a name="return-value"></a>반환 값

메서드가 성공 하는 경우에 ERROR_SUCCESS 반환 됩니다. 값을 읽는 메서드가 실패 하면, WINERROR에 정의 된 0이 아닌 오류 코드를 반환 합니다. 8. 참조 하는 데이터 형식 REG_DWORD 없으면 ERROR_INVALID_DATA 반환 됩니다.

### <a name="remarks"></a>설명

이 메서드를 활용 `RegQueryValueEx` 확인 올바른 형식의 데이터 반환 됩니다. 참조 [regqueryvalueex가](/windows/desktop/api/winreg/nf-winreg-regqueryvalueexa) 대 한 자세한 내용은 합니다.

> [!IMPORTANT]
>  이 메서드는 호출자가 잠재적으로 신뢰할 수 없는 데이터를 읽는 모든 레지스트리 위치를 지정할 수 있습니다. 또한 합니다 [regqueryvalueex가](/windows/desktop/api/winreg/nf-winreg-regqueryvalueexa) 이 메서드에서 사용 되는 함수는 NULL 종료 문자열을 명시적으로 처리 하지 않습니다. 두 조건은 모두 호출 코드에서 확인 해야 합니다.

##  <a name="queryguidvalue"></a>  CRegKey::QueryGUIDValue

지정 된 값 이름에 대 한 GUID 데이터를 검색 하려면이 메서드를 호출 합니다.

```
LONG QueryGUIDValue(
    LPCTSTR pszValueName,
    GUID& guidValue) throw();
```

### <a name="parameters"></a>매개 변수

*pszValueName*<br/>
쿼리 값의 이름을 포함 하는 null로 끝나는 문자열에 대 한 포인터입니다.

*guidValue*<br/>
GUID를 수신 하는 변수에 대 한 포인터입니다.

### <a name="return-value"></a>반환 값

메서드가 성공 하는 경우에 ERROR_SUCCESS 반환 됩니다. 값을 읽는 메서드가 실패 하면, WINERROR에 정의 된 0이 아닌 오류 코드를 반환 합니다. 8. 참조 하는 데이터가 올바른 GUID가 없는 경우 ERROR_INVALID_DATA 반환 됩니다.

### <a name="remarks"></a>설명

이 메서드를 활용 `CRegKey::QueryStringValue` 사용 하 여 GUID 문자열을 변환 하 고 [CLSIDFromString](/windows/desktop/api/combaseapi/nf-combaseapi-clsidfromstring)합니다.

> [!IMPORTANT]
>  이 메서드는 호출자가 잠재적으로 신뢰할 수 없는 데이터를 읽는 모든 레지스트리 위치를 지정할 수 있습니다.

##  <a name="querymultistringvalue"></a>  CRegKey::QueryMultiStringValue

지정 된 값 이름에 대 한 다중 데이터를 검색 하려면이 메서드를 호출 합니다.

```
LONG QueryMultiStringValue(
    LPCTSTR pszValueName,
    LPTSTR pszValue,
    ULONG* pnChars) throw();
```

### <a name="parameters"></a>매개 변수

*pszValueName*<br/>
쿼리 값의 이름을 포함 하는 null로 끝나는 문자열에 대 한 포인터입니다.

*pszValue*<br/>
다중 데이터를 받는 버퍼에 대 한 포인터입니다. multistring은 두 null 문자로 끝나는 null로 끝나는 문자열의 배열.

*pnChars*<br/>
크기를 가리키는 버퍼의 TCHARs *pszValue*합니다. 메서드는 반환 될 때 *pnChars* 의 null 종결 문자를 포함 하는 검색 multistring TCHARs의 크기를 포함 합니다.

### <a name="return-value"></a>반환 값

메서드가 성공 하는 경우에 ERROR_SUCCESS 반환 됩니다. 값을 읽는 메서드가 실패 하면, WINERROR에 정의 된 0이 아닌 오류 코드를 반환 합니다. 8. 참조 하는 데이터 형식 REG_MULTI_SZ 없으면 ERROR_INVALID_DATA 반환 됩니다.

### <a name="remarks"></a>설명

이 메서드를 활용 `RegQueryValueEx` 확인 올바른 형식의 데이터 반환 됩니다. 참조 [regqueryvalueex가](/windows/desktop/api/winreg/nf-winreg-regqueryvalueexa) 대 한 자세한 내용은 합니다.

> [!IMPORTANT]
>  이 메서드는 호출자가 잠재적으로 신뢰할 수 없는 데이터를 읽는 모든 레지스트리 위치를 지정할 수 있습니다. 또한 합니다 [regqueryvalueex가](/windows/desktop/api/winreg/nf-winreg-regqueryvalueexa) 이 메서드에서 사용 되는 함수는 NULL 종료 문자열을 명시적으로 처리 하지 않습니다. 두 조건은 모두 호출 코드에서 확인 해야 합니다.

##  <a name="queryqwordvalue"></a>  CRegKey::QueryQWORDValue

지정 된 값 이름을 QWORD 데이터를 검색 하려면이 메서드를 호출 합니다.

```
LONG QueryQWORDValue(
    LPCTSTR pszValueName,
    ULONGLONG& qwValue) throw();
```

### <a name="parameters"></a>매개 변수

*pszValueName*<br/>
쿼리 값의 이름을 포함 하는 null로 끝나는 문자열에 대 한 포인터입니다.

*qwValue*<br/>
QWORD를 받는 버퍼에 대 한 포인터입니다.

### <a name="return-value"></a>반환 값

메서드가 성공 하는 경우에 ERROR_SUCCESS 반환 됩니다. 값을 읽는 메서드가 실패 하면, WINERROR에 정의 된 0이 아닌 오류 코드를 반환 합니다. 8. 참조 하는 데이터 형식 REG_QWORD 없으면 ERROR_INVALID_DATA 반환 됩니다.

### <a name="remarks"></a>설명

이 메서드를 활용 `RegQueryValueEx` 확인 올바른 형식의 데이터 반환 됩니다. 참조 [regqueryvalueex가](/windows/desktop/api/winreg/nf-winreg-regqueryvalueexa) 대 한 자세한 내용은 합니다.

> [!IMPORTANT]
>  이 메서드는 호출자가 잠재적으로 신뢰할 수 없는 데이터를 읽는 모든 레지스트리 위치를 지정할 수 있습니다. 또한 합니다 [regqueryvalueex가](/windows/desktop/api/winreg/nf-winreg-regqueryvalueexa) 이 메서드에서 사용 되는 함수는 NULL 종료 문자열을 명시적으로 처리 하지 않습니다. 두 조건은 모두 호출 코드에서 확인 해야 합니다.

##  <a name="querystringvalue"></a>  CRegKey::QueryStringValue

지정 된 값 이름에 대 한 문자열 데이터를 검색 하려면이 메서드를 호출 합니다.

```
LONG QueryStringValue(
    LPCTSTR pszValueName,
    LPTSTR pszValue,
    ULONG* pnChars) throw();
```

### <a name="parameters"></a>매개 변수

*pszValueName*<br/>
쿼리 값의 이름을 포함 하는 null로 끝나는 문자열에 대 한 포인터입니다.

*pszValue*<br/>
문자열 데이터를 받는 버퍼에 대 한 포인터입니다.

*pnChars*<br/>
크기를 가리키는 버퍼의 TCHARs *pszValue*합니다. 메서드는 반환 될 때 *pnChars* TCHARs, 종결 null 문자를 포함 하 여 검색 문자열의 크기를 포함 합니다.

### <a name="return-value"></a>반환 값

메서드가 성공 하는 경우에 ERROR_SUCCESS 반환 됩니다. 값을 읽는 메서드가 실패 하면, WINERROR에 정의 된 0이 아닌 오류 코드를 반환 합니다. 8. 참조 하는 데이터 형식 REG_SZ 없으면 ERROR_INVALID_DATA 반환 됩니다. 메서드가 ERROR_MORE_DATA를 반환 하면 *pnChars* 가 0 이면 하지 필요한 버퍼 크기 (바이트)입니다.

### <a name="remarks"></a>설명

이 메서드를 활용 `RegQueryValueEx` 확인 올바른 형식의 데이터 반환 됩니다. 참조 [regqueryvalueex가](/windows/desktop/api/winreg/nf-winreg-regqueryvalueexa) 대 한 자세한 내용은 합니다.

> [!IMPORTANT]
>  이 메서드는 호출자가 잠재적으로 신뢰할 수 없는 데이터를 읽는 모든 레지스트리 위치를 지정할 수 있습니다. 또한 합니다 [regqueryvalueex가](/windows/desktop/api/winreg/nf-winreg-regqueryvalueexa) 이 메서드에서 사용 되는 함수는 NULL 종료 문자열을 명시적으로 처리 하지 않습니다. 두 조건은 모두 호출 코드에서 확인 해야 합니다.

##  <a name="queryvalue"></a>  CRegKey::QueryValue

지정 된 값 필드에 대 한 데이터를 검색 하려면이 메서드를 호출 [m_hKey](#m_hkey)합니다. 이 메서드의 이전 버전이 더 이상 지원 되지 않으며 ATL_DEPRECATED로 표시 됩니다.

```
LONG QueryValue(
    LPCTSTR pszValueName,
    DWORD* pdwType,
    void* pData,
    ULONG* pnBytes) throw();

ATL_DEPRECATED LONG QueryValue(
    DWORD& dwValue,
    LPCTSTR lpszValueName);

ATL_DEPRECATED LONG QueryValue(
    LPTSTR szValue,
    LPCTSTR lpszValueName,
    DWORD* pdwCount);
```

### <a name="parameters"></a>매개 변수

*pszValueName*<br/>
쿼리 값의 이름을 포함 하는 null로 끝나는 문자열에 대 한 포인터입니다. 하는 경우 *pszValueName* NULL 이거나 빈 문자열 "", 메서드 형식을 검색 및 키에 대 한 데이터의 명명 되지 않은 또는 기본값이 있는 경우.

*pdwType*<br/>
지정된 된 값에 저장 된 데이터의 형식을 나타내는 코드를 수신 하는 변수에 대 한 포인터입니다. 합니다 *pdwType* 매개 변수 형식 코드를 필요 하지 않은 경우 NULL 일 수 있습니다.

*pData*<br/>
값의 데이터를 받는 버퍼에 대 한 포인터입니다. 이 매개 변수는 데이터가 필요 하지 않은 경우 NULL 일 수 있습니다.

*pnBytes*<br/>
버퍼를 바이트 단위로 크기를 지정 하는 변수에 대 한 포인터에서 가리키는 합니다 *pData* 매개 변수입니다. 메서드가 반환 될 때이 변수 복사할 데이터의 크기를 포함 하는 *pData 합니다.*

*dwValue*<br/>
값 필드의 숫자 데이터입니다.

*lpszValueName*<br/>
값 필드를 쿼리할 수를 지정 합니다.

*szValue*<br/>
값 필드의 문자열 데이터입니다.

*pdwCount*<br/>
문자열 데이터의 크기입니다. 해당 값이 처음 크기를 설정 합니다 *szValue* 버퍼입니다.

### <a name="return-value"></a>반환 값

성공 하면 반환 ERROR_SUCCESS입니다. 그렇지 않으면 0이 아닌 오류 코드를 WINERROR에 정의 합니다. 8.

### <a name="remarks"></a>설명

두 개의 원래 버전의 `QueryValue` 더 이상 지원 되지 않으며 ATL_DEPRECATED로 표시 됩니다. 이 양식을 사용 하는 경우 컴파일러에서 경고가 발생 합니다.

나머지 메서드 호출 regqueryvalueex가 있습니다.

> [!IMPORTANT]
>  이 메서드는 호출자가 잠재적으로 신뢰할 수 없는 데이터를 읽는 모든 레지스트리 위치를 지정할 수 있습니다. 또한이 메서드에서 사용 되는 regqueryvalueex가 함수는 NULL 종료 문자열을 명시적으로 처리 하지 않습니다. 두 조건은 모두 호출 코드에서 확인 해야 합니다.

##  <a name="recursedeletekey"></a>  CRegKey::RecurseDeleteKey

레지스트리에서 지정된 된 키를 제거 하 고 모든 하위 키를 명시적으로 제거 하려면이 메서드를 호출 합니다.

```
LONG RecurseDeleteKey(LPCTSTR lpszKey) throw();
```

### <a name="parameters"></a>매개 변수

*lpszKey*<br/>
삭제할 키의 이름을 지정 합니다. 이 이름은는 하위 키를 사용 해야 합니다. [m_hKey](#m_hkey)합니다.

### <a name="return-value"></a>반환 값

성공 하면 반환 ERROR_SUCCESS입니다. 그렇지 않으면 0이 아닌 오류 값 WINERROR에 정의 합니다. 8.

### <a name="remarks"></a>설명

키에 하위 키를 삭제 하려면이 메서드를 호출 해야 합니다.

##  <a name="setbinaryvalue"></a>  CRegKey::SetBinaryValue

레지스트리 키의 이진 값을 설정 하려면이 메서드를 호출 합니다.

```
LONG SetBinaryValue(
    LPCTSTR pszValueName,
    const void* pValue,
    ULONG nBytes) throw();
```

### <a name="parameters"></a>매개 변수

*pszValueName*<br/>
설정할 값의 이름을 포함 하는 문자열에 대 한 포인터입니다. 이 이름의 값을 아직 없는 경우, 메서드가 키에 추가 됩니다.

*pValue*<br/>
지정 된 값 이름으로 저장 될 데이터가 포함 된 버퍼에 대 한 포인터입니다.

*nBytes*<br/>
가 가리키는 정보를 바이트 단위로 크기를 지정 합니다 *pValue* 매개 변수입니다.

### <a name="return-value"></a>반환 값

메서드가 성공 하면 반환 값은 ERROR_SUCCESS입니다. 메서드가 실패 하는 경우 반환 값은 WINERROR에 정의 된 0이 아닌 오류 코드입니다. 8.

### <a name="remarks"></a>설명

이 메서드는 [regsetvalueex에 오류가 발생](/windows/desktop/api/winreg/nf-winreg-regsetvalueexa) 레지스트리 값을 작성할 수 있습니다.

##  <a name="setdwordvalue"></a>  CRegKey::SetDWORDValue

레지스트리 키 DWORD 값을 설정 하려면이 메서드를 호출 합니다.

```
LONG SetDWORDValue(LPCTSTR pszValueName, DWORD dwValue) throw();
```

### <a name="parameters"></a>매개 변수

*pszValueName*<br/>
설정할 값의 이름을 포함 하는 문자열에 대 한 포인터입니다. 이 이름의 값을 아직 없는 경우, 메서드가 키에 추가 됩니다.

*dwValue*<br/>
지정 된 값 이름으로 저장 될 DWORD 데이터입니다.

### <a name="return-value"></a>반환 값

메서드가 성공 하면 반환 값은 ERROR_SUCCESS입니다. 메서드가 실패 하는 경우 반환 값은 WINERROR에 정의 된 0이 아닌 오류 코드입니다. 8.

### <a name="remarks"></a>설명

이 메서드는 [regsetvalueex에 오류가 발생](/windows/desktop/api/winreg/nf-winreg-regsetvalueexa) 레지스트리 값을 작성할 수 있습니다.

##  <a name="setguidvalue"></a>  CRegKey::SetGUIDValue

레지스트리 키의 GUID 값을 설정 하려면이 메서드를 호출 합니다.

```
LONG SetGUIDValue(LPCTSTR pszValueName, REFGUID guidValue) throw();
```

### <a name="parameters"></a>매개 변수

*pszValueName*<br/>
설정할 값의 이름을 포함 하는 문자열에 대 한 포인터입니다. 이 이름의 값을 아직 없는 경우, 메서드가 키에 추가 됩니다.

*guidValue*<br/>
지정 된 값 이름으로 저장 GUID에 대 한 참조입니다.

### <a name="return-value"></a>반환 값

메서드가 성공 하면 반환 값은 ERROR_SUCCESS입니다. 메서드가 실패 하는 경우 반환 값은 WINERROR에 정의 된 0이 아닌 오류 코드입니다. 8.

### <a name="remarks"></a>설명

이 메서드를 활용 `CRegKey::SetStringValue` GUID를 사용 하 여 문자열 변환 [StringFromGUID2](/windows/desktop/api/combaseapi/nf-combaseapi-stringfromguid2)합니다.

##  <a name="setkeyvalue"></a>  CRegKey::SetKeyValue

지정된 된 키의 지정 된 값 필드에 데이터를 저장 하려면이 메서드를 호출 합니다.

```
LONG SetKeyValue(
    LPCTSTR lpszKeyName,
    LPCTSTR lpszValue,
    LPCTSTR lpszValueName = NULL) throw();
```

### <a name="parameters"></a>매개 변수

*lpszKeyName*<br/>
만들거나 열 수는 키의 이름을 지정 합니다. 이 이름은는 하위 키를 사용 해야 합니다. [m_hKey](#m_hkey)합니다.

*lpszValue*<br/>
데이터를 저장할 수를 지정 합니다. 이 매개 변수는 NULL 이어야 합니다.

*lpszValueName*<br/>
설정할 값 필드를 지정 합니다. 이 이름의 값 필드 없는 키에서에 추가 됩니다.

### <a name="return-value"></a>반환 값

성공 하면 반환 ERROR_SUCCESS입니다. 그렇지 않으면 0이 아닌 오류 코드를 WINERROR에 정의 합니다. 8.

### <a name="remarks"></a>설명

만들거나 열이 메서드를 호출는 *lpszkeyname 만들기* 키를 저장 합니다 *lpszValue* 에서 데이터를 *lpszValueName* 값 필드입니다.

##  <a name="setkeysecurity"></a>  CRegKey::SetKeySecurity

레지스트리 키의 보안을 설정 하려면이 메서드를 호출 합니다.

```
LONG SetKeySecurity(SECURITY_INFORMATION si, PSECURITY_DESCRIPTOR psd) throw();
```

### <a name="parameters"></a>매개 변수

*si*<br/>
설정할 보안 설명자의 구성 요소를 지정 합니다. 값에는 다음 값의 조합 수 있습니다.

|값|의미|
|-----------|-------------|
|DACL_SECURITY_INFORMATION|키의 임의 액세스 제어 목록 (DACL)을 설정합니다. 키 WRITE_DAC 액세스 해야 합니다. 또는 호출 하는 프로세스 개체의 소유자 여야 합니다.|
|GROUP_SECURITY_INFORMATION|키의 주 그룹 SID (보안 식별자)를 설정합니다. 키 WRITE_OWNER 액세스 해야 합니다. 또는 호출 하는 프로세스 개체의 소유자 여야 합니다.|
|OWNER_SECURITY_INFORMATION|키의 소유자 SID를 설정합니다. 키 WRITE_OWNER 액세스 해야 합니다. 또는 호출 프로세스에 개체의 소유자 이거나 SE_TAKE_OWNERSHIP_NAME 권한을 사용 하도록 설정 해야 합니다.|
|SACL_SECURITY_INFORMATION|키의 시스템 액세스 제어 목록 (SACL)를 설정합니다. 키에 ACCESS_SYSTEM_SECURITY 권한이 있어야 합니다. 이 액세스 권한을 얻을 수 있는 적절 한 방법은 se_security_name 권한을 사용 하도록 설정 하는 것 [권한](/windows/desktop/secauthz/privileges) 호출자의 현재 액세스 토큰에서 ACCESS_SYSTEM_SECURITY 액세스에 대 한 핸들을 연 다음 권한을 사용 하지 않도록 설정 합니다.|

*psd*<br/>
에 대 한 포인터를 [SECURITY_DESCRIPTOR](/windows/desktop/api/winnt/ns-winnt-_security_descriptor) 설정할 지정된 된 키에 대 한 보안 특성을 지정 하는 구조입니다.

### <a name="return-value"></a>반환 값

메서드가 성공 하면 반환 값은 ERROR_SUCCESS입니다. 메서드가 실패 하는 경우 반환 값은 WINERROR에 정의 된 0이 아닌 오류 코드입니다. 8.

### <a name="remarks"></a>설명

키의 보안 특성을 설정합니다. 참조 [RegSetKeySecurity](/windows/desktop/api/winreg/nf-winreg-regsetkeysecurity) 대 한 자세한 내용은 합니다.

##  <a name="setmultistringvalue"></a>  CRegKey::SetMultiStringValue

레지스트리 키의 다중 문자열 값을 설정 하려면이 메서드를 호출 합니다.

```
LONG SetMultiStringValue(LPCTSTR pszValueName, LPCTSTR pszValue) throw();
```

### <a name="parameters"></a>매개 변수

*pszValueName*<br/>
설정할 값의 이름을 포함 하는 문자열에 대 한 포인터입니다. 이 이름의 값을 아직 없는 경우, 메서드가 키에 추가 됩니다.

*pszValue*<br/>
지정 된 값 이름으로 저장 하려면 다중 데이터에 대 한 포인터입니다. multistring은 두 null 문자로 끝나는 null로 끝나는 문자열의 배열.

### <a name="return-value"></a>반환 값

메서드가 성공 하면 반환 값은 ERROR_SUCCESS입니다. 메서드가 실패 하는 경우 반환 값은 WINERROR에 정의 된 0이 아닌 오류 코드입니다. 8.

### <a name="remarks"></a>설명

이 메서드는 [regsetvalueex에 오류가 발생](/windows/desktop/api/winreg/nf-winreg-regsetvalueexa) 레지스트리 값을 작성할 수 있습니다.

##  <a name="setqwordvalue"></a>  CRegKey::SetQWORDValue

레지스트리 키의 QWORD 값을 설정 하려면이 메서드를 호출 합니다.

```
LONG SetQWORDValue(LPCTSTR pszValueName, ULONGLONG qwValue) throw();
```

### <a name="parameters"></a>매개 변수

*pszValueName*<br/>
설정할 값의 이름을 포함 하는 문자열에 대 한 포인터입니다. 이 이름의 값을 아직 없는 경우, 메서드가 키에 추가 됩니다.

*qwValue*<br/>
지정 된 값 이름으로 저장 하려면 QWORD 데이터입니다.

### <a name="return-value"></a>반환 값

메서드가 성공 하면 반환 값은 ERROR_SUCCESS입니다. 메서드가 실패 하는 경우 반환 값은 WINERROR에 정의 된 0이 아닌 오류 코드입니다. 8.

### <a name="remarks"></a>설명

이 메서드는 [regsetvalueex에 오류가 발생](/windows/desktop/api/winreg/nf-winreg-regsetvalueexa) 레지스트리 값을 작성할 수 있습니다.

##  <a name="setstringvalue"></a>  CRegKey::SetStringValue

레지스트리 키의 문자열 값을 설정 하려면이 메서드를 호출 합니다.

```
LONG SetStringValue(
    LPCTSTR pszValueName,
    LPCTSTR pszValue,
    DWORD dwType = REG_SZ) throw();
```

### <a name="parameters"></a>매개 변수

*pszValueName*<br/>
설정할 값의 이름을 포함 하는 문자열에 대 한 포인터입니다. 이 이름의 값을 아직 없는 경우, 메서드가 키에 추가 됩니다.

*pszValue*<br/>
지정 된 값 이름으로 저장할 문자열 데이터에 대 한 포인터입니다.

*dwType*<br/>
레지스트리에 쓸 문자열 형식: REG_SZ (기본값) 또는 REG_EXPAND_SZ (다중 문자열)입니다.

### <a name="return-value"></a>반환 값

메서드가 성공 하면 반환 값은 ERROR_SUCCESS입니다. 메서드가 실패 하는 경우 반환 값은 WINERROR에 정의 된 0이 아닌 오류 코드입니다. 8.

### <a name="remarks"></a>설명

이 메서드는 [regsetvalueex에 오류가 발생](/windows/desktop/api/winreg/nf-winreg-regsetvalueexa) 레지스트리 값을 작성할 수 있습니다.

##  <a name="setvalue"></a>  CRegKey::SetValue

지정 된 값 필드에 데이터를 저장 하려면이 메서드를 호출 [m_hKey](#m_hkey)합니다. 이 메서드의 이전 버전이 더 이상 지원 되지 않으며 ATL_DEPRECATED로 표시 됩니다.

```
LONG SetValue(
    LPCTSTR pszValueName,
    DWORD dwType,
    const void* pValue,
    ULONG nBytes) throw();

static LONG WINAPI SetValue(
    HKEY hKeyParent,
    LPCTSTR lpszKeyName,
    LPCTSTR lpszValue,
    LPCTSTR lpszValueName = NULL);

ATL_DEPRECATED LONG SetValue(
    DWORD dwValue,
    LPCTSTR lpszValueName);

ATL_DEPRECATED LONG SetValue(
    LPCTSTR lpszValue,
    LPCTSTR lpszValueName = NULL,
    bool bMulti = false,
    int nValueLen = -1);
```

### <a name="parameters"></a>매개 변수

*pszValueName*<br/>
설정할 값의 이름을 포함 하는 문자열에 대 한 포인터입니다. 이 이름의 값을 이미 키에 없는 경우 메서드가 키에 추가 됩니다. 하는 경우 *pszValueName* NULL 이거나 빈 문자열인 경우 "", 형식을 설정 하는 메서드 및 키에 대 한 데이터의 명명 되지 않은 값 이나 기본값입니다.

*dwType*<br/>
가리키는 데이터의 형식을 나타내는 코드를 지정 합니다 *pValue* 매개 변수입니다.

*pValue*<br/>
지정 된 값 이름으로 저장 될 데이터가 포함 된 버퍼에 대 한 포인터입니다.

*nBytes*<br/>
가 가리키는 정보를 바이트 단위로 크기를 지정 합니다 *pValue* 매개 변수입니다. 데이터 형식 REG_SZ, REG_MULTI_SZ, REG_EXPAND_SZ, 이면 *nBytes* null 종결 문자 크기를 포함 해야 합니다.

*hKeyParent*<br/>
열린 키는의 핸들입니다.

*lpszKeyName*<br/>
만들거나 열 수는 키의 이름을 지정 합니다. 이 이름은는 하위 키를 사용 해야 합니다. *hKeyParent*합니다.

*lpszValue*<br/>
데이터를 저장할 수를 지정 합니다. 이 매개 변수는 NULL 이어야 합니다.

*lpszValueName*<br/>
설정할 값 필드를 지정 합니다. 이 이름의 값 필드 없는 키에서에 추가 됩니다.

*dwValue*<br/>
데이터를 저장할 수를 지정 합니다.

*bMulti*<br/>
False 인 경우에 문자열 형식 REG_SZ 인지를 나타냅니다. True 이면 문자열은 형식 REG_MULTI_SZ multistring 나타냅니다.

*nValueLen*<br/>
하는 경우 *bMulti* 가 true 이면 *nValueLen* 의 길이 *lpszValue* 문자에서 문자열입니다. 하는 경우 *bMulti* 이 false 이면 값이-1 이면 메서드 길이 자동으로 계산 됩니다.

### <a name="return-value"></a>반환 값

성공 하면 반환 ERROR_SUCCESS입니다. 그렇지 않으면 0이 아닌 오류 코드를 WINERROR에 정의 합니다. 8.

### <a name="remarks"></a>설명

두 개의 원래 버전의 `SetValue` ATL_DEPRECATED로 표시 되 고 더 이상 사용 해야 합니다. 이 양식을 사용 하는 경우 컴파일러에서 경고가 발생 합니다.

세 번째 메서드 호출 [RegSetValueEx](/windows/desktop/api/winreg/nf-winreg-regsetvalueexa)합니다.

## <a name="see-also"></a>참고자료

[DCOM 예제](../../overview/visual-cpp-samples.md)<br/>
[클래스 개요](../../atl/atl-class-overview.md)
