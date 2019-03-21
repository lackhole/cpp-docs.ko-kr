---
title: 컴파일러 오류 C3859
ms.date: 03/08/2019
f1_keywords:
- C3859
helpviewer_keywords:
- C3859
ms.assetid: 40e93b25-4393-4467-90de-035434a665c7
ms.openlocfilehash: 9b20224207ba797c6ee93c06404e4d90c3d02525
ms.sourcegitcommit: dedd4c3cb28adec3793329018b9163ffddf890a4
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/11/2019
ms.locfileid: "57738644"
---
# <a name="compiler-error-c3859"></a>컴파일러 오류 C3859

> 가상 메모리 범위를 초과 했습니다; PCH에 대 한 명령줄 옵션을 사용 하 여 다시 컴파일하십시오 '-Zm*값*' 이상

미리 컴파일된 헤더에 할당 된 가상 메모리는 컴파일러에서 넣으려는 시도 하는 데이터 양에 비해 너무 작습니다. Visual Studio 2015부터 합니다 **/Zm** 권장 사항을 유효만 사용 하는 경우는 `#pragma hdrstop` 지시문입니다. 다른 경우에 Windows 가상 메모리 부족 문제를 나타내는 의사 오류를 것입니다.

미리 컴파일된 헤더가 사용 하는 경우는 `#pragma hdrstop` 지시문을 사용 합니다 **/Zm** 미리 컴파일된 헤더 파일에 대 한 더 큰 값을 지정 하는 컴파일러 플래그입니다. 그렇지 않으면 빌드에 대 한 병렬 컴파일 프로세스의 수를 줄이는 것이 좋습니다. 자세한 내용은 [/Zm (지정 미리 컴파일된 헤더 메모리 할당 제한)](../../build/reference/zm-specify-precompiled-header-memory-allocation-limit.md)합니다.
