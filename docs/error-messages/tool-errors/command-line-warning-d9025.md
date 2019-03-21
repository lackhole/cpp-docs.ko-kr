---
title: 명령줄 경고 D9025
ms.date: 11/04/2016
f1_keywords:
- D9025
helpviewer_keywords:
- D9025
ms.assetid: 6edff72c-1508-46c2-99f4-0e4b3c5e60c9
ms.openlocfilehash: e7090dda72868ad7ee4d5f8e4f1ba6a0ad121c98
ms.sourcegitcommit: 8105b7003b89b73b4359644ff4281e1595352dda
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/14/2019
ms.locfileid: "57822468"
---
# <a name="command-line-warning-d9025"></a>명령줄 경고 D9025

'option2'를 사용 하 여 ' option1' 재정의

합니다 *option1* 옵션에 지정 되었지만 다음에 의해 재정의 되었습니다 *option2*합니다. 합니다 *option2* 옵션 사용.

모순 또는 호환 되지 않는 지시문을 지정 하는 두 가지 옵션을 지정 하거나 명령줄에서 오른쪽에 있는 옵션의 사용 권한에 포함 된 지시문이 사용 됩니다.

개발 환경에서 컴파일할 때 경고가이 확실 하지 않은 충돌 하는 옵션에서 생성 되는 경우 다음 사항을 고려 합니다.

- 코드 또는 프로젝트의 프로젝트 설정에서 옵션을 지정할 수 있습니다. 컴파일러의 살펴보면 [명령줄 속성 페이지](../../build/reference/command-line-property-pages.md) 충돌 하는 옵션을 표시 하는 경우를 **옵션을 모두** 옵션이 고, 그렇지 프로젝트의 속성 페이지에서 옵션 설정 되어 다음 필드 소스 코드에서 설정 됩니다.

   프로젝트의 속성 페이지에서 옵션을 설정 (솔루션 탐색기에서 선택한 프로젝트 노드)와 컴파일러의 전처리기 속성 페이지에서 확인 합니다.  여기서 설정, 솔루션 탐색기에서 각 소스 코드 파일에 대 한 전처리기 속성 페이지 설정 되었는지 확인 하는 옵션을 표시 되지 않으면 있습니다 추가 되지 않습니다.

   옵션은 코드에서 설정 된 경우 코드에서 또는 windows 헤더에서 설정할 수 있습니다.  전처리 된 파일을 만들어 볼 수 있습니다 ([/P](../../build/reference/p-preprocess-to-a-file.md)) 기호에 대 한 검색 합니다.