---
title: /FD(IDE 최소 재빌드)
ms.date: 04/08/2019
f1_keywords:
- /FD
helpviewer_keywords:
- /FD compiler option [C++]
- -FD compiler option [C++]
- FD compiler option [C++]
ms.assetid: 7ef21b8c-a448-4bb4-9585-a2a870028e17
ms.openlocfilehash: ac63b021dc0cb9ee5964af7fa2e168f710653979
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62292877"
---
# <a name="fd-ide-minimal-rebuild"></a>/FD(IDE 최소 재빌드)

**/FD**는 C++ 프로젝트의 **속성 페이지** 대화 상자의 [명령줄](command-line-property-pages.md)의 속성 페이지에서 사용자에게만 노출됩니다. 비추천 및 기본값에 의한 [/Gm (최소 다시 빌드 사용)](gm-enable-minimal-rebuild.md)옵션이 선택되지 않는 경우에만 사용할 수 있습니다. **/FD**는 개발 환경 이외의 다른 영향을 끼치지 않습니다. **/FD**는 `cl /?`의 출력에 표시 되지 않습니다.

개발 환경에서 사용하지 않을것을 권장하는 옵션 **/Gm**을 사용하지 않으면 **/FD**가 사용 됩니다. **/FD**는 .idb 파일에 충분한 종속성 정보를 보장 합니다. **/FD**는 개발 환경에서만 사용되며 명령줄 또는 빌드 스크립트에서 사용해서는 않됩니다.

## <a name="see-also"></a>참고자료

[출력 파일(/F) 옵션](output-file-f-options.md)<br/>
[MSVC 컴파일러 옵션](compiler-options.md)<br/>
[MSVC 컴파일러 명령줄 구문](compiler-command-line-syntax.md)
