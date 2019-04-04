---
title: /FD(IDE 최소 재빌드)
ms.date: 11/04/2016
f1_keywords:
- /FD
helpviewer_keywords:
- /FD compiler option [C++]
- -FD compiler option [C++]
- FD compiler option [C++]
ms.assetid: 7ef21b8c-a448-4bb4-9585-a2a870028e17
ms.openlocfilehash: 323a0045ab11f23ab996d5179a135d0eb4184f20
ms.sourcegitcommit: 8105b7003b89b73b4359644ff4281e1595352dda
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/14/2019
ms.locfileid: "57817441"
---
# <a name="fd-ide-minimal-rebuild"></a>/FD(IDE 최소 재빌드)

[Gm(최소 재빌드 사용)](gm-enable-minimal-rebuild.md) 또한 선택되지 않은 경우에만 **/FD**가 C++ 프로젝트의 속성 페이지 대화 상자의 명령 줄 속성 페이지를 제외하고 사용자에게 노출되지 않습니다. **/FD**는 개발 환경 이외의 다른 영향이 없습니다. **/FD**는 **cl /?**의 출력에서 노출되지 않습니다.

사용 하지 않는 경우 **/Gm** 개발 환경의 **/FD** 사용 됩니다. **/FD** .idb 파일에 충분 한 종속성 정보가 있는지 확인 합니다. **/FD** 개발 환경 에서만 사용 되는 명령줄 또는 빌드 스크립트에서 사용 해야 합니다.

## <a name="see-also"></a>참고자료

[출력 파일(/F) 옵션](output-file-f-options.md)<br/>
[MSVC 컴파일러 옵션](compiler-options.md)<br/>
[MSVC 컴파일러 명령줄 구문](compiler-command-line-syntax.md)
