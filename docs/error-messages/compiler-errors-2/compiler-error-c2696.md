---
title: 컴파일러 오류 C2696
ms.date: 11/04/2016
f1_keywords:
- C2696
helpviewer_keywords:
- C2696
ms.assetid: 6c6eb7df-1230-4346-9a73-abf14c20785d
ms.openlocfilehash: 340a5d0596160b6c9c7bcfc78aed812f8c5f3fa3
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62367605"
---
# <a name="compiler-error-c2696"></a>컴파일러 오류 C2696

'Type' 형식의 관리 되는 임시 개체를 만들 수 없습니다.

에 대 한 참조 `const` 관리 되지 않는 프로그램에서 사용 하면 컴파일러가 스택의 임시 개체를 만들고 생성자를 호출 합니다. 그러나 관리 되는 클래스를 스택에 되지 만들 수 있습니다.

C2696 사용 되지 않는 컴파일러 옵션을 사용 하 여 전용인 **/clr: oldsyntax**합니다.
