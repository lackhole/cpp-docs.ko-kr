---
title: LINK 입력 파일
ms.date: 11/04/2016
f1_keywords:
- link
helpviewer_keywords:
- files [C++], LINK
- module definition files
- resources [C++], linker files
- LINK tool [C++], input files
- module definition files, linker files
- input files [C++], LINK
- linker [C++], input files
- import libraries [C++], linker files
- command input to linker files [C++]
ms.assetid: bb26fcc5-509a-4620-bc3e-b6c6e603a412
ms.openlocfilehash: 48ad9423ae35c22a97a873fe6a2a0479c12ab33b
ms.sourcegitcommit: 8105b7003b89b73b4359644ff4281e1595352dda
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/14/2019
ms.locfileid: "57817792"
---
# <a name="link-input-files"></a>LINK 입력 파일

개체, 가져오기 및 표준 라이브러리, 리소스, 모듈 정의 입력 명령을 포함 하는 파일을 사용 하 여 링커를 제공 합니다. 링크 파일의 콘텐츠에 대 한 가정을에 파일 확장명을 사용 하지 않습니다. 대신 링크 파일의 종류를 확인 하려면 각 입력된 파일을 검사 합니다.

명령줄에서 개체 파일은 명령줄에서 순서 대로 처리 됩니다. 라이브러리는 다음 주의 사용 하 여 명령줄 순서로 검색 됩니다. 경우 라이브러리에서 개체 파일을 가져오는 검색 라이브러리에서 먼저 및 명령줄에서 다음 라이브러리는 기호 확인 되지 않은 하 고 [/DEFAULTLIB (기본 라이브러리 지정)](defaultlib-specify-default-library.md) 지시문을 선택한 다음 명령줄의 시작 부분에 있는 라이브러리입니다.

> [!NOTE]
>  링크는 더 이상 응답 파일과 순서에 주석의 시작으로 세미콜론 (또는 다른 모든 문자)를 받아들입니다. 세미콜론으로 모듈 정의 파일 (.def) 주석의 시작 으로만 인식 됩니다.

링크는 입력된 파일의 다음 형식을 사용합니다.

- [.obj 파일](dot-obj-files-as-linker-input.md)

- [.netmodule 파일](netmodule-files-as-linker-input.md)

- [.lib 파일](dot-lib-files-as-linker-input.md)

- [.exp 파일](dot-exp-files-as-linker-input.md)

- [.def 파일](dot-def-files-as-linker-input.md)

- [.pdb files](dot-pdb-files-as-linker-input.md)

- [.res 파일](dot-res-files-as-linker-input.md)

- [.exe 파일](dot-exe-files-as-linker-input.md)

- [.txt 파일](dot-txt-files-as-linker-input.md)

- [.ilk 파일](dot-ilk-files-as-linker-input.md)

## <a name="see-also"></a>참고자료

[MSVC 링커 참조](linking.md)<br/>
[MSVC 링커 옵션](linker-options.md)
