---
title: 심각한 오류 C1045
ms.date: 11/04/2016
f1_keywords:
- C1045
helpviewer_keywords:
- C1045
ms.assetid: 766c2f89-4ecd-4281-adaa-14b270cc0829
ms.openlocfilehash: 4503580e33bf89fc913b1941b4f9916f59e397d0
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62243816"
---
# <a name="fatal-error-c1045"></a>심각한 오류 C1045

컴파일러 한계 : 링크 사양이 너무 많이 중첩되었습니다.

중첩된 외부 참조가 컴파일러 한계를 초과했습니다. 중첩된 외부 참조는 `extern` "C++"와 같은 외부 링크 형식에서 사용할 수 있습니다. 오류를 해결하려면 중첩된 외부 참조 수를 줄입니다.