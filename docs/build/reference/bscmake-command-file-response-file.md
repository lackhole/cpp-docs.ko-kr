---
title: BSCMAKE 명령 파일(지시 파일)
ms.date: 11/04/2016
helpviewer_keywords:
- BSCMAKE, response file
- BSCMAKE, command file
- response files, BSCMAKE
- command files, BSCMAKE
- response files
- command files
ms.assetid: abdffeea-35c7-4f2d-8c17-7d0d80bac314
ms.openlocfilehash: 6a55fd616a00aeb3ade229bf7cff8220f86085b7
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62295047"
---
# <a name="bscmake-command-file-response-file"></a>BSCMAKE 명령 파일(지시 파일)

> [!WARNING]
> BSCMAKE는 Visual Studio와 함께 설치되지만 더 이상 IDE에서 사용되지 않습니다. Visual Studio 2008부터 찾아보기 및 기호 정보는 자동으로 솔루션 폴더의 SQL Server .sdf 파일에 저장됩니다.

일부 또는 전체 명령 파일에서 명령줄 입력을 제공할 수 있습니다. 다음 구문을 사용 하 여 명령 파일을 지정 합니다.

```
BSCMAKE @filename
```

하나의 명령 파일은 허용 됩니다. 사용 하 여 경로 지정할 수 있습니다 *filename*합니다. 앞에 야 *filename* 사용 하 여는 at 기호 (**\@**). BSCMAKE는 확장을 가정 하지 않습니다. 추가 지정할 수 있습니다 *sbrfiles* 한 후 명령줄에서 *filename*합니다. 명령 파일은 명령줄에서 지정 하는 것 처럼 동일한 순서로 BSCMAKE에 대 한 입력을 포함 하는 텍스트 파일입니다. 하나 이상의 공백, 탭 또는 줄 바꿈 문자를 사용 하 여 명령줄 인수를 구분 합니다.

다음 명령은 BSCMAKE 명령 파일을 사용 하 여 호출 합니다.

```
BSCMAKE @prog1.txt
```

다음은 샘플 명령 파일입니다.

```
/n /v /o main.bsc /El
/S (
toolbox.h
verdate.h c:\src\inc\screen.h
)
file1.sbr file2.sbr file3.sbr file4.sbr
```

## <a name="see-also"></a>참고자료

[BSCMAKE 참조](bscmake-reference.md)
