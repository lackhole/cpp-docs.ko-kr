---
title: 컴파일러 경고 (수준 1) C4274
ms.date: 11/04/2016
f1_keywords:
- C4274
helpviewer_keywords:
- C4274
ms.assetid: 5a948680-7ed1-469f-978d-ae99d154e161
ms.openlocfilehash: f73fa8e09baab127e7755ebe3def69c2fb585744
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62207209"
---
# <a name="compiler-warning-level-1-c4274"></a>컴파일러 경고 (수준 1) C4274

\#ident 무시 됩니다. #pragma 주석 (exestr, 'string')에 대 한 설명서를 참조 하세요.

`#ident` 개체 또는 실행 파일의 사용자 지정 문자열을 삽입는 지시문은 사용 되지 않습니다. 결과적으로 컴파일러 지시문을 무시합니다.

> [!CAUTION]
>  사용 하 여 경고 C4274 조언 합니다 [#pragma 주석 (exestr, 'string')](../../preprocessor/comment-c-cpp.md) 지시문입니다. 그러나이 권장 사항은 않으며 컴파일러의 이후 릴리스에서 수정 될 예정입니다. 사용 하는 경우는 `#pragma` 지시문에 링커 도구 (LINK.exe)를 무시 주석 기록은 지시문에 의해 발생 하 고 경고가 발생 [LNK4229](../../error-messages/tool-errors/linker-tools-warning-lnk4229.md)합니다. 대신는 `#ident` 파일 버전 리소스 문자열을 사용 하 여 응용 프로그램에서 지시문을 권장 합니다.

## <a name="to-correct-this-error"></a>이 오류를 해결하려면

- 제거 된 `#ident "` *문자열* `"` 지시문입니다.

## <a name="see-also"></a>참고자료

[C 주석(C/C++)](../../preprocessor/comment-c-cpp.md)<br/>
[링커 도구 경고 LNK4229](../../error-messages/tool-errors/linker-tools-warning-lnk4229.md)<br/>
[리소스 파일 작업](../../windows/working-with-resource-files.md)