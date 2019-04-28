---
title: 링커 도구 오류 LNK1211
ms.date: 12/05/2017
f1_keywords:
- LNK1211
helpviewer_keywords:
- LNK1211
ms.assetid: 607400eb-4180-4892-817f-eedfa628af61
ms.openlocfilehash: 7c918cacb87460c2aad30285b750d9b170425534
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62242671"
---
# <a name="linker-tools-error-lnk1211"></a>링커 도구 오류 LNK1211

> 미리 컴파일된 형식 정보를 찾을 수 없습니다. '*filename*' 링크 되지 않았거나 덮어

합니다 *filename* 사용 하 여 컴파일된 개체 파일 [/Yc](../../build/reference/yc-create-precompiled-header-file.md), LINK 명령에 지정 되지 않았거나 덮어 쓰여졌습니다.

미리 컴파일된 헤더를 사용 하는 디버그 라이브러리를 만들려는 경우 및 지정 하는 경우 **/Yc** 하 고 [/z7](../../build/reference/z7-zi-zi-debug-information-format.md)시각적 C++ 디버그 정보를 포함 하는 미리 컴파일된 개체 파일을 생성 합니다. 만 저장 하는 경우 미리 컴파일된 개체 파일을 라이브러리에 오류가 발생 하 고 라이브러리를 사용 하 여 실행 가능 이미지를 빌드 참조 되는 개체 파일 참조가 없는 전이 미리 컴파일된 개체 파일을 정의 하는 함수 중 하나에.

이 문제를 해결 하는 방법은 두 가지가 있습니다.

- 지정 된 [/Yd](../../build/reference/yd-place-debug-information-in-object-file.md) 컴파일러 옵션이 미리 컴파일된 헤더의 각 개체 모듈에 디버그 정보를 추가 합니다. 이 메서드는 일반적으로 응용 프로그램을 연결 하는 데 필요한 시간을 향상 시킬 수 있는 큰 개체 모듈을 생성 하기 때문에 그다지 바람직하지 않습니다.

- 지정할 [/Yl](../../build/reference/yl-inject-pch-reference-for-debug-library.md) 함수 정의 포함 하지 않는 하는 미리 컴파일된 헤더 파일을 만들 때 이름을 임의의 문자열을 전달 합니다. 이 미리 컴파일된 개체 파일에 기호를 만들고 미리 컴파일된 개체와 연결 된 미리 컴파일된 헤더 파일을 사용 하는 각 개체 파일의 기호에 대 한 참조를 내보낼 수 컴파일러를 지시 합니다.

사용 하 여 모듈을 컴파일할 때 **/Yc** 및 **/Yl**, 컴파일러 기호를 비슷한 만듭니다 `__@@_PchSym_@00@...@symbol_name`여기서 줄임표 (...) 컴파일러에서 생성 된 문자열을 나타내며에 저장 합니다 개체 모듈입니다. 이 미리 컴파일된 헤더를 사용 하 여 컴파일하는 모든 원본 파일은 링커가 개체 모듈 및 라이브러리에서 디버깅 정보를 포함 하는 지정된 된 기호를 가리킵니다.
