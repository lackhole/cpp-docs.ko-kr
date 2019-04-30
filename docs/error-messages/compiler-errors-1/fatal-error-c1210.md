---
title: 심각한 오류 C1210
ms.date: 11/04/2016
f1_keywords:
- C1210
helpviewer_keywords:
- C1210
ms.assetid: e2208309-c284-425c-a7e8-48e96e66f35b
ms.openlocfilehash: a90ca3e3b55642f1a6cd847997b83e4b7db46818
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62385851"
---
# <a name="fatal-error-c1210"></a>심각한 오류 C1210

> 설치된 런타임 버전에서는 /clr:pure 및 /clr:safe가 지원되지 않습니다.

**/clr: pure** 및 **/clr: safe** Visual Studio 2015에서 사용 되지 않고 Visual Studio 2017에서 지원 되지 않는 컴파일러 옵션입니다.

현재 릴리스에 대한 컴파일러가 있지만 이전 릴리스의 공용 언어 런타임을 사용하는 경우 C1210이 발생합니다.

컴파일러의 일부 기능은 이전 버전의 런타임에서 작동하지 않을 수 있습니다.

C1210을 해결하려면 컴파일러와 함께 사용하도록 디자인된 공용 언어 런타임 버전을 설치합니다.