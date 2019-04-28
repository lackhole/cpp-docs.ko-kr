---
title: 심각한 오류 C1091
ms.date: 11/04/2016
f1_keywords:
- C1091
helpviewer_keywords:
- C1091
ms.assetid: 812d4201-9154-48b0-b9af-5959c082ca33
ms.openlocfilehash: 9758d4b779f4727012041da60632bcea8ce18d42
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62208538"
---
# <a name="fatal-error-c1091"></a>심각한 오류 C1091

컴파일러 한계: 문자열 길이가 'length'바이트를 초과합니다.

문자열 상수가 문자열 길이의 현재 한계를 초과했습니다.

정적 문자열을 둘 이상의 변수로 분할한 다음 선언의 일부로 또는 런타임 중에 [strcpy_s](../../c-runtime-library/reference/strcpy-s-wcscpy-s-mbscpy-s.md) 를 사용하여 결과를 결합하는 것이 좋습니다.