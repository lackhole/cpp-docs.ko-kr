---
title: comment (C/C++)
ms.date: 11/04/2016
f1_keywords:
- vc-pragma.comment
- comment_CPP
helpviewer_keywords:
- annotations [C++]
- comments [C++], compiled files
- pragmas, comment
- comment pragma
ms.assetid: 20f099ff-6303-49b3-9c03-a94b6aa69b85
ms.openlocfilehash: fb9bfef2ae751529b8424143cde020e78f17ec72
ms.sourcegitcommit: c7f90df497e6261764893f9cc04b5d1f1bf0b64b
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/05/2019
ms.locfileid: "59025272"
---
# <a name="comment-cc"></a>comment (C/C++)

주석 기록을 개체 파일 또는 실행 파일에 배치합니다.

## <a name="syntax"></a>구문

```
#pragma comment( comment-type [,"commentstring"] )
```

## <a name="remarks"></a>설명

합니다 *주석 형식* 주석 기록 형식을 지정 하는 하나 아래에 설명 된, 미리 정의 된 식별자입니다. 선택적 *commentstring* 일부 주석 형식에 대 한 추가 정보를 제공 하는 문자열 리터럴입니다. 때문에 *commentstring* 은 문자열 리터럴, 이스케이프 문자를 포함 된 큰 따옴표와 관련 하 여 문자열 리터럴에 대 한 모든 규칙을 따르는 것 (`"`), 및 연결 합니다.

### <a name="compiler"></a>컴파일러

컴파일러의 이름 및 버전 이름을 개체 파일에 배치합니다. 이 주석 기록은 링커에 의해 무시됩니다. 제공 하는 경우는 *commentstring* 이 레코드 형식에 컴파일러에 대 한 매개 변수는 경고를 생성 합니다.

### <a name="exestr"></a>exestr

장소 *commentstring* 개체 파일에 있습니다. 이 문자열은 링크 타임에 실행 파일에 배치됩니다. 이 문자열은 실행 파일이 로드될 때 메모리에 로드되지 않지만, 파일 내에 인쇄 가능한 문자열을 찾는 프로그램에서는 발견될 수 있습니다. 이 주석 기록 형식의 용도는 실행 파일의 버전 번호 또는 유사 정보를 포함하는 것입니다.

`exestr` 사용 되지 않으며 후속 릴리스에서 제거 됩니다 링커 주석 레코드를 처리 하지 않습니다.

### <a name="lib"></a>lib

라이브러리 검색 기록을 개체 파일에 배치합니다. 이러한 주석 형식은 수반 되어야 합니다는 *commentstring* 매개 변수 이름 (및 가능한 경로)은 링커가 검색할 라이브러리의를 포함 합니다. 라이브러리 이름 개체 파일의 기본 라이브러리 검색 기록을 따릅니다. 링커가 검색 하는이 라이브러리에 대 한 것 처럼 명명 된 해당 명령줄에서 라이브러리를 지정 하지 않으면 것임 [/nodefaultlib](../build/reference/nodefaultlib-ignore-libraries.md)합니다. 여러 라이브러리 검색 기록을 같은 소스 파일에 배치할 수 있으며 각 기록은 소스 파일과 동일한 순서로 개체 파일에 표시됩니다.

기본 라이브러리 및 추가 순서 중요 한 경우 사용 하 여 컴파일하는 [/Zl](../build/reference/zl-omit-default-library-name.md) 스위치 개체 모듈에 배치 되지 않게 기본 라이브러리 이름을 수 없게 됩니다. 그런 다음 두 번째 주석 pragma를 사용하여 추가된 라이브러리 다음에 기본 라이브러리의 이름을 삽입할 수 있습니다. pragma를 사용하여 나열된 라이브러리는 소스 코드와 동일한 순서로 개체 모듈에 표시됩니다.

### <a name="linker"></a>링커

위치는 [링커 옵션](../build/reference/linker-options.md) 개체 파일에 있습니다. 이 주석 형식을 이용하여 명령줄에 주석을 전달하거나 개발 환경에 지정하는 대신 링커 옵션을 지정할 수 있습니다. 예를 들어, /include 옵션을 지정하면 기호를 포함하도록 할 수 있습니다.

```
#pragma comment(linker, "/include:__mySymbol")
```

다음만 (*주석 형식*) 링커 옵션은 링커 식별자로 전달할 수 있습니다.

- [/DEFAULTLIB](../build/reference/defaultlib-specify-default-library.md)

- [/EXPORT](../build/reference/export-exports-a-function.md)

- [/INCLUDE](../build/reference/include-force-symbol-references.md)

- [/MANIFESTDEPENDENCY](../build/reference/manifestdependency-specify-manifest-dependencies.md)

- [/MERGE](../build/reference/merge-combine-sections.md)

- [/SECTION](../build/reference/section-specify-section-attributes.md)

### <a name="user"></a>사용자

일반 주석을 개체 파일에 배치합니다. 합니다 *commentstring* 매개 변수 설명의 텍스트를 포함 합니다. 이 주석 기록은 링커에 의해 무시됩니다.

다음 pragma를 사용하면 링커가 연결하는 동안 EMAPI.LIB 라이브러리를 검색할 수 있습니다. 링커는 먼저 현재 작업 경로에서 검색한 다음 LIB 환경 변수에 지정된 경로에서 검색합니다.

```
#pragma comment( lib, "emapi" )
```

다음 pragma는 컴파일러가 컴파일러의 이름과 버전 번호를 개체 파일에 배치하도록 합니다.

```
#pragma comment( compiler )
```

> [!NOTE]
> 사용 하는 주석의 *commentstring* 매개 변수를 사용할 수 있습니다 매크로 문자열 리터럴을 사용 하는 위치 어디서에서는 매크로 문자열 리터럴로 확장 합니다. 문자열 리터럴에 확장되는 문자열 리터럴 및 매크로의 조합을 연결할 수도 있습니다. 예를 들어, 다음 문을 사용할 수 있습니다.

```
#pragma comment( user, "Compiled on " __DATE__ " at " __TIME__ )
```

## <a name="see-also"></a>참고자료

[Pragma 지시문 및 __Pragma 키워드](../preprocessor/pragma-directives-and-the-pragma-keyword.md)