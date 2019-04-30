---
title: HStringReference 클래스
ms.date: 09/25/2018
ms.topic: reference
f1_keywords:
- corewrappers/Microsoft::WRL::Wrappers::HStringReference
- corewrappers/Microsoft::WRL::Wrappers::HStringReference::CopyTo
- corewrappers/Microsoft::WRL::Wrappers::HStringReference::Get
- corewrappers/Microsoft::WRL::Wrappers::HStringReference::HStringReference
- corewrappers/Microsoft::WRL::Wrappers::HStringReference::operator=
- corewrappers/Microsoft::WRL::Wrappers::HStringReference::operator==
- corewrappers/Microsoft::WRL::Wrappers::HStringReference::operator!=
- corewrappers/Microsoft::WRL::Wrappers::HStringReference::operator<
helpviewer_keywords:
- Microsoft::WRL::Wrappers::HStringReference class
- Microsoft::WRL::Wrappers::HStringReference::CopyTo method
- Microsoft::WRL::Wrappers::HStringReference::Get method
- Microsoft::WRL::Wrappers::HStringReference::HStringReference, constructor
- Microsoft::WRL::Wrappers::HStringReference::operator= operator
- Microsoft::WRL::Wrappers::HStringReference::operator== operator
- Microsoft::WRL::Wrappers::HStringReference::operator!= operator
- Microsoft::WRL::Wrappers::HStringReference::operator< operator
ms.assetid: 9bf823b1-17eb-4ac4-8c5d-27d27c7a4150
ms.openlocfilehash: b9d2e49d0a7e1321e2259c06e1313a90d55dc90e
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62398279"
---
# <a name="hstringreference-class"></a>HStringReference 클래스

기존 문자열에서 생성 된 HSTRING을 나타냅니다.

## <a name="syntax"></a>구문

```cpp
class HStringReference;
```

## <a name="remarks"></a>설명

새 HSTRING의 백업 버퍼의 수명은 Windows 런타임에서 관리 되지 않습니다. 호출자에 게 힙 할당을 방지 하 고 메모리 누수의 위험을 제거 하려면 스택 프레임에 소스 문자열을 할당 합니다. 또한 호출자는 연결 된 HSTRING의 수명 동안 소스 문자열은 변경 되지 않은 것을 확인 해야 합니다. 자세한 내용은 [WindowsCreateStringReference 함수](/windows/desktop/api/winstring/nf-winstring-windowscreatestringreference)합니다.

## <a name="members"></a>멤버

### <a name="public-constructors"></a>Public 생성자

