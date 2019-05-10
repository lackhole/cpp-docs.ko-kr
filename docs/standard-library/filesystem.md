---
title: '&lt;filesystem&gt;'
ms.date: 11/04/2016
f1_keywords:
- filesystem/std::experimental::filesystem::directory_entry
- filesystem/std::experimental::filesystem::recursive_directory_iterator
- filesystem/std::experimental::filesystem::path
- filesystem/std::experimental::filesystem::filesystem_error
- filesystem/std::experimental::filesystem::directory_iterator
- <filesystem>
ms.assetid: 5005753b-46fa-43e1-8d4e-1b38617d3cfd
ms.openlocfilehash: 0f397d8b0c39769fde20b6aa50412c979237f70a
ms.sourcegitcommit: da32511dd5baebe27451c0458a95f345144bd439
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/07/2019
ms.locfileid: "65220378"
---
# <a name="ltfilesystemgt"></a>&lt;filesystem&gt;

경로, 파일 및 디렉터리에 대한 정보를 조작하고 검색하는 클래스 및 함수에 액세스할 수 있도록 &lt;filesystem> 헤더를 포함합니다.

## <a name="syntax"></a>구문

```cpp
#include <experimental/filesystem> // C++-standard header file name
#include <filesystem> // Microsoft-specific implementation header file name
using namespace std::experimental::filesystem::v1;
```

> [!IMPORTANT]
> Visual Studio 2017의 릴리스 기준으로 합니다 \<파일 시스템 > 헤더 없습니다 아직 C++ 표준입니다. C++Visual Studio 2017 (MSVC v141) 구현에서에서 찾을 수 있는 최종 초안 표준을 [ISO/IEC JTC 1/SC 22/WG 21 N4100](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2014/n4100.pdf)합니다.

이 헤더는 호스트 운영 체제의 두 가지 광범위 한 클래스 중 하나에 대 한 파일 시스템을 지원합니다. Microsoft Windows 및 Posix 합니다.

대부분의 기능이 두 운영 체제에서 공통되지만 이 문서에서는 차이가 있는 위치를 식별합니다. 예를 들어:

- Windows는 c: 또는 \\\network_name과 같은 여러 루트 이름을 지원합니다. 파일 시스템은 트리 포리스트로 구성되며, 각각에는 고유한 루트 디렉터리(예: c:\ 또는 \\\network_name\\)와 고유한 현재 디렉터리가 있어 절대 경로 이름이 아닌 상대 경로 이름을 완성합니다.

- Posix는 루트 이름이 없고 단일 루트 디렉터리 /와 단일 현재 디렉터리가 있는 단일 트리를 지원합니다.

또 다른 중요한 차이점은 경로 이름의 기본 표시입니다.

- Windows에서는 UTF-16(각 문자에 대해 하나 또는 두 개의 요소 사용)으로 인코드된, null 종료 wchar_t 시퀀스를 사용합니다.

- Posix에서는 UTF-8(각 문자에 대해 하나 이상의 요소 사용)로 인코드된, null 종료 char 시퀀스를 사용합니다.

- 클래스 경로의 개체는 경로 이름을 네이티브 형식으로 저장하지만 이 저장된 형식과 여러 가지 외부 형식 간에 쉽게 변환할 수 있습니다.

- 운영 체제에서 선호하는 방식으로 인코드된, null 종료 char 시퀀스

- UTF-8로 인코드된, null 종료 char 시퀀스

- 운영 체제에서 선호하는 방식으로 인코드된, null 종료 wchar_t 시퀀스

- UTF-16으로 인코드된, null 종료 char16_t 시퀀스

- UTF-32로 인코드된, null 종료 char32_t 시퀀스

이러한 표시 간의 상호 변환은 하나 이상의 `codecvt` 패싯을 사용하여 필요에 따라 조정됩니다. 특정 로캘 개체를 지정하지 않은 경우 전역 로캘에서 이러한 패싯을 가져옵니다.

또 다른 차이점은 각 운영 체제에서 파일 또는 디렉터리 액세스 권한을 지정할 수 있는 세부 정보입니다.

1. Windows에서는 디렉터리에는 의미가 없는 특성인 파일이 읽기 전용인지 쓰기 가능한지를 기록합니다.

