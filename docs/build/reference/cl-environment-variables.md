---
title: CL 환경 변수
ms.date: 06/06/2019
f1_keywords:
- cl
helpviewer_keywords:
- INCLUDE environment variable
- cl.exe compiler, environment variables
- LIBPATH environment variable
- environment variables, CL compiler
ms.assetid: 2606585b-a681-42ee-986e-1c9a2da32108
ms.openlocfilehash: 0f7930728ef1bf6bea50c4388d52d30c569a8795
ms.sourcegitcommit: 8adabe177d557c74566c13145196c11cef5d10d4
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/10/2019
ms.locfileid: "66821528"
---
# <a name="cl-environment-variables"></a>CL 환경 변수

CL 도구는 다음과 같은 환경 변수를 사용합니다.

- CL 및 \_CL_를 정의 하는 경우. CL 도구 옵션 및 명령줄 인수를 CL 환경 변수에 정의 된 인수 앞에 추가 옵션을 추가 및 인수에 정의 된 \_CL_를 처리 하기 전에 합니다.

- 포함 하는 Visual Studio 설치의 \include 하위 디렉터리를 가리켜야 합니다.

- 사용 하 여 참조 하는 메타 데이터 파일을 검색할 디렉터리를 지정 하는 LIBPATH [#using](../../preprocessor/hash-using-directive-cpp.md)합니다. LIBPATH에 대 한 자세한 내용은 참조 하세요. [#using](../../preprocessor/hash-using-directive-cpp.md)합니다.

CL를 설정할 수 있습니다 또는 \_CL_ 환경 변수는 다음 구문을 사용 하 여:

> SET CL=[ [*option*] ... [*file*] ...] [/link *link-opt* ...] \
> SET \_CL\_=[ [*option*] ... [*file*] ...] [/link *link-opt* ...]

CL에 대 한 인수에 대 한 내용은 및 \_CL_ 환경 변수를 참조 하세요 [MSVC 컴파일러 명령줄 구문](compiler-command-line-syntax.md)합니다.

파일 및 가장 자주 사용 하는 옵션을 정의 하려면 이러한 환경 변수를 사용할 수 있습니다. 다음 명령줄을 사용 하 여 특정 용도 맞게 CL에 더 많은 파일 및 옵션을 지정 하 합니다. CL 및 \_CL_ 환경 변수는 1024 자 (명령줄 입력된 제한)로 제한 합니다.

사용할 수 없습니다는 [/D](d-preprocessor-definitions.md) 등호를 사용 하는 기호를 정의 하는 옵션 ( **=** ). 대신, 숫자 기호를 사용할 수 있습니다 ( **#** ) 등호 기호에 대 한 합니다. 이러한 방식으로 CL를 사용할 수 있습니다 또는 \_명시적 값으로 전처리기 상수를 정의 하려면 CL_ 환경 변수-예를 들어 `/DDEBUG#1` 정의 하 `DEBUG=1`합니다.

관련 정보를 참조 하세요 [환경 변수 설정](../setting-the-path-and-environment-variables-for-command-line-builds.md)합니다.

## <a name="examples"></a>예제

다음 명령은 CL 환경 변수 설정 예는 다음과 같습니다.

> SET CL=/Zp2 /Ox /I\INCLUDE\MYINCLS \LIB\BINMODE.OBJ

CL 환경 변수가 설정 된 경우 입력 하는 경우 `CL INPUT.C` 명령줄에서 명령이 적용 됩니다.

> CL /Zp2 /Ox /I\INCLUDE\MYINCLS \LIB\BINMODE.OBJ INPUT.C

다음 예제에서는 일반 CL 명령을 사용하여 소스 파일 FILE1.c 및 FILE2.c를 컴파일한 다음 개체 파일 FILE1.obj, FILE2.obj 및 FILE3.obj를 연결합니다.

> SET CL=FILE1.C FILE2.C \
> SET \_CL_=FILE3.OBJ \
> CL

다음 명령줄과 같은 효과가 CL는 호출을 수행 하는 이러한 환경 변수:

> CL FILE1.C FILE2.C FILE3.OBJ

## <a name="see-also"></a>참고자료

[컴파일러 옵션 설정](compiler-command-line-syntax.md) \
[MSVC 컴파일러 옵션](compiler-options.md)
