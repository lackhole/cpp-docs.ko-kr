---
title: CL에서의 링커 호출
ms.date: 11/04/2016
f1_keywords:
- cl
helpviewer_keywords:
- compiling source code [C++], without linking
- invoking linker from the compiler
- LINK tool [C++], invoking from CL compiler
- cl.exe compiler [C++], compiling without linking
- cl.exe compiler [C++], controlling linker
ms.assetid: eae47ef7-09eb-40c9-b318-7c714cd452fc
ms.openlocfilehash: f8d8c5e1b0ca4d2a35a57683fea2e6de12747860
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62294540"
---
# <a name="cl-invokes-the-linker"></a>CL에서의 링커 호출

자동으로 CL /c 옵션이 사용 되지 않으면 컴파일한 다음 링커를 호출 합니다. CL 컴파일하는 동안 생성 된.obj 파일의 이름과 명령줄에 지정 된 다른 모든 파일을 링커에 전달 합니다. 링커에 링크 환경 변수에 나열 된 옵션을 사용 합니다. CL 명령줄에서 링커 옵션을 지정 하려면 /link 옵션을 사용할 수 있습니다. /Link 옵션 뒤에 있는 옵션 링크가 환경 변수를 무시 합니다. 다음 표의 옵션 링크 하지 않도록 합니다.

|옵션|설명|
|------------|-----------------|
|/c|연결 하지 않고 컴파일하면|
|/E, /EP, /P|링크 하지 않고 전처리|
|/Zg|함수 프로토타입 생성|
|/Zs|구문 검사|

연결 하는 방법에 대 한 세부 정보를 참조 하세요 [MSVC 링커 옵션](linker-options.md)합니다.

## <a name="example"></a>예제

세 가지 C 소스 파일을 컴파일한다고 가정 합니다. MAIN.c MOD1.c 하며 MOD2.c 합니다. 각 파일에 다른 파일에 정의 된 함수에 대 한 호출에 포함 됩니다.

- 함수를 호출 하는 MAIN.c `func1` MOD1.c 함수에 `func2` MOD2.c에서.

- 표준 라이브러리 함수를 호출 하는 MOD1.c `printf_s` 고 `scanf_s`입니다.

- 라는 그래픽 함수를 호출 하는 MOD2.c `myline` 및 `mycircle`, 합니다에 정의 된 합니다.

이 프로그램을 빌드하려면 다음 명령줄을 사용 하 여 컴파일하십시오.

```
CL MAIN.c MOD1.C MOD2.C MYGRAPH.lib
```

CL C 소스 파일 먼저 컴파일하고 MAIN.obj, MOD1.obj 및 MOD2.obj 개체 파일을 만듭니다. 컴파일러는 각.obj 파일의 표준 라이브러리의 이름을 배치합니다. 자세한 내용은 참조 하세요. [런타임 라이브러리 사용](md-mt-ld-use-run-time-library.md)합니다.

CL 링커 합니다, 이름과 함께.obj 파일의 이름을 전달합니다. 링커가 외부 참조를 다음과 같이 해결합니다.

1. MAIN.obj에 대 한 참조에서에서 `func1` MOD1.obj;에서 정의 사용 하 여 확인 됩니다에 대 한 참조 `func2` MOD2.obj의 정의 사용 하 여 확인 됩니다.

1. MOD1.obj에 대 한 참조에서 `printf_s` 및 `scanf_s` MOD1.obj 내 라는 라이브러리를 링커 찾는의 정의 사용 하 여 확인 됩니다.

1. MOD2.obj에 대 한 참조에서에서 `myline` 고 `mycircle` 합니다의 정의 사용 하 여 확인 됩니다.

## <a name="see-also"></a>참고자료

[MSVC 컴파일러 옵션](compiler-options.md)<br/>
[컴파일러 옵션 설정](compiler-command-line-syntax.md)