이름                                                    | 설명
------------------------------------------------------- | -----------------------------------------------------------
[HStringReference::HStringReference](#hstringreference) | `HStringReference` 클래스의 새 인스턴스를 초기화합니다.

### <a name="public-methods"></a>Public 메서드

멤버                              | 설명
----------------------------------- | ------------------------------------------------------------------
[HStringReference::CopyTo](#copyto) | 현재 복사 `HStringReference` 개체를 HSTRING 개체로 합니다.
[HStringReference::Get](#get)       | 기본 HSTRING 핸들의 값을 검색 합니다.

### <a name="public-operators"></a>Public 연산자

이름                                                  | 설명
----------------------------------------------------- | ----------------------------------------------------------------------------------------------
[HStringReference::operator=](#operator-assign)       | 다른 값으로 이동 `HStringReference` 개체를 현재 `HStringReference` 개체입니다.
[HStringReference::operator==](#operator-equality)    | 두 매개 변수가 같은지 여부를 나타냅니다.
[HStringReference::operator!=](#operator-inequality)  | 두 매개 변수가 같지 않은지를 나타냅니다.
[HStringReference::operator&lt;](#operator-less-than) | 첫 번째 매개 변수 인지 보다 작은 두 번째 매개 변수를 나타냅니다.

## <a name="inheritance-hierarchy"></a>상속 계층 구조

`HStringReference`

## <a name="requirements"></a>요구 사항

**헤더:** corewrappers.h

**네임스페이스:** Microsoft::WRL::Wrappers

## <a name="copyto"></a>HStringReference::CopyTo

현재 복사 `HStringReference` 개체를 HSTRING 개체로 합니다.

```cpp
HRESULT CopyTo(
   _Out_ HSTRING *str
   ) const throw();
```

### <a name="parameters"></a>매개 변수

*str*<br/>
복사본을 받는 HSTRING입니다.

### <a name="remarks"></a>설명

이 메서드를 호출 합니다 [WindowsDuplicateString](/windows/desktop/api/winstring/nf-winstring-windowsduplicatestring) 함수입니다.

## <a name="get"></a>HStringReference::Get

기본 HSTRING 핸들의 값을 검색 합니다.

```cpp
HSTRING Get() const throw()
```

### <a name="return-value"></a>반환 값

기본 HSTRING 핸들의 값입니다.

## <a name="hstringreference"></a>HStringReference::HStringReference

`HStringReference` 클래스의 새 인스턴스를 초기화합니다.

```cpp
template<unsigned int sizeDest>
HStringReference(wchar_t const (&str)[ sizeDest]) throw();

template<unsigned int sizeDest>
HStringReference(wchar_t const (&str)[ sizeDest],
                 unsigned int len) throw();

HStringReference(HStringReference&& other) throw();
```

### <a name="parameters"></a>매개 변수

*sizeDest*<br/>
대상의 크기를 지정 하는 템플릿 매개 변수 `HStringReference` 버퍼입니다.

*str*<br/>
와이드 문자 문자열에 대한 참조입니다.

*len*<br/>
최대 길이 *str* 이 작업에 사용할 매개 변수 버퍼입니다. 경우는 *len* 매개 변수를 지정 하지 않으면 전체 *str* 매개 변수를 사용 합니다. 하는 경우 *len* 보다 크면 *sizeDest*를 *len* 로 설정 되어 *sizeDest*-1입니다.

*other*<br/>
다른 `HStringReference` 개체입니다.

### <a name="remarks"></a>설명

첫 번째 생성자는 초기화 된 새 `HStringReference` 과 동일한 크기의 매개 변수로 개체 *str*합니다.

두 번째 생성자는 새 `HStringReference` 개체를 매개 변수로 지정 된 크기의 *len*합니다.

세 번째 생성자는 새 `HStringReference` 개체의 값을 *다른* 매개 변수를 되지 않으며 합니다 *다른* 매개 변수.

## <a name="operator-assign"></a>HStringReference::operator=

다른 값으로 이동 `HStringReference` 개체를 현재 `HStringReference` 개체입니다.

```cpp
HStringReference& operator=(HStringReference&& other) throw()
```

### <a name="parameters"></a>매개 변수

*other*<br/>
기존 `HStringReference` 개체입니다.

### <a name="remarks"></a>설명

기존 값 *다른* 현재 개체를 복사할 `HStringReference` 개체를 차례로 합니다 *다른* 개체는 소멸 됩니다.

## <a name="operator-equality"></a>HStringReference::operator==

두 매개 변수가 같은지 여부를 나타냅니다.

```cpp
inline bool operator==(
               const HStringReference& lhs,
               const HStringReference& rhs) throw()

inline bool operator==(
               const HSTRING& lhs,
               const HStringReference& rhs) throw()

inline bool operator==(
               const HStringReference& lhs,
               const HSTRING& rhs) throw()
```

### <a name="parameters"></a>매개 변수

*lhs*<br/>
비교할 첫 번째 매개 변수입니다. *lhs* 수는 `HStringReference` 개체 또는 HSTRING 핸들입니다.

*rhs*<br/>
비교할 두 번째 매개 변수입니다.  *rhs* 수는 `HStringReference` 개체 또는 HSTRING 핸들입니다.

### <a name="return-value"></a>반환 값

**true** 경우는 *lhs* 하 고 *rhs* 매개 변수는 같고, 그렇지 않으면 **false**합니다.

## <a name="operator-inequality"></a>HStringReference::operator!=

두 매개 변수가 같지 않은지를 나타냅니다.

```cpp
inline bool operator!=(
               const HStringReference& lhs,
               const HStringReference& rhs) throw()

inline bool operator!=(
               const HSTRING& lhs,
               const HStringReference& rhs) throw()

inline bool operator!=(
               const HStringReference& lhs,
               const HSTRING& rhs) throw()
```

### <a name="parameters"></a>매개 변수

*lhs*<br/>
비교할 첫 번째 매개 변수입니다. *lhs* 수는 `HStringReference` 개체 또는 HSTRING 핸들입니다.

*rhs*<br/>
비교할 두 번째 매개 변수입니다.  *rhs* 수는 `HStringReference` 개체 또는 HSTRING 핸들입니다.

### <a name="return-value"></a>반환 값

**true** 경우는 *lhs* 하 고 *rhs* 매개 변수는 같고, 그렇지 않으면 **false**합니다.

## <a name="operator-less-than"></a>HStringReference::operator&lt;

첫 번째 매개 변수 인지 보다 작은 두 번째 매개 변수를 나타냅니다.

```cpp
inline bool operator<(
    const HStringReference& lhs,
    const HStringReference& rhs) throw()
```

### <a name="parameters"></a>매개 변수

*lhs*<br/>
비교할 첫 번째 매개 변수입니다. *lhs* 에 대 한 참조 수를 `HStringReference`입니다.

*rhs*<br/>
비교할 두 번째 매개 변수입니다.  *rhs* 에 대 한 참조 수를 `HStringReference`입니다.

### <a name="return-value"></a>반환 값

**true** 경우는 *lhs* 매개 변수는 보다 작은 *rhs* 매개 변수가 고, 그렇지 않으면 **false**합니다.
