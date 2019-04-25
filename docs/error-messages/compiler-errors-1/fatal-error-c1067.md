---
title: 심각한 오류 C1067
ms.date: 11/04/2016
f1_keywords:
- C1067
helpviewer_keywords:
- C1067
ms.assetid: e2c94be6-4573-4571-aac9-73d657fe9f96
ms.openlocfilehash: f8fe301e25d9ecb5cc67397f9537e0bbd86c0627
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62165855"
---
# <a name="fatal-error-c1067"></a>심각한 오류 C1067

컴파일러 한계: 형식 레코드 크기의 64k 제한이 초과 되었습니다.

기호 이름이 데코 레이트 된 247 자를 초과 하는 경우이 오류가 발생할 수 있습니다.  를 해결 하려면 기호 이름을 단축 합니다.

컴파일러가 디버그 정보를 생성할 때 소스 코드에서 발생 하는 형식을 정의 하는 형식 레코드를 내보냅니다.  예를 들어 형식 레코드에는 간단한 구조 및 함수의 인수 목록이 포함 됩니다.  이러한 형식 레코드의 일부 목록 크기를 수 있습니다.

형식 레코드 크기의 64k 제한이 있습니다.  64k 제한을 초과 하는 경우이 오류가 발생 합니다.

긴 이름 가진 많은 기호가 있거나 클래스, 구조체 또는 공용 구조체 멤버가 너무 많이 C1067 발생할 수 있습니다.