---
title: 링커 도구 경고 LNK4254
ms.date: 11/04/2016
f1_keywords:
- LNK4254
helpviewer_keywords:
- LNK4254
ms.assetid: 6f41dfb3-ca21-40d3-bac7-b637e578efa4
ms.openlocfilehash: 8431bd2d89fd5df5cf076ad006ab04006f552c4c
ms.sourcegitcommit: 573b36b52b0de7be5cae309d45b68ac7ecf9a6d8
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/10/2019
ms.locfileid: "74988068"
---
# <a name="linker-tools-warning-lnk4254"></a>링커 도구 경고 LNK4254

' section1 ' (offset) 섹션이 다른 특성을 사용 하 여 ' section2 ' (오프셋)에 병합 되었습니다.

한 섹션의 내용이 다른 섹션에 병합 되었지만 두 섹션의 특성은 서로 다릅니다. 프로그램에서 예기치 않은 결과를 제공할 수 있습니다. 예를 들어 읽기 전용 데이터는 이제 쓰기 가능한 섹션에 있을 수 있습니다.

LNK4254를 해결 하려면 merge 요청을 수정 하거나 제거 합니다.

시각적 개체 C++를 사용 하 여 x86 컴퓨터와 Windows CE 대상 (ARM, MIPS, SH4 및 Thumb)을 대상으로 하는 경우입니다. CRT 섹션은 읽기 전용입니다. 코드가 이전 동작에 종속 되는 경우 (. CRT 섹션은 읽기/쓰기입니다. 예기치 않은 동작이 표시 될 수 있습니다.

자세한 내용은 다음 항목을 참조하세요.

- [/MERGE(섹션 결합)](../../build/reference/merge-combine-sections.md)

- [C 주석(C/C++)](../../preprocessor/comment-c-cpp.md)

## <a name="example"></a>예제

다음 샘플에서는 LNK4254를 생성 합니다.

```cpp
// LNK4254.cpp
// compile with: /W1 /link /WX
// LNK4254 expected
#pragma comment(linker, "/merge:.data=.text")
int main() {}
```
