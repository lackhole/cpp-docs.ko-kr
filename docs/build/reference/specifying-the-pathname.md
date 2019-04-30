---
title: 경로 이름 지정
ms.date: 11/04/2016
helpviewer_keywords:
- names [C++], compiler output files
- cl.exe compiler, output files
- output files, specifying pathnames
ms.assetid: 7a6595ce-3383-44ae-957a-466bfa29c343
ms.openlocfilehash: dcff3610255c40f4e06201e52a53eb5dd965a4be
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62317941"
---
# <a name="specifying-the-pathname"></a>경로 이름 지정

각 출력 파일 옵션을 *pathname* 인수를 출력 파일에 대 한 이름과 위치를 지정할 수 있습니다. 인수는 드라이브 이름, 디렉터리 및 파일 이름을 포함할 수 있습니다. 옵션 및 인수 간에 공백이 없어야 합니다.

하는 경우 *pathname* 파일 이름을 포함가 확장명 없이 컴파일러 출력 기본 확장명을 사용 합니다. 하는 경우 *pathname* 포함 디렉터리 되지만 파일 이름은 없으므로 컴파일러는 지정된 된 디렉터리에 있는 기본 이름으로 파일을 만듭니다. 기본 이름은 기본 이름 소스 파일 및 출력 파일의 형식을 기반으로 하는 기본 확장 프로그램을 기반으로 합니다. 두면 *pathname* 완전히 컴파일러 기본 디렉터리에 있는 기본 이름으로 파일을 만듭니다.

또는 합니다 *pathname* 인수 파일 이름 대신 장치 이름을 (AUX, CON, PRN, 또는 NUL) 될 수 있습니다. 옵션 및 장치 이름이 나 콜론과 사이 공백을 장치 이름의 일부로 사용 하지 마십시오.

|장치 이름|표현|
|-----------------|----------------|
|AUX|보조 장치|
|CON|콘솔|
|PRN|프린터|
|NUL|Null 장치 (파일 생성)|

## <a name="example"></a>예제

다음 명령줄은 프린터를 맵 파일을 보냅니다.

```
CL /FmPRN HELLO.CPP
```

## <a name="see-also"></a>참고자료

[출력 파일(/F) 옵션](output-file-f-options.md)<br/>
[MSVC 컴파일러 옵션](compiler-options.md)<br/>
[MSVC 컴파일러 명령줄 구문](compiler-command-line-syntax.md)
