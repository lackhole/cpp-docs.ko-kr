---
title: 프로필 기반 최적화 오류 PG0165
description: PGO (프로필 기반 최적화) 데이터를 읽는 PG0165 오류에 대해 설명 합니다.
ms.date: 10/30/2019
f1_keywords:
- PG0165
helpviewer_keywords:
- PG0165
ms.assetid: e98122e7-ddee-4a2c-96b2-d232e4c65f3e
ms.openlocfilehash: c5e5c5d37f8c70a6c2a3d9f7a43c13bb46d0e25a
ms.sourcegitcommit: 0cfc43f90a6cc8b97b24c42efcf5fb9c18762a42
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/05/2019
ms.locfileid: "73626798"
---
# <a name="profile-guided-optimization-error-pg0165"></a>프로필 기반 최적화 오류 PG0165

프로필 기반 최적화 데이터를 읽는 동안 오류가 발생 했습니다. 이 오류는 다음과 같은 여러 형식으로 나타날 수 있습니다.

> '*Filename .pgd*': ' pgd 버전은 지원 되지 않습니다 (버전 불일치) '를 읽습니다.

PGD 파일은 특정 컴파일러 도구 집합에만 적용 됩니다. 이 오류는 *filename*을 만드는 데 사용 된 것과 다른 컴파일러를 사용 하는 경우에 생성 됩니다. 이 오류는이 컴파일러 도구 집합이 현재 프로그램을 최적화 하기 위해 *filename* 의 데이터를 사용할 수 없음을 나타냅니다. 이 문제를 해결 하려면 현재 컴파일러 도구 집합을 사용 하 여 *Filename*.pgd를 다시 생성 하십시오.

> '*Filename .pgd*': ' pgd 파일이 읽기 전용입니다. '를 읽는 중입니다.

이 오류는 PGD 파일이 파일 시스템에서 읽기 전용으로 표시 된 경우 표시 됩니다. 이 문제를 해결 하려면 파일 특성을 읽기/쓰기로 변경 합니다.
