---
title: filesystem_error 클래스
ms.date: 09/10/2018
f1_keywords:
- filesystem/std::experimental::filesystem::filesystem_error
ms.assetid: c53aac27-c1fa-43e4-8967-48ea8ba1f172
ms.openlocfilehash: 7bd6b2d3d716ba25999388d44e7bd5a8d0750eb5
ms.sourcegitcommit: 76cc69b482ada8ebf0837e8cdfd4459661f996dd
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/19/2019
ms.locfileid: "71127208"
---
# <a name="filesystem_error-class"></a>filesystem_error 클래스

하위 수준 시스템 오버플로를 보고하기 위해 throw되는 모든 예외에 대한 기본 클래스입니다.

## <a name="syntax"></a>구문

```cpp
class filesystem_error    : public system_error;
```

## <a name="remarks"></a>설명

이 클래스는 \<filesystem> 함수의 오류를 보고하기 위해 throw된 모든 예외에 대한 기본 클래스로 사용됩니다. 표시의 목적 `mymesg` 으로 여기에 `string`해당 하는 형식의 개체를 저장 합니다. 또한 및 `path` 이라는`mypval2`두 가지 형식의 개체를 저장 합니다. `mypval1`

## <a name="members"></a>멤버

### <a name="constructors"></a>생성자

|||
|-|-|
|[filesystem_error](#filesystem_error)|메시지를 `filesystem_error` 생성 합니다.|

### <a name="functions"></a>함수

|||
|-|-|
|[path1](#path1)|`mypval1`를 반환합니다.|
|[path2](#path2)|`mypval2`를 반환합니다.|
|[what](#what)|`NTBS`에 대한 포인터를 반환합니다.|

## <a name="requirements"></a>요구 사항

**헤더:** \<파일 시스템 >

**네임스페이스:** std::experimental::filesystem

## <a name="filesystem_error"></a>filesystem_error

첫 번째 생성자는 *what_arg* 및 *ec*에서 해당 메시지를 생성 합니다. 또한 두 번째 생성자는 *pval1*에서 해당 메시지를 생성 하 여에 `mypval1`저장 합니다. 세 번째 생성자는 *pval1* `mypval1`에서 해당 메시지를 생성 하 고에 `mypval2`저장 되는 *pval1*에서 해당 메시지를 생성 합니다.

```cpp
filesystem_error(const string& what_arg,
    error_code ec);

filesystem_error(const string& what_arg,
    const path& pval1,
    error_code ec);

filesystem_error(const string& what_arg,
    const path& pval1,
    const path& pval2,
    error_code ec);
```

### <a name="parameters"></a>매개 변수

*what_arg*\
지정 된 메시지입니다.

*ec*\
지정 된 오류 코드입니다.

*mypval1*\
지정 된 추가 메시지 매개 변수입니다.

*mypval2*\
지정 된 추가 메시지 매개 변수입니다.

## <a name="path1"></a>path1

구성원 함수는 `mypval1`을 반환합니다.

```cpp
const path& path1() const noexcept;
```

## <a name="path2"></a>path2

구성원 함수는 `mypval2`을 반환합니다.

```cpp
const path& path2() const noexcept;
```

## <a name="what"></a>이며

멤버 함수는, `NTBS` `system_error::what()` `runtime_error::what()` ,`mymesg`, 및`mypval2.native_string()`에서 구성 된에 대 한 포인터를 반환 합니다. `mypval1.native_string()`

```cpp
const char *what() const noexcept;
```
