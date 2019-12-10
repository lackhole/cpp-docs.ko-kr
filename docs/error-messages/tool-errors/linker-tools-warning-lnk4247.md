---
title: 링커 도구 경고 LNK4247
ms.date: 11/04/2016
f1_keywords:
- LNK4247
helpviewer_keywords:
- LNK4247
ms.assetid: 085d7fdf-9eaf-4641-8473-6eaadd073c7b
ms.openlocfilehash: 344c219fa1f3daa1e5f9c31431e608f5e7036400
ms.sourcegitcommit: 573b36b52b0de7be5cae309d45b68ac7ecf9a6d8
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/10/2019
ms.locfileid: "74991160"
---
# <a name="linker-tools-warning-lnk4247"></a>링커 도구 경고 LNK4247

' decorated_function_name ' 진입점에는 이미 스레드 특성이 있습니다. ' attribute '가 무시 됩니다.

[/Entry (진입점 기호)](../../build/reference/entry-entry-point-symbol.md)로 지정 된 진입점에 스레딩 특성이 있지만 다른 스레딩 모델을 사용 하 여 [/CLRTHREADATTRIBUTE (CLR 스레드 특성 설정)](../../build/reference/clrthreadattribute-set-clr-thread-attribute.md) 도 지정 했습니다.

링커가/CLRTHREADATTRIBUTE.로 지정 된 값을 무시 했습니다.

이 경고를 해결 하려면:

- 빌드에서/CLRTHREADATTRIBUTE를 제거 합니다.

- 소스 코드 파일에서 특성을 제거 합니다.

- 빌드에서 소스 및/CLRTHREADATTRIBUTE의 특성을 모두 제거 하 고 기본 CLR 스레딩 모델을 적용 합니다.

- /CLRTHREADATTRIBUTE에 전달 된 값을 변경 하 여 원본에서 특성에 동의 합니다.

- /CLRTHREADATTRIBUTE.에 전달 된 값에 동의 하도록 원본에서 특성을 변경 합니다.

다음 샘플에서는 LNK4247를 생성 합니다.

```cpp
// LNK4247.cpp
// compile with: /clr /c
// post-build command: link /CLRTHREADATTRIBUTE:STA LNK4247.obj /entry:functionTitle /SUBSYSTEM:Console
[System::MTAThreadAttribute]
void functionTitle (){}
```
