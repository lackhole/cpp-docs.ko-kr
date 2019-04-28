---
title: 심각한 오류 C1092
ms.date: 11/04/2016
f1_keywords:
- C1092
helpviewer_keywords:
- C1092
ms.assetid: bcaa87f0-fbfc-4a33-844b-3b9f5d67f279
ms.openlocfilehash: 3268e5b124be40313bdc97b4c95d935ddd4f9160
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62208548"
---
# <a name="fatal-error-c1092"></a>심각한 오류 C1092

편집하며 계속하기는 데이터 형식에 대한 변경 내용은 지원하지 않습니다. 빌드해야 합니다.

변경 하거나 마지막으로 빌드가 성공한 이후 데이터 형식을 추가 합니다.

- 편집 하며 계속 하기를 클래스, 구조체 또는 열거형 정의 포함 하 여 기존 데이터 형식으로 변경 내용을 지원 하지 않습니다. 디버깅을 중지 하 고 응용 프로그램을 작성 해야 합니다.

- 편집 하며 계속 하기 새 데이터 형식의 경우 vc 같은 프로그램 데이터베이스 파일에 추가 지원 하지 않습니다*x*0.pdb (여기서 *x* 는 시각적 개체의 주 버전 C++ 사용에서) 읽기 전용입니다. 데이터 형식에 추가 하려면 컴파일러 쓰기 모드에서.pdb 파일을 열어야 합니다.

### <a name="to-remove-this-error-without-ending-the-current-debug-session"></a>현재 디버그 세션을 끝내 지 않고이 오류를 제거 하려면

1. 데이터 형식을 오류가 발생하기 이전 상태로 다시 변경합니다.

1. **디버그** 메뉴에서 **코드 변경 내용 적용**을 선택합니다.

### <a name="to-remove-this-error-without-changing-your-source-code"></a>소스 코드를 변경하지 않고 이 오류를 제거하려면

1. **디버그** 메뉴에서 **디버깅 중지**를 선택합니다.

1. **빌드** 메뉴에서 **빌드**를 선택합니다.

자세한 내용은 [지원되는 코드 변경](/visualstudio/debugger/supported-code-changes-cpp)을 참조하세요.