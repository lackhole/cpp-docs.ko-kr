---
title: 리소스 컴파일러 경고 RW4004
ms.date: 11/04/2016
f1_keywords:
- RW4004
helpviewer_keywords:
- RW4004
ms.assetid: 596b6a89-9ce7-4ba7-bdcb-e8054c7efafa
ms.openlocfilehash: bafd1084a665fc656fe184064a48e5fffc61c957
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62346082"
---
# <a name="resource-compiler-warning-rw4004"></a>리소스 컴파일러 경고 RW4004

ASCII 문자가 가상 키 코드와 일치하지 않습니다.

VIRTKEY 형식 액셀러레이터의 가상 키 코드에 문자열 리터럴을 사용했습니다.

이 경고가 표시되어도 계속 진행할 수 있지만 생성된 액셀러레이터 키가 지정한 문자열과 일치하지 않을 수 있습니다. (VIRTKEY가 ASCII 액셀러레이터와 다른 키 코드를 사용합니다.)

문자열 리터럴이 구문상 유효한 동안 확인할 수 있습니다만 사용 하 여 원하는 액셀러레이터 키를 가져와야 합니다 **VK_\* #define** WINDOWS.h의 값입니다.