1. Posix에서는 소유자, 소유자 그룹 또는 모든 사람이 파일을 읽거나, 쓰거나, 실행(디렉터리인 경우 검색)할 수 있는지와 몇 가지 다른 권한을 기록합니다.

두 시스템에 공통되는 점은 루트 이름을 통과할 경우 경로 이름에 적용되는 구조입니다. 경로 이름이 c:/abc/xyz/def.ext일 경우 다음과 같습니다.

- 루트 이름은 c:입니다.

- 루트 디렉터리는 /입니다.

- 루트 경로는 c:/입니다.

- 상대 경로는 abc/xyz/def.ext입니다.

- 부모 경로는 c:/abc/xyz입니다.

- 파일 이름은 def.ext입니다.

- 어간은 def입니다.

- 확장명은 .ext입니다.

사소한 차이점은 경로 이름에서 디렉터리 시퀀스 사이의 **기본 구분 기호**입니다. 두 운영 체제에서 슬래시 /를 쓸 수 있지만 일부 컨텍스트에서 Windows는 백슬래시 \\를 선호합니다.

마지막으로 경로 개체의 중요한 기능은 \<fstream> 헤더에 정의된 클래스에서 filename 인수가 필요한 모든 위치에서 사용할 수 있다는 점입니다.

자세한 내용 및 코드 예제를 보려면 [파일 시스템 탐색(C++)](../standard-library/file-system-navigation.md)을 참조하세요.

## <a name="classes"></a>클래스

|이름|설명|
|----------|-----------------|
|[directory_entry 클래스](../standard-library/directory-entry-class.md)|`directory_iterator` 또는 `recursive_directory_iterator`에서 반환된 개체를 설명하고 경로를 포함합니다.|
|[directory_iterator 클래스](../standard-library/directory-iterator-class.md)|파일 시스템 디렉터리에서 파일 이름을 통해 시퀀스되는 입력 반복기에 대해 설명합니다.|
|[filesystem_error 클래스](../standard-library/filesystem-error-class.md)|하위 수준 시스템 오버플로를 보고하기 위해 throw되는 예외에 대한 기본 클래스입니다.|
|[path 클래스](../standard-library/path-class.md)|파일 이름으로 사용하기 적합한 템플릿 형식 `String` 의 개체를 저장하는 클래스를 정의합니다.|
|[recursive_directory_iterator 클래스](../standard-library/recursive-directory-iterator-class.md)|파일 시스템 디렉터리에서 파일 이름을 통해 시퀀스되는 입력 반복기에 대해 설명합니다. 이 반복기는 하위 디렉터리로도 상속됩니다.|
|[file_status 클래스](../standard-library/file-status-class.md)|`file_type`을 래핑합니다.|

## <a name="structs"></a>구조체

|이름|설명|
|----------|-----------------|
|[space_info 구조체](../standard-library/space-info-structure.md)|볼륨에 대한 정보를 보관합니다.|

## <a name="functions"></a>함수

[\<filesystem> 함수](../standard-library/filesystem-functions.md)

## <a name="operators"></a>연산자

[\<filesystem> 연산자](../standard-library/filesystem-operators.md)

## <a name="enumerations"></a>열거형

|이름|설명|
|----------|-----------------|
|[copy_options](../standard-library/filesystem-enumerations.md#copy_options)|[copy_file](../standard-library/filesystem-functions.md#copy_file) 과 함께 사용되는 열거형이며 대상 파일이 이미 있는 경우의 동작을 결정합니다.|
|[copy_options](../standard-library/filesystem-enumerations.md#copy_options)|[copy_file](../standard-library/filesystem-functions.md#copy_file) 과 함께 사용되는 열거형이며 대상 파일이 이미 있는 경우의 동작을 결정합니다.|
|[directory_options](../standard-library/filesystem-enumerations.md#directory_options)|디렉터리 반복기에 대한 옵션을 지정하는 열거형입니다.|
|[file_type](../standard-library/filesystem-enumerations.md#file_type)|파일 형식에 대한 열거형입니다.|
|[perms](../standard-library/filesystem-enumerations.md#perms)|사용 권한 및 사용 권한에 대한 옵션을 전달하는 데 사용되는 비트 마스크 형식입니다.|

## <a name="see-also"></a>참고자료

[헤더 파일 참조](../standard-library/cpp-standard-library-header-files.md)<br/>
