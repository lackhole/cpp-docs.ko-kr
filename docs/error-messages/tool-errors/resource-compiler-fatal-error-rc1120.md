---
title: 리소스 컴파일러 심각한 오류 RC1120
ms.date: 11/04/2016
f1_keywords:
- RC1120
helpviewer_keywords:
- RC1120
ms.assetid: 4e462931-e42e-42e3-8bfc-847677194286
ms.openlocfilehash: eff46ddee118c3355e548c73220b407db0561e36
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62374258"
---
# <a name="resource-compiler-fatal-error-rc1120"></a>리소스 컴파일러 심각한 오류 RC1120

메모리에서 필요한 바이트 수입니다.

리소스 컴파일러는 힙에 저장 하는 항목에 대 한 저장소 부족 합니다. 일반적으로 너무 많은 기호가의 결과입니다.

### <a name="to-fix-by-using-the-following-possible-solutions"></a>아래의 해결 방법 따라 수정합니다.

1. Windows 스왑 파일 공간을 늘립니다. 파일 스왑 공간을 늘리는 방법에 대 한 자세한 내용은 Windows 도움말에서 가상 메모리를 참조 하세요.

1. 불필요 한 제거 포함 파일, 특히 `#define`지시문과 함수 프로토타입을 합니다.

1. 현재 파일을 두 개 이상의 파일로 분할 하 고 개별적으로 컴파일할 수 있습니다.

1. 다른 프로그램 또는 많은 양의 메모리가 소비 되는 시스템에서 실행 되는 드라이버를 제거 합니다.