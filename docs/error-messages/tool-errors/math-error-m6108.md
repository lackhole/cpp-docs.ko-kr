---
title: 수학 오류 M6108
ms.date: 11/04/2016
f1_keywords:
- M6108
helpviewer_keywords:
- M6108
ms.assetid: 054893b4-49bc-45d9-882f-7cb50ba387c0
ms.openlocfilehash: d60e9b6284c79828fda1f7af542fcf197f189ad0
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62393274"
---
# <a name="math-error-m6108"></a>수학 오류 M6108

제곱근

제곱근 연산의 피연산자가 음수입니다.

프로그램은 136 종료 코드로 종료 됩니다.

> [!NOTE]
>  합니다 `sqrt` FORTRAN 내장 함수 및 C 런타임 라이브러리 함수 **SQRT** 이 오류를 생성 하지 않습니다. C `sqrt` 함수는 작업을 수행 하기 전에 인수를 확인 하 고 피연산자가 음수 오류 값을 반환 합니다. 포트란 **SQRT** 함수에는 도메인 오류를 생성 합니다 [M6201](../../error-messages/tool-errors/math-error-m6201.md) 이 오류는 대신 합니다.