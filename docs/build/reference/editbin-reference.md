---
title: EDITBIN 참조
ms.date: 11/04/2016
f1_keywords:
- editbin
helpviewer_keywords:
- binary data, editing
- object files, modifying
- EDITBIN program
- COFF files, editing
ms.assetid: efdda03b-3dfc-4d31-90e6-caf5b3977914
ms.openlocfilehash: 45c2967a55e85ae31bb77bb2e8d50415eafbea46
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62293032"
---
# <a name="editbin-reference"></a>EDITBIN 참조

Microsoft COFF Binary 파일 편집기 (EDITBIN 합니다. EXE) 개체 파일 형식 COFF (공용) 이진 파일을 수정 합니다. 개체 파일, 실행 파일 및 동적 연결 라이브러리 (DLL)를 수정 하려면 EDITBIN를 사용할 수 있습니다.

> [!NOTE]
>  이 도구는 Visual Studio 명령 프롬프트에서만 시작할 수 있습니다. 시스템 명령 프롬프트 또는 파일 탐색기에서는 시작할 수 없습니다.

EDITBIN를 사용 하 여 생성 된 파일에서 사용 하기 위해 사용할 수 없는 합니다 [/GL](gl-whole-program-optimization.md) 컴파일러 옵션입니다. 다시 컴파일 및 연결 하 여 구현할 수 /GL을 사용 하 여 생성 된 이진 파일을 수정 해야 합니다.

- [EDITBIN 명령줄](editbin-command-line.md)

- [EDITBIN 옵션](editbin-options.md)

## <a name="see-also"></a>참고자료

[추가 MSVC 빌드 도구](c-cpp-build-tools.md)
