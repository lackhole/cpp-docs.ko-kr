---
title: 링커 도구 경고 LNK4102
ms.date: 11/04/2016
f1_keywords:
- LNK4102
helpviewer_keywords:
- LNK4102
ms.assetid: bfd1b17e-05c7-4bc2-80d6-2888b1a425b2
ms.openlocfilehash: 0f9c8649988dd3056e98730ac4b02022a8c9dd51
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62327264"
---
# <a name="linker-tools-warning-lnk4102"></a>링커 도구 경고 LNK4102

내보내기 삭제 중인 소멸자 'name'; 이미지가 올바르게 실행 되지 않을 수 있습니다.

프로그램 삭제 소멸자 내보내기 하려고 했습니다. 결과 삭제 프로세스를 소유 하지 않은 메모리를 확보할 수 있도록 DLL 경계를 넘어 발생할 수 있습니다. 지정 된 기호는.def 파일에 없는 기호의 인수로 나타나지는 있는지 확인 합니다 **가져오기/** 또는 **/내보내기** 링커 명령줄에 옵션입니다.

C 런타임 라이브러리를 다시 작성 하는 경우에이 메시지를 무시할 수 있습니다.