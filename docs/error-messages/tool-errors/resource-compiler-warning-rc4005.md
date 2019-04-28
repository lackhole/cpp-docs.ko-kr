---
title: 리소스 컴파일러 오류 RC4005
ms.date: 11/04/2016
f1_keywords:
- RC4005
helpviewer_keywords:
- RC4005
ms.assetid: 71f03b4a-c9a9-415d-920f-bf2e58507f93
ms.openlocfilehash: 571c4ac285e9477b017dbc21cf9ff733539759d2
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62346186"
---
# <a name="resource-compiler-warning-rc4005"></a>리소스 컴파일러 오류 RC4005

'identifier': 매크로 재정의

식별자가 두 번 정의 됩니다. 컴파일러는 두 번째 매크로 정의 사용 합니다.

명령줄에 사용 하 여 코드에서 매크로 정의 하 여이 경고를 발생할 수 있습니다는 `#define` 지시문입니다. 또한이 추가 포함 파일에서 가져온 매크로 발생할 수 있습니다.

경고를 제거 하려면 정의 중 하나를 제거 하거나 사용을 `#undef` 두 번째 정의 하기 전에 지시문입니다.