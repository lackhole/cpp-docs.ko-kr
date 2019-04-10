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
ms.sourcegitcommit: 39debf8c525c3951af6913ee5e514617658f8859
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/09/2019
ms.locfileid: "59424055"
---
# <a name="fd-ide-minimal-rebuild"></a>/FD(IDE 최소 재빌드)

**/FD** 에서 사용자에만 노출 되는 [명령줄](command-line-property-pages.md) 의 속성 페이지를 C++ 프로젝트의 **속성 페이지** 대화 상자. 이면 사용 가능 하 고 경우에만 사용 되지 않는 및 해제 기본적 [/Gm (최소 다시 빌드 사용)](gm-enable-minimal-rebuild.md) 옵션이 선택 되지 않습니다. **/FD** 개발 환경에서 다른 효과가 있습니다. **/FD** 의 출력에 표시 되지 않습니다 `cl /?`합니다.

사용 되지 않는 사용 하지 않는 경우 **/Gm** 개발 환경 옵션 **/FD** 사용 됩니다. **/FD** .idb 파일에 충분 한 종속성 정보를 확인 합니다. **/FD** 개발 환경 에서만 사용 되며 않으며 명령줄 또는 빌드 스크립트에서 사용할 수 없습니다.

## <a name="see-also"></a>참고자료

[출력 파일(/F) 옵션](output-file-f-options.md)<br/>
[MSVC 컴파일러 옵션](compiler-options.md)<br/>
[MSVC 컴파일러 명령줄 구문](compiler-command-line-syntax.md)
