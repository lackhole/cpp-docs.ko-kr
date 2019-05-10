---
title: 컴파일러 경고 (수준 1) C4049
ms.date: 11/04/2016
f1_keywords:
- C4049
helpviewer_keywords:
- C4049
ms.assetid: d11c1870-bcfc-4d71-8945-b87ec6ec3514
ms.openlocfilehash: a4958bb446b5f7e80ef2eef92b52a0f86cf6a134
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62388765"
---
# <a name="compiler-warning-level-1-c4049"></a>컴파일러 경고 (수준 1) C4049

컴파일러 한계: 줄 번호 내보내기를 종료

파일에 두 개 16777215 (2<sup>24</sup>-1) 소스 줄. 컴파일러는 16777215에서 번호 매기기를 중지 합니다.

다음에 나오는 코드에 대 한 16777215 줄:

- 이미지에는 줄 번호에 대 한 디버깅 정보가 포함 됩니다.

- 잘못 된 줄 번호를 사용 하 여 일부 진단 보고 될 수 있습니다.

- .asm 목록 (/ FAs) 잘못 된 줄 번호가 있을 수 있습니다.