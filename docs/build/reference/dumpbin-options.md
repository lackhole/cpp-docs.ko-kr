---
title: DUMPBIN 옵션
ms.date: 10/24/2019
f1_keywords:
- dumpbin
helpviewer_keywords:
- DUMPBIN program, options
ms.assetid: 563b696e-7599-4480-94b9-014776289ec8
ms.openlocfilehash: 81c66f1971294531a2904a0b681819476bcc1eb2
ms.sourcegitcommit: 6ed1bc5b26dc60a780c1fc5f2f19d57ba1dc47d8
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/30/2019
ms.locfileid: "73144548"
---
# <a name="dumpbin-options"></a>DUMPBIN 옵션

옵션은 대시 (`-`) 또는 슬래시 (`/`), 옵션 이름을 차례로 나타내는 *옵션 지정자*로 구성 됩니다. 옵션 이름은 약식 일 수 없습니다. 일부 옵션은 콜론 (`:`) 뒤에 지정 되는 인수를 사용 합니다. 옵션 지정 내에는 공백 또는 탭을 사용할 수 없습니다. 하나 이상의 공백 또는 탭을 사용 하 여 명령줄에서 옵션 사양을 구분 합니다. 옵션 이름과 해당 키워드 또는 파일 이름 인수는 대/소문자를 구분 하지 않습니다. 대부분의 옵션은 모든 이진 파일에 적용 되지만 몇 가지 옵션은 특정 파일 형식에만 적용 됩니다. 기본적으로 DUMPBIN은 표준 출력으로 정보를 보냅니다. [/Out](out-dumpbin.md) 옵션을 사용 하 여 출력을 파일로 보냅니다.

## <a name="options-list"></a>옵션 목록

DUMPBIN에는 다음과 같은 옵션이 있습니다.

- [/ALL](all.md)

- [/ARCHIVEMEMBERS](archivemembers.md)

- [/CLRHEADER](clrheader.md)

- [/DEPENDENTS](dependents.md)

- [/DIRECTIVES](directives.md)

- [/DISASM\[: {BYTES\|NOBYTES}\]](disasm.md)

- [/ERRORREPORT: {NONE | 프롬프트 | 큐 | 보내시겠습니까](errorreport-dumpbin-exe.md)

- [/EXPORTS](dash-exports.md)

- [/FPO](fpo.md)

- [/HEADERS](headers.md)

- [/IMPORTS\[: 파일 이름\]](imports-dumpbin.md)

- [/LINENUMBERS](linenumbers.md)

- [/LINKERMEMBER\[: {1 | 2}\]](linkermember.md)

- [/LOADCONFIG](loadconfig.md)

- [/NOPDB](nopdb.md)

- [/OUT: filename](out-dumpbin.md)

- [/PDATA](pdata.md)

- [/PDBPATH\[: VERBOSE\]](pdbpath.md)

- [/RANGEE: vaMin\[, Vamin\]](range.md)

- [/RAWDATA\[: {NONE\|1\|2\|4\|8}\[, #\]\]](rawdata.md)

- [/RELOCATIONS](relocations.md)

- [/SECTION: 이름](section-dumpbin.md)

- [/SUMMARY](summary.md)

- [/SYMBOLS](symbols.md)

- [/TLS](tls.md)

명령줄에서 DUMPBIN에서 지 원하는 옵션을 나열 하려면 **/?** 를 사용 합니다. option.

## <a name="see-also"></a>참조

[추가 MSVC 빌드 도구](c-cpp-build-tools.md)\
[DUMPBIN 명령줄](dumpbin-command-line.md)\
[DUMPBIN 참조](dumpbin-reference.md)
