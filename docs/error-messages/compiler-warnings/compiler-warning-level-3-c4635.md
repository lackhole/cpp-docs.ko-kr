---
title: 컴파일러 경고(수준 3) C4635
ms.date: 11/04/2016
f1_keywords:
- C4635
helpviewer_keywords:
- C4635
ms.assetid: b2ba90de-c093-4a76-8076-b65878467574
ms.openlocfilehash: fd3bf6c1b14c6dae8e2fa95a54e2d4fbc4f295c5
ms.sourcegitcommit: 573b36b52b0de7be5cae309d45b68ac7ecf9a6d8
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/10/2019
ms.locfileid: "74991843"
---
# <a name="compiler-warning-level-3-c4635"></a>컴파일러 경고(수준 3) C4635

XML 문서 주석 대상: 잘못된 형식의 XML: 이유

컴파일러가 XML 태그에서 일부 문제를 발견했습니다.  문제를 수정하고 다시 컴파일합니다.

다음 샘플에서는 C4635를 생성합니다.

```cpp
// C4635.cpp
// compile with: /doc /clr /W3 /c
/// <summary>
/// The contents of the folder have changed.
/// <summary/>   // C4635

// try the following line instead
// /// </summary>
public ref class Test {};
```

이 샘플은 **끝 태그 'member'가 시작 태그 'summary'와 일치하지 않습니다**를 출력합니다.

이 샘플의 문제는 \<요약 >의 끝 태그 형식이 잘못 되어 컴파일러에서이 태그를 \<summary > 끝 태그로 인식 하지 않는다는 것입니다.  \<멤버 > 태그는 모든/doc 컴파일의 컴파일러에 의해 .xdc 파일에 포함 됩니다.  따라서 여기에서 발생 하는 문제는 끝 태그 \</멤버 >가 컴파일러가 처리 한 이전 시작 태그 (\<요약 >와 일치 하지 않는다는 것입니다.
