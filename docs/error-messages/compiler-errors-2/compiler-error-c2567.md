---
title: 컴파일러 오류 C2567
ms.date: 11/04/2016
f1_keywords:
- C2567
helpviewer_keywords:
- C2567
ms.assetid: 9c140ac9-7059-47e6-9ba1-e7939c8c0dc3
ms.openlocfilehash: eec529f43e23810843651888ef5722c5d0a0b2c9
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62366357"
---
# <a name="compiler-error-c2567"></a>컴파일러 오류 C2567

'file'에서 메타 데이터를 열 수 없습니다 파일 수 삭제 되었거나 이동

원본에서 참조 되는 메타 데이터 파일 (사용 하 여 `#using`) 찾을 수 없습니다 동일한 디렉터리에 컴파일러 백 엔드 프로세스에 의해 컴파일러 프런트 엔드 프로세스로 처럼 합니다. 참조 [#using 지시문](../../preprocessor/hash-using-directive-cpp.md) 자세한 내용은 합니다.

C2567로 컴파일하는 경우 발생할 수 있습니다 **/c** 하나에서 컴퓨터를 다른 컴퓨터에서 링크 타임 코드 생성을 시도 합니다. 자세한 내용은 [/LTCG (링크 타임 코드 생성)](../../build/reference/ltcg-link-time-code-generation.md)).

또한 컴퓨터에 메모리가 더 이상 없습니다 남은 나타낼 수 있습니다.

이 오류를 해결 하려면 빌드 프로세스의 모든 단계에 대 한 메타 데이터 파일을 동일한 디렉터리 위치에는 확인 합니다.