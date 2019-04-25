---
title: 심각한 오류 C1900
ms.date: 11/04/2016
f1_keywords:
- C1900
helpviewer_keywords:
- C1900
ms.assetid: 3aaa583b-4c1a-45de-aa34-527d806f2cb5
ms.openlocfilehash: c4622dd4552f7bfcc822a3aab4d5783146d68ac7
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62165725"
---
# <a name="fatal-error-c1900"></a>심각한 오류 C1900

> Il 불일치 '*tool1*'version'*number1*'및'*tool2*'version'*number2*'

컴파일러의 여러 패스에서 실행되는 도구가 일치하지 않습니다. *number1* 하 고 *number2* 파일에 날짜를 참조 합니다. 예를 들어 패스 1에서는 컴파일러 프런트 엔드가 실행되고(c1.dll) 패스 2에서는 컴파일러 백 엔드가 실행됩니다(c2.dll) 파일의 날짜는 일치해야 합니다.

이 문제를 해결하려면 Visual Studio에 모든 업데이트가 적용되었는지 확인합니다. 사용 하 여 문제가 지속 되 면 **프로그램 및 기능** 을 복구 하거나 Visual Studio를 다시 설치 하려면 Windows 제어판에서.