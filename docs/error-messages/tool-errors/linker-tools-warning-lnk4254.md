---
title: 링커 도구 경고 LNK4254
ms.date: 11/04/2016
f1_keywords:
- LNK4254
helpviewer_keywords:
- LNK4254
ms.assetid: 6f41dfb3-ca21-40d3-bac7-b637e578efa4
ms.openlocfilehash: 2c68e49d58b0fd6b28607eb0ba78c092441f6f4b
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62352491"
---
# <a name="linker-tools-warning-lnk4254"></a>링커 도구 경고 LNK4254

'사항 구역 1' 섹션 (오프셋) 'section2'에 병합 (오프셋) 서로 다른 특성을 사용 하 여

하나의 섹션의 내용을 다른 테이블로 병합 된 하지만 두 섹션의 특성 다릅니다. 프로그램은 예기치 않은 결과 제공할 수 있습니다. 예를 들어, 데이터를 읽으려면 수만 이제 될 쓰기 가능한 섹션.

LNK4254를 해결 하려면 수정 하거나 병합 요청을 제거 합니다.

X86을 대상으로 할 때 컴퓨터 및 Windows CE 대상 (ARM, MIPS, SH4, 및 엄지 단추) 시각적 개체를 사용 하 여 C++는 합니다. CRT 섹션은 읽기 전용입니다. 코드가 이전 동작에 의존 하는 경우 (합니다. CRT 섹션은 읽기/쓰기), 예기치 않은 동작을 볼 수 있습니다.

자세한 내용은 다음 항목을 참조하세요.

- [/MERGE(섹션 결합)](../../build/reference/merge-combine-sections.md)

- [C 주석(C/C++)](../../preprocessor/comment-c-cpp.md)

## <a name="example"></a>예제

다음 샘플 LNK4254를 생성합니다.

```
// LNK4254.cpp
// compile with: /W1 /link /WX
// LNK4254 expected
#pragma comment(linker, "/merge:.data=.text")
int main() {}
```