---
title: filesystem_error 클래스
ms.date: 09/10/2018
f1_keywords:
- filesystem/std::experimental::filesystem::filesystem_error
ms.assetid: c53aac27-c1fa-43e4-8967-48ea8ba1f172
ms.openlocfilehash: add1e0da43a44c35f39c96e8d65e36aeea0d3afb
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62405159"
---
# <a name="filesystemerror-class"></a>filesystem_error 클래스

하위 수준 시스템 오버플로를 보고하기 위해 throw되는 모든 예외에 대한 기본 클래스입니다.

## <a name="syntax"></a>구문

```cpp
class filesystem_error    : public system_error;
```

## <a name="remarks"></a>설명

이 클래스는 \<filesystem> 함수의 오류를 보고하기 위해 throw된 모든 예외에 대한 기본 클래스로 사용됩니다. 형식의 개체를 저장 하며 `string`라는 `mymesg` 표시를 위해 여기 있습니다. 형식의 두 개체도 저장 `path`라는 `mypval1` 고 `mypval2`입니다.

### <a name="constructors"></a>생성자

|생성자|설명|
|-|-|
|[filesystem_error](#filesystem_error)|생성 된 `filesystem_error` 메시지입니다.|

### <a name="member-functions"></a>멤버 함수

|멤버 함수|설명|
|-|-|
|[path1](#path1)|`mypval1`를 반환합니다.|
|[path2](#path2)|`mypval2`를 반환합니다.|
|[what](#what)|`NTBS`에 대한 포인터를 반환합니다.|

## <a name="requirements"></a>요구 사항

**헤더:** \<파일 시스템 >

**네임스페이스:** std::experimental::filesystem

## <a name="filesystem_error"></a> filesystem_error::filesystem_error

메시지를 생성 하는 첫 번째 생성자는 *what_arg* 하 고 *ec*합니다. 두 번째 생성자는 또한에서 해당 메시지를 생성 *pval1*에 저장 되 `mypval1`합니다. 세 번째 생성자 또한에서 해당 메시지를 생성 *pval1*에 저장 되 `mypval1`, 및 *pval2*에 저장 되 `mypval2`합니다.

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

*what_arg*<br/>
지정 된 메시지입니다.

*ec*<br/>
지정 된 오류 코드입니다.

*mypval1*<br/>
추가로 지정한 메시지 매개 변수입니다.

*mypval2*<br/>
추가로 지정한 메시지 매개 변수입니다.

## <a name="path1"></a> filesystem_error::path1

구성원 함수는 `mypval1`을 반환합니다.

```cpp
const path& path1() const noexcept;
```

## <a name="path2"></a> filesystem_error::path2

구성원 함수는 `mypval2`을 반환합니다.

```cpp
const path& path2() const noexcept;
```

## <a name="what"></a> filesystem_error::what

멤버 함수에 대 한 포인터를 반환 합니다.는 `NTBS`에서으로 구성 된 것이 좋습니다 `runtime_error::what()`, `system_error::what()`, `mymesg`를 `mypval1.native_string()`, 및 `mypval2.native_string()`합니다.

```cpp
const char *what() const noexcept;
```

## <a name="see-also"></a>참고자료

[헤더 파일 참조](../standard-library/cpp-standard-library-header-files.md)<br/>
[system_error 클래스](../standard-library/system-error-class.md)<br/>
[\<filesystem>](../standard-library/filesystem.md)<br/>
[\<exception>](../standard-library/exception.md)<br/>
