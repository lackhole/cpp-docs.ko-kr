---
title: 식 계산기 오류 CXX0033
ms.date: 11/04/2016
f1_keywords:
- CXX0033
helpviewer_keywords:
- CAN0033
- CXX0033
ms.assetid: 0bd62c5b-de89-481f-9b12-88fe84805afe
ms.openlocfilehash: 8563eb2fbc24c6ad8db639d2e227802412a16090
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62397057"
---
# <a name="expression-evaluator-error-cxx0033"></a>식 계산기 오류 CXX0033

OMF 형식 정보에 오류가 있습니다.

실행 파일에 디버깅에 대 한 유효한 개체 모듈 형식 (OMF) 없었습니다.

이 오류는 can0033과 동일 합니다.

### <a name="to-fix-by-checking-the-following-possible-causes"></a>다음과 같은 가능한 원인을 확인하여 수정하려면

1. 시각적 개체의이 버전을 사용 하 여 릴리스된 링커를 사용 하 여 실행 파일 만들어지지 않은 C++입니다. LINK.exe의 현재 버전을 사용 하 여 개체 코드를 다시 연결 합니다.

1. .Exe 파일이 손상 되었을 수 있습니다. 다시 컴파일하고 프로그램을 다시 연결 합니다.