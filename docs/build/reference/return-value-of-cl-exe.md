---
title: cl.exe의 반환 값
ms.date: 09/05/2018
helpviewer_keywords:
- cl.exe compiler, return value
ms.assetid: 7c2d7f33-ee0d-4199-8ef4-75fe2b007670
ms.openlocfilehash: 1617208a8d99e3c5643330f75faf9beed9ce5f1b
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62319020"
---
# <a name="return-value-of-clexe"></a>cl.exe의 반환 값

성공한 경우(오류가 없는 경우) cl.exe는 0을 반환하고 그렇지 않은 경우 0이 아닌 값을 반환합니다.

cl.exe의 반환 값은 스크립트, powershell, .cmd 또는 .bat 파일에서 컴파일하는 경우 유용할 수 있습니다. 오류나 경고가 발생할 경우 해결할 수 있도록 이 경우에도 컴파일러의 출력을 캡처하기 위한 계획을 세우는 것이 좋습니다.

가능한 오류 종료 코드가 너무 많아 cl.exe가 모두 나열할 수 없습니다. winerror에 오류 코드를 조회할 수 있습니다 또는 ntstatus.h 파일 키트를 %ProgramFiles (x86)%\Windows Windows 소프트웨어 개발 키트에 포함\\<em>버전</em>\Include\shared\ 디렉터리입니다. 10진수로 반환된 오류 코드는 검색을 위해 16진수로 변환해야 합니다. 예를 들어 오류 코드 -1073741620를 16진수로 변환하면 0xC00000CC입니다. 이 오류는 ntstatus.h에서 찾을 수 있는데, 여기에서 해당 메시지는 "원격 서버에서 지정된 공유 이름을 찾을 수 없습니다."입니다. Windows 오류 코드 목록은 다운로드 가능한 대해서 [ &#91;MS ERREF&#93;: Windows 오류 코드](https://msdn.microsoft.com/library/cc231196)합니다.

Visual Studio의 오류 조회 유틸리티를 사용하여 컴파일러 오류 메시지의 의미를 찾을 수도 있습니다. Visual Studio 명령 셸에서 입력 **errlook.exe** 유틸리티를 시작 하거나 메뉴 모음에서 Visual Studio IDE에서 선택 **도구**합니다 **오류 조회**합니다. 오류와 연결된 설명 텍스트를 찾으려면 오류 값을 입력합니다. 자세한 내용은 참조 [ERRLOOK 참조](errlook-reference.md)합니다.

## <a name="remarks"></a>설명

아래의 예제 .bat 파일에서는 cl.exe의 반환 값을 사용합니다.

```cmd
echo off
cl /W4 t.cpp
@if ERRORLEVEL == 0 (
   goto good
)

@if ERRORLEVEL != 0 (
   goto bad
)

:good
   echo "clean compile"
   echo %ERRORLEVEL%
   goto end

:bad
   echo "error or warning"
   echo %ERRORLEVEL%
   goto end

:end
```

## <a name="see-also"></a>참고자료

[MSVC 컴파일러 명령줄 구문](compiler-command-line-syntax.md)
