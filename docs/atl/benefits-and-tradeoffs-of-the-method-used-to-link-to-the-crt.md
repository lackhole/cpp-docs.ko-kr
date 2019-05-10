---
title: CRT에 링크 하는 데 사용 하는 방법의 장단점
ms.date: 05/06/2019
helpviewer_keywords:
- _ATL_MIN_CRT macro
ms.assetid: 49b485f7-9487-49e4-b12a-0f710b620e2b
ms.openlocfilehash: b2e504de91cea9fef6e9acb0fc851bc2cc271e97
ms.sourcegitcommit: da32511dd5baebe27451c0458a95f345144bd439
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/07/2019
ms.locfileid: "65221270"
---
# <a name="benefits-and-tradeoffs-of-the-method-used-to-link-to-the-crt"></a>CRT에 링크 하는 데 사용 하는 방법의 장단점

프로젝트는 동적 또는 정적으로 CRT에 연결할 수 있습니다. 아래 테이블에는 장점과 단점을 사용할 방법을 선택과 관련 된 간략하게 설명 합니다.

|메서드|이점|균형을 유지|
|------------|-------------|--------------|
|정적으로 CRT에 연결<br /><br /> (**런타임 라이브러리** 로 설정 **단일 스레드**)|CRT DLL 이미지가 실행 되는 시스템에 필요 하지 않습니다.|약 25 개 중 K 시작 코드는 해당 크기를 늘리지 이미지에 추가 됩니다.|
|동적으로 CRT에 연결<br /><br /> (**런타임 라이브러리** 로 설정 **멀티스레드**)|이미지는 훨씬 더 작기 때문 이므로 CRT 시작 코드가 필요가 없습니다.|CRT DLL 이미지를 실행 하는 시스템에 있어야 합니다.|

항목 [ATL 프로젝트에서 CRT에 연결할](../atl/linking-to-the-crt-in-your-atl-project.md) CRT에 연결 하는 방식을 선택 하는 방법에 설명 합니다.

## <a name="see-also"></a>참고자료

[ATL 및 C 런타임 코드를 사용한 프로그래밍](../atl/programming-with-atl-and-c-run-time-code.md)<br/>
[DLL 및 Visual C++ 런타임 라이브러리 동작](../build/run-time-library-behavior.md)<br/>
[CRT 라이브러리 기능](../c-runtime-library/crt-library-features.md)
