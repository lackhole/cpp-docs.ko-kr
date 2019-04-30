---
title: /Fe(EXE 파일 이름 지정)
ms.date: 11/04/2016
f1_keywords:
- /fe
helpviewer_keywords:
- -Fe compiler option [C++]
- executable files, renaming
- rename file compiler option [C++]
- /Fe compiler option [C++]
- Fe compiler option [C++]
ms.assetid: 49f594fd-5e94-45fe-a1bf-7c9f2abb6437
ms.openlocfilehash: 5901ef1997cfea84c97b6d91b30335ff7dbc1d9f
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62292617"
---
# <a name="fe-name-exe-file"></a>/Fe(EXE 파일 이름 지정)

이름 및.exe 파일 또는 컴파일러에서 생성 하는 DLL에 대 한 디렉터리를 지정 합니다.

## <a name="syntax"></a>구문

> **/Fe**[_pathname_] **/Fe:** _pathname_

### <a name="arguments"></a>인수

*pathname*<br/>
상대 또는 절대 경로 및 기본 파일 이름 또는 디렉터리, 또는 생성된 된 실행 파일에 사용할 기본 파일 이름에 상대 또는 절대 경로입니다.

## <a name="remarks"></a>설명

합니다 **/Fe** 옵션을 사용 하면 출력 디렉터리, 출력 실행 파일 이름 또는 생성된 된 실행 파일에 둘 다 지정할 수 있습니다. 하는 경우 *pathname* 경로 구분 기호로 끝나는 (**&#92;**)에 출력 디렉터리를 지정 하는로 간주 됩니다. 이 고, 그렇지의 마지막 구성 요소 *pathname* 출력 파일 기본 이름 및의 나머지 부분으로 사용 됩니다 *pathname* 출력 디렉터리를 지정 합니다. 하는 경우 *pathname* 모든 경로 구분 기호가 없는 현재 디렉터리에 출력 파일 이름을 지정 하는로 간주 됩니다. 합니다 *pathname* 큰따옴표로 묶어야 합니다 (**"**) 공백과 같은 짧은 경로의 수 없는 문자가 포함 된 경우 확장 문자 또는 경로 구성 요소 8 자 보다 긴 합니다.

경우는 **/Fe** 옵션을 지정 하지 않으면 또는 기본 파일 이름에 지정 되지 않은 *pathname*, 컴파일러에서는 출력 파일의 지정 된 첫 번째 원본 또는 목적 물 파일 기본 이름을 사용 하는 기본 이름 명령줄 및 확장명이.exe 또는.dll입니다.

지정 하는 경우는 [(컴파일 없이 링크 사용)는 /c](c-compile-without-linking.md) 옵션을 **/Fe** 영향을 주지 않습니다.

### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Visual Studio 개발 환경에서 이 컴파일러 옵션을 설정하려면

1. 프로젝트의 **속성 페이지** 대화 상자를 엽니다. 자세한 내용은 [컴파일러 및 빌드 속성 설정](../working-with-project-properties.md)을 참조합니다.

1. 엽니다는 **구성 속성** > **링커** > **일반** 속성 페이지.

1. 수정 된 **출력 파일** 속성입니다. **확인**을 선택하여 변경 내용을 저장합니다.

### <a name="to-set-this-compiler-option-programmatically"></a>프로그래밍 방식으로 이 컴파일러 옵션을 설정하려면

- <xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.OutputFile%2A>을 참조하세요.

## <a name="example"></a>예제

다음 명령줄을 컴파일하고 현재 디렉터리의 모든 C 소스 파일을 연결 합니다. 결과 실행 파일 PROCESS.exe 라고 하 고 "C:\Users\User Name\repos\My Project\bin" 디렉터리에 만들어집니다.

```
CL /Fe"C:\Users\User Name\repos\My Project\bin\PROCESS" *.C
```

## <a name="example"></a>예제

다음 명령줄에서 실행 파일을 만듭니다 `C:\BIN` 현재 디렉터리의 첫 번째 소스 파일과 동일한 기본 이름을 사용 하 여:

```
CL /FeC:\BIN\ *.C
```

## <a name="see-also"></a>참고자료

[출력 파일(/F) 옵션](output-file-f-options.md)<br/>
[MSVC 컴파일러 옵션](compiler-options.md)<br/>
[MSVC 컴파일러 명령줄 구문](compiler-command-line-syntax.md)<br/>
[경로 이름 지정](specifying-the-pathname.md)<br/>
