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

각 출력 파일 옵션은 출력 파일의 위치와 이름을 지정할 수 있는 *pathname* 인수를 사용할 수 있습니다. 인수는 드라이브 이름, 디렉터리 및 파일 이름을 포함할 수 있습니다. 옵션과 인수 사이에 공백이 없어야 합니다.

*pathname*에 확장자 없이 파일이름이 포함되면 컴파일러는 출력에 기본 확장명을 사용합니다. *pathname*에 디렉터리가 있지만 파일 이름이 없다면 컴파일러는 지정된 디렉터리에 기본 이름으로 파일을 만듭니다. 기본 이름은 원본 파일의 기본 이름과 및 출력 파일의 형식을 기반으로 하는 기본 확장자를 기반으로 합니다. *pathname*을 완전히 무시하면 컴파일러는 기본 디렉터리에 있는 기본 이름으로 파일을 만듭니다.

또는 *pathname* 인수는 파일 이름 대신 장치 이름(AUX, CON, PRN, 또는 NUL)이 될 수 있습니다. 장치 이름의 일부로 옵션과 장치 이름 또는 콜론 사이에 공백을 사용하지 마세요.

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
