---
title: 심각한 오류 C1128
ms.date: 11/04/2016
f1_keywords:
- C1128
helpviewer_keywords:
- C1128
ms.assetid: 6f9580fd-ecef-48be-9780-dcf666704279
ms.openlocfilehash: bb1d9af10084d6b3e75325450c7f13ea1683ee2e
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62229048"
---
# <a name="fatal-error-c1128"></a>심각한 오류 C1128

섹션 수가 개체 파일 형식 한도 초과 했습니다: /bigobj를 사용 하 여 컴파일

COFF 개체 파일 형식 제한 허용 되는 섹션의 수를 초과 하는.obj 파일.

이 섹션에서는 제한을 사용 하 여 발생할 수 있습니다 [/Gy](../../build/reference/gy-enable-function-level-linking.md) 및 디버그 빌드에 있습니다. **/Gy** 하면 함수는 자신의 COMDAT 섹션으로 이동 합니다. 디버그 빌드에서 각 COMDAT 함수에 대 한 디버그 정보 섹션.

C1128은 인라인 함수가 너무 많을 경우에 발생할 수 있습니다.

이 오류를 해결 하려면 소스 파일이 여러 소스 코드 파일 나눌, 하지 않고 컴파일할 **/Gy**를 사용 하 여 컴파일 또는 [/bigobj (섹션 수 늘리기에 있습니다. Obj 파일)](../../build/reference/bigobj-increase-number-of-sections-in-dot-obj-file.md)합니다.  사용 하 여 컴파일하지 않는 경우 **/Gy**, 최적화를 개별적으로 지정 해야 하므로 **/o2** 및 **/o1** 모두 의미 **/Gy**합니다.

가능한 경우 디버깅 정보 없이 컴파일하십시오.

내보낼 컴파일러 보다는 템플릿의 특정 인스턴스화를 별도 소스 코드 파일에도 해야 합니다.

코드를 이식할 때 C1128 가능성이 나타납니다 먼저 x64를 사용 하는 경우 컴파일러, 그리고 나중에 x86 컴파일러. x64 최소 4 개의 섹션에서는 컴파일된 각 함수를 사용 하 여 연결 해야 합니다. **/Gy** 인라인으로 템플릿 또는 클래스 인라인으로부터 인라인 된: 코드, pdata 및 디버그 정보와 xdata 합니다.  X86 pdata가 없습니다.