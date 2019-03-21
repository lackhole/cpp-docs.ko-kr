---
title: 심각한 오류 C1001
ms.date: 11/04/2016
f1_keywords:
- C1001
helpviewer_keywords:
- C1001
ms.assetid: 5736cdb3-22c8-4fad-aa85-d5e0d2b232f4
ms.openlocfilehash: a7130ed0568de387c99b8296dc4e10d92baec337
ms.sourcegitcommit: 8105b7003b89b73b4359644ff4281e1595352dda
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/14/2019
ms.locfileid: "57821367"
---
# <a name="fatal-error-c1001"></a>심각한 오류 C1001

> 내부 컴파일러 ERROR(compiler file *file*, line *number*)

컴파일러는 구문 분석 중에 특정 식 및 최적화 옵션 또는 문제의 조합으로 인해 종종 구문에 대해 올바른 코드를 생성할 수 없습니다. 나열 된 컴파일러 파일 utc 또는 C2 경로 세그먼트가 있으면 최적화 오류 때문일 수 있습니다. 파일 msc1.cpp 아니고 cxxfe 또는 c1xx 경로 세그먼트를 파서 오류 때문일 수 있습니다. Cl.exe 라는 파일을 사용 하는 경우 다른 정보가 없는 사용할 수 있습니다.

종종 하나 이상의 최적화 옵션을 제거 하 여 최적화 문제를 해결할 수 있습니다. 잘못 된 옵션을 확인, 오류 메시지를 지금까지 시간과 recompile 옵션 하나를 제거 합니다. 가장 일반적으로 담당 하는 옵션은 [/Og (전역 최적화)](../../build/reference/og-global-optimizations.md) 하 고 [/Oi (내장 함수 생성)](../../build/reference/oi-generate-intrinsic-functions.md)합니다. 원인이 되는 최적화 옵션을 결정 한 후 사용 하 여 오류가 발생 하는 함수 주위 비활성화할 수 있습니다 합니다 [최적화](../../preprocessor/optimize.md) pragma, 모듈의 나머지 부분에 대 한 옵션을 사용 하 여 계속 합니다. 최적화 옵션에 대 한 자세한 내용은 참조 하세요. [최적화에 대 한 유용한 정보](../../build/optimization-best-practices.md)합니다.

최적화 된 오류가 발생 한 경우 오류가 보고 된 줄 또는 여러 줄의 코드가 해당 줄 주위를 다시 작성 하십시오. 컴파일러가 전처리 후 표시 되는 방법은 코드를 보려면를 사용할 수 있습니다 합니다 [/P (파일로 전처리)](../../build/reference/p-preprocess-to-a-file.md) 옵션입니다.

오류 원인을 격리 하는 방법 및 Microsoft에 내부 컴파일러 오류를 보고 하는 방법에 대 한 자세한 내용은 참조 하세요. [Visual c + + 도구 집합을 사용 하 여 문제를 보고 하는 방법을](../../how-to-report-a-problem-with-the-visual-cpp-toolset.md)합니다.