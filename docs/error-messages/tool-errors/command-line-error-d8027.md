---
title: 명령줄 오류 D8027
ms.date: 11/04/2016
f1_keywords:
- D8027
helpviewer_keywords:
- D8027
ms.assetid: f228220f-0c7f-49a6-a6e0-1f7bd4745aa6
ms.openlocfilehash: d3a7908ec9e7e37d83fd7b928cad2ef256313c40
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62214183"
---
# <a name="command-line-error-d8027"></a>명령줄 오류 D8027

'구성 요소' 실행할 수 없습니다.

컴파일러는 지정 된 컴파일러 구성 요소 또는 링커를 실행 하지 못했습니다.

### <a name="to-fix-by-checking-the-following-possible-causes"></a>다음과 같은 가능한 원인을 확인하여 수정하려면

1. 구성 요소를 로드 하는 메모리가 부족 합니다. NMAKE 컴파일러를 호출 하는 경우 외부 메이크파일 컴파일러를 실행 합니다.

1. 현재 운영 체제 구성 요소를 실행할 수 없습니다. 해야 경로 지점을 실행 파일에 현재 운영 체제에 적합 합니다.

1. 구성 요소가 손상 되었습니다. 설치 프로그램을 사용 하 여 배포 디스크에서 구성 요소를 다시 복사 합니다.

1. 옵션을 올바르게 지정 되었습니다. 예를 들어:

    ```
    cl /B1 file1.c
    ```