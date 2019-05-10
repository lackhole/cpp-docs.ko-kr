---
title: CL 환경 변수
ms.date: 05/06/2019
f1_keywords:
- cl
helpviewer_keywords:
- INCLUDE environment variable
- cl.exe compiler, environment variables
- LIBPATH environment variable
- environment variables, CL compiler
ms.assetid: 2606585b-a681-42ee-986e-1c9a2da32108
ms.openlocfilehash: 620ec386e06b1a0eed91c94e9b2b891d9955fd00
ms.sourcegitcommit: da32511dd5baebe27451c0458a95f345144bd439
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/07/2019
ms.locfileid: "65217628"
---
# <a name="cl-environment-variables"></a>CL 환경 변수

CL 도구는 다음과 같은 환경 변수를 사용합니다.

- CL 및 \_CL\_정의 합니다. CL 도구 옵션 및 명령줄 인수를 CL 환경 변수에 정의 된 인수 앞에 추가 옵션을 추가 하 고에 정의 된 인수 \_CL\_를 처리 하기 전에 합니다.

- 포함 하는 Visual Studio 설치의 \include 하위 디렉터리를 가리켜야 합니다.

- 사용 하 여 참조 하는 메타 데이터 파일을 검색할 디렉터리를 지정 하는 LIBPATH [#using](../../preprocessor/hash-using-directive-cpp.md)합니다. LIBPATH에 대한 자세한 내용은 `#using`을 참조하세요.

CL를 설정할 수 있습니다 또는 \_CL\_ 다음 구문을 사용 하 여 환경 변수:

> SET CL=[ [*option*] ... [*file*] ...] [/link *link-opt* ...] SET \_CL\_=[ [*option*] ... [*file*] ...] [/link *link-opt* ...]

CL에 대 한 인수에 대 한 내용은 및 \_CL\_ 환경 변수를 참조 하십시오 [MSVC 컴파일러 명령줄 구문](compiler-command-line-syntax.md)합니다.

이러한 환경 변수를 사용하여 가장 자주 사용하는 파일 및 옵션을 정의하고 명령줄을 사용하여 특정 용도에 맞는 특정 파일 및 옵션을 정의할 수 있습니다. CL 및 \_CL\_ 환경 변수는 1024 자 (명령줄 입력된 제한)로 제한 합니다.

등호 기호(=)를 사용하는 기호를 정의할 때는 /D 옵션을 사용할 수 없습니다. 등호 기호에 대신 숫자 기호(#)를 사용할 수 있습니다. 따라서에서 CL를 사용할 수 있습니다 또는 \_CL\_ 명시적 값으로 전처리기 상수를 정의 하는 환경 변수-예를 들어 `/DDEBUG#1` 정의 하려면 `DEBUG=1`합니다.

관련 정보를 참조 하세요 [환경 변수 설정](../setting-the-path-and-environment-variables-for-command-line-builds.md)합니다.

## <a name="examples"></a>예제

다음은 CL 환경 변수를 설정 하는 예제입니다.

> SET CL=/Zp2 /Ox /I\INCLUDE\MYINCLS \LIB\BINMODE.OBJ

입력 하는 경우,이 환경 변수가 설정 되어 `CL INPUT.C` 명령줄에서이 명령이 적용 됩니다.

> CL /Zp2 /Ox /I\INCLUDE\MYINCLS \LIB\BINMODE.OBJ INPUT.C

다음 예제에서는 일반 CL 명령을 사용하여 소스 파일 FILE1.c 및 FILE2.c를 컴파일한 다음 개체 파일 FILE1.obj, FILE2.obj 및 FILE3.obj를 연결합니다.

> SET CL=FILE1.C FILE2.C SET \_CL\_=FILE3.OBJ CL

이 예제는 다음 명령줄과 동일한 효과가 있습니다.

> CL FILE1.C FILE2.C FILE3.OBJ

## <a name="see-also"></a>참고자료

[컴파일러 옵션 설정](compiler-command-line-syntax.md)<br/>
[MSVC 컴파일러 옵션](compiler-options.md)
