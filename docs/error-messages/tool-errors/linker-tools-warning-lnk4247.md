---
title: 링커 도구 경고 LNK4247
ms.date: 11/04/2016
f1_keywords:
- LNK4247
helpviewer_keywords:
- LNK4247
ms.assetid: 085d7fdf-9eaf-4641-8473-6eaadd073c7b
ms.openlocfilehash: cd4108f8bd06ec7a0b2d2eb9fab13917174b797b
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62346962"
---
# <a name="linker-tools-warning-lnk4247"></a>링커 도구 경고 LNK4247

항목 지점 'decorated_function_name'에 이미 스레드 특성이 있습니다. ' attribute' 무시

진입점을 사용 하 여 지정 된 [/ENTRY (진입점 기호)](../../build/reference/entry-entry-point-symbol.md)에 스레드 특성이 있지만 [/CLRTHREADATTRIBUTE (CLR 스레드 특성 설정)](../../build/reference/clrthreadattribute-set-clr-thread-attribute.md) 다른 스레딩 모델로 지정 했습니다.

링커는 /CLRTHREADATTRIBUTE를 사용 하 여 지정 된 값을 무시 합니다.

이 경고를 해결 방법:

- 빌드에서 /CLRTHREADATTRIBUTE를 제거 합니다.

- 소스 코드 파일에서 특성을 제거 합니다.

- 빌드에서 원본 및 /CLRTHREADATTRIBUTE에서 두 특성을 제거 하 고 기본 CLR 스레딩 모델을 허용 합니다.

- 원본에 있는 특성을 사용 해도 되도록 /CLRTHREADATTRIBUTE, 전달 되는 값을 변경 합니다.

- /CLRTHREADATTRIBUTE 전달 되는 값을 사용 해도 되도록 원본의 특성을 변경 합니다.

다음 샘플에서는 LNK4247

```
// LNK4247.cpp
// compile with: /clr /c
// post-build command: link /CLRTHREADATTRIBUTE:STA LNK4247.obj /entry:functionTitle /SUBSYSTEM:Console
[System::MTAThreadAttribute]
void functionTitle (){}
```