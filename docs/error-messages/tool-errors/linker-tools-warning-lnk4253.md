---
title: 링커 도구 경고 LNK4253
ms.date: 11/04/2016
f1_keywords:
- LNK4253
helpviewer_keywords:
- LNK4253
ms.assetid: ec7433a9-aa9c-495a-a9f2-075e7bc3e7bc
ms.openlocfilehash: c3f45880571e5c06f76d5f063ff993e2f6b2be9b
ms.sourcegitcommit: 573b36b52b0de7be5cae309d45b68ac7ecf9a6d8
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/10/2019
ms.locfileid: "74988093"
---
# <a name="linker-tools-warning-lnk4253"></a>링커 도구 경고 LNK4253

' section1 ' 섹션이 ' section2 '에 병합 되지 않았습니다. 이미 ' section3 '에 병합 되었습니다.

링커가 충돌 하는 여러 병합 요청을 검색 했습니다. 링커는 요청 중 하나를 무시 합니다.

이전 **/merge** 옵션 또는 지시문 (또는 링커에의 암시적 병합)으로 인해 **/merge** 옵션이 나 지시어가 발생 하 고 `from` 섹션이 다른 섹션에 이미 병합 되었습니다.

LNK4253를 해결 하려면 병합 요청 중 하나를 제거 합니다.

시각적 개체 C++를 사용 하 여 x86 컴퓨터와 Windows CE 대상 (ARM, MIPS, SH4 및 Thumb)을 대상으로 하는 경우입니다. CRT 섹션은 이제 읽기 전용입니다. 코드가 이전 동작에 의존 하는 경우 (. CRT 섹션은 읽기/쓰기입니다. 예기치 않은 동작이 표시 될 수 있습니다.

자세한 내용은 다음 항목을 참조하세요.

- [/MERGE(섹션 결합)](../../build/reference/merge-combine-sections.md)

- [C 주석(C/C++)](../../preprocessor/comment-c-cpp.md)

## <a name="example"></a>예제

다음 샘플에서 링커는 `.rdata` 섹션을 다른 섹션으로 두 번 병합 하도록 지시 합니다. 다음 샘플에서는 LNK4253를 생성 합니다.

```cpp
// LNK4253.cpp
// compile with: /W1 /link /merge:.rdata=text2
// LNK4253 expected
#pragma comment(linker, "/merge:.rdata=.text")
int main() {}
```